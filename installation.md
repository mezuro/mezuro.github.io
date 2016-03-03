---
layout: page
title: Installation
permalink: /installation/
---
Pre-built packages for the Mezuro platform components are available for Linux, either Debian Jessie or CentOS/RHEL 7.

They are hosted on [Bintray](https://bintray.com/mezurometrics), which should have the latest stable versions available.

### Installation steps for Debian Jessie

```bash
# Add the Bintray repository to your apt sources list
echo 'deb https://dl.bintray.com/mezurometrics/deb jessie main' | sudo tee /etc/apt/sources.list.d/mezurometrics.list

# Update the repository information
sudo apt-get update

# Install each package independently to make sure each database is set up in order
sudo apt-get install kalibro-configurations
sudo apt-get install kalibro-processor
sudo apt-get install prezento

# Start all the services
sudo systemctl start kalibro-configurations.target
sudo systemctl start kalibro-processor.target
sudo systemctl start prezento.target

# Optionally enable them to start at boot
sudo systemctl enable kalibro-configurations.target kalibro-processor.target prezento.target

# Afterwards, Prezento should be accessible at http://localhost:8081
```

### Installation steps for CentOS 7

```bash
# Add the Bintray repository to your yum repository list
sudo wget https://bintray.com/mezurometrics/rpm/rpm -O /etc/yum.repos.d/mezurometrics.repo

# Install the PostgreSQL database server and make sure it is initialized, so the
# Mezuro databases can be created during installation
sudo yum install -y postgresql-server
sudo postgresql-setup initdb

# Install each package independently to make sure each database is set up in order
sudo yum install -y kalibro-configurations
sudo yum install -y kalibro-processor
sudo yum install -y prezento

# Start all the services
sudo systemctl start kalibro-configurations.target
sudo systemctl start kalibro-processor.target
sudo systemctl start prezento.target

# Optionally enable them to start at boot
sudo systemctl enable kalibro-configurations.target kalibro-processor.target prezento.target

# Afterwards, Prezento should be accessible at http://localhost:8081
```
