# Gitlab + Jenkins 实现React Web 自动部署

# GitLab设置

* 在Gitlab中新建一个用户，专用于CI/CD,登录该用户，点击右上角用户下来中的Settings进入下面的页面![](/chi-xu-ji-cheng/jenkins/images/gitlab-accessToken-1.jpg)
* 点击右边的Access Tokens,在右边的Name中输入一个名称jenkins，该名称随意，根据需要勾选Scopes选项，点击Create personal access token![](/chi-xu-ji-cheng/jenkins/images/gitlab-accessToken-2.jpg)
* 生成AccessToken :wGL4D6C7VfvF8Gs9oeEr![](/chi-xu-ji-cheng/jenkins/images/gitlab-accessToken-3.jpg)

# Jenkins设置

安装插件GitLab

* Jenkins-&gt;系统管理-&gt;系统设置![](/chi-xu-ji-cheng/jenkins/images/jenkins-gitlab-1.jpg)

* 添加gitlab地址信息![](/chi-xu-ji-cheng/jenkins/images/jenkins-gitlab-2.jpg)

* 设置AccessToken![](/chi-xu-ji-cheng/jenkins/images/jenkins-gitlab-3.jpg)

测试，点击Test Connection![](/chi-xu-ji-cheng/jenkins/images/jenkins-gitlab-4.jpg)

