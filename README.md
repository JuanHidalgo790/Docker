# Docker 
Procedures for installing and getting started on Windows.

## Virtualization

Before installation, some steps are required. First, the user must check if virtualization is enabled.

Right click on the taskbar and access the “task manager”. Then, in the CPU tab, check if the virtualization is set to "enabled". 

Then, search for “Turn Windows Feature on or off” (ativar ou desativar os recursos do Windows), and check if the following options (marked with red lines) are enabled. 

![image](https://user-images.githubusercontent.com/125278160/230932820-e5edd654-c444-4dcc-bdce-fb1aceac6a02.png)

With these changes, the computer will need to be restarted. 

## WSL2

Before downloading and installing Docker, it is necessary to enable wsl2 on Windows. 

To check if there is already a Unix distribution installed and the wsl version (1 or 2), open Powershell (as administrator), and then type:

```bash
wsl -l -v
```

![image](https://user-images.githubusercontent.com/125278160/230934507-218f576b-98a4-43fd-998a-472645fbf9db.png)

In the example above, Ubuntu is already installed. If the available version was 1, the user would need to type:

```bash
wsl --set-default-version 2
```

In the case that nothing is installed, the user must download the required package manually. Thus, go to the following link:

https://aka.ms/wsl2kernel

Download the package (indicated with a red line) and install.

![image](https://user-images.githubusercontent.com/125278160/230935073-1b32f52f-91cd-446d-8610-4e2c2e8f75e8.png)

## Installing Docker

After installation of wsl, go to https://www.docker.com/ and download Docker Desktop for Windows.

After downloading it, click and run the installer. Accept all the options and then the installation is finished. 

Open Docker and then, click in the settings button. 

![image](https://user-images.githubusercontent.com/125278160/230936125-e501ef66-eb73-4b02-b184-dd077687f496.png)

Ensure that the WSL2 option is activated, and then exit by clicking in the “x” button above.

![image](https://user-images.githubusercontent.com/125278160/230936258-85507bf3-0b33-48e0-9c80-672c2b132631.png)

Now, you can check the wsl distro.

![image](https://user-images.githubusercontent.com/125278160/230936349-3c5901f1-66b1-4210-bdb7-00fe19c4552e.png)

To check if Docker is recognized at Powershell, and check version, type the following command:

```bash
docker version
```

![image](https://user-images.githubusercontent.com/125278160/230936588-896485b3-548f-4b2b-b09f-eb3f1d97b372.png)

To test if Docker is correctly running type:

```bash
docker run hello-world
```

This command downloads a test image and runs it in a container. When the container runs, it prints a confirmation message and exits. Now Docker has been successfully installed. 

OBS: To work with Docker using CLIs, the user must ensure that Docker Desktop is running. Thus, open it always when using command lines. Otherwise, the Docker commands will not work.

## Ubuntu Terminal

It is also interesting to use Ubuntu terminal for running Docker instead of Powershell, taking advantage of the installed wsl2. To see a list of the available distributions, type:

```bash
wsl -l -o
```

![image](https://user-images.githubusercontent.com/125278160/230939383-ebdbb0da-35c8-46cf-a7d8-e0e036a4e4d6.png)

Select the desired distribution (Ubuntu), and then type:

```bash
wsl --install -d Ubuntu
```

![image](https://user-images.githubusercontent.com/125278160/230939538-45ca255b-7159-4213-be49-d0ded193d0aa.png)

Create a user, then a password. And, so, Ubuntu terminal is now installed. 

![image](https://user-images.githubusercontent.com/125278160/230939601-0cdf462a-7d85-40c2-ac10-7a2630293586.png)

OBS: Eventually it will be needed to restart the computer after installing Ubuntu, and, also, reactivate the WSL2 option in the Docker Desktop settings (as described previously).

## Testing Docker

With Docker correctly installed, try to get started with the examples from the following website:

https://docs.docker.com/get-started/

In this website, an example is going to be explored, giving insights on some useful commands. It is divided into 10 parts, and it is recommended to perform at least steps 2 to 6. The following figure illustrates the example app, named as “to do list”.

![image](https://user-images.githubusercontent.com/125278160/230939803-5913150e-ff44-4a34-9839-06148746857e.png)

Another interesting website that can be addressed is the following, in which common commands are listed and depicted with some examples. 

https://docs.docker.com/engine/reference/commandline/docker/
