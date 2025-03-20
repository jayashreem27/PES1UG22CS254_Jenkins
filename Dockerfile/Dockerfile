FROM jenkins/jenkins:lts

USER root

# Update package lists first
RUN apt-get update

# Install make
RUN apt-get install -y --no-install-recommends make

# Fix broken dependencies, then install g++
RUN apt-get install -y --fix-missing --no-install-recommends g++ || (dpkg --configure -a && apt-get install -y --fix-missing --no-install-recommends g++)

# Clean up
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

USER jenkins
