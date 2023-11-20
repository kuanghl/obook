
- Build
  环境设置和编译指令
  ```yml
  runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: install mdbook
      run: cargo install mdbook --version 0.4.35
      
    - name: Build docs
      run: |
        mdbook build
  ```



- Deploy
  首先要设置`Setting-->Actions-->General-->Workflow permissions`开启读写权限,加入部署持续集成
  ```yml
  - name: Deploy 🚀
      uses: JamesIves/github-pages-deploy-action@v4
      with:
        folder: docs # The folder the action should deploy.
  ```