# Git

<img src="../image/git/logo_git.png" title="Git" width="100">

1. Git 安装
  - PortableGit 解压缩
2. IDEA 中配置 Git
  - File - Settings - Version Control - Git - Path to git executable
  - 选择本地 Git/bin 下的 git.exe
3. 从 GitHub 检出项目
  - 复制项目 `HTTPS` 地址
  - VCS - Checkout from Version Control - GitHUb
  - 粘贴地址到 Git Repository URL
  - Clone
  - 根据向导在本地建立项目
4. 在 GitHub 中托管项目
  - 建立 `.gitconfig` 文件
  
    ```
    开始 - cmd - enter
    DOS
    C:\Users\Administrator>edit .gitconfig
    
    输入：
    [user]
       name = your_github_username
       email = your_github_email
    
    或：
    
    d:
    cd (change directory)
    D:\0\PortableGit\bin>

    git config --global user.email = your github email
    git config -- global user.name = you github username
    ```

  - 创建 .gitignore 文件
    
    ```
    .idea

    *.iml
    ```
      
  - VCS - Import into Version Control - Share Project on GitHub
  - Share - OK
  
  
5. Git 相关快捷键
  - `Ctrl + T` Update
  - `Ctrl + K` Commit / Push