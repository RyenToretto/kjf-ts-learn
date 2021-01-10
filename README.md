### 目录结构 node 14.15.3
    npm config set registry https://registry.npm.taobao.org
    npm config set registry https://registry.npmjs.org
    /build
        webpack.config.js ---- 入口
        webpack.base.config.js ---- 公共环境的配置
        webpack.dev.config.js ---- 开发环境的配置
        webpack.prod.config.js ---- 生产环境的配置
    /doc
    /src
        .editorconfig
        .gitignore
        package.json
        README.md
### git config --global credential.helper store
### npm init -y
### tsc --init

### npm i -D webpack webpack-cli webpack-dev-server
    yarn add webpack webpack-cli@3.3.12 webpack-dev-server@3.11.0 --dev
### npm i -D ts-loader typescript
    yarn add ts-loader typescript --dev
### npm i -D webpack-merge
    yarn add webpack-merge --dev
### npm i -D html-webpack-plugin
    yarn add html-webpack-plugin --dev
### npm i -D clean-webpack-plugin
    yarn add clean-webpack-plugin --dev
