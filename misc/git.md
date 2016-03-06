# Git

1. Git 安装
  - PortableGit 解压缩
2. IDEA 中配置 Git
  - File - Settings - Version Control - Git - Path to git executable
  - 选择本地 Git/bin 下的 git.exe
3. 在 GitHub 中托管项目
  - 建立 .gitconfig 文件
  
    ```
    开始 - cmd - enter
    DOS
    d:
    cd (change directory)
    D:\0\PortableGit\bin>

    git config --global user.email = your github email
    git config -- global user.name = you github username
    ```
  
  - VCS - Import into Version Control - Share Project on GitHub
  - 创建 .gitignore 文件
    
    ```
    .idea

    *.iml
    ```
  - Share - OK
4. 从 GitHub 检出项目
  - 复制项目 HTTPS 地址
  - VCS - Checkout from Version Control - GitHUb
  - 粘贴地址到 Git Repository URL
  - Clone
  - 根据向导在本地建立项目