# 📚 GZHULib-EasyReserve

> 广州大学图书馆自动预约工具，支持自动预约座位、研讨室，并提供自动签到功能。通过GitHub Actions实现全自动化运行，让你告别抢不到座位、研讨室的烦恼。

## 📁 目录说明

### 核心文件
- `seat_reservation.py` - 座位预约核心代码
- `studyroom_reservation.py` - 研讨室预约核心代码
- `seat_sign.py` - 自动签到核心代码
- `util.py` - 工具函数库
- `config.py` - 配置文件

### 配置文件
- `user_config.json` - 用户配置文件
- `user_config_example.json` - 用户配置示例文件
- `user_config_explain.md` - 用户配置说明文档
- `requirements.txt` - Python依赖包列表

### 数据文件
- `campus.db` - 图书馆座位、房间和校区数据库文件
- `room_csv/` - 座位编码数据目录

### 自动化配置
- `.github/workflows/` - GitHub Actions工作流配置
  - `seat.yml` - 座位预约工作流
  - `room.yml` - 研讨室预约工作流
  - `seat_sign.yml` - 自动签到工作流

## 🚀 快速开始

### 1️⃣ 获取项目
~~1. 点击本页面右上角的"Fork"按钮~~

~~2. 等待Fork完成，你将获得一个属于自己的仓库副本(‼️注意是私人仓库即勾选`private`,不然你的学号密码将可能泄露‼️)~~

(**Fork的项目只能为公共仓库，切勿Fork本项目以免账号密码泄露**)

创建拥有本仓库代码的私有仓库，参考https://blog.csdn.net/NSJim/article/details/140453315

### 2️⃣ 设置个人信息
1. 在你的仓库中，找到 `user_config.json` 文件
2. 点击编辑按钮(铅笔图标)
3. 修改以下信息(参考 [`user_config_example.json`](user_config_example.json) 中的注释说明进行修改)：
   - 将 `username` 改为你的学号
   - 将 `password` 改为你的密码
   - `seat_info` 为预约座位信息(如果需要)：
     - 将 `seat_name` 改为你想预约的座位号(例如：103-085，座位编码在room_csv目录下)
     - 将 `time` 改为你想预约的时间段
   - `room_info` 为预约研讨室信息(如果需要)：
     - 将 `room_names` 改为你想预约的研讨室名称,此项可多选(例如：研讨室A，研讨室名称可在官网查询)
     - 将 `time` 改为你想预约的时间段
     - 将 `other_ids` 改为其他用户的学号(可选，一些研讨室需要多个用户)
4. 将配置好的信息粘贴到https://www.bejson.com 中校验是否格式正确
5. 确认格式正确后点击"Commit changes"保存修改

### 3️⃣ 启用GitHub Actions
1. 点击页面上方的 "Actions" 标签
2. 点击 "I understand my workflows, go ahead and enable them" 按钮
3. 查看是否有 `AUTO-ROOM`、`AUTO-SEAT` 和 `AUTO-SIGN` 三个工作流
4. 默认是关闭所有的工作流，你可以根据需要启用相应的工作流，点击`Enable workflow`：
   - `AUTO-ROOM` - 研讨室预约
   - `AUTO-SEAT` - 座位预约
   - `AUTO-SIGN` - 自动签到

## ⚠️ 注意事项
1. 请确保你的账号密码正确
2. 请遵守图书馆的使用规则
3. 不要频繁触发运行

## ❓ 遇到问题？
1. 检查 `user_config.json` 中的配置是否正确
2. 查看Actions运行日志了解详细错误信息
3. 个人配置是否正确，详情参考 [`user_config_explain.md`](user_config_explain.md)
4. **正确**在GitHub上提交Issue，附带详细错误信息
5. 发送详细错误信息邮件到作者邮箱`gomorebug@gmail.com`

## 💡 需要更多帮助？
如果你仍是无法使用，或者对GitHub不熟悉，可以发送邮件附带个人联系方式付费咨询，或者付费让作者帮忙预约，联系方式`gomorebug@gmail.com`

## 后文
+ 由于Github Actions时间上普遍不准，在设置Github WorkerFlows文件上的时间要比实际预约的时间提前半小时以上。由于Github Actions的这个特征，本项目的自动签到时常失效，建议关闭签到工作流。
+ 有计算机相关知识的人可以阅读https://docs.github.com/en/actions定制化自己的工作流
+ 如果你有更好的建议或者想法，欢迎提交PR或者Issue

## 📝 免责声明
本项目仅供学习交流使用，请勿用于商业用途。使用本程序产生的任何后果由使用者自行承担。 
