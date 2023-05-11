# Windows Subsystem for Linux (WSL) Setup

Windows Subsystem for Linux (**WSL**) allows Windows users to run Ubuntu Linux natively. This course extensively uses a Unix bash terminal. This allows Windows users to follow along and run bash commands natively.

<br/>

## Install WSL 2

<br/>

Follow Microsoft official documentation to [**install WSL 2**](https://docs.microsoft.com/en-us/windows/wsl/install).

<br/>

**NOTE:**
>**UPGRADE WINDOWS FIRST**
>
>Most issues regarding WSL installation arise from older versions of Windows. If you are running a Windows Build lower than **19041**, before enabling WSL 2 you must **upgrade** Windows using **Windows Update Assistant**. To find your Windows Build info, hit the Windows key and type _"System Information"_. (At the time of this writing, the latest build is 10.0.19041)

<br/>

> **Window 11**
> 
>Some users are reporting issues with WSL when upgrading to Windows 11, with no clear fix yet. The links below might help you troubleshoot the problem. If you experience this, please let the instructor know, and we can take a look at your specific installation:
>- [WSL File System Error # 1](https://github.com/microsoft/WSL/issues/7435)
>- [WSL File System Error # 2](https://github.com/microsoft/WSL/issues/5456)

<br/><br/>

## Install Ubuntu 20.04

Once you have WSL installed, you can install Ubuntu 20.04, which is our recommended Linux distribution. 

Open the Microsoft Store App: **[Install Ubuntu from the Microsoft store](https://www.microsoft.com/en-us/p/ubuntu-2004-lts/9n6svws3rx71?activetab=pivot:overviewtab)**

![Microsoft Store](img/wsl-ms-store.png)

<br/>

Once you have Ubuntu installed on your WSL, you should update your Ubuntu install:

1. Start an **Ubuntu** terminal from the **Start Menu** 

2. You will be prompted to choose a **root** password. Make sure to **remember** this. You do not have a chance to reset this if you forget.

3. Run the following:

    ```bash
    sudo apt update
    sudo apt -y upgrade
    ```

**NOTE:** You MUST first update/upgrade Ubuntu before you can properly install and run Python.

<br/>

## Accessing Files

Because Ubuntu uses a file structure, it's hard to find where your WSL Ubuntu files live under you actual Windows machine. To open the content of any Ubuntu folder, you can simple run the following command:

```bash
explorer.exe .
```

This will open a Windows Explorer windows that points to your current Ubuntu directory.

<br/>

In reverse, your Windows files can be access from Ubuntu under:

```bash
cd /mnt/c
ls -l
```

This will list the content of your C Drive.
