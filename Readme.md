### <center/> Hexo博客搭建工具下载与安装

* 1、需要工具

    |工具|下载|
    |---|---|
    |nodejs|https://nodejs.org/en/download/|
    |hexo|npm install hexo-cli -g|
    |deploy|npm install hexo-deployer-git --save|
    |server|npm i hexo-server|

* 2、常用命令  

    <table>
        <tr>
            <th>操作</th>
            <th>命令</th>
            <th>命令缩写</th>
        </tr>
        <tr>
            <td rowspan="3">本地启动</td>
            <td>hexo clean</td>
            <td style="text-align:center">-</td>
        </tr>
        <tr>
            <td>hexo generate</td>
            <td style="text-align:center">hexo g</td>
        </tr>
        <tr>
            <td>hexo server</td>
            <td style="text-align:center">hexo s</td>
        </tr>
        <tr>
            <td rowspan="3">部署github</td>
            <td>hexo clean</td>
            <td style="text-align:center">-</td>
        </tr>
        <tr>
            <td>hexo generate</td>
            <td style="text-align:center">hexo g</td>
        </tr>
        <tr>
            <td>hexo deploy</td>
            <td style="text-align:center">hexo d</td>
        </tr>
    </table>

* 3、部署地址配置，在`_config.yml`文件内修改如下属性。

    ```
    deploy:
    type: git
    repo: https://github.com/YourgithubName/YourgithubName.github.io.git
    branch: master
    ```

* 4、在`hexo`官网下载自己喜欢的主题，放置到`themes`目录下，然后在`_config.yml`文件内修改`theme`属性为你的主题文件名，重启服务可以查看效果。

* 5、设置RSS

    * 安装rss相关插件：`npm i hexo-generator-feed`  
    * 在`_config.yml`配置文件下找到`Extensions`添加如下内容：

        ``` 
        plugin:
        - hexo-generator-feed
        #Feed Atom
        feed:
        type: atom
        path: atom.xml
        limit: 20
        ```
    * 进入到你的主题的配置文件下，找到你的放`rss`的位置，添加`/atom.xml`即可。

* 常见问题汇总  
  * hexo发生error：spawn failed错误的解决方法
    ```
    1. 删除.deploy_git文件夹;
    2. 输入git config --global core.autocrlf false
    ```

