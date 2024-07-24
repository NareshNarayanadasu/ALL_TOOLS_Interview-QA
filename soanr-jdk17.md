#!/bin/bash

# Update package lists
sudo apt update

# Install OpenJDK 17 with universe repository enabled
sudo apt install -y openjdk-17-jdk universe

# Install and configure PostgreSQL
# Add PostgreSQL repository
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" /etc/apt/sources.list.d/pgdg.list'

# Add PostgreSQL signing key
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4C1D70BD9C31 | sudo apt-key add -

# Update package lists again
sudo apt update

# Install PostgreSQL
sudo apt install -y postgresql postgresql-contrib

# Enable the database server to start automatically on reboot
sudo systemctl enable postgresql

# Start the database server
sudo systemctl start postgresql

# Change the default PostgreSQL password (highly recommended)
sudo -u postgres psql -c "ALTER USER postgres PASSWORD 'your_strong_password';"

# Create a dedicated user for SonarQube (replace 'sonar_user' with your desired username)
sudo su - postgres -c "createuser -d sonar_user"

# Set a password for the SonarQube user (replace 'your_sonar_password' with a strong password)
sudo su - postgres -c "psql -c \"ALTER USER sonar_user with PASSWORD 'your_sonar_password';\""

# Download the latest SonarQube distribution (adjust the URL for your desired version)
wget https://binaries.sonarsource.com/sonarqube/latest/sonarqube-linux-x86-64.zip

# Unzip the downloaded file
unzip sonarqube-linux-x86-64.zip

# Move the unzipped directory to a suitable location (replace '/opt/sonarqube' with your preferred location)
sudo mv sonarqube-9.3.0 /opt/sonarqube

# Create a SonarQube group
sudo groupadd sonar

# Create a SonarQube user and set its home directory
sudo useradd -M -g sonar sonar

# Grant ownership of the SonarQube directory to the SonarQube user
sudo chown -R sonar:sonar /opt/sonarqube

# Configure SonarQube (edit sonar.properties as needed)
sudo nano /opt/sonarqube/conf/sonar.properties

# (Optional) Set the `sonar.jdbc.url` property to point to your PostgreSQL database
# (e.g., sonar.jdbc.url=jdbc:postgresql://localhost:5432/your_sonar_database)

# Create a systemd service file for SonarQube
sudo nano /etc/systemd/system/sonarqube.service

# Paste the following content into the service file, replacing paths if necessary:

[Unit]
Description=SonarQube server
After=network.target postgresql.service

[Service]
User=sonar
Group=sonar
WorkingDirectory=/opt/sonarqube
Environment="JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64"  # Adjust for your Java installation
ExecStart=/opt/sonarqube/bin/wrapper.sh start

[Install]
WantedBy=multi-user.target

# Reload systemd and enable the SonarQube service
sudo systemctl daemon-reload
sudo systemctl enable sonarcube.service

# Start the SonarQube service
sudo systemctl start sonarcube.service

# Check the service status
sudo systemctl status sonarcube.service
