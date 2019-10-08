# Teamcity Agent 安装教程

## Linux 安装

1. 目录准备
```bash
# 根目录下创建 `/teamcity`
sudo mkdir /teamcity

# 如果需要以其他身份执行的话，记得赋予相关权限
sudo chown -R gitlab-runner:gitlab-runner teamcity/
sudo su gitlab-runner
```

2. 安装并解压
```bash
cd /teamcity

# 下载 zip 包
curl https://teamcity.example.com/update/buildAgent.zip > buildAgent.zip

# 解压至 /teamcity 目录下
unzip buildAgent.zip -d buildAgent
```

3. 更改配置并启动

```bash
cd buildAgent/conf
cp buildAgent.dist.properties buildAgent.properties
vim buildAgent.properties
```

> `serverUrl`： 可以改成你的 Teamcity 服务域名，例如 `https://teamcity.example.com`
> `name`： 可以改成自己的 anget 名，例如 `linux-prod-001`

改完配置可以准备启动了，将下面这脚本写入 `~/start_teamcity.sh`

```shell
#!/usr/bin/env bash

/teamcity/buildAgent/bin/agent.sh start
```

执行启动脚本：

```bash
~/start_teamcity.sh
```

## 配置

1. 打开 Agents 标签页，如果有管理员权限的话，可以看到 Unauthorized 下已经有你的 agent 了
![Agents](https://ws1.sinaimg.cn/large/818cd4dagy1g7qslwfd93j21c20fqtbe.jpg)

2. 点击 Authorize 授权即可
![Authorize](https://ws1.sinaimg.cn/large/818cd4dagy1g7qsn8rogxj20x40he3zz.jpg)

> 如果没有权限，可以联系管理员
