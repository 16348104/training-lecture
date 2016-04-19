# IDEA

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
  File-Settings-Keymap
  Main menu-Code-Completion-Basci
  Add Keyboard Shortcut: Alt+斜杠

  File-Settings-Editor-Code Completion
  Case sensitive completion: None
  ```
  
4. IDEA key map reference
  
    [http://thu.github.io/IDEA/](http://thu.github.io/IDEA/)
    
