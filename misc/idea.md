# IDEA

<img src="../image/idea/logo_idea.png" title="Intellij IDEA" width="100">

1. unzip IDEA.zip to your-idea-install-folder

2. 修改 IDEA 配置文件 your-idea-install-folder/bin/idea.properties

  ```
  idea.config.path=your-idea-properties-folder/config
  idea.system.path=your-idea-properties-folder/system
  idea.plugins.path=${idea.config.path}/plugins
  idea.log.path=${idea.system.path}/log
  ```

3. 修改两处配置

  ```
  File - Settings - Keymap
  Main menu - Code - Completion - Basci
  Add Keyboard Shortcut: Alt+斜杠

  File - Settings - Editor - Code Completion
  Case sensitive completion: None
  ```
  
4. IDEA key map reference
  
    [http://thu.github.io/IDEA/](http://thu.github.io/IDEA/)
    
5. 创建基于 Gradle 构建的 Java Web 项目

  - 安装 gradle
    - 参见 [Gradle 的安装](gradle.md)
  - 创建项目

    ```
    Idea > File > New > Project... 
    
    左侧 选择 Gradle 
    右侧勾选 Java 和 Web
    单击 Next
    参见图一
    
    填写 GroupId 和 ArtifactId
    单击 Next
    
    勾选 Create directories for empty content roots automatically
    选择 Use local gradle distribution
    指定 Gradle home
    单击 Next
    参见图二
    
    确认 Project name 和 Project location
    单击 Finish
    ```
    
    图一
    
    ![图一](../image/idea/gradle_web_1.png)
    
    图二
    
    ![图二](../image/idea/gradle_web_2.png)
    
6. Java Web 项目在 Tomcat 中的部署

  - 安装 Tomcat
    参见 [JavaEE 引言](../javaee/intro.md)
  - 在 Idea 中关联 Tomcat

    ```
    Idea > File > Settings... > Build, Execution, Deployment > Application servers
    单击 +
    选择 Tomcat Server
    指定 Tomcat Home
    单击 OK
    ```
   
   - 创建 Java Web 项目
     - 参见 [5. 创建基于 Gradle 构建的 Java Web 项目](idea.md)
   - 在 Tomcat 中部署 Java Web 项目
   
     ```
     Idea > Run > Edit Configurations...
     单击 +
     选择 Tomcat Server
     单击 Local
     
     在 Server 选项卡中
     On 'Update' action 选择 Update classes and resources
     On frame deactivation 选择 Update classes and resources
     
     在 Deployment 选项卡中
     单击 +
     单击 Artifact...
     选择含有 exploded 的 Artifact
     单击 OK
     ```
   - Tomcat　的启动　/ 重启　/　重部署
     -  Shift + Alt + F10
    
