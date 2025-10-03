# Complete A-Z Setup Guide for Dynamic KPI Dashboard on Windows

This guide is designed for beginner developers to set up the Dynamic KPI Dashboard project on a Windows machine. Follow these steps carefully to ensure a successful installation.

## Table of Contents
1. [System Requirements](#system-requirements)
2. [Installing Node.js and npm](#installing-nodejs-and-npm)
3. [Installing Git](#installing-git)
4. [Installing Docker Desktop](#installing-docker-desktop)
5. [Installing Python](#installing-python)
6. [Cloning the Repository](#cloning-the-repository)
7. [Setting Up Node.js Version Management](#setting-up-nodejs-version-management)
8. [Installing Backend Dependencies](#installing-backend-dependencies)
9. [Installing Frontend Dependencies](#installing-frontend-dependencies)
10. [Building the Frontend](#building-the-frontend)
11. [Setting Up MongoDB with Docker](#setting-up-mongodb-with-docker)
12. [Configuring Environment Variables](#configuring-environment-variables)
13. [Starting the Application](#starting-the-application)
14. [Troubleshooting Common Issues](#troubleshooting-common-issues)

## System Requirements

- Windows 10 or Windows 11
- At least 4GB RAM (8GB recommended)
- At least 2GB free disk space
- Administrator privileges for installation

## Installing Node.js and npm

1. Visit the official Node.js website: https://nodejs.org/
2. Download the **LTS (Long Term Support)** version, which is recommended for most users
3. Run the installer as an administrator
4. Follow the installation wizard:
   - Accept the license agreement
   - Choose the installation directory (default is fine)
   - Make sure to check "Automatically install the necessary tools..." if available
   - Click "Next" until you reach the installation screen
5. Click "Install" and wait for the installation to complete
6. Click "Finish" when done
7. Verify the installation:
   - Open Command Prompt (Press Windows key + R, type `cmd`, press Enter)
   - Run the following commands:
     ```
     node --version
     npm --version
     ```
   - You should see version numbers for both

## Installing Git

1. Visit the official Git website: https://git-scm.com/download/win
2. Download the Windows version
3. Run the installer as an administrator
4. Follow the installation wizard:
   - Accept the license agreement
   - Choose the installation directory (default is fine)
   - Select components (default selections are recommended)
   - Choose the default editor (Vim is fine, or you can choose another)
   - Adjust your PATH environment (choose "Git from the command line and also from 3rd-party software")
   - Choose the SSH executable (Use bundled OpenSSH is recommended)
   - Configure line ending conversions (Choose "Checkout Windows-style, commit Unix-style line endings")
   - Configure the terminal emulator (Use Windows' default console window is recommended)
   - Configure extra options (default selections are fine)
5. Click "Install" and wait for the installation to complete
6. Click "Finish" when done
7. Verify the installation:
   - Open a new Command Prompt window
   - Run the command:
     ```
     git --version
     ```
   - You should see the Git version number

## Installing Docker Desktop

1. Visit the official Docker Desktop website: https://www.docker.com/products/docker-desktop
2. Click on "Download Docker Desktop"
3. Run the installer as an administrator
4. Follow the installation wizard:
   - Accept the license agreement
   - Choose the installation directory (default is fine)
   - Make sure "Add Docker Desktop to PATH" is checked
   - Click "Install"
5. After installation, Docker Desktop will start automatically
6. You may need to enable WSL 2 or Hyper-V features:
   - If prompted, allow Docker Desktop to enable required Windows features
   - You might need to restart your computer
7. Sign in to Docker Desktop (or create a free account)
8. Wait for Docker to finish starting up (check the Docker icon in the system tray)
9. Verify the installation:
   - Open Command Prompt
   - Run the command:
     ```
     docker --version
     ```
   - You should see the Docker version number

## Installing Python

1. Visit the official Python website: https://www.python.org/downloads/
2. Download the latest Python 3.x version for Windows
3. Run the installer as an administrator
4. **Important**: Check the box "Add Python to PATH" before clicking "Install Now"
5. Click "Install Now" and wait for the installation to complete
6. Click "Close" when done
7. Verify the installation:
   - Open a new Command Prompt window
   - Run the following commands:
     ```
     python --version
     python -m pip --version
     ```
   - You should see version numbers for both

## Cloning the Repository

1. Open Command Prompt
2. Navigate to the directory where you want to store the project (e.g., Desktop):
   ```
   cd Desktop
   ```
3. Clone the repository:
   ```
   git clone https://github.com/payalpatra/Dynamic-KPI-Dashboard.git
   ```
4. Navigate into the project directory:
   ```
   cd Dynamic-KPI-Dashboard
   ```

## Setting Up Node.js Version Management

For Windows, we'll use nvm-windows to manage Node.js versions:

1. Visit the nvm-windows releases page: https://github.com/coreybutler/nvm-windows/releases
2. Download the latest installer (nvm-setup.exe)
3. Run the installer as an administrator
4. Follow the installation wizard:
   - Accept the license agreement
   - Choose the installation directory (default is fine)
   - Choose the symlink directory (default is fine)
   - Click "Next" and then "Install"
5. Click "Finish" when done
6. Open a new Command Prompt window
7. Verify the installation:
   ```
   nvm --version
   ```
8. Install the required Node.js version for this project:
   ```
   nvm install 16.20.2
   ```
9. Switch to this version:
   ```
   nvm use 16.20.2
   ```
10. Verify you're using the correct version:
    ```
    node --version
    ```
    You should see `v16.20.2`

## Installing Backend Dependencies

1. Make sure you're in the project root directory (`Dynamic-KPI-Dashboard`)
2. Make sure you're using Node.js v16.20.2:
   ```
   node --version
   ```
3. Install backend dependencies:
   ```
   npm install
   ```
4. Wait for the installation to complete (this may take a few minutes)

## Installing Frontend Dependencies

1. Navigate to the frontend directory:
   ```
   cd frontend
   ```
2. Install frontend dependencies with legacy peer dependencies to avoid conflicts:
   ```
   npm install --legacy-peer-deps
   ```
3. Wait for the installation to complete (this may take several minutes)

## Building the Frontend

1. Make sure you're in the frontend directory
2. Build the frontend application:
   ```
   npm run build
   ```
3. Wait for the build to complete successfully
4. Navigate back to the project root directory:
   ```
   cd ..
   ```

## Setting Up MongoDB with Docker

1. Make sure Docker Desktop is running (check the system tray)
2. Make sure you're in the project root directory
3. Start MongoDB using Docker Compose:
   ```
   docker-compose up -d
   ```
4. Wait for MongoDB to start (this may take a minute)
5. Verify MongoDB is running:
   ```
   docker-compose ps
   ```
   You should see the MongoDB container with a status of "Up"

## Configuring Environment Variables

1. In the project root directory, you'll find a file named `.env.example`
2. Create a copy of this file named `.env`:
   ```
   copy .env.example .env
   ```
3. The `.env` file should contain:
   ```
   PORT=5000
   MONGO_URI=mongodb://admin:password@localhost:27018/kpi_dashboard?authSource=admin
   NODE_ENV=development
   ```

## Starting the Application

1. Make sure you're in the project root directory
2. Make sure you're using Node.js v16.20.2:
   ```
   node --version
   ```
3. Start the application:
   ```
   npm start
   ```
4. Wait for the application to start
5. You should see messages indicating:
   - Server is running on http://localhost:5000
   - MongoDB connection SUCCESS
6. Open your web browser and navigate to http://localhost:5000
7. You should see the Dynamic KPI Dashboard application

## Troubleshooting Common Issues

### Issue: Permission denied errors with Docker

**Solution**:
1. Make sure Docker Desktop is running as administrator
2. Right-click on Docker Desktop in the Start menu
3. Select "Run as administrator"
4. Try the Docker command again

### Issue: Node.js version conflicts

**Solution**:
1. Check your current Node.js version:
   ```
   node --version
   ```
2. Make sure you're using v16.20.2:
   ```
   nvm use 16.20.2
   ```
3. If you get an error, try reinstalling:
   ```
   nvm install 16.20.2
   nvm use 16.20.2
   ```

### Issue: Python-related errors during npm install

**Solution**:
1. Make sure Python is installed and added to PATH
2. Try specifying Python explicitly during installation:
   ```
   npm install --python=python
   ```

### Issue: MongoDB connection fails

**Solution**:
1. Check if Docker is running:
   ```
   docker info
   ```
2. Check if MongoDB container is running:
   ```
   docker-compose ps
   ```
3. If not running, start it:
   ```
   docker-compose up -d
   ```
4. Check if port 27018 is available:
   ```
   netstat -an | findstr ":27018"
   ```

### Issue: Port already in use

**Solution**:
1. Find what's using the port:
   ```
   netstat -ano | findstr ":5000"
   ```
2. Kill the process using the PID from the above command:
   ```
   taskkill /PID <PID> /F
   ```
3. Or change the port in the `.env` file to something else like 5001

### Issue: Git not found during installation

**Solution**:
1. Make sure Git is installed correctly
2. Restart your Command Prompt
3. Check if Git is in your PATH:
   ```
   where git
   ```

### Issue: npm install fails with EACCES permissions error

**Solution**:
1. Run Command Prompt as administrator
2. Or configure npm to use a different directory:
   ```
   mkdir ~/.npm-global
   npm config set prefix '~/.npm-global'
   ```
3. Add this to your PATH environment variable

## Additional Resources

- Node.js Documentation: https://nodejs.org/en/docs/
- npm Documentation: https://docs.npmjs.com/
- Docker Documentation: https://docs.docker.com/
- Git Documentation: https://git-scm.com/doc
- MongoDB Documentation: https://docs.mongodb.com/

## Getting Help

If you encounter issues not covered in this guide:

1. Check the project's README.md file for additional information
2. Search for error messages online
3. Consult the documentation links provided above
4. Consider reaching out to the project maintainers if it's an open-source project

Congratulations! You've successfully set up the Dynamic KPI Dashboard on your Windows machine. Enjoy developing and exploring the application!
