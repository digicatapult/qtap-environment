# Docker setup

[Setup for MAC](#docker-on-macos)
[Setup for Windows](#docker-on-windows)

## Docker on macOS
Follow the steps below to install and configure Docker on macOS:

### 1. Install Docker Desktop for Mac

1: Download Docker Desktop for Mac from the official website: [Docker Desktop for Mac](https://docs.docker.com/desktop/setup/install/mac-install/)
2: Open the downloaded .dmg file and drag the Docker icon to the Applications folder.
3: Open the Applications folder and double-click the Docker app to start it. Docker will run in the background.

### 2. Set Up Docker

1: After starting Docker, you may need to provide your system password to allow Docker to install its components.
2: Wait for Docker to initialize. Once ready, the Docker icon will appear in your menu bar at the top-right of the screen.
3: You can skip signing in if you don’t have a Docker Hub account. Docker will still work without it.

### 3. Verify Installation

Open Terminal (Applications > Utilities > Terminal).

You can verify docker installation by typing this to your terminal:

```
docker --version
```

If you want to test docker type this to the terminal:

```
docker run hello-world
```

This command will download a test image and run it, showing a message that confirms Docker is running properly.

## Docker on Windows

Follow the steps below to install and configure Docker on Windows:

### 1. Install Docker Desktop for Windows

1: Download Docker Desktop for Windows from the official website: [Docker Desktop for Windows](https://docs.docker.com/desktop/setup/install/windows-install/)
2: Open the downloaded .exe file to start the installation process.
3: Follow the installation prompts, accepting the license agreement and choosing installation options.

### 2. Enable WSL 2 (Windows Subsystem for Linux)

Docker requires WSL 2 to run properly. The Docker Desktop installer will guide you through enabling this if it’s not already set up.

1: Open PowerShell as Administrator and run the following commands to enable WSL 2:

```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

2: Download and install the Linux kernel update package.
3: Set WSL 2 as the default version by running this command in PowerShell:

```
wsl --set-default-version 2
```

### 3. Start Docker Desktop
1: After installation, search for Docker Desktop in the Start menu and open it.
2: Docker will start. You may need to log in with your Docker Hub account (you can skip this if you don’t have one).

### 4. Verify Installation

Open PowerShell or Command Prompt and run the following command to check if Docker is installed:

You can verify docker installation by typing this to your terminal:

```
docker --version
```

If you want to test docker type this to the terminal:

```
docker run hello-world
```

This command will download a test image and run it, showing a message that confirms Docker is running properly.

### Further reading on docker

[Getting Started](https://docs.docker.com/get-started/)
[What is Docker](https://docs.docker.com/get-started/docker-overview/)

I haven't used this, but it looks nice:
[Docker Curriculum](https://docker-curriculum.com/)
