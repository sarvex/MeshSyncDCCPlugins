# Installation

- [Automatic Installation via Unity Editor](#automatic-installation-via-unity-editor)
- [Manual Installation](#manual-installation)
  - [Preparation](#preparation)
  - [Maya](#maya)
  - [3ds Max](#3ds-max)
  - [MotionBuilder](#motionbuilder)
  - [Blender](#blender)
- [Unity Project Setup via DCC tools](#unity-project-setup-via-dcc-tools)

## Automatic Installation via Unity Editor

![](images/MeshSyncPreferences.png)

[MeshSync](https://docs.unity3d.com/Packages/com.unity.meshsync@latest)'s Preferences page
provides easy installation on several DCC tools.    
Alternatively, we can also [install the plugins manually](#manual-installation).

---

## Manual Installation


### Preparation

![](images/PackageManager.png)

First, get **MeshSync DCC Plugins** package in a Unity project.
1. Open [Package Manager](https://docs.unity3d.com/Manual/upm-ui.html). 
2. Click the **+** button, and choose **Add package from git URL**.
3. Type in `com.unity.meshsync.dcc-plugins`.

### Maya

1. Open `Packages/MeshSync DCC Plugins/Editor/Plugins` folder using a file explorer 
   and uncompress the appropriate zip file for Maya.
1. Copy the uncompressed files:
   - Windows:   
     If `MAYA_APP_DIR` environment variable is setup, copy the *modules* directory there.  
     If not, go to `%USERPROFILE%\Documents\maya` in Windows Explorer, and copy the *modules* directory there.
   - Mac:   
     Copy the *UnityMeshSync* directory and *UnityMeshSync.mod* file to `/Users/Shared/Autodesk/modules/maya`.
   - Linux:  
     Copy the *modules* directory to `~/maya/<maya_version>`
  
  
1. Start Maya, then go to Windows &rarr; Settings/Preferences &rarr; Plug-in Manager.
1. Activate MeshSync DCC plugin by checking Loaded under *MeshSyncClient*.
1. Notice that *UnityMeshSync* should now be available on the shelf UI.  
  Click on the gear icon to open the settings menu and start playing around with MeshSync.
  
![MeshSyncClientMaya](images/MeshSyncClientMaya.png)

---

### 3ds Max

1. Open `Packages/MeshSync DCC Plugins/Editor/Plugins` folder using a file explorer 
   and uncompress the appropriate zip file for 3ds Max.
1. Start 3ds Max
1. Copy *MeshSyncClient3dsMax.dlu* that corresponds to the used version of 3ds Max into 
   one of the following directories:
   - **(Recommended)** A custom directory for plugins that has been added in 3ds Max by the following menu:
     * 3ds Max 2019 and earlier: Customize &rarr; Configure System Paths. Then select *3rd Party Plug-Ins* tab.
     * 3ds Max 2020: Customize &rarr; Configure User and System Paths. Then select *3rd Party Plug-Ins* tab.
   - The plugin path under the installation directory, e.g: `C:\Program Files\Autodesk\3ds Max 2019\Plugins`
1. Restart 3ds Max 
1. Confirm that "UnityMeshSync" has been added to the main menu bar.
   The settings window can be opened by clicking "Window". 
   > If we change the menu bar, "UnityMeshSync" will be added under Action, which 
   > still allows us to access MeshSync features.

![MeshSyncClient3dsMax](images/MeshSyncClient3dsMax.png)

---

### MotionBuilder

1. Open `Packages/MeshSync DCC Plugins/Editor/Plugins` folder using a file explorer 
   and uncompress the appropriate zip file for MotionBuilder.
1. Start MotionBuilder.
1. Add a path for custom plugins by clicking on Settings &rarr; Preferences &rarr; SDK menu.
1. Copy *MeshSyncClientMotionBuilder.dll* that corresponds to the used version of MotionBuilder into 
   the custom plugin path.
1. Restart MotionBuilder.
1. Confirm that "UnityMeshSync" is added in the AssetBrowser under Templates &rarr; Devices folder.
1. Add "UnityMeshSync" to the scene.
1. Start playing around with various MeshSync settings and features by 
   selecting Devices &rarr; UnityMeshSync in the Navigator.

![MeshSyncClientMotionBuilder](images/MeshSyncClientMotionBuilder.png)

---

### Blender
  
1. Open `Packages/MeshSync DCC Plugins/Editor/Plugins` folder using a file explorer 
   and uncompress the appropriate zip file for Blender.
1. Start Blender
1. Go to Edit &rarr; User Preferences
1. Click "Install" at the top right of the window, and select the appropriate **blender-x.xx.zip** file.
1. Confirm that "Import-Export: Unity Mesh Sync" is added to the Add-ons tab.     
   ![MeshSyncClientBlender_Installation](images/MeshSyncClientBlender_Installation.png)

1. Check "Import-Export: Unity Mesh Sync" to enable it.
1. Confirm that MeshSync panel is added.
  
<img src="images/MeshSyncClientBlender.png" alt="drawing" width="500"/>

#### Caveat

When installing a Blender plugin, the older version has to be uninstalled first if it exists.   
Steps to uninstall:

1. Select "Import-Export: Unity Mesh Sync" from the Add-ons menu.
1. Click "Remove" button.
1. Restart Blender. 
1. On Mac OSX, delete the installed plugin files in the following folder:

   ``` 
   ~/Library/ApplicationSupport/Blender/2.xx/scripts/addons/MeshSyncClientBlender
   ``` 

---

## Unity Project Setup via DCC tools
We can install MeshSync on a Unity project through DCC tools. This install method is designed for users who are not familiar with the Unity Editor or the Unity Package Manager.

Currently, this install method is available only for Blender. For other DCC tools, see [MeshSync](https://docs.unity3d.com/Packages/com.unity.meshsync@latest)'s installation page.
### Blender
Install the Blender add-on:
1. Download the [installer add-on](./BlenderInstaller.md).
1. Install the add-on.
1. On the add-on preferences, click on Install. 

#### Unity Editor setup
In the add-on preferences, click on the **Auto Detect** button to detect the location of the Unity Hub and the Unity Editor.
![](images/EditorSettings.png)

#### Unity project setup
1. In the add-on preferences, click on the **Select or Create Project via Unity Hub**
2. Unity Hub will open. In the hub, select or create a project.
3. If MeshSync is not setup for the selected project, follow the instructions on the add-on preferences panel to install it.
![](images/ProjectSettings.png)

#### Sync
1. Click on **Auto Sync** or **Manual Sync**.
![](images/BlenderSyncButtons.png)

The Unity project will be launched with the Blender scene synchronised.

