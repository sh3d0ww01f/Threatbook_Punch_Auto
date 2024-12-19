# Threatbook_Punch_Auto

## 功能
微步情报社区自动获取成长值脚本（不包括发帖、情报打标、被关注等获取方式），支持githubaction自动定时运行。获取每日成长值主要包括：  
1.每日登录（10成长值）  
2.每日内容点赞（5成长值×10次上限=50成长值）  
3.每日关注（5成长值×3次上限=15成长值）  
每日共75成长值，不包括可能会有用户回关，被关注+10成长值/个
## 配置
项目根目录下`config.json`为配置文件，包括cookie配置,以及微步社区相关接口（若接口后续有更新则修改配置文件即可）
## 使用
脚本有以下两种部署方式。
#### action（推荐）
* 在GitHubaction环境变量中配置threatbook_cookie
* 启用action
* 默认23:30自动运行

#### 2.直接运行脚本/定时运行
```
vi config.json #配置cookie
pip install -r requirements.txt
crontab -e  # 编辑crontab
30 23 * * * python3 /path/to/Threatbook_Punch_Auto.py  # 每日23:30执行脚本,将脚本路径替换为实际路径
```

