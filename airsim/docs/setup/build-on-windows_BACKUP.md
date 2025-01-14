---
description: >-
  Read [AirSim Doc](https://microsoft.github.io/AirSim/build_windows) for more detailed
  information
---

# Build on Windows

### Install Unreal Engine

1. [Download](https://www.unrealengine.com/download) the Epic Games Launcher. While the Unreal Engine is open source and free to download, registration is still required.
    ![Install](install1.jpg)
2. Run the Epic Games Launcher, open the `Library` tab on the left pane. Click on the `Add Versions` which should show the option to download **Unreal 4.24** as shown below. If you have multiple versions of Unreal installed then **make sure 4.24 is set to `current`** by clicking down arrow next to the Launch button for the version.

   **Note**: AirSim also works with UE &gt;= 4.22, however, we recommend you update to 4.24. **Note**: If you have UE 4.16 or older projects, please see the [upgrade guide](https://github.com/ykkimhgu/gitbook_docs/tree/744cefa60529ba375f5fbccce60616d217c2429b/airsim/setup/unreal_upgrade.md) to upgrade your projects.

   ![Install](install2.jpg)

### Install Git for Windows

* [Download](https://git-scm.com/) Git for Windows (lastes source, release 2.27.0)
* Use default settings to install
  ![gitInstall](gitInstall.jpg)
  
### Install Visual Studio

* Install Visual Studio 2019.


   **Note**: Use **English** for the VS2019 language. If you choose **Korean**, you may need to convert 'UTF Encoding' is some AirSim source files.

   ![Install](install_vs1.jpg)
  
  **Make sure** to select **Desktop Development with C++** and **Windows 10 SDK 10.0.18362** \(should be selected by default\) while installing VS 2019.

   ![Install](install_vs2.jpg)

   **Note**: Use **English** for the VS2019 language. If you choose **Korean**, you may need to convert 'UTF Encoding' is some AirSim source files.


### Download AirSim

* Start `Git Bash` or `Git GUI`
* Move to the target directory to install AirSim. Use `cd` command to change directory
* Clone the AirSim repo by typing
  
  ```text
     git clone https://github.com/Microsoft/AirSim.git
  ```
 
  ![gitInstall](clone1.jpg)


### Build AirSim

* Open `Command Prompt for VS2019`
* Move to the installed AirSim directory by `cd AirSim`.
* Run `build.cmd` from the command line. This will create ready to use plugin bits in the `Unreal\Plugins` folder that can be dropped into any Unreal project.
  ![build1](build1.jpg)

> **Build error**:  If the build error message is related to UTF decoding Go to FAQ #1

### Build Unreal Project

Finally, you will need an Unreal project that hosts the environment for your vehicles. AirSim comes with a built-in "Blocks Environment" which you can use, or you can create your own. Please see [setting up Unreal Environment](https://github.com/ykkimhgu/gitbook_docs/tree/744cefa60529ba375f5fbccce60616d217c2429b/airsim/setup/unreal_proj.md).

## FAQ

#### Building Error message of Error C2220

The initial setting for VS2019 gives the warning as the compile error.
This error has to do with some sources have some characters encoded which shows warning by the compiler.

* Open the header/source files that gives encoding warning with VS2019
* **Save As** with **Save with Encoding**: Encoding **UTF-8 with signature** 

  ![faq1](FAQ1.jpg)

  ![faq2](faq2.jpg)

#### Clashes of VS 2017 and VS2019. How to force Unreal to use Visual Studio 2019?

If different versions of Visual Studio are installed. such as VS2017 and VS 2019,  Unreal may be associated with VS2017. Building an AirSim project in VS2019 with Unreal associated with VS2017 can give build error.

Need to Change the Unreal configuration to associate with VS2019

* Open `C:\Users$user\AppData\Roaming\Unreal Engine\UnrealBuildTool\BuildConfiguration.xml`
* Modify as following
  
  ```xml
  <?xml version="1.0" encoding="utf-8" ?>
  <Configuration xmlns="https://www.unrealengine.com/BuildConfiguration">
  <BuildConfiguration>        
      </BuildConfiguration>
      <VCProjectFileGenerator>
          <Version>VisualStudio2019</Version>
      </VCProjectFileGenerator>

      <WindowsPlatform>
          <Compiler>VisualStudio2019</Compiler>
      </WindowsPlatform>
  </Configuration>
  ```
