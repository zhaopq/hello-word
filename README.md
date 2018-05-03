问题1：jar包引入后报错<br/>
首先检查maven服务器地址（本地服务器地址），然后更新项目，并且在本地上下载jar包。<br/>
问题2：项目中清除workspace中的内容出现 ！号<br/>
1.将maven->userSetting.xml引入，Libraries中配置jdk1.7，部署Tomcat<br/>
2.对应的jar包没有引入，将Libraries中报错的jar包删除，点击Add JARs功能，找到当前项目中的jar包，导入到eclipse项目中<br/>
问题3：如何设置权限<br/>
