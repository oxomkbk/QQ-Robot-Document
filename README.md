# QQ 机器人 API v2 完整文档

> 本文档完整收录了 QQ 机器人开放平台 API v2 的全部接口说明。
>
> **来源**：https://bot.q.qq.com/wiki/develop/api-v2/
> **交流群**：https://qm.qq.com/q/f7AF4aVyKW
>
> **生成日期**：2026-09-010
>
> **收录页面数**：130 个完整 API 文档页面

---

## 目录

- **起步指南**
  - 启动接入
  - 获取访问凭证
  - API 调用指南
  - **事件订阅与通知**
    - 通用数据结构
    - Webhook 方式
    - WebSocket 方式
- **服务端接口**
  - **消息收发**
    - 消息收发概述
    - **单聊消息**
      - 发送单聊消息
      - 流式发送单聊消息
      - 撤回单聊消息
      - **事件**
        - 单聊消息事件
    - **群聊消息**
      - 发送群聊消息
      - 撤回群聊消息
      - **事件**
        - 群消息（全量模式）
        - 群@机器人消息
    - **频道消息**
      - 发送子频道消息
      - 内嵌格式
      - 撤回子频道消息
      - 频道私信
      - 表情表态
      - 频道消息事件
    - **消息类型**
      - 消息类型
      - Markdown 消息
      - **富媒体**
        - 富媒体消息概述
        - 单聊富媒体上传
        - 单聊富媒体预上传
        - 单聊分片上传完成
        - 群聊富媒体上传
        - 群聊富媒体预上传
        - 群聊分片上传完成
    - **消息交互**
      - 消息交互概述
      - **按钮互动**
        - 互动事件
        - 互动事件响应
      - 文本交互
  - **机器人**
    - 获取机器人详情
    - 获取机器人加入的频道列表
    - 生成分享链接
    - **自定义菜单与指令面板**
      - 查询全局自定义菜单
      - 修改全局自定义菜单
      - 查询指令面板列表
      - 创建指令面板
      - 查询指令面板详情
      - 修改指令面板
      - 删除指令面板
      - 修改指令面板关联对象
    - **事件**
      - 用户添加好友
      - 用户删除好友
      - 单聊消息接收开启
      - 单聊消息接收关闭
  - **群聊管理**
    - **接口**
      - 获取群基本信息
      - 获取机器人群内状态
      - 入群申请列表拉取
      - 入群申请审批
      - 查询群禁言状态
      - 设置群成员禁言
      - **入群自动审批**
        - 查询入群自动审批策略列表
        - 创建入群自动审批策略
        - 修改入群自动审批策略
        - 删除入群自动审批策略
        - 执行入群自动审批策略
        - 修改入群自动审批策略的白名单号码
      - **群成员管理**
        - 获取群成员列表
        - 获取群成员信息
        - 群成员批量移除
        - 群黑名单查询
        - 群黑名单操作
    - **事件**
      - 机器人加入群聊
      - 机器人退出群聊
      - 群聊消息接收开启
      - 群聊消息接收关闭
      - 群成员加入
      - 群成员退出
      - 用户申请加群事件
  - **频道管理**
    - **事件**
      - 频道创建
      - 频道更新
      - 频道解散
      - 子频道创建
      - 子频道更新
      - 子频道删除
    - **频道管理**
      - 获取频道详情
      - 获取子频道列表
      - 创建子频道
      - 获取子频道详情
      - 修改子频道
      - 删除子频道
    - **频道成员**
      - 获取子频道在线成员数
      - 获取频道成员列表
      - 获取频道身份组成员列表
      - 获取频道成员详情
      - 删除频道成员
      - 频道成员事件
      - 音视频/直播子频道成员进出事件
    - **身份组与权限管理**
      - 获取频道身份组列表
      - 创建频道身份组
      - 修改频道身份组
      - 删除频道身份组
      - 创建频道身份组成员
      - 删除频道身份组成员
      - 获取子频道用户权限
      - 修改子频道用户权限
      - 获取子频道身份组权限
      - 修改子频道身份组权限
    - **接口授权管理**
      - 获取机器人在频道可用权限列表
      - 发送机器人在频道接口权限的授权链接
    - **发言管理**
      - 获取频道消息频率的设置详情
      - 频道全员禁言
      - 频道指定成员禁言
      - 频道批量成员禁言
    - **内容管理**
      - 创建频道公告
      - 删除频道公告
      - 添加精华消息
      - 删除精华消息
      - 获取精华消息
      - 获取频道日程列表
      - 获取日程详情
      - 创建日程
      - 修改日程
      - 删除日程
      - 音频控制
      - 机器人上麦
      - 机器人下麦
      - 获取帖子列表
      - 获取帖子详情
      - 发表帖子
      - 删除帖子
      - 论坛事件对象(ForumEvent)
      - 开放论坛事件对象(OpenForumEvent)
    - **小程序相关**
      - 开放数据域加密
      - 获取频道和当前人信息
- **变更记录**
  - 变更记录

---

## 起步指南

# 启动接入
 
## 账号注册
 
QQ 机器人：一个机器人可以被添加到 `群聊/频道` 内互动对话，QQ 用户也可以直接跟机器人 `单独对话`。
 
注册地址：[QQ 开放平台官网  (opens new window)](https://q.qq.com/#/)
 
## 接入票据
 
注册创建机器人后：获得的开发机器人接入票据 `AppID` `AppSecret`
         
| 名称 | 描述 | 备注 |
| --- | --- | --- |
| AppID | 机器人 ID | 必须使用 |
| AppSecret | 机器人密钥 | 用于请求签名的密钥 |
 
Token 的鉴权方式已废弃，请使用更安全的 `Access Token` 鉴权方式。
 
开发过程中如遇任何问题，可联系 QQ 机器人反馈助手反馈。
  
## SDK DEMO
 
快速搭建机器人服务端可参考以下 SDK DEMO。（SDK 仅提供接入参考，详情能力以官方文档能力描述为准）
 
Go: [botgo  (opens new window)](https://github.com/tencent-connect/botgo)
 
Python: [botpy  (opens new window)](https://github.com/tencent-connect/botpy)
 
NodeJs: [bot-node-sdk  (opens new window)](https://github.com/tencent-connect/bot-node-sdk)

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/dev-prepare/getting-started.html>


---

# 获取访问凭证
 
QQ 机器人开放平台提供以下类型的访问凭证：
      
| 凭证类型 | 是否需要用户授权 | 说明 |
| --- | --- | --- |
| access_token | 否 | 机器人身份调用 API 时使用的凭证，可读写的数据范围由机器人的权限范围决定。适用于机器人主动发消息、管理群聊等场景。 |
 
## 获取 access_token
 
### 请求
     
| 基本 |  |
| --- | --- |
| HTTP URL | https://api.bot.qq.com/app/getAppAccessToken |
| HTTP Method | POST |
 
### 请求参数
            
| 属性 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| appId | string | 是 | 在开放平台管理端上获得。 |
| clientSecret | string | 是 | 在开放平台管理端上获得。 |
 
### 返回参数
         
| 属性 | 类型 | 说明 |
| --- | --- | --- |
| access_token | string | 获取到的凭证。 |
| expires_in | number | 凭证有效时间，单位：秒。目前是 7200 秒之内的值。 |
 
### 错误码
               
| 错误码 | 错误信息 | 排查指南 |
| --- | --- | --- |
| 100001 | Too many requests | 请求过于频繁，请降低调用频率后重试 |
| 100007 | appid invalid | AppID 无效，或机器人状态不正常（被封禁或已删除），请检查 AppID 是否正确以及机器人状态 |
| 100016 | invalid appid or secret | AppID 或 ClientSecret 不正确，请检查传入的 appId 和 clientSecret 是否与开放平台管理端一致 |
| 10004 | 机器人不存在 | AppID 对应的机器人不存在，请确认 AppID 是否正确 |
 
### 调用示例
 

```shell
curl --location 'https://api.bot.qq.com/app/getAppAccessToken' \
--header 'Content-Type: application/json' \
--data '{
  "appId": "APPID",
  "clientSecret": "CLIENTSECRET"
}'
```

### 返回示例
 

```json
{
  "access_token": "ACCESS_TOKEN",
  "expires_in": "7200"
}
```

## 凭证有效期与刷新
 
目前 `access_token` 生命周期默认 `7200` 秒（2 小时），开发者需要在过期后自行刷新 `access_token`，保证调用链路权限正常。
 - 每次请求不会刷新新的 `access_token`，在有效期内重复获取会返回相同的值
 - 在上一个 `access_token` 接近过期时间 `60` 秒内，获取 `access_token` 时，会获得一个新的 `access_token`，老的 `access_token` 在这个 `60` 秒内仍然有效
 - 建议开发者在服务端设置定时刷新凭证的业务逻辑，以防止过期

 
## 使用访问凭证
 
在每次调用 OpenAPI 开放接口时，需要在 HTTP 请求头中引入 `access_token` 进行调用权限验证。
 
请求头：
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| Authorization | string | 是 | 格式值：`QQBot ACCESS_TOKEN` |
 
示例：
 

```shell
curl --location 'https://api.bot.qq.com/users/@me' \
--header 'Authorization: QQBot ACCESS_TOKEN'
```

> **注意**
> 注意 为了安全考虑，请勿在应用前端使用访问凭证。请在应用服务端发起 API 访问请求。

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/dev-prepare/access-token.html>


---

# API 调用指南
 
QQ 机器人开放平台提供了基于 HTTPS 协议的 OpenAPI 接口，开发者可以通过这些接口实现消息收发、群聊管理、频道管理等功能。
 
## 调用方式
 
### 统一请求地址
 

```
https://api.bot.qq.com
```

### 鉴权方式
 
调用 API 时，需要将 access_token 放入请求 Header 中：
 

```
Authorization: QQBot {ACCESS_TOKEN}
```

### 请求示例
 
以发送单聊消息为例：
 

```shell
curl -X POST 'https://api.bot.qq.com/v2/users/A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4/messages' \
-H 'Authorization: QQBot {ACCESS_TOKEN}' \
-H 'Content-Type: application/json; charset=utf-8' \
-d '{
  "content": "Hello World",
  "msg_type": 0,
  "msg_id": "previous_msg_id"
}'
```

### 响应结构
 
API 调用成功时，响应体直接返回业务数据；调用失败时，响应体包含 `err_code`、`message` 等错误信息：
 - err_code：错误码。成功时为 0
 - message：错误信息
 - trace_id：链路追踪 ID，用于问题排查

 
成功响应示例：
 

```json
{
  "id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "timestamp": "2026-07-21T10:30:00+08:00"
}
```

失败响应示例：
 

```json
{
  "err_code": 40034005,
  "message": "回复消息msg_id已过期",
  "trace_id": "4a8a61565b909f199b1ec169fdd6f49e"
}
```

> **注意**
> 注意 请不要依据 `message` 来判定一个请求是否失败，`message` 可能会随时调整，建议根据 `err_code` 判断请求是否失败。
 
## 唯一身份机制
 
不同的 `bot(AppID)` 获取到的用户 `openid`，群 `openid`，频道 `openid` 均不相同，若跨业务有关联用户身份需求，后续提供跨 `AppID` 绑定后，使用类似 `unionid` 的机制打通身份。
 - 不同 `bot` 在单聊场景，获取到的用户唯一识别 `openid` 不一样，称为 `user_openid`
- 不同 `bot` 在群聊场景，获取到的群唯一识别号 `openid` 不一样，称为 `group_openid`
- `bot` 在群聊场景，获取到用户在群内的唯一识别号，称为 `member_openid`

> **提示**
> 举例
 
## 全链路追踪
 
平台的链路追踪 `TraceID` 可通过两种方式获取：
 - HTTP 响应头：`X-Tps-trace-ID` 字段
 - 响应 Body：返回体中的 `trace_id` 字段

 
如果开发者有无法自行定位的问题，需要找平台协助时，可提取该 ID 提交给平台方，方便查询相关日志。
 
## OpenAPI 错误码
 
错误码分为两部分：
 - HTTP 状态码
 - HTTP Body 返回的 JSON 中的 `err_code`

 
### HTTP 状态码
                    
| 值 | 含义 |
| --- | --- |
| 200 | 成功 |
| 204 | 成功，但是无包体，一般用于删除操作 |
| 201, 202 | 异步操作成功，虽然说成功，但是会返回一个 error body，需要特殊处理 |
| 401 | 认证失败 |
| 404 | 未找到 API |
| 405 | HTTP Method 不允许 |
| 429 | 频率限制 |
| 500 | 处理失败 |
| 504 | 处理失败 |
 
### 公共错误码
 
> 以下为所有接口通用的公共错误码。各接口特有的错误码请查阅具体接口文档中的「错误码」章节。
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
| 值 | 含义 |
| --- | --- |
| 10001 | UnknownAccount 账号异常 |
| 10003 | UnknownChannel 子频道异常 |
| 10004 | UnknownGuild 频道异常 |
| 11281 | ErrorCheckAdminFailed 检查是否是管理员失败，系统错误，一般重试一次会好，最多只能重试一次 |
| 11282 | ErrorCheckAdminNotPass 检查是否是管理员未通过，该接口需要管理员权限，但是用户在添加机器人的时候并未授予该权限，属于逻辑错误，可以提示用户进行授权 |
| 11251 | ErrorWrongAppid 参数中的 appid 错误，开发者填的 token 错误，appid 无法识别 |
| 11252 | ErrorCheckAppPrivilegeFailed 检查应用权限失败，系统错误，一般重试一次会好，最多只能重试一次 |
| 11253 | ErrorCheckAppPrivilegeNotPass 检查应用权限不通过，该机器人应用未获得调用该接口的权限，需要向平台申请 |
| 11254 | ErrorInterfaceForbidden 应用接口被封禁，该机器人虽然获得了该接口权限，但是被封禁了 |
| 11261 | ErrorWrongAppid 参数中缺少 appid，同 11251 |
| 11262 | ErrorCheckRobot 当前接口不支持使用机器人 Bot Token 调用 |
| 11263 | ErrorCheckGuildAuth 检查频道权限失败，系统错误，一般重试一次会好，最多只能重试一次 |
| 11264 | ErrorGuildAuthNotPass 检查小站权限未通过，管理员添加机器人的时候未授予该接口权限，属于逻辑错误，可提示用户进行授权，如果已经给予授权，请检查传递的 guild id 是否正确 |
| 11265 | ErrorRobotHasBaned 机器人已经被封禁 |
| 11241 | ErrorWrongToken 参数中缺少 token |
| 11242 | ErrorCheckTokenFailed 校验 token 失败，系统错误，一般重试一次会好，最多只能重试一次 |
| 11243 | ErrorCheckTokenNotPass 校验 token 未通过，用户填充的 token 错误，需要开发者进行检查 |
| 11273 | ErrorCheckUserAuth 检查用户权限失败，当前接口不支持使用 Bearer Token 调用 |
| 11274 | ErrorUserAuthNotPass 检查用户权限未通过，用户 OAuth 授权时未给与该接口权限，可提示用户重新进行授权 |
| 11275 | ErrorWrongAppid 无 appid，同 11251 |
| 11301 | ErrorGetHTTPHeader HTTP Header 无效 |
| 11302 | ErrorGetHeaderUIN HTTP Header 无效 |
| 11303 | ErrorGetNick 获取昵称失败 |
| 11304 | ErrorGetAvatar 获取头像失败 |
| 11305 | ErrorGetGuildID 获取频道 ID 失败 |
| 11306 | ErrorGetGuildInfo 获取频道信息失败 |
| 12001 | ReplaceIDFailed 替换 id 失败 |
| 12002 | RequestInvalid 请求体错误 |
| 12003 | ResponseInvalid 回包错误 |
| 20028 | ChannelHitWriteRateLimit 子频道消息触发限频 |
| 50006 | CannotSendEmptyMessage 消息为空 |
| 50035 | InvalidFormBody form-data 内容异常 |
| 50037 | 带有 markdown 消息只支持 markdown 或者 keyboard 组合 |
| 50038 | 非同频道同子频道 |
| 50039 | 获取消息失败 |
| 50040 | 消息模版类型错误 |
| 50041 | markdown 有空值 |
| 50042 | markdown 列表长达最大值 |
| 50043 | guild_id 转换失败 |
| 50045 | 不能回复机器人自己产生的消息 |
| 50046 | 非 at 机器人消息 |
| 50047 | 非机器人产生的消息 或者 at 机器人消息 |
| 50048 | message id 不能为空 |
| 50049 | 只能修改含有 keyboard 元素的消息 |
| 50050 | 修改消息时，keyboard 元素不能为空 |
| 50051 | 只能修改机器人自己发送的消息 |
| 50053 | 修改消息错误 |
| 50054 | markdown 模版参数错误 |
| 50055 | 无效的 markdown content |
| 50056 | 不允许发送 markdown content |
| 50057 | markdown 参数只支持原生语法或者模版二选一 |
| 301000~301099 | 子频道权限错误 |
| 301000 | 参数错误 |
| 301001 | 查询频道信息错误 |
| 301002 | 查询子频道权限错误 |
| 301003 | 修改子频道权限错误 |
| 301004 | 私密子频道关联的人数到达上限 |
| 301005 | 调用 Rpc 服务失败 |
| 301006 | 非群成员没有查询权限 |
| 301007 | 参数超过数量限制 |
| 302000 | 参数错误 |
| 302001 | 查询频道信息错误 |
| 302002 | 查询日程列表失败 |
| 302003 | 查询日程失败 |
| 302004 | 修改日程失败 |
| 302005 | 删除日程失败 |
| 302006 | 创建日程失败 |
| 302007 | 获取创建者信息失败 |
| 302008 | 子频道 ID 不能为空 |
| 302009 | 频道系统错误，请联系客服 |
| 302010 | 暂无修改日程权限 |
| 302011 | 日程活动已被删除 |
| 302012 | 每天只能创建 10 个日程，明天再来吧！ |
| 302013 | 创建日程触发安全打击 |
| 302014 | 日程持续时间超过 7 天，请重新选择 |
| 302015 | 开始时间不能早于当前时间 |
| 302016 | 结束时间不能早于开始时间 |
| 302017 | Schedule 对象为空 |
| 302018 | 参数类型转换失败 |
| 302019 | 调用下游失败，请联系客服 |
| 302020 | 日程内容违规、账号违规 |
| 302021 | 频道内当日新增活动达上限 |
| 302022 | 不能绑定非当前频道的子频道 |
| 302023 | 开始时跳转不可绑定日程子频道 |
| 302024 | 绑定的子频道不存在 |
| 304003 | URL_NOT_ALLOWED url 未报备 |
| 304004 | ARK_NOT_ALLOWED 没有发 ark 消息权限 |
| 304005 | EMBED_LIMIT embed 长度超限 |
| 304006 | SERVER_CONFIG 后台配置错误 |
| 304007 | GET_GUILD 查询频道异常 |
| 304008 | GET_BOT 查询机器人异常 |
| 304009 | GET_CHENNAL 查询子频道异常 |
| 304010 | CHANGE_IMAGE_URL 图片转存错误 |
| 304011 | NO_TEMPLATE 模板不存在 |
| 304012 | GET_TEMPLATE 取模板错误 |
| 304014 | TEMPLATE_PRIVILEGE 没有模板权限 |
| 304016 | SEND_ERROR 发消息错误 |
| 304017 | UPLOAD_IMAGE 图片上传错误 |
| 304018 | SESSION_NOT_EXIST 机器人没连上 gateway |
| 304019 | AT_EVERYONE_TIMES @全体成员 次数超限 |
| 304020 | FILE_SIZE 文件大小超限 |
| 304021 | GET_FILE 下载文件错误 |
| 304022 | PUSH_TIME 推送消息时间限制 |
| 304023 | PUSH_MSG_ASYNC_OK 推送消息异步调用成功，等待人工审核 |
| 304024 | REPLY_MSG_ASYNC_OK 回复消息异步调用成功，等待人工审核 |
| 304025 | BEAT 消息被打击 |
| 304026 | MSG_ID 回复的消息 id 错误 |
| 304027 | MSG_EXPIRE 回复的消息过期 |
| 304028 | MSG_PROTECT 非 At 当前用户的消息不允许回复 |
| 304029 | CORPUS_ERROR 调语料服务错误 |
| 304030 | CORPUS_NOT_MATCH 语料不匹配 |
| 304031 | 私信已关闭 |
| 304032 | 私信不存在 |
| 304033 | 拉私信错误 |
| 304034 | 不是私信成员 |
| 304035 | 推送消息超过子频道数量限制 |
| 304036 | 没有 markdown 模板的权限 |
| 304037 | 没有发消息按钮组件的权限 |
| 304038 | 消息按钮组件不存在 |
| 304039 | 消息按钮组件解析错误 |
| 304040 | 消息按钮组件消息内容错误 |
| 304044 | 取消息设置错误 |
| 304045 | 子频道主动消息数限频 |
| 304046 | 不允许在此子频道发主动消息 |
| 304047 | 主动消息推送超过限制的子频道数 |
| 304048 | 不允许在此频道发主动消息 |
| 304049 | 私信主动消息数限频 |
| 304050 | 私信主动消息总量限频 |
| 304051 | 消息设置引导请求构造错误 |
| 304052 | 发消息设置引导超频 |
| 306001 | param invalid 撤回消息参数错误 |
| 306002 | msgid error 消息 id 错误 |
| 306003 | fail to get message 获取消息错误(可重试) |
| 306004 | no permission to delete message 没有撤回此消息的权限 |
| 306005 | retract message error 消息撤回失败(可重试) |
| 306006 | fail to get channel 获取子频道失败(可重试) |
| 501000~501999 | 公告错误 |
| 501001 | 参数校验失败 |
| 501002 | 创建子频道公告失败(可重试) |
| 501003 | 删除子频道公告失败(可重试) |
| 501004 | 获取频道信息失败(可重试) |
| 501005 | MessageID 错误 |
| 501006 | 创建频道全局公告失败(可重试) |
| 501007 | 删除频道全局公告失败(可重试) |
| 501008 | MessageID 不存在 |
| 501009 | MessageID 解析失败 |
| 501010 | 此条消息非子频道内消息 |
| 501011 | 创建精华消息失败(可重试) |
| 501012 | 删除精华消息失败(可重试) |
| 501013 | 精华消息超过最大数量 |
| 501014 | 安全打击 |
| 501015 | 此消息不允许设置 |
| 501016 | 频道公告子频道推荐超过最大数量 |
| 501017 | 非频道主或管理员 |
| 501018 | 推荐子频道 ID 无效 |
| 501019 | 公告类型错误 |
| 501020 | 创建推荐子频道类型频道公告失败 |
| 502000~502099 | 禁言相关错误 |
| 502001 | 频道 id 无效 |
| 502002 | 频道 id 为空 |
| 502003 | 用户 id 无效 |
| 502004 | 用户 id 为空 |
| 502005 | timestamp 不合法 |
| 502006 | timestamp 无效 |
| 502007 | 参数转换错误 |
| 502008 | rpc 调用失败 |
| 502009 | 安全打击 |
| 502010 | 请求头错误 |
| 503001 | 频道 id 无效 |
| 503002 | 频道 id 为空 |
| 503003 | 获取子频道信息失败 |
| 503004 | 超出发布帖子的频次限制 |
| 503005 | 帖子标题为空 |
| 503006 | 帖子内容为空 |
| 503007 | 帖子ID为空 |
| 503008 | 获取X-Uin失败 |
| 503009 | 帖子ID无效或不合法 |
| 503010 | 通过Uin获取TinyID失败 |
| 503011 | 帖子ID里面的时间戳无效或不合法 |
| 503012 | 帖子不存在或已删除 |
| 503013 | 服务器内部错误 |
| 503014 | 帖子JSON内容解析失败 |
| 503015 | 帖子内容转换失败 |
| 503016 | 链接数量超过限制 |
| 503017 | 字数超过限制 |
| 503018 | 图片数量超过限制 |
| 503019 | 视频数量超过限制 |
| 503020 | 标题长度超过限制 |
| 504000~504999 | 消息频率相关错误 |
| 504001 | 请求参数无效错误 |
| 504002 | 获取 HTTP 头失败 |
| 504003 | 获取 BOT UIN 错误 |
| 504004 | 获取消息频率设置信息错误 |
| 610000-619999 | 频道权限错误 |
| 610001 | 获取频道 ID 失败 |
| 610002 | 获取 HTTP 头失败 |
| 610003 | 获取机器人号码失败 |
| 610004 | 获取机器人角色失败 |
| 610005 | 获取机器人角色内部错误 |
| 610006 | 拉取机器人权限列表失败 |
| 610007 | 机器人不在频道内 |
| 610008 | 无效参数 |
| 610009 | 获取 API 接口详情失败 |
| 610010 | API 接口已授权 |
| 610011 | 获取机器人信息失败 |
| 610012 | 限频失败 |
| 610013 | 已限频 |
| 610014 | api 授权链接发送失败 |
| 620001-629999 | 表情表态错误 |
| 620001 | 表情表态无效参数 |
| 620002 | 已经达到表情反应的类型数量上限 |
| 620003 | 已经设置过该表情表态 |
| 620004 | 没有设置过该表情表态 |
| 620005 | 没有权限设置表情表态 |
| 620006 | 操作限频 |
| 620007 | 表情表态操作失败，请重试 |
| 630001-639999 | 互动回调数据更新 |
| 630001 | 互动回调数据更新无效参数 |
| 630002 | 互动回调数据更新获取AppID失败 |
| 630003 | 互动回调数据AppID不匹配 |
| 630004 | 互动回调数据更新内部存储错误 |
| 630005 | 互动回调数据更新内部存储读取错误 |
| 630006 | 互动回调数据更新读取请求AppID失败 |
| 630007 | 互动回调数据太大 |
| 1000000~2999999 | 发消息错误 |
| 1100100 | 安全打击：消息被限频 |
| 1100101 | 安全打击：内容涉及敏感，请返回修改 |
| 1100102 | 安全打击：抱歉，暂未获得新功能体验资格 |
| 1100103 | 安全打击 |
| 1100104 | 安全打击：该群已失效或当前群已不存在 |
| 1100300 | 系统内部错误 |
| 1100301 | 调用方不是群成员 |
| 1100302 | 获取指定频道名称失败 |
| 1100303 | 主页频道非管理员不允许发消息 |
| 1100304 | @次数鉴权失败 |
| 1100305 | TinyId 转换 Uin 失败 |
| 1100306 | 非私有频道成员 |
| 1100307 | 非白名单应用子频道 |
| 1100308 | 触发频道内限频 |
| 1100499 | 其他错误 |
| 3000000~3999999 | 编辑消息错误 |
| 3300006 | 安全打击 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/dev-prepare/api-call-guide.html>


---

### 事件订阅与通知

# 通用数据结构
 
`payload` 指的是在 `webhook` 或 `websocket` 连接上传输的数据，网关的上下行消息采用的都是同一个结构，如下：
 

```json
{
  "id":"event_id",
  "op": 0,
  "d": {},
  "s": 42,
  "t": "GATEWAY_EVENT_NAME"
}
```

           
| 字段 | 描述 |
| --- | --- |
| id | 事件id |
| op | 指的是 opcode，参考连接维护 |
| s | 下行消息都会有一个序列号，标识消息的唯一性，客户端需要再发送心跳的时候，携带客户端收到的最新的 s |
| t | 代表事件类型。主要用在 op 为 0 Dispatch 的时候 |
| d | 代表事件内容，不同事件类型的事件内容格式都不同，请注意识别。主要用在 op 为 0 Dispatch 的时候 |
 
## OpCode 含义
 
所有 `opcode` 列表如下：
                                                       
| CODE | 名称 | 接入方式 | 客户端行为 | 描述 |
| --- | --- | --- | --- | --- |
| 0 | Dispatch | webhook/websocket | Receive | 服务端进行消息推送 |
| 1 | Heartbeat | websocket | Send/Receive | 客户端或服务端发送心跳 |
| 2 | Identify | websocket | Send | 客户端发送鉴权 |
| 6 | Resume | websocket | Send | 客户端恢复连接 |
| 7 | Reconnect | websocket | Receive | 服务端通知客户端重新连接 |
| 9 | Invalid Session | websocket | Receive | 当 identify 或 resume 的时候，如果参数有错，服务端会返回该消息 |
| 10 | Hello | websocket | Receive | 当客户端与网关建立 ws 连接之后，网关下发的第一条消息 |
| 11 | Heartbeat ACK | websocket | Receive/Reply | 当发送心跳成功之后，就会收到该消息 |
| 12 | HTTP Callback ACK | webhook | Reply | 仅用于 http 回调模式的回包，代表机器人收到了平台推送的数据 |
| 13 | 回调地址验证 | webhook | Receive | 开放平台对机器人服务端进行验证 |
 
客户端行为含义如下：
 - `Receive` 客户端接收到服务端 `push` 的消息
 - `Send` 客户端发送消息
 - `Reply` 客户端接收到服务端发送的消息之后的回包（HTTP 回调模式）

 
## 事件订阅 Intents
 
事件的 `intents` 是一个标记位，每一位都代表不同的事件，如果需要接收某类事件，就将该位置为 `1`。
 
每个 `intents` 位代表的是一类事件，可以使用 `websocket` 传输的数据中的 `t` 字段的值来区分。
 
事件和位移的关系如下：
 

```
GUILDS (1 << 0)
  - GUILD_CREATE           // 当机器人加入新guild时
  - GUILD_UPDATE           // 当guild资料发生变更时
  - GUILD_DELETE           // 当机器人退出guild时
  - CHANNEL_CREATE         // 当channel被创建时
  - CHANNEL_UPDATE         // 当channel被更新时
  - CHANNEL_DELETE         // 当channel被删除时

GUILD_MEMBERS (1 << 1)
  - GUILD_MEMBER_ADD       // 当成员加入时
  - GUILD_MEMBER_UPDATE    // 当成员资料变更时
  - GUILD_MEMBER_REMOVE    // 当成员被移除时

GUILD_MESSAGES (1 << 9)    // 消息事件，仅 *私域* 机器人能够设置此 intents。
  - MESSAGE_CREATE         // 发送消息事件，代表频道内的全部消息，而不只是 at 机器人的消息。内容与 AT_MESSAGE_CREATE 相同
  - MESSAGE_DELETE         // 删除（撤回）消息事件

GUILD_MESSAGE_REACTIONS (1 << 10)
  - MESSAGE_REACTION_ADD    // 为消息添加表情表态
  - MESSAGE_REACTION_REMOVE // 为消息删除表情表态

DIRECT_MESSAGE (1 << 12)
  - DIRECT_MESSAGE_CREATE   // 当收到用户发给机器人的私信消息时
  - DIRECT_MESSAGE_DELETE   // 删除（撤回）消息事件

GROUP_AND_C2C_EVENT (1 << 25)
  - C2C_MESSAGE_CREATE      // 用户单聊发消息给机器人时候
  - FRIEND_ADD              // 用户添加使用机器人
  - FRIEND_DEL              // 用户删除机器人
  - C2C_MSG_REJECT          // 用户在机器人资料卡手动关闭"主动消息"推送
  - C2C_MSG_RECEIVE         // 用户在机器人资料卡手动开启"主动消息"推送开关
  - GROUP_AT_MESSAGE_CREATE // 用户在群里@机器人时收到的消息
  - GROUP_ADD_ROBOT         // 机器人被添加到群聊
  - GROUP_DEL_ROBOT         // 机器人被移出群聊
  - GROUP_MSG_REJECT        // 群管理员主动在机器人资料页操作关闭通知
  - GROUP_MSG_RECEIVE       // 群管理员主动在机器人资料页操作开启通知

INTERACTION (1 << 26)
  - INTERACTION_CREATE     // 互动事件创建时

MESSAGE_AUDIT (1 << 27)
  - MESSAGE_AUDIT_PASS     // 消息审核通过
  - MESSAGE_AUDIT_REJECT   // 消息审核不通过

FORUMS_EVENT (1 << 28)  // 论坛事件，仅 *私域* 机器人能够设置此 intents。
  - FORUM_THREAD_CREATE     // 当用户创建主题时
  - FORUM_THREAD_UPDATE     // 当用户更新主题时
  - FORUM_THREAD_DELETE     // 当用户删除主题时
  - FORUM_POST_CREATE       // 当用户创建帖子时
  - FORUM_POST_DELETE       // 当用户删除帖子时
  - FORUM_REPLY_CREATE      // 当用户回复评论时
  - FORUM_REPLY_DELETE      // 当用户回复评论时
  - FORUM_PUBLISH_AUDIT_RESULT      // 当用户发表审核通过时

AUDIO_ACTION (1 << 29)
  - AUDIO_START             // 音频开始播放时
  - AUDIO_FINISH            // 音频播放结束时
  - AUDIO_ON_MIC            // 上麦时
  - AUDIO_OFF_MIC           // 下麦时

PUBLIC_GUILD_MESSAGES (1 << 30) // 消息事件，此为公域的消息事件
  - AT_MESSAGE_CREATE       // 当收到@机器人的消息时
  - PUBLIC_MESSAGE_DELETE   // 当频道的消息被删除时
```

### 举例
 
如开发者需要接收用户 at 机器人的消息，那么就需要在 `intents` 中设置接收 `PUBLIC_GUILD_MESSAGES`。则需要先计算 `1 << 30` 的值。然后与 `0` 做位或操作，得到最终需要传递的 `intents`。
 
如果涉及到多个事件类型的接收，则需要将多个结果做位或操作，如：`0|1<<30|1<<1` 代表订阅 `PUBLIC_GUILD_MESSAGES` 和 `GUILD_MEMBERS` 这两类事件。
 
### 权限
 
事件类型的订阅，是有权限控制的，除了 `GUILDS`，`PUBLIC_GUILD_MESSAGES`，`GUILD_MEMBERS` 事件是基础的事件，默认有权限订阅之外，其他的特殊事件，都需要经过申请才能够使用，如果在鉴权的时候传递了无权限的 `intents`，`websocket` 会报错，并直接关闭连接。请开发者注意订阅事件的范围需要控制在自己所需要的范围之内。
 
如果拥有的某个特殊事件类型的权限被取消，则在当前连接上不会报错，但是将不会收到对应的事件类型，如果重新连接，则报错，所以如果开发者的事件类型权限被取消，请及时调整监听事件代码，避免报错导致的无法连接。

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/dev-prepare/event-emit/payload.html>


---

# Webhook 方式
 
QQ 机器人开放平台支持通过使用 HTTP 接口接收事件。开发者可通过[管理端  (opens new window)](https://q.qq.com/qqbot/#/developer/webhook-setting)设定回调地址，监听事件等。
 
目前回调地址允许配置的端口号为：80、443、8080、8443。
 
## 签名校验
 
机器人服务端需要对回调请求进行签名验证以保证数据没有被篡改过。[签名算法](/wiki/develop/api-v2/dev-prepare/interface-framework/sign.html)
 
## 回调地址及事件监听配置
 
开发者需要提供一个 HTTPS 回调地址。并选定监听的事件类型。开放平台会将事件通过回调的方式推送给机器人。
 ![event_subscription](https://qq-ai.cdn-go.cn/web/bot-docs/-/v1.28.0/assets/img/event_subscription.fa237046.png) 
配置回调地址后，开放平台会对回调地址进行验证：
 - 请求结构(Payload.d)

      
| 字段 | 描述 |
| --- | --- |
| plain_token | 需要计算签名的字符串 |
| event_ts | 计算签名使用时间戳 |
 - 返回结果

      
| 字段 | 描述 |
| --- | --- |
| plain_token | 需要计算签名的字符串 |
| signature | 签名 |
 
计算过程如下(golang)：
 

```go
func handleValidation(rw http.ResponseWriter, r *http.Request, botSecret string) {
	httpBody, err := io.ReadAll(r.Body)
	if err != nil {
		log.Println("read http body err", err)
		return
	}
	payload := &Payload{}
	if err = json.Unmarshal(httpBody, payload); err != nil {
		log.Println("parse http payload err", err)
		return
	}
	validationPayload := &ValidationRequest{}
	if 	err = json.Unmarshal(payload.Data, validationPayload);err != nil {
		log.Println("parse http payload failed:", err)
		return
	}
	seed := botSecret
	for len(seed) < ed25519.SeedSize {
		seed = strings.Repeat(seed, 2)
	}
	seed = seed[:ed25519.SeedSize]
	reader := strings.NewReader(seed)
	// GenerateKey 方法会返回公钥、私钥，这里只需要私钥进行签名生成不需要返回公钥
	_, privateKey, err := ed25519.GenerateKey(reader)
	if err != nil {
		log.Println("ed25519 generate key failed:", err)
		return
	}
	var msg bytes.Buffer
	msg.WriteString(validationPayload.EventTs)
	msg.WriteString(validationPayload.PlainToken)
	signature := hex.EncodeToString(ed25519.Sign(privateKey, msg.Bytes()))
	if err != nil {
		log.Println("generate signature failed:", err)
		return
	}
	rspBytes, err := json.Marshal(
		&ValidationResponse{
			PlainToken: validationPayload.PlainToken,
			Signature:  signature,
		})
	if err != nil {
		log.Println("handle validation failed:", err)
		return
	}
	rw.Write(rspBytes)
}
```

例如机器人账号
 

```
appid: 11111111
secret: DG5g3B4j9X2KOErG
```

回调验证请求：
 

```
headers: User-Agent:[QQBot-Callback] X-Bot-Appid:[11111111]
body: {"d":{"plain_token":"Arq0D5A61EgUu4OxUvOp","event_ts":"1725442341"},"op":13},
```

机器人应返回：
 

```
body: {"plain_token": "Arq0D5A61EgUu4OxUvOp","signature": "87befc99c42c651b3aac0278e71ada338433ae26fcb24307bdc5ad38c1adc2d01bcfcadc0842edac85e85205028a1132afe09280305f13aa6909ffc2d652c706"}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/dev-prepare/event-emit/webhook.html>


---

# WebSocket 方式
 
## 发起连接到 Gateway
 
第一步先调用 [获取通用WSS 接入点](/wiki/develop/api-v2/openapi/wss/url_get.html) 或 [获取带分片WSS 接入点](/wiki/develop/api-v2/openapi/wss/shard_url_get.html) 接口获取网关地址。
 
会得到一个类似下面这样的地址：
 

```
wss://api.bot.qq.com/websocket/
```

然后进行 `websocket` 长连接建立，一旦连接成功，就会返回 OpCode 10 Hello 消息。这个消息主要的内容是心跳周期，单位毫秒(milliseconds)，如下：
 

```json
{
  "op": 10,
  "d": {
    "heartbeat_interval": 45000
  }
}
```

## 登录鉴权获得 Session
 
`websocket` 长连接建立之后，需要进行登录鉴权，登录鉴权成功后会获得一个 session 会话 id，只有登录成功后，QQ 后台才会下发事件通知。
 
发送一个 OpCode 2 Identify 消息，`payload` 如下：
 

```json
{
  "op": 2,
  "d": {
    "token": "token string",
    "intents": 513,
    "shard": [0, 4],
    "properties": {
      "$os": "linux",
      "$browser": "my_library",
      "$device": "my_library"
    }
  }
}
```

         
| 字段 | 描述 |
| --- | --- |
| token | 格式为 "QQBot {AccessToken}" |
| intents | 是此次连接所需要接收的事件，具体可参考 [事件订阅 Intents](/wiki/develop/api-v2/dev-prepare/event-emit/payload.html#事件订阅-intents) |
| shard | 考虑到开发者事件接收时可以实现负载均衡，QQ 提供了分片逻辑，事件通知会落在不同的分片上，该参数是个拥有两个元素的数组。例如：`[0,4]`，代表分为四个片，当前链接是第 0 个片，业务稍后应该继续建立 `shard` 为 `[1,4]`, `[2,4]`, `[3,4]` 的链接，才能完整接收事件，更多详细的内容可以参考 Shard 机制。若无需分片，使用 `[0, 1]` 即可。 |
| properties | 目前无实际作用，可以按照自己的实际情况填写，也可以留空 |
 
鉴权成功之后，QQ 后台会下发一个 Ready Event，`payload` 如下：
 

```json
{
  "op": 0,
  "s": 1,
  "t": "READY",
  "d": {
    "version": 1,
    "session_id": "082ee18c-0be3-491b-9d8b-fbd95c51673a",
    "user": {
      "id": "6158788878435714165",
      "username": "群pro测试机器人",
      "bot": true
    },
    "shard": [0, 0]
  }
}
```

## 发送心跳 Ack
 
鉴权成功之后，就需要按照周期进行心跳发送。d 为客户端收到的最新的消息的 s，如果是首次连接，d 为传 null，`payload` 如下：
 

```json
{
  "op": 1,
  "d": 251
}
```

心跳发送成功之后会收到 OpCode 11 Heartbeat ACK 消息，`payload` 如下：
 

```json
{
  "op": 11
}
```

## 恢复登录态 Session
 
有很多原因可能会导致 `websocket` 长连接断开，断开之后短时间内重连会补发中间遗漏的事件，以保障业务逻辑的正确性。断开重连 gateway 后不需要发送重新登录 OpCode 2 Identify 请求。在连接到 `Gateway` 之后，需要发送 OpCode 6 Resume 消息，`payload` 如下：
 

```json
{
  "op": 6,
  "d": {
    "token": "my_token",
    "session_id": "session_id_i_stored",
    "seq": 1337
  }
}
```

其中 `seq` 指的是在接收事件时候的 `s` 字段，我们推荐开发者在处理过事件之后记录下 `s` 这样可以在 `resume` 的时候传递给 `websocket`，`websocket` 会自动补发这个 seq 之后的事件。
 
恢复成功之后，就开始补发遗漏事件，所有事件补发完成之后，会下发一个 `Resumed Event`，`payload` 如下：
 

```json
{
  "op": 0,
  "s": 2002,
  "t": "RESUMED",
  "d": ""
}
```

## 分片连接 LoadBalance
 
随着 bot 的增长并被添加到越来越多的频道中，事件越来越多，业务有必要对事件进行水平分割，实现负载均衡。机器人网关实现了一种用户可控制的分片方法，该方法允许跨多个网关连接拆分事件。分片完全由用户控制，并且不需要在单独的连接之间进行状态共享。
 
要在连接上启用分片，需要在建立连接的时候指定分片参数，具体参考 [gateway](/wiki/develop/api-v2/dev-prepare/interface-framework/reference.html)
 
### 获得合适的分片数
 
使用 [/gateway/bot](/wiki/develop/api-v2/openapi/wss/shard_url_get.html) 接口获取网关地址的时候，会同时返回一个建议的 `shard` 数，及最大并发限制。
 

```json
{
  "url": "wss://api.bot.qq.com/websocket",
  "shards": 1,
  "session_start_limit": {
    "total": 1000,
    "remaining": 1000,
    "reset_after": 86400000,
    "max_concurrency": 1
  }
}
```

### 分片规则
 
分片是按照频道 id 进行哈希的，同一个频道的信息会固定从同一个链接推送。具体哈希计算规则如下：
 

```bash
shard_id = (guild_id >> 22) % num_shards
```

### 最大连接数
 
每个机器人创建的连接数不能超过 `remaining` 剩余连接数。
 
## WebSocket 错误码
                                                            
| 值 | 含义 | 是否可以重试 RESUME | 是否可以重试 IDENTIFY |
| --- | --- | --- | --- |
| 4001 | 无效的 opcode | 否 | 否 |
| 4002 | 无效的 payload | 否 | 否 |
| 4007 | seq 错误 | 否 | 是 |
| 4006 | 无效的 session id，无法继续 resume，请 identify | 否 | 是 |
| 4008 | 发送 payload 过快，请重新连接，并遵守连接后返回的频控信息 | 是 | 是 |
| 4009 | 连接过期，请重连并执行 resume 进行重新连接 | 是 | 是 |
| 4010 | 无效的 shard | 否 | 否 |
| 4011 | 连接需要处理的 guild 过多，请进行合理的分片 | 否 | 否 |
| 4012 | 无效的 version | 否 | 否 |
| 4013 | 无效的 intent | 否 | 否 |
| 4014 | intent 无权限 | 否 | 否 |
| 4900~4913 | 内部错误，请重连 | 否 | 是 |
| 4914 | 机器人已下架，只允许连接沙箱环境，请断开连接，检验当前连接环境 | 否 | 否 |
| 4915 | 机器人已封禁，不允许连接，请断开连接，申请解封后再连接 | 否 | 否 |
 
针对 WebSocket 错误码的简单处理逻辑：
 - 4009 可以重新发起 resume
 - 4914，4915 不可以连接，请联系官方解封
 - 其他错误，请重新发起 identify

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/dev-prepare/event-emit/websocket.html>


---

## 服务端接口

### 消息收发

# 消息收发概述
 
机器人可在 QQ 单聊、群聊、频道三种场景下收发消息。本页介绍基础概念与通用规则，具体接口与事件请参考对应子分类。
 
## 收发场景
            
| 场景 | 发送消息 | 接收事件 |
| --- | --- | --- |
| QQ 单聊 | [发送单聊消息](/wiki/develop/api-v2/autogen/api/v2_users_user_openid_messages.post.html) / [流式消息](/wiki/develop/api-v2/autogen/api/v2_users_user_openid_stream_messages.post.html) | [C2C_MESSAGE_CREATE](/wiki/develop/api-v2/autogen/event/c2c_message_create.html) |
| QQ 群聊 | [发送群消息](/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_messages.post.html) | [GROUP_AT_MESSAGE_CREATE](/wiki/develop/api-v2/autogen/event/group_at_message_create.html) / [GROUP_MESSAGE_CREATE](/wiki/develop/api-v2/autogen/event/group_message_create.html) |
| 频道 | [发送子频道消息](/wiki/develop/api-v2/server-inter/channel/message/send.html) / [频道私信](/wiki/develop/api-v2/server-inter/channel/message/dms.html) | [频道消息事件](/wiki/develop/api-v2/server-inter/channel/message/event.html) |
 
### 对话场景图示
 
> **提示**
> 说明 机器人可以被添加各种聊天场景下
        
| 单聊 | 群聊 | 文字子频道 | 频道私信 |
| --- | --- | --- | --- |
| ![单聊](https://qq-ai.cdn-go.cn/web/bot-docs/-/v1.28.0/assets/img/chat-single.c4f33531.jpg) | ![群聊](https://qq-ai.cdn-go.cn/web/bot-docs/-/v1.28.0/assets/img/chat-group.d5318db5.jpg) | ![文字子频道](https://qq-ai.cdn-go.cn/web/bot-docs/-/v1.28.0/assets/img/chat-text-channel.6dfae006.jpg) | ![频道私信](https://qq-ai.cdn-go.cn/web/bot-docs/-/v1.28.0/assets/img/chat-c2c.33e2820c.jpg) |
 
## 主动消息与被动消息
               
| 类型 | 特征 | 说明 |
| --- | --- | --- |
| 主动消息 | 无任何条件 | 机器人主动触达用户，用户可在客户端关闭「允许主动发送」开关，关闭后主动消息将发送失败 |
| 互动召回消息 | `is_wakeup=true` | 用户主动与机器人对话之后每个周期内可下发 1 条召回消息 |
| 被动消息（回复用户） | 携带 `msg_id` | 对用户消息的回复 |
| 被动消息（响应事件） | 携带 `event_id` | 对事件的回复 |
 
## 消息类型
 
通过 `msg_type` 指定消息内容格式：
                    
| msg_type | 类型 | 内容字段 | 发送 | 接收 |
| --- | --- | --- | --- | --- |
| 0 | 文本 | `content` | ✅ | ✅ |
| 2 | Markdown | `markdown` | ✅ | - |
| 7 | 富媒体 | `media`（需先上传文件获取 `file_info`） | ✅ | ✅ |
 
除上述之外，响应中还可能收到图片、视频、语音、表情、卡片等类型，详见 [消息类型](/wiki/develop/api-v2/server-inter/message/type/overview.html)。
 
## 富媒体消息
 
图片、视频、语音、文件等富媒体需先上传获取 `file_info`，再通过发消息接口（`msg_type=7`）携带 `media.file_info` 发送。
 
上传方式：
 - 分片上传：推荐使用，无需开发者提供公网 CDN 地址，参考 [分片上传流程](/wiki/develop/api-v2/server-inter/message/rich-media.html#分片上传（推荐）)
 - 整文件上传：[单聊上传](/wiki/develop/api-v2/server-inter/message/rich-media.html#url-上传) / [群聊上传](/wiki/develop/api-v2/server-inter/message/rich-media.html#url-上传)

 - `file_info` 有时效性（`ttl`），过期需重新上传。
- 单聊和群聊的文件上传接口不互通。

 
## 频率与时效规则
 
### 被动消息
            
| 场景 | 有效期 | 每条消息可回复次数 |
| --- | --- | --- |
| 单聊 | 60 分钟 | 4 次 |
| 群聊 | 5 分钟 | 5 次 |
| 频道 | 5 分钟 | - |
 
### 主动消息
 
主动消息与被动消息说明： QQ 用户可以在 QQ 客户端主动设置是否接收机器人发送的主动消息，如果设置了关闭，主动消息一律发送失败。
 
#### 单聊
 - 主动消息发送频率限制（HTTP接口）

                    
| 认证类型 | 场景 | Bot 维度频控 | 单关系维度频控 | 每日上限 |
| --- | --- | --- | --- | --- |
| 企业认证 | 单聊 | 10/qps | 20/qpm | 1000 条/用户 |
| 个人认证 | 单聊 | 10/qps | 20/qpm | 1000 条/用户 |
| 未认证 | 单聊 | 5/qps & 30/qpm | 20/qpm | 1000 条/用户 |
 - 互动召回消息：在用户主动与机器人对话之后，机器人在未来 30 天内可下发互动召回消息给用户（消息类型与当前机器人拥有的消息类型权限一致），每个周期内可下发一条。分别为：当天、1 - 3 天、3 - 7 天、7 - 30 天，合计：4 个周期。在发消息接口中使用 is_wakeup 字段声明使用该能力。

 
#### 群聊
 - 主动消息发送频率限制（HTTP接口）

                    
| 认证类型 | 场景 | Bot 维度频控 | 单关系维度频控 | 每日上限 |
| --- | --- | --- | --- | --- |
| 企业认证 | 群 | 60/qpm | 20/qpm | 1000 条/群 |
| 个人认证 | 群 | 60/qpm | 20/qpm | 1000 条/群 |
| 未认证 | 群 | 30/qpm | 20/qpm | 1000 条/群 |
 
#### 文字子频道
   - 主动推送消息，默认每天往每个子频道可推送的消息数是 20 条，超过会被限制。
   - 主动推送消息在每个频道中，每天可以往 2 个子频道推送消息。超过后会被限制。
  - 主动推送消息在每个频道中，每天可以往 2 个子频道推送消息。超过后会被限制。
 - 不论主动消息还是被动消息，在一个子频道中，每秒 最多可发送 5 条 消息。
 - 被动回复消息有效期为 5 分钟，超时会发送失败。
 - 发送消息接口要求机器人接口需要连接到 WebSocket 上保持在线状态
 - 有关主动消息审核，可以通过 事件订阅 Intents 中审核事件 MESSAGE_AUDIT 返回 MessageAudited 对象获取结果。

 
#### 频道私信
 - 私信场景下，每个机器人每天可以对一个用户发 2 条 主动消息。
 - 私信场景下，每个机器人每天累计可以发 200 条 主动消息。
 - 被动回复消息有效期为 5 分钟，超时会发送失败。

 
## 消息去重
 
相同 `msg_id` 可能多次推送，请结合 `msg_seq` 去重。被动回复时，相同的 `msg_id + msg_seq` 重复发送会失败，可递增 `msg_seq` 实现对同一消息的多次回复。
 
## 撤回消息
 
机器人可撤回自己发送的消息（发送超过 2 分钟不可撤回）：
 - [撤回单聊消息](/wiki/develop/api-v2/autogen/api/v2_users_user_openid_messages_message_id.delete.html)
 - [撤回群聊消息](/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_messages_message_id.delete.html)
 - [撤回频道消息](/wiki/develop/api-v2/server-inter/channel/message/recall.html) / [撤回频道私信](/wiki/develop/api-v2/server-inter/channel/message/dms.html#撤回私信)

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/message/overview.html>


---

#### 单聊消息

# 发送单聊消息
 
向指定用户发送私聊消息。
 - 被动消息有效时间 60 分钟，每个消息最多回复 4 次
   - Bot 维度（发送方）：企业认证/个人身份证认证 10/qps；未认证 5/qps 且 30/qpm
   - 单关系维度（接收方）：20/qpm，每个好友 1 天最多接收 1000 条
  - 单关系维度（接收方）：20/qpm，每个好友 1 天最多接收 1000 条
 - 互动召回消息：在用户主动与机器人对话之后，机器人在未来 30 天内可下发互动召回消息给用户（消息类型与当前机器人拥有的消息类型权限一致），每个周期内可下发一条。分别为：当天、1 - 3 天、3 - 7 天、7 - 30 天，合计：4 个周期。在发消息接口中使用 is_wakeup 字段声明使用该能力。

 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/users/{user_openid}/messages |
| HTTP Method | POST |
| 接口频率限制 | 100 QPS，包括主动、被动等所有消息类型 |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| user_openid | string | 是 | 用户 OpenID |
 
## 请求体
                                                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| msg_type | integer | 否 | 消息类型。决定哪个内容字段生效: 0=纯文本(content) 2=Markdown(markdown) 6=输入中状态（input_notify) 7=富媒体(media) |
| content | string | 否 | 文本内容。msg_type=0 时为全文 注意: 传了 markdown 后此字段必须为空 |
| markdown | MessageMarkdown | 否 | Markdown 消息。msg_type=2 时必填 注意: 填写此字段后 content/ark 必须全为空 |
| keyboard | Keyboard | 否 | 内嵌键盘。短形式只传 id，长形式传 content.rows |
| msg_id | string | 否 | 被动回复的消息 ID。从 C2C_MESSAGE_CREATE 等事件的 d.id 获取，5 分钟内有效 |
| event_id | string | 否 | 被动回复的事件 ID。从事件最外层的id获取。与 msg_id 二选一，支持事件："INTERACTION_CREATE"、"C2C_MSG_RECEIVE"、"FRIEND_ADD" |
| msg_seq | integer | 否 | 回复消息的序号，与 msg_id 联合使用，避免相同消息 id 回复重复发送，不填默认是 1。相同的 msg_id + msg_seq 重复发送会失败。 |
| media | MediaInfo | 否 | 富媒体消息。msg_type=7 时填写，file_info 来自 /v2/users/{user_openid}/files |
| message_reference | MessageReference | 否 | 引用回复。填写后以引用形式展示，关联上下文 |
| is_wakeup | boolean | 否 | 指明发送消息为互动召回消息，与 msg_id，event_id 互斥使用 |
| input_notify | InputNotify | 否 | 输入中状态，msg_type=6时使用 |
 
MessageMarkdown
                    
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| template_id | integer | 否 | 【已废弃】平台 Markdown 模板 ID。使用模板时填写，非模板不传 |
| content | string | 否 | Markdown 内容。支持的格式参考文档：[Markdown (opens new window)](https://bot.q.qq.com/wiki/develop/api-v2/server-inter/message/type/markdown.html) |
| custom_template_id | string | 否 | 【已废弃】自定义模板 ID，与 template_id 二选一 |
| force_verify_image_resource | boolean | 否 | 是否校验图片转存结果，当为true时，如果出现图片转存失败，则会返回错误，消息不会发送。 默认为false |
 
Keyboard
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| id | string | 否 | 内嵌键盘模板 ID。使用平台预设模板时填写此字段 |
| content | KeyboardContent | 否 | 自定义键盘布局。与 id 互斥，用于自定义按钮 |
 
KeyboardContent
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| rows | []Row | 否 | 按钮行列表 |
 
Row
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| buttons | []Button | 否 | 行内按钮，从左到右排列 |
 
Button
                    
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| id | string | 否 | 按钮 ID。同一键盘内唯一 |
| render_data | RenderData | 否 | 按钮渲染 |
| action | Action | 否 | 按钮点击行为 |
| group_id | string | 否 | 分组ID, 同一分组内有一个按钮操作后, 其它按钮则变灰不可点击 注意:只有当action.type = 1 时才有效 |
 
RenderData
                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| label | string | 否 | 按钮文字，最多 10 字符 |
| visited_label | string | 否 | 点击后文字，不传则保持不变 |
| style | integer | 否 | 0：灰色线框，1：蓝色线框 3: 白色背景+红色字体, 4:蓝色背景+白色字体 |
 
Action
                                        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| type | integer | 否 | 0：跳转按钮：http 或 小程序 1：回调按钮：回调后台接口, data 传给后台， 2：指令按钮：自动在输入框插入 @bot data |
| permission | Permission | 否 | 操作权限 |
| data | string | 否 | 回调数据。type=1/2 时必填 |
| click_limit | integer | 否 | 【已废弃】可点击次数限制。0=无限 |
| unsupport_tips | string | 否 | 版本过低时提示文案 |
| enter | boolean | 否 | 指令按钮可用，点击按钮后直接自动发送 data，仅单聊可用，默认 false。支持版本 8983 |
| reply | boolean | 否 | 指令按钮可用，指令是否带引用回复本消息，默认 false。支持版本 8983 |
| anchor | integer | 否 | 本字段仅在指令按钮下有效，设置后后会忽略 action.enter 配置。 设置为 1 时 ，点击按钮自动唤起启手Q选图器，其他值暂无效果。 （仅支持手机端版本 8983+ 的单聊场景，桌面端不支持） |
| modal | Modal | 否 | 用户点击二次确认操作 |
 
Permission
                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| type | integer | 否 | 0=指定用户, 1=管理员, 2=所有人 |
| specify_user_ids | []string | 否 | 有权限的用户 id 的列表 |
| specify_role_ids | []string | 否 | 有权限的身份组 id 的列表（仅频道可用） |
 
Modal
                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| content | string | 否 | 二次确认的提示文本,如果不为空则会进行二次确认. 注意:最多40个字符, 不能有URL |
| confirm_text | string | 否 | 二次确认提示确认按钮中展示的文字,可以为空, 默认为"确认" 注意:最多4个字符 |
| cancel_text | string | 否 | 二次确认提示取消按钮中的文字,可以为空,默认为"取消" 注意:最多4个字符 |
 
MediaInfo
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| file_info | string | 否 | 文件数据。来自文件上传接口返回值 |
 
MessageReference
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| message_id | string | 否 | 被引用消息 ID，例如REFIDX_xxxxxx - 非机器人发的消息，从消息事件的`MessageScene`的`ext`数组，`msg_idx`字段中获取 - 机器人自己发的消息，从发消息请求响应`ext_info.ref_idx`获取 |
 
InputNotify
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| input_type | integer | 否 | 填1 |
| input_second | integer | 否 | 状态持续时间，最长60s |
 
### 请求示例
 
文本消息 (msg_type=0)
 

```
POST /v2/users/A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4/messages
{
  "content": "你好，欢迎使用机器人助手！",
  "msg_type": 0,
  "msg_id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "msg_seq": 1
}
```

Markdown 消息 (msg_type=2)
 

```
POST /v2/users/A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4/messages
{
  "msg_type": 2,
  "markdown": {
    "content": "# 今日推荐\n\n**精选文章**\n> 知识就是力量，学习永无止境\n\n[点击查看详情](https://example.com)"
  },
  "keyboard": {
    "id": "1070001"
  },
  "msg_id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "msg_seq": 1
}
```

输入状态通知 (msg_type=6)
 

```
POST /v2/users/A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4/messages
{
  "msg_type": 6,
  "input_notify": {
    "input_type": 1,
    "input_second": 60
  },
  "msg_id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "msg_seq": 1
}
```

富媒体消息 (msg_type=7)
 

```
POST /v2/users/A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4/messages
{
  "msg_type": 7,
  "media": {
    "file_info": "AE86C5D3F0E14B238C656C0F6DD1D0479C"
  },
  "msg_id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "msg_seq": 1
}
```

## 响应
 
### 响应体
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 消息 ID，可用于后续撤回 |
| timestamp | string | 发送时间，RFC3339 东八区 |
| ext_info | MessageExtInfo | 扩展信息 |
 
MessageExtInfo
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| ref_idx | string | 引用消息索引。对应消息时间ext里的msg_idx与ref_msg_idx |
 
## 响应示例
 
消息发送成功
 

```json
{
  "id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "timestamp": "2026-07-21T10:30:00+08:00"
}
```

消息发送成功（含扩展信息）
 

```json
{
  "id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "timestamp": "2026-07-21T10:30:00+08:00",
  "ext_info": {
    "ref_idx": "REFIDX_xxxxxxxxxxxxxxxxxxxx=="
  }
}
```

### 错误码
                                                                                                                        
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 22006 | 消息类型与内容不匹配 | 请检查msg_type与content是否对应 |
| 50059 | 输入类型错误 | 请检查输入类型 |
| 304004 | 无权限使用该ARK模板 | 请先申请ARK模板权限 |
| 304061 | 消息内容无效 | 请检查消息格式是否符合要求 |
| 304062 | 订阅按钮数量达到上限 | 请减少按钮数量 |
| 304064 | 订阅消息未授权 | 请先引导用户授权订阅消息 |
| 304080 | 文件信息无效 | 请检查文件信息格式是否正确 |
| 304103 | 消息ID已过期，不能回复 | 请在收到消息后尽快回复 |
| 340067 | 获取机器人信息失败 | 请检查机器人状态 |
| 40034004 | 富媒体信息转存失败 | 请重试 |
| 40034005 | 回复消息msg_id已过期 | 请在收到消息后尽快回复 |
| 40034006 | 消息内容违规 | 请修改消息内容后重试 |
| 40034008 | markdown参数有空值 | 请确保所有Markdown参数都有值 |
| 40034009 | markdown参数有换行符 | 请移除Markdown参数中的换行符 |
| 40034010 | 模版参数中不能含有markdown语法 | 请使用纯文本参数，不要包含Markdown语法 |
| 40034011 | 无效的markdown内容 | 请检查Markdown语法是否正确 |
| 40034024 | 请求参数msg_id无效或越权 | 请检查msg_id是否正确 |
| 40034025 | 请求参数event_id无效 | 请检查event_id是否正确 |
| 40034026 | 请求参数event_id已过期 | 请在收到事件后尽快回复 |
| 40034027 | 该事件不支持回复消息 | 请确认事件类型是否支持回复 |
| 40034029 | 内联键盘行/列超限 | 请减少键盘按钮数量 |
| 40034100 | 主动消息发送超过频控限制 | 请降低发送频率或等待配额恢复 |
| 40034105 | 主动消息发送失败，无权限 | 请检查机器人权限设置 |
| 40034106 | 消息不支持该指令类型 | 请检查消息指令类型 |
| 40034108 | 指令参数长度超限 | 请缩短指令参数 |
| 40034109 | 指令参数解析失败 | 请检查指令参数格式 |
| 40034122 | 召回消息已达区间上限 | 召回消息已达上限，无法继续召回 |
| 40034123 | 不支持召回消息 | 该消息不支持召回操作 |
| 40034124 | markdown消息参数错误 | 请检查Markdown参数格式 |
| 40034127 | 无markdown模板权限 | 请先申请Markdown模板权限 |
| 40034128 | 被动回复时间或次数超限 | 请在收到事件后尽快回复 |
| 40054004 | 无好友关系 | 请先添加好友后再发送私信 |
| 40054005 | 消息被去重 | 请确保每次请求使用不同的msgseq值 |
| 40054006 | 验证好友关系失败 | 请重试 |
| 40054007 | 消息长度超限 | 请缩短消息内容 |
| 40054013 | 用户拒收消息 | 用户已拒收消息，无法发送 |
| 40054016 | 机器人已下线 | 请检查机器人状态 |
| 40054018 | 消息过长或异常 | 请缩短消息内容 |
| 50055002 | 消息发送异常，请稍后重试 | 请稍后重试 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_users_user_openid_messages.post.html>


---

# 流式发送单聊消息
 
流式分批发送单聊消息。每个分片使用相同 stream_msg_id，
index 从0递增。支持 markdown 内容格式。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/users/{user_openid}/stream_messages |
| HTTP Method | POST |
| 接口频率限制 | 50 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| user_openid | string | 是 |  |
 
## 请求体
                                            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| input_mode | string | 否 | 输入模式。 append（默认）：ContentRaw 拼接到 Pending。 replace：ContentRaw 为当前全量正文，须以上游已下发前缀 SentContent 开头；合并后 Pending 仅存未下发后缀。 |
| input_state | integer | 否 | 输入状态。1=生成中，10=生成结束 |
| index | integer | 否 | 分片序号，从0递增 |
| content_type | string | 否 | 内容格式类型 text: 文本消息 markdown：MarkDown消息 |
| content_raw | string | 否 | Markdown 格式的文本内容 |
| event_id | string | 否 | 被动回复事件ID（与 msg_id 二选一） |
| msg_id | string | 否 | 被动回复消息ID（与 event_id 二选一） |
| stream_msg_id | string | 否 | 流式消息ID。第一条由服务端生成并返回，后续分片需携带上一分片返回的 id |
| msg_seq | integer | 否 | 消息序号，用于去重 |
| is_wakeup | boolean | 否 | 是否为召回消息。true 时不校验 msg_id/event_id 有效期 |
 
### 请求示例
 
首片消息 (input_state=1, index=0)
 

```
POST /v2/users/A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4/stream_messages
{
  "input_mode": "replace",
  "input_state": 1,
  "index": 0,
  "content_type": "markdown",
  "content_raw": "正在生成回答，请稍候",
  "msg_id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "msg_seq": 1
}
```

续片消息 (input_state=1, index=1)
 

```
POST /v2/users/A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4/stream_messages
{
  "input_mode": "replace",
  "input_state": 1,
  "index": 1,
  "content_type": "markdown",
  "content_raw": "正在生成回答，请稍候。目前已完成大部分内容",
  "msg_id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "stream_msg_id": "a1b2c3d4-e5f6-7890-abcd-ef1234567890",
  "msg_seq": 1
}
```

结束片消息 (input_state=10)
 

```
POST /v2/users/A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4/stream_messages
{
  "input_mode": "replace",
  "input_state": 10,
  "index": 2,
  "content_type": "markdown",
  "content_raw": "正在生成回答，请稍候。目前已完成全部内容，以下是最终结果。",
  "msg_id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "stream_msg_id": "a1b2c3d4-e5f6-7890-abcd-ef1234567890",
  "msg_seq": 1
}
```

## 响应
 
### 响应体
               
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 消息ID。首条返回 stream_msg_id，用于后续分片 |
| timestamp | string | 消息发送时间，RFC3339 格式 |
| ext_info | MessageExtInfo | 扩展信息。ref_idx: 引用消息索引 扩展信息 |
| remain_msg_len | integer | 流式消息剩余长度（字符数） |
 
MessageExtInfo
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| ref_idx | string | 引用消息索引。对应消息时间ext里的msg_idx与ref_msg_idx |
 
## 响应示例
 
首片响应（返回 stream_msg_id）
 

```json
{
  "id": "a1b2c3d4-e5f6-7890-abcd-ef1234567890",
  "timestamp": "2026-07-21T10:00:00+08:00",
  "ext_info": {
    "ref_idx": "REFIDX_xxxxxxxxxxxxxxx=="
  }
}
```

续片/结束片响应
 

```json
{
  "id": "a1b2c3d4-e5f6-7890-abcd-ef1234567890",
  "timestamp": "2026-07-21T10:00:01+08:00",
  "ext_info": {
    "ref_idx": "REFIDX_xxxxxxxxxxxxxxx=="
  }
}
```

### 错误码
            
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 40007 | 已下发内容前缀不可修改 | 请保持已下发内容前缀一致 |
| 50001 | 服务内部错误 | 请稍后重试 |
| 50002 | 频率限制 | 请降低调用频率 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_users_user_openid_stream_messages.post.html>


---

# 撤回单聊消息
 
撤回机器人发送给当前用户的消息。发送超过 2 分钟的消息不可撤回。
成功返回 HTTP 200，无响应体。
 - 发送超出 2 分钟的消息不可撤回

 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/users/{user_openid}/messages/{message_id} |
| HTTP Method | DELETE |
| 接口频率限制 | 10 QPS |
 
## 路径参数
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| user_openid | string | 是 | 用户 OpenID |
| message_id | string | 是 | 消息 ID |
 
### 请求示例
 
示例1
 

```
DELETE /v2/users/A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4/messages/0123456789ABCDEF0123456789ABCDEF0123456789ABCDEF0123456789ABCDEF
```

## 响应
 
无
 
## 响应示例
 
示例1
 

```json
{}
```

### 错误码
               
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 306009 | 用户openid无效 | 请检查user_openid是否正确 |
| 40061001 | 请求参数无效 | 请检查请求参数格式 |
| 40061002 | 请求参数msgid无效 | 请检查msgid格式是否正确 |
| 40064004 | 已超出消息撤回时限 | 消息发送超过2分钟后不可撤回 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_users_user_openid_messages_message_id.delete.html>


---

##### 事件

# 单聊消息事件
 
用户给机器人发送单聊消息时触发。
为确保消息可达，相同 msg_id 可能重复推送，开发者需结合 msg_seq 做去重。
 
为确保消息可达，相同 msg_id 可能重复推送，需结合 message_scene.ext 中的 msg_idx 做去重。message_type 决定消息结构：0=纯文本，3=ARK卡片（ark_data 有值），103=引用消息（msg_elements 有值，message_scene.ext 含 ref_msg_idx）。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | C2C_MESSAGE_CREATE |
| Intent | GROUP_AND_C2C_EVENT (1<<25) |
 
### 事件体
                              
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 消息 ID，可用于被动回复和撤回 |
| author | User | 发送者（user_openid 有值） |
| content | string | 消息文本内容 |
| timestamp | string | 消息发送时间，RFC3339 格式 |
| message_type | integer | 消息内容类型: 0=普通文本, 3=结构化卡片, 101=并行消息, 102=聊天记录, 103=引用消息 |
| message_scene | MessageScene | 消息场景上下文（含消息索引、鉴权令牌等） |
| attachments | []MessageAttachment | 消息附件（图片、文件、语音等） |
| ark_data | ARKData | 结构化卡片消息数据（message_type=3 时有值） |
| msg_elements | []MsgElement | 消息元素列表（message_type=103 引用消息时包含被引用内容） |
 
User
                           
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 用户唯一标识（OpenID 格式） |
| username | string | 用户昵称 |
| bot | boolean | 是否为机器人 |
| union_openid | string | 跨应用统一用户 OpenID（可能为空） |
| union_user_account | string | 跨应用统一用户账号（可能为空） |
| user_openid | string | 用户 OpenID（单聊场景使用） |
| member_openid | string | 群成员 OpenID（群聊场景使用） |
| member_role | string | 群内角色。member=普通成员, admin=管理员, owner=群主 |
 
MessageScene
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| source | string | 场景来源。default=默认聊天窗口 |
| ext | []string | 扩展数据列表，key=value 格式: msg_idx=消息索引, 用于引用场景 ref_msg_idx=引用的消息索引 auth_token=鉴权令牌 |
 
MessageAttachment
                           
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| url | string | 附件下载 URL |
| filename | string | 文件名 |
| width | integer | 图片宽度（像素），非图片附件无此字段 |
| height | integer | 图片高度（像素），非图片附件无此字段 |
| size | integer | 文件大小（字节） |
| content_type | string | 附件内容类型（MIME 类型）: voice=语音消息 image/jpeg=JPEG 图片 image/png=PNG 图片 image/gif=GIF 图片 video/mp4=MP4 视频 file=群文件 |
| voice_wav_url | string | 语音消息 SILK 等转换后的 WAV 文件 URL |
| asr_refer_text | string | 语音消息 ASR 参考结果 |
 
ARKData
               
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| prompt | string | 卡片消息中的用户操作提示文本 |
| ark_type | string | 卡片消息类型标识: tuwen = 图文 H5（如快手分享链接） feed = 图文卡片（群相册、频道帖子、分享卡片） miniapp = 小程序（微信小程序、QQ 小程序、哔哩哔哩等） map = 位置卡片 contact_card = 好友名片 video_share = 视频分享 music_together = 一起听歌 |
| ark_name | string | 卡片消息类型的中文名称，如"图文 H5"、"小程序"、"图文卡片" |
| fields | object | 卡片消息字段，常见键名: tag/tags=来源标签, title=标题, desc=描述, jump_url=跳转链接, preview=预览图, source=来源名称, source_logo=来源图标, tag_icon=标签图标, nickname=昵称, avatar=头像, address=地址 |
 
MsgElement
                        
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| msg_idx | string | 消息元素在列表中的引用消息索引 |
| author | User | 该元素对应的消息发送者 |
| message_type | integer | 消息内容类型: 0=普通文本, 3=结构化卡片, 101=并行消息, 102=聊天记录, 103=引用消息 |
| content | string | 消息正文内容 |
| attachments | []MessageAttachment | 该元素携带的附件 |
| ark_data | ARKData | 结构化卡片消息数据（message_type=3 时有值） |
| msg_elements | []MsgElement | 嵌套消息元素列表（递归结构） |
 
### 事件示例
 
示例1
 

```
{
  "id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "author": {
    "id": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
    "user_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
    "union_openid": "",
    "username": "",
    "bot": false
  },
  "content": "你好，今天有什么推荐的活动吗？",
  "message_type": 0,
  "message_scene": {
    "source": "default",
    "ext": [
      "msg_idx=REFIDX_xxxxxxxxxxxxxxx=="
    ]
  },
  "timestamp": "2026-07-21T10:00:00+08:00"
}
```

示例2
 

```
{
  "id": "ROBOT1.0_yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy",
  "author": {
    "id": "B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5",
    "user_openid": "B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5",
    "union_openid": "B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5",
    "username": "",
    "bot": false
  },
  "content": "[卡片消息] 小程序\n摘要: [每日打卡]快来完成今日学习打卡",
  "message_type": 3,
  "ark_data": {
    "ark_type": "miniapp",
    "ark_name": "小程序",
    "prompt": "[每日打卡]快来完成今日学习打卡",
    "fields": {
      "title": "快来完成今日学习打卡",
      "source": "学习助手",
      "tag": "微信小程序",
      "preview": "https://pubminishare-30161.picsz.qpic.cn/preview_a1b2c3d4",
      "source_logo": "https://miniapp.gtimg.cn/generated-icon/app_a1b2c3d4.png",
      "tag_icon": "https://miniapp.gtimg.cn/public/miniwx.png"
    }
  },
  "message_scene": {
    "source": "default",
    "ext": [
      "msg_idx=REFIDX_yyyyyyyyyyyyyyy=="
    ]
  },
  "timestamp": "2026-07-21T10:01:00+08:00"
}
```

示例3
 

```
{
  "id": "ROBOT1.0_zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzz",
  "author": {
    "id": "C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6",
    "user_openid": "C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6",
    "union_openid": "",
    "username": "",
    "bot": false
  },
  "content": "这个建议很有帮助，谢谢你！",
  "message_type": 103,
  "msg_elements": [
    {
      "msg_idx": "REFIDX_aaaaaaaaaaaaaaa==",
      "message_type": 103,
      "content": "每天坚持阅读半小时，一个月后你会发现自己的变化"
    }
  ],
  "message_scene": {
    "source": "default",
    "ext": [
      "ref_msg_idx=REFIDX_aaaaaaaaaaaaaaa==",
      "msg_idx=REFIDX_zzzzzzzzzzzzzzz=="
    ]
  },
  "timestamp": "2026-07-21T10:02:00+08:00"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/c2c_message_create.html>


---

#### 群聊消息

# 发送群聊消息
 
向指定群发送消息。支持文本/Markdown/富媒体等类型，可附带内嵌键盘。
注意: 群消息不支持流式参数
 - 被动消息有效时间 5 分钟，每个消息最多回复 5 次
   - Bot 维度（发送方）：企业认证/个人身份证认证 60/qpm；未认证 30/qpm
   - 单关系维度（接收方）：20/qpm，每个群 1 天最多接收 1000 条
  - 单关系维度（接收方）：20/qpm，每个群 1 天最多接收 1000 条

 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/messages |
| HTTP Method | POST |
| 接口频率限制 | 100 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群 OpenID |
 
## 请求体
                                        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| msg_type | integer | 否 | 消息类型。决定哪个内容字段生效: 0=纯文本(content) 2=Markdown(markdown) 7=富媒体(media) |
| content | string | 否 | 文本内容。msg_type=0 时为全文 注意: 传了 markdown 后此字段必须为空 |
| markdown | MessageMarkdown | 否 | Markdown 消息。msg_type=2 时必填 注意: 填写此字段后 content/ark 必须全为空 |
| keyboard | Keyboard | 否 | 内嵌键盘。短形式只传 id，长形式传 content.rows |
| msg_id | string | 否 | 被动回复的消息 ID。从 GROUP_AT_MESSAGE_CREATE 等事件的 d.id 获取，5 分钟内有效 |
| event_id | string | 否 | 被动回复的事件 ID。从事件最外层的id获取。与 msg_id 二选一，支持事件："INTERACTION_CREATE"、"GROUP_ADD_ROBOT"、"GROUP_MSG_RECEIVE" |
| msg_seq | integer | 否 | 回复消息的序号，与 msg_id 联合使用，避免相同消息 id 回复重复发送，不填默认是 1。相同的 msg_id + msg_seq 重复发送会失败。 |
| media | MediaInfo | 否 | 富媒体消息。msg_type=7 时填写，file_info 来自 /v2/groups/{group_openid}/files |
| message_reference | MessageReference | 否 | 引用回复。填写后以引用形式展示，关联上下文 |
 
MessageMarkdown
                    
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| template_id | integer | 否 | 【已废弃】平台 Markdown 模板 ID。使用模板时填写，非模板不传 |
| content | string | 否 | Markdown 内容。支持的格式参考文档：[Markdown (opens new window)](https://bot.q.qq.com/wiki/develop/api-v2/server-inter/message/type/markdown.html) |
| custom_template_id | string | 否 | 【已废弃】自定义模板 ID，与 template_id 二选一 |
| force_verify_image_resource | boolean | 否 | 是否校验图片转存结果，当为true时，如果出现图片转存失败，则会返回错误，消息不会发送。 默认为false |
 
Keyboard
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| id | string | 否 | 内嵌键盘模板 ID。使用平台预设模板时填写此字段 |
| content | KeyboardContent | 否 | 自定义键盘布局。与 id 互斥，用于自定义按钮 |
 
KeyboardContent
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| rows | []Row | 否 | 按钮行列表 |
 
Row
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| buttons | []Button | 否 | 行内按钮，从左到右排列 |
 
Button
                    
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| id | string | 否 | 按钮 ID。同一键盘内唯一 |
| render_data | RenderData | 否 | 按钮渲染 |
| action | Action | 否 | 按钮点击行为 |
| group_id | string | 否 | 分组ID, 同一分组内有一个按钮操作后, 其它按钮则变灰不可点击 注意:只有当action.type = 1 时才有效 |
 
RenderData
                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| label | string | 否 | 按钮文字，最多 10 字符 |
| visited_label | string | 否 | 点击后文字，不传则保持不变 |
| style | integer | 否 | 0：灰色线框，1：蓝色线框 3: 白色背景+红色字体, 4:蓝色背景+白色字体 |
 
Action
                                        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| type | integer | 否 | 0：跳转按钮：http 或 小程序 1：回调按钮：回调后台接口, data 传给后台， 2：指令按钮：自动在输入框插入 @bot data |
| permission | Permission | 否 | 操作权限 |
| data | string | 否 | 回调数据。type=1/2 时必填 |
| click_limit | integer | 否 | 【已废弃】可点击次数限制。0=无限 |
| unsupport_tips | string | 否 | 版本过低时提示文案 |
| enter | boolean | 否 | 指令按钮可用，点击按钮后直接自动发送 data，仅单聊可用，默认 false。支持版本 8983 |
| reply | boolean | 否 | 指令按钮可用，指令是否带引用回复本消息，默认 false。支持版本 8983 |
| anchor | integer | 否 | 本字段仅在指令按钮下有效，设置后后会忽略 action.enter 配置。 设置为 1 时 ，点击按钮自动唤起启手Q选图器，其他值暂无效果。 （仅支持手机端版本 8983+ 的单聊场景，桌面端不支持） |
| modal | Modal | 否 | 用户点击二次确认操作 |
 
Permission
                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| type | integer | 否 | 0=指定用户, 1=管理员, 2=所有人 |
| specify_user_ids | []string | 否 | 有权限的用户 id 的列表 |
| specify_role_ids | []string | 否 | 有权限的身份组 id 的列表（仅频道可用） |
 
Modal
                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| content | string | 否 | 二次确认的提示文本,如果不为空则会进行二次确认. 注意:最多40个字符, 不能有URL |
| confirm_text | string | 否 | 二次确认提示确认按钮中展示的文字,可以为空, 默认为"确认" 注意:最多4个字符 |
| cancel_text | string | 否 | 二次确认提示取消按钮中的文字,可以为空,默认为"取消" 注意:最多4个字符 |
 
MediaInfo
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| file_info | string | 否 | 文件数据。来自文件上传接口返回值 |
 
MessageReference
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| message_id | string | 否 | 被引用消息 ID，例如REFIDX_xxxxxx - 非机器人发的消息，从消息事件的`MessageScene`的`ext`数组，`msg_idx`字段中获取 - 机器人自己发的消息，从发消息请求响应`ext_info.ref_idx`获取 |
 
### 请求示例
 
文本消息 (msg_type=0)
 

```
POST /v2/groups/B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5/messages
{
  "msg_type": 0,
  "content": "欢迎使用本群助手，有什么可以帮你的吗？",
  "msg_id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "msg_seq": 1
}
```

Markdown + 键盘消息 (msg_type=2)
 

```
POST /v2/groups/B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5/messages
{
  "msg_type": 2,
  "markdown": {
    "content": "## 每日签到\n\n今日签到成功！获得 **50** 积分\n连续签到 **7** 天"
  },
  "keyboard": {
    "content": {
      "rows": [
        {
          "buttons": [
            {
              "id": "btn_signin",
              "render_data": {
                "label": "签到",
                "style": 1
              },
              "action": {
                "type": 2,
                "permission": {
                  "type": 2
                },
                "data": "/签到",
                "enter": true
              }
            }
          ]
        }
      ]
    }
  },
  "msg_id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "msg_seq": 1
}
```

富媒体消息 (msg_type=7)
 

```
POST /v2/groups/B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5/messages
{
  "msg_type": 7,
  "msg_id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "msg_seq": 2,
  "media": {
    "file_info": "AE86C5D3F0E14B238C656C0F6DD1D0479C"
  },
  "message_reference": {
    "message_id": "ROBOT1.0_yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy"
  }
}
```

## 响应
 
### 响应体
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 消息 ID，可用于后续撤回 |
| timestamp | string | 发送时间，RFC3339 东八区 |
| ext_info | MessageExtInfo | 扩展信息 |
 
MessageExtInfo
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| ref_idx | string | 引用消息索引。对应消息时间ext里的msg_idx与ref_msg_idx |
 
## 响应示例
 
发送成功
 

```json
{
  "id": "ROBOT1.0_a1b2c3d4e5f6a7b8c9d0e1f2a3b4c5d6e7f8a9b0c1d2e3f4a5b6c7d8e9f0a1b2",
  "timestamp": "2026-07-21T10:00:00+08:00",
  "ext_info": {
    "ref_idx": "REFIDX_xxxxxxxxxxxxxxx=="
  }
}
```

### 错误码
                                                                                                                     
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 22006 | 消息类型与内容不匹配 | 请检查msg_type与content是否对应 |
| 304004 | 无权限使用该ARK模板 | 请先申请ARK模板权限 |
| 304036 | 无Markdown模板权限 | 请先申请Markdown模板权限 |
| 304061 | 消息内容无效 | 请检查消息格式是否符合要求 |
| 304064 | 订阅消息未授权 | 请先引导用户授权订阅消息 |
| 304080 | 文件信息无效 | 请检查文件信息格式是否正确 |
| 304103 | 消息ID已过期，不能回复 | 请在收到消息后尽快回复 |
| 305007 | 键盘样式参数错误 | 请检查keyboard参数 |
| 340069 | 消息类型无效 | 请检查msg_type取值 |
| 40034004 | 富媒体信息转存失败 | 请重试 |
| 40034005 | 回复消息msg_id已过期 | 请在收到消息后尽快回复 |
| 40034006 | 消息内容违规 | 请修改消息内容后重试 |
| 40034008 | markdown参数有空值 | 请确保所有Markdown参数都有值 |
| 40034009 | markdown参数有换行符 | 请移除Markdown参数中的换行符 |
| 40034010 | 模版参数中不能含有markdown语法 | 请使用纯文本参数，不要包含Markdown语法 |
| 40034011 | 无效的markdown内容 | 请检查Markdown语法是否正确 |
| 40034024 | 请求参数msg_id无效或越权 | 请检查msg_id是否正确 |
| 40034025 | 请求参数event_id无效 | 请检查event_id是否正确 |
| 40034026 | 请求参数event_id已过期 | 请在收到事件后尽快回复 |
| 40034027 | 该事件不支持回复消息 | 请确认事件类型是否支持回复 |
| 40034029 | 内联键盘行/列超限 | 请减少键盘按钮数量 |
| 40034100 | 主动消息发送超过频控限制 | 请降低发送频率或等待配额恢复 |
| 40034101 | 机器人非群成员 | 请先将机器人加入群聊 |
| 40034105 | 主动消息发送失败，无权限 | 请检查机器人权限设置 |
| 40034106 | 消息不支持该指令类型 | 请检查消息指令类型 |
| 40034108 | 指令参数长度超限 | 请缩短指令参数 |
| 40034109 | 指令参数解析失败 | 请检查指令参数格式 |
| 40034124 | markdown消息参数错误 | 请检查Markdown参数格式 |
| 40034127 | 无markdown模板权限 | 请先申请Markdown模板权限 |
| 40034128 | 被动回复时间或次数超限 | 请在收到事件后尽快回复 |
| 40054002 | 机器人被禁言 | 请等待解禁后再发送 |
| 40054003 | 机器人不是群成员 | 请先将机器人加入群聊 |
| 40054005 | 消息被去重 | 请确保每次请求使用不同的msgseq值 |
| 40054007 | 消息长度超限 | 请缩短消息内容 |
| 40054010 | 不允许发送URL | 请移除消息中的URL |
| 40054016 | 机器人已下线 | 请检查机器人状态 |
| 50055001 | 消息发送异常，请稍后重试 | 请稍后重试 |
| 50055006 | ARK消息发送异常，请稍后重试 | 请稍后重试 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_messages.post.html>


---

# 撤回群聊消息
 
撤回群消息。发送超过 2 分钟的消息不可撤回。
成功返回 HTTP 200，无响应体。
 - 发送超出 2 分钟的消息不可撤回。
 - 机器人如果是群管理员，可以撤回机器人自己的消息以及普通群成员的消息，群成员的消息ID从群消息事件`GROUP_AT_MESSAGE_CREATE`或`GROUP_MESSAGE_CREATE`里，`d.id`这个字段中获取。
 - 机器人如果是普通成员，只能撤回机器人自己发送的消息，消息ID可以从消息发送接口响应里获取。

 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/messages/{message_id} |
| HTTP Method | DELETE |
| 接口频率限制 | 10 QPS |
 
## 路径参数
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群 OpenID |
| message_id | string | 是 | 消息 ID |
 
### 请求示例
 
撤回群消息
 

```
DELETE /v2/groups/B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5/messages/0123456789ABCDEF0123456789ABCDEF0123456789ABCDEF0123456789ABCDEF
```

## 响应
 
无
 
## 响应示例
 
响应示例
 

```json
{}
```

### 错误码
               
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 40061001 | 请求参数无效 | 请检查请求参数格式 |
| 40062003 | 无操作权限 | 请检查机器人是否有操作权限，机器人是否为群管理员或者发消息的用户是否为普通用户 |
| 40064004 | 已超出消息撤回时限 | 消息发送超过2分钟后不可撤回 |
| 50065001 | 消息撤回失败，请稍后重试 | 请稍后重试 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_messages_message_id.delete.html>


---

##### 事件

# 群消息（全量模式）
 
当机器人开启了"接收所有消息"功能后，群里的每一条消息（不限于@机器人）都会推送此事件。
各字段含义与 GROUP_AT_MESSAGE_CREATE 完全一致。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | GROUP_MESSAGE_CREATE |
| Intent | GROUP_AND_C2C_EVENT (1<<25) |
 
### 事件体
                                    
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 消息 ID，可用于被动回复和撤回 |
| author | User | 发送者 |
| content | string | 消息文本内容（已去除@机器人的前缀） |
| group_openid | string | 群 OpenID |
| timestamp | string | 消息发送时间，RFC3339 格式 |
| message_type | integer | 消息内容类型 |
| message_scene | MessageScene | 消息场景上下文 |
| attachments | []MessageAttachment | 消息附件 |
| mentions | []User | 消息中@的用户列表 |
| ark_data | ARKData | 结构化卡片消息数据 |
| msg_elements | []MsgElement | 消息元素列表 |
 
User
                           
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 用户唯一标识（OpenID 格式） |
| username | string | 用户昵称 |
| bot | boolean | 是否为机器人 |
| union_openid | string | 跨应用统一用户 OpenID（可能为空） |
| union_user_account | string | 跨应用统一用户账号（可能为空） |
| user_openid | string | 用户 OpenID（单聊场景使用） |
| member_openid | string | 群成员 OpenID（群聊场景使用） |
| member_role | string | 群内角色。member=普通成员, admin=管理员, owner=群主 |
 
MessageScene
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| source | string | 场景来源。default=默认聊天窗口 |
| ext | []string | 扩展数据列表，key=value 格式: msg_idx=消息索引, 用于引用场景 ref_msg_idx=引用的消息索引 auth_token=鉴权令牌 |
 
MessageAttachment
                           
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| url | string | 附件下载 URL |
| filename | string | 文件名 |
| width | integer | 图片宽度（像素），非图片附件无此字段 |
| height | integer | 图片高度（像素），非图片附件无此字段 |
| size | integer | 文件大小（字节） |
| content_type | string | 附件内容类型（MIME 类型）: voice=语音消息 image/jpeg=JPEG 图片 image/png=PNG 图片 image/gif=GIF 图片 video/mp4=MP4 视频 file=群文件 |
| voice_wav_url | string | 语音消息 SILK 等转换后的 WAV 文件 URL |
| asr_refer_text | string | 语音消息 ASR 参考结果 |
 
ARKData
               
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| prompt | string | 卡片消息中的用户操作提示文本 |
| ark_type | string | 卡片消息类型标识: tuwen = 图文 H5（如快手分享链接） feed = 图文卡片（群相册、频道帖子、分享卡片） miniapp = 小程序（微信小程序、QQ 小程序、哔哩哔哩等） map = 位置卡片 contact_card = 好友名片 video_share = 视频分享 music_together = 一起听歌 |
| ark_name | string | 卡片消息类型的中文名称，如"图文 H5"、"小程序"、"图文卡片" |
| fields | object | 卡片消息字段，常见键名: tag/tags=来源标签, title=标题, desc=描述, jump_url=跳转链接, preview=预览图, source=来源名称, source_logo=来源图标, tag_icon=标签图标, nickname=昵称, avatar=头像, address=地址 |
 
MsgElement
                        
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| msg_idx | string | 消息元素在列表中的引用消息索引 |
| author | User | 该元素对应的消息发送者 |
| message_type | integer | 消息内容类型: 0=普通文本, 3=结构化卡片, 101=并行消息, 102=聊天记录, 103=引用消息 |
| content | string | 消息正文内容 |
| attachments | []MessageAttachment | 该元素携带的附件 |
| ark_data | ARKData | 结构化卡片消息数据（message_type=3 时有值） |
| msg_elements | []MsgElement | 嵌套消息元素列表（递归结构） |
 
### 事件示例
 
示例1
 

```
{
  "id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "author": {
    "id": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
    "member_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
    "member_role": "member",
    "username": "小明",
    "bot": false
  },
  "content": "大家早上好呀",
  "group_openid": "B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5",
  "message_type": 0,
  "timestamp": "2026-07-21T08:00:00+08:00",
  "message_scene": {
    "source": "default",
    "ext": [
      "msg_idx=REFIDX_xxxxxxxxxxxxxxx==",
      "auth_token=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
    ]
  }
}
```

示例2
 

```
{
  "id": "ROBOT1.0_yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy",
  "author": {
    "id": "C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6",
    "member_openid": "C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6",
    "member_role": "owner",
    "username": "小红",
    "bot": false
  },
  "content": "分享一张今天的风景照",
  "group_openid": "B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5",
  "message_type": 0,
  "timestamp": "2026-07-21T09:30:00+08:00",
  "attachments": [
    {
      "content_type": "image/jpeg",
      "filename": "photo.jpg",
      "url": "https://multimedia.nt.qq.com.cn/download?appid=xxx&fileid=xxx&rkey=xxx&spec=0",
      "width": 1920,
      "height": 1080,
      "size": 256000
    }
  ],
  "message_scene": {
    "source": "default",
    "ext": [
      "msg_idx=REFIDX_yyyyyyyyyyyyyyy==",
      "auth_token=yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy"
    ]
  }
}
```

示例3
 

```
{
  "id": "ROBOT1.0_zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzz",
  "author": {
    "id": "D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6A1",
    "member_openid": "D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6A1",
    "member_role": "admin",
    "username": "小华",
    "bot": false
  },
  "content": " ",
  "group_openid": "B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5",
  "message_type": 103,
  "timestamp": "2026-07-21T10:10:00+08:00",
  "msg_elements": [
    {
      "content": "=== 消息 1 ===\n[消息内容] 今天的学习计划已完成\n\n=== 消息 2 ===\n[消息内容] 很棒！继续保持，明天继续加油\n\n=== 消息 3 ===\n[消息内容] 好的，一起进步！"
    }
  ],
  "message_scene": {
    "source": "default",
    "ext": [
      "msg_idx=REFIDX_zzzzzzzzzzzzzzz==",
      "auth_token=zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzz",
      "ref_msg_idx=TMP_xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
    ]
  }
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/group_message_create.html>


---

# 群@机器人消息
 
用户在群里@机器人发送消息时触发。这是机器人最常接收的事件。
content 字段已自动去除@机器人的前缀。
为确保消息可达，相同 msg_id 可能重复推送，开发者需结合 msg_seq 做去重。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | GROUP_AT_MESSAGE_CREATE |
| Intent | GROUP_AND_C2C_EVENT (1<<25) |
 
### 事件体
                                    
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 消息 ID，可用于被动回复和撤回 |
| author | User | 发送者（member_openid 有值） |
| content | string | 消息文本内容（已去除@机器人的前缀） |
| group_openid | string | 群 OpenID |
| timestamp | string | 消息发送时间，RFC3339 格式 |
| message_type | integer | 消息内容类型（同 C2C_MESSAGE_CREATE） |
| message_scene | MessageScene | 消息场景上下文 |
| attachments | []MessageAttachment | 消息附件 |
| mentions | []User | 消息中@的用户列表（不含@机器人自身） |
| ark_data | ARKData | 结构化卡片消息数据 |
| msg_elements | []MsgElement | 消息元素列表 |
 
User
                           
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 用户唯一标识（OpenID 格式） |
| username | string | 用户昵称 |
| bot | boolean | 是否为机器人 |
| union_openid | string | 跨应用统一用户 OpenID（可能为空） |
| union_user_account | string | 跨应用统一用户账号（可能为空） |
| user_openid | string | 用户 OpenID（单聊场景使用） |
| member_openid | string | 群成员 OpenID（群聊场景使用） |
| member_role | string | 群内角色。member=普通成员, admin=管理员, owner=群主 |
 
MessageScene
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| source | string | 场景来源。default=默认聊天窗口 |
| ext | []string | 扩展数据列表，key=value 格式: msg_idx=消息索引, 用于引用场景 ref_msg_idx=引用的消息索引 auth_token=鉴权令牌 |
 
MessageAttachment
                           
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| url | string | 附件下载 URL |
| filename | string | 文件名 |
| width | integer | 图片宽度（像素），非图片附件无此字段 |
| height | integer | 图片高度（像素），非图片附件无此字段 |
| size | integer | 文件大小（字节） |
| content_type | string | 附件内容类型（MIME 类型）: voice=语音消息 image/jpeg=JPEG 图片 image/png=PNG 图片 image/gif=GIF 图片 video/mp4=MP4 视频 file=群文件 |
| voice_wav_url | string | 语音消息 SILK 等转换后的 WAV 文件 URL |
| asr_refer_text | string | 语音消息 ASR 参考结果 |
 
ARKData
               
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| prompt | string | 卡片消息中的用户操作提示文本 |
| ark_type | string | 卡片消息类型标识: tuwen = 图文 H5（如快手分享链接） feed = 图文卡片（群相册、频道帖子、分享卡片） miniapp = 小程序（微信小程序、QQ 小程序、哔哩哔哩等） map = 位置卡片 contact_card = 好友名片 video_share = 视频分享 music_together = 一起听歌 |
| ark_name | string | 卡片消息类型的中文名称，如"图文 H5"、"小程序"、"图文卡片" |
| fields | object | 卡片消息字段，常见键名: tag/tags=来源标签, title=标题, desc=描述, jump_url=跳转链接, preview=预览图, source=来源名称, source_logo=来源图标, tag_icon=标签图标, nickname=昵称, avatar=头像, address=地址 |
 
MsgElement
                        
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| msg_idx | string | 消息元素在列表中的引用消息索引 |
| author | User | 该元素对应的消息发送者 |
| message_type | integer | 消息内容类型: 0=普通文本, 3=结构化卡片, 101=并行消息, 102=聊天记录, 103=引用消息 |
| content | string | 消息正文内容 |
| attachments | []MessageAttachment | 该元素携带的附件 |
| ark_data | ARKData | 结构化卡片消息数据（message_type=3 时有值） |
| msg_elements | []MsgElement | 嵌套消息元素列表（递归结构） |
 
### 事件示例
 
示例1
 

```
{
  "id": "ROBOT1.0_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "author": {
    "id": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
    "member_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
    "member_role": "member",
    "username": "小明",
    "bot": false
  },
  "content": " /今日天气 ",
  "group_openid": "B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5",
  "message_type": 0,
  "timestamp": "2026-07-21T10:00:00+08:00",
  "message_scene": {
    "source": "default",
    "ext": [
      "msg_idx=REFIDX_xxxxxxxxxxxxxxx==",
      "auth_token=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
    ]
  }
}
```

示例2
 

```
{
  "id": "ROBOT1.0_yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy",
  "author": {
    "id": "C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6",
    "member_openid": "C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6",
    "member_role": "member",
    "username": "小红",
    "bot": false
  },
  "content": " 看看这张风景照 ",
  "group_openid": "B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5",
  "message_type": 0,
  "timestamp": "2026-07-21T10:05:00+08:00",
  "attachments": [
    {
      "content_type": "image/jpeg",
      "filename": "photo.jpg",
      "url": "https://multimedia.nt.qq.com.cn/download?appid=xxx&fileid=xxx&rkey=xxx&spec=0",
      "width": 1920,
      "height": 1080,
      "size": 256000
    }
  ],
  "message_scene": {
    "source": "default",
    "ext": [
      "msg_idx=REFIDX_yyyyyyyyyyyyyyy==",
      "auth_token=yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy"
    ]
  }
}
```

示例3
 

```
{
  "id": "ROBOT1.0_zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzz",
  "author": {
    "id": "D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6A1",
    "member_openid": "D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6A1",
    "member_role": "owner",
    "username": "小华",
    "bot": false
  },
  "content": " ",
  "group_openid": "B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5",
  "message_type": 103,
  "timestamp": "2026-07-21T10:10:00+08:00",
  "msg_elements": [
    {
      "content": "=== 消息 1 ===\n[消息内容] 今天的学习计划已完成\n\n=== 消息 2 ===\n[消息内容] 很棒！继续保持，明天继续加油\n\n=== 消息 3 ===\n[消息内容] 好的，一起进步！"
    }
  ],
  "message_scene": {
    "source": "default",
    "ext": [
      "msg_idx=REFIDX_zzzzzzzzzzzzzzz==",
      "auth_token=zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzz",
      "ref_msg_idx=TMP_xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
    ]
  }
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/group_at_message_create.html>


---

#### 频道消息

# 发送子频道消息
 
### 接口
 
`POST /channels/{channel_id}/messages`
 
### 功能描述
 
用于向 `channel_id` 指定的子频道发送消息。
 - 要求操作人在该子频道具有`发送消息`的权限。
   - 主动推送消息，默认每天往每个子频道可推送的消息数是 `20` 条，超过会被限制。
   - 主动推送消息在每个频道中，每天可以往 `2` 个子频道推送消息。超过后会被限制。
  - 主动推送消息在每个频道中，每天可以往 `2` 个子频道推送消息。超过后会被限制。
 - 不论主动消息还是被动消息，在一个子频道中，每 `1s` 只能发送 `5` 条消息。
 - 被动回复消息有效期为 `5` 分钟。超时会报错。
 - 发送消息接口要求机器人接口需要连接到 websocket 上保持在线状态
 - 有关主动消息审核，可以通过 [Intents](/wiki/develop/api-v2/dev-prepare/interface-framework/event-emit.html#事件订阅Intents) 中审核事件 MESSAGE_AUDIT 返回 [MessageAudited](/wiki/develop/api-v2/server-inter/message/template/model.html#messageaudited) 对象获取结果。

 
### Content-Type
 - 请求支持 `application/json` 和 `multipart/form-data` 两种。对于类型为 `multipart/form-data` 的请求，当字段类型为对象或数组时需要将字段序列化为 JSON 字符串后进行调用，可参考下文的示例。
 - 回包统一使用 `application/json`

 
### 通用参数
                           
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| content | string | 选填，消息内容，文本内容，支持[内嵌格式](/wiki/develop/api-v2/server-inter/channel/message/format.html) |
| embed | [MessageEmbed](/wiki/develop/api-v2/server-inter/message/template/model.html#messageembed) | 选填，embed 消息，一种特殊的 ark，详情参考[Embed消息](/wiki/develop/api-v2/server-inter/message/type/embed.html) |
| ark | [MessageArk](/wiki/develop/api-v2/server-inter/message/template/model.html#messageark) ark消息对象 | 选填，ark 消息 |
| message_reference | [MessageReference](/wiki/develop/api-v2/server-inter/message/template/model.html#messagereference) 引用消息对象 | 选填，引用消息 |
| image | string | 选填，图片url地址，平台会转存该图片，用于下发图片消息 |
| msg_id | string | 选填，要回复的消息id([Message](/wiki/develop/api-v2/server-inter/message/template/model.html#message).id), 在 [AT_MESSAGE_CREATE](/wiki/develop/api-v2/server-inter/channel/message/event.html#at_message_create) 事件中获取。 |
| event_id | string | 选填，要回复的事件id, 在各事件对象中获取。 |
| markdown | [MessageMarkdown](/wiki/develop/api-v2/server-inter/message/template/model.html#messagemarkdown) markdown 消息对象 | 选填，markdown 消息 |
 
### `multipart/form-data` 专有参数
      
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| file_image | file | 图片文件。form-data 支持直接通过文件上传的方式发送图片。 |
 
content, embed, ark, image/file_image, markdown 至少需要有一个字段，否则无法下发消息。
 
#### 主动消息与被动消息
 - 主动消息：发送消息时，未填充 `msg_id/event_id` 字段的消息。
 - 被动消息：发送消息时，填充了 `msg_id/event_id` 字段的消息。`msg_id` 和 `event_id` 两个字段任意填一个即为被动消息。接口使用此 `msg_id/event_id` 拉取用户的消息或事件，同时判断用户消息或事件的发送时间，如果超过被动消息回复时效，将会不允许发送该消息。
 - 目前支持被动回复的事件类型有:
GUILD_MEMBER_ADD
GUILD_MEMBER_UPDATE
GUILD_MEMBER_REMOVE
MESSAGE_REACTION_ADD
MESSAGE_REACTION_REMOVE
FORUM_THREAD_CREATE
FORUM_THREAD_UPDATE
FORUM_THREAD_DELETE
FORUM_POST_CREATE
FORUM_POST_DELETE
FORUM_REPLY_CREATE
FORUM_REPLY_DELETE

 
### 返回
 
返回[Message](/wiki/develop/api-v2/server-inter/message/template/model.html#message) 对象。
 
### 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
其中推送、回复消息的 `code` 错误码 `304023`、`304024` 会在 响应数据包 `data` 中返回 [MessageAudit](/wiki/develop/api-v2/openapi/error/data/model.html) 审核消息的信息，结构如下:
 

```json
{
  "code": 304023,
  "message": "push message is waiting for audit now",
  "data": {
    "message_audit": {
      "audit_id": "ab9bd72f-19e8-4394-b09e-66caca0d64e4"
    }
  }
}
```

### JSON 格式示例
 
请求数据包
 

```json
{
  "content": "<@!1234>hello world",
  "msg_id": "xxxxxx"
}
```

响应数据包
 

```json
{
  "id": "xxxxxx",
  "channel_id": "xxxxxx",
  "guild_id": "xxxxxx",
  "content": "<@!1234>hello world",
  "timestamp": "2021-05-13T14:45:45+08:00",
  "tts": false,
  "mention_everyone": false,
  "author": {
    "id": "xxxxxx",
    "username": "abc",
    "avatar": "",
    "bot": true
  },
  "embeds": [{}],
  "pinned": false,
  "type": 0,
  "flags": 0
}
```

### form-data 格式示例
 
请求数据包
      
| 字段名 | 值 |
| --- | --- |
| content | <@!1234>hello world |
| ark | {"ark":{"template_id":1,"kv":[{"key":"#DESC#","value":"机器人订阅消息"}]}} |
 

```json
{
  "id": "xxxxxx",
  "channel_id": "xxxxxx",
  "guild_id": "xxxxxx",
  "content": "<@!1234>hello world",
  "timestamp": "2021-05-13T14:45:45+08:00",
  "tts": false,
  "mention_everyone": false,
  "author": {
    "id": "xxxxxx",
    "username": "abc",
    "avatar": "",
    "bot": true
  },
  "embeds": [{}],
  "pinned": false,
  "type": 0,
  "flags": 0
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/message/send.html>


---

# 内嵌格式
 
### 功能描述
 
利用 `content` 字段发送内嵌格式的消息。
 - 内嵌格式仅在 `content` 中会生效，在 `Ark` 和 `Embed` 中不生效。
 - 为了区分是文本还是内嵌格式，消息抄送和发送会对消息内容进行相关的转义，参考 转义内容

 
### 支持的格式
                    
| 类型 | 结构 | 描述 | 示例 |
| --- | --- | --- | --- |
| @用户 | `<@user_id>` 或者 `<@!user_id>` | 解析为 `@用户` 标签 | `<@1234000000001>` |
| @所有人 | `@everyone` | 解析为 `@所有人` 标签，需要机器人拥有发送 `@所有人` 消息的权限 | `@everyone` |
| #子频道 | `<#channel_id>` | 解析为 `#子频道` 标签，点击可以跳转至子频道，仅支持当前频道内的子频道 | `<#12345>` |
| 表情 | `<emoji:id>` | 解析为系统表情，具体表情id参考 [Emoji 列表](/wiki/develop/api-v2/openapi/emoji/model.html#Emoji列表)，仅支持type=1的系统表情，type=2的emoji表情直接按字符串填写即可 | `<emoji:4>` 解析为得意情 |
 
### 转义内容
 - 消息抄送会将源字符转为转义后内容然后抄送给机器人
 - 发消息会将转义后字符转为源字符后抄再发

        
| 源字符 | 转义后 |
| --- | --- |
| & | &amp; |
| < | &lt; |
| > | &gt; |
 
### 示例
 
请求数据包
 

```json
{
    "content":"<@!1234>hello world"
}
```

响应数据包
 

```json
{
  "id": "xxxxxx",
  "channel_id": "xxxxxx",
  "guild_id": "xxxxxx",
  "content": "<@!1234>hello world",
  "timestamp": "2021-05-13T14:45:45+08:00",
  "tts": false,
  "mention_everyone": false,
  "author": {
    "id": "xxxxxx",
    "username": "abc",
    "avatar": "",
    "bot": true
  },
  "embeds": [{}],
  "pinned": false,
  "type": 0,
  "flags": 0
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/message/format.html>


---

# 撤回子频道消息
 
### 接口
 

```http
DELETE /channels/{channel_id}/messages/{message_id}?hidetip=false
```

### 参数
      
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| hidetip | bool | 选填，是否隐藏提示小灰条，true 为隐藏，false 为显示。默认为false |
 
### 功能描述
 
用于撤回子频道 `channel_id` 下的消息 `message_id`
 - 管理员可以撤回普通成员的消息。
 - 频道主可以撤回所有人的消息。

 - 公域机器人暂不支持申请，仅私域机器人可用，选择私域机器人后默认开通。
- 注意: 开通后需要先将机器人从频道移除，然后重新添加，方可生效。

> **警告**
> 注意
 
### Content-Type
 

```http
application/json
```

### 返回
 
成功返回 HTTP 状态码 `200`。
 
### 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
### 示例
 
请求数据包
 

```http
DELETE /channels/123456/messages/112233
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/message/recall.html>


---

# 频道私信
 
机器人可与同一频道内的成员建立私信会话，通过私信接口收发消息。
 
## 创建私信会话
 
### 接口
 

```http
POST /users/@me/dms
```

### 功能描述
 
用于机器人和在同一个频道内的成员创建私信会话。
 - 机器人和用户存在共同频道才能创建私信会话。
 - 创建成功后，返回创建成功的频道 `id` ，子频道 `id` 和创建时间。

 
### Content-Type
 

```http
application/json
```

### 参数
         
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| recipient_id | string | 接收者 id |
| source_guild_id | string | 源频道 id |
 
### 返回
 
返回DMS对象。
 
### 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
### 示例
 
请求数据包
 

```json
{
  "recipient_id": "123456",
  "source_guild_id": "112233"
}
```

响应数据包
 

```json
{
  "guild_id": "xxxxxx",
  "channel_id": "xxxxxx",
  "create_time": "1642545606"
}
```

## 发送私信
 
### 接口
 

```http
POST /dms/{guild_id}/messages
```

### 功能描述
 
用于发送私信消息，前提是已经创建了私信会话。
 - 私信的 `guild_id` 在创建私信会话时以及[私信消息事件](/wiki/develop/api-v2/server-inter/channel/message/event.html#direct_message_create)中获取。
 - 私信场景下，每个机器人每天可以对一个用户发 `2` 条主动消息。
 - 私信场景下，每个机器人每天累计可以发 `200` 条主动消息。
 - 私信场景下，被动消息没有条数限制。

 
### Content-Type
 

```http
application/json
```

### 参数
 
和[发送子频道消息](/wiki/develop/api-v2/server-inter/channel/message/send.html)参数一致。
 
### 返回
 
和[发送子频道消息](/wiki/develop/api-v2/server-inter/channel/message/send.html)返回一致。
 
### 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
### 示例
 
参见[发送子频道消息](/wiki/develop/api-v2/server-inter/channel/message/send.html#json-格式示例)示例。
 
## 撤回私信
 
### 接口
 

```http
DELETE /dms/{guild_id}/messages/{message_id}?hidetip=false
```

### 参数
      
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| hidetip | bool | 选填，是否隐藏提示小灰条，true 为隐藏，false 为显示。默认为false |
 
### 功能描述
 
用于撤回私信频道 `guild_id` 中 `message_id` 指定的私信消息。只能用于撤回机器人自己发送的私信。
 - 公域机器人暂不支持申请，仅私域机器人可用，选择私域机器人后默认开通。
- 注意: 开通后需要先将机器人从频道移除，然后重新添加，方可生效。

> **警告**
> 注意
 
### Content-Type
 

```http
application/json
```

### 返回
 
成功返回 HTTP 状态码 `200`。
 
### 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
### 示例
 
请求数据包
 

```http
DELETE /dms/123456/messages/112233
```

## DMS 对象
  
### DMS
            
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| guild_id | string | 私信会话关联的频道 id |
| channel_id | string | 私信会话关联的子频道 id |
| create_time | string | 创建私信会话时间戳 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/message/dms.html>


---

# 表情表态
 
> **提示**
> 说明 目前表情表态仅支持在频道内使用
 
## 机器人发表表情表态
 
### 接口
 

```http
PUT /channels/{channel_id}/messages/{message_id}/reactions/{type}/{id}
```

### 功能描述
 
对消息 `message_id` 进行表情表态
 
### 参数
               
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| channel_id | string | 子频道ID |
| message_id | string | 消息ID |
| type | int | 表情类型，参考 [EmojiType](/wiki/develop/api-v2/openapi/emoji/model.html#EmojiType) |
| id | string | 表情ID，参考 [Emoji 列表](/wiki/develop/api-v2/openapi/emoji/model.html#Emoji 列表) |
 
### 返回
 
成功返回 HTTP 状态码 `204`。
 
### 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
### 示例
 
请求数据包
 

```http
PUT /channels/1013531/messages/08c095b7ba8ed4abd7e00110cbd83f3841489aa2bd9006/reactions/1/203
```

## 删除机器人发表的表情表态
 
### 接口
 

```http
DELETE /channels/{channel_id}/messages/{message_id}/reactions/{type}/{id}
```

### 功能描述
 
删除自己对消息 `message_id` 的表情表态
 
### 参数
               
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| channel_id | string | 子频道ID |
| message_id | string | 消息ID |
| type | int | 表情类型，参考 [EmojiType](/wiki/develop/api-v2/openapi/emoji/model.html#EmojiType) |
| id | string | 表情ID，参考 [Emoji 列表](/wiki/develop/api-v2/openapi/emoji/model.html#Emoji 列表) |
 
### 返回
 
成功返回 HTTP 状态码 `204`。
 
### 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
### 示例
 
请求数据包
 

```http
DELETE /channels/1013531/messages/08c095b7ba8ed4abd7e00110cbd83f3841489aa2bd9006/reactions/1/203
```

## 获取消息表情表态的用户列表
 
### 接口
 

```http
GET /channels/{channel_id}/messages/{message_id}/reactions/{type}/{id}?cookie={cookie}&limit={limit}
```

### 功能描述
 
拉取对消息 `message_id` 指定表情表态的用户列表
 
### Path 参数
               
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| channel_id | string | 子频道ID |
| message_id | string | 消息ID |
| type | int | 表情类型，参考 EmojiType |
| id | string | 表情ID，参考 Emoji 列表 |
 
### Query 参数
         
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| cookie | string | 上次请求返回的cookie，第一次请求无需填写 |
| limit | int | 每次拉取数量，默认20，最多50，只在第一次请求时设置 |
 
### 返回
            
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| users | array | 用户对象，参考 User，会返回 id, username, avatar |
| cookie | string | 分页参数，用于拉取下一页 |
| is_end | bool | 是否已拉取完成到最后一页，true代表完成 |
 
### 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
### 示例
 
请求数据包
 

```http
GET /channels/1013531/messages/08c095b7ba8ed4abd7e00110cbd83f3841489aa2bd9006/reactions/1/203?cookie=&limit=20
```

返回数据包
 

```json
{
    "users": [
        {
            "id": "1158788878435714165",
            "username": "频道机器人",
            "avatar": "http://thirdqq.qlogo.cn/g?b=oidb&k=T2qBkyqicopYXA5mn0lBkqA&s=0&t=1635736336"
        }
    ],
    "cookie":"1_2",
    "is_end": false
}
```

## 事件
 
### 用户发表
 - 基本概况

 
用户对消息进行表情表态时，触发事件通知。
 
#### MESSAGE_REACTION_ADD (intents GUILD_MESSAGE_REACTIONS)
 
##### 发送时机
 - 用户对消息进行表情表态时

 
#### MESSAGE_REACTION_REMOVE (intents GUILD_MESSAGE_REACTIONS)
 
##### 发送时机
 - 用户对消息进行取消表情表态时

 
##### 内容
 
内容为 [MessageReaction](/wiki/develop/api-v2/openapi/reaction/model.html#MessageReaction) 对象
 
##### 示例
 

```json
{
  "user_id": "1111222233333",
  "emoji": {
    "id": "277",
    "type": 1
  },
  "channel_id": "12345",
  "guild_id": "11110011112222",
  "target": {
    "id": "2",
    "type": 0
  }
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/message/trans/emoji.html>


---

# 频道消息事件
 
## AT_MESSAGE_CREATE（intents PUBLIC_GUILD_MESSAGES）
  
### 发送时机
 - 用户发送消息，@当前机器人或回复机器人消息时
 - 为保障消息投递的速度，消息顺序我们虽然会尽量有序，但是并不保证是严格有序的，如开发者对消息顺序有严格有序的需求，可以自行缓冲消息事件之后，基于 Message.seq 进行排序

 
### 内容
 
内容为 [Message](/wiki/develop/api-v2/server-inter/message/template/model.html#message) 对象
 
### 示例
 

```json
{
  "author": {
    "avatar": "http://thirdqq.qlogo.cn/0",
    "bot": false,
    "id": "1234",
    "username": "abc"
  },
  "channel_id": "100010",
  "content": "ndnnd",
  "guild_id": "18700000000001",
  "id": "0812345677890abcdef",
  "member": {
    "joined_at": "2021-04-12T16:34:42+08:00",
    "roles": ["1"]
  },
  "timestamp": "2021-05-20T15:14:58+08:00",
  "seq": 101
}
```

## MESSAGE_CREATE（intents PUBLIC_GUILD_MESSAGES，私域）
  
### 发送时机
 - 用户在文字子频道内发送的所有聊天消息（私域）
 - 为保障消息投递的速度，消息顺序我们虽然会尽量有序，但是并不保证是严格有序的，如开发者对消息顺序有严格有序的需求，可以自行缓冲消息事件之后，基于 Message.seq 进行排序

 
### 内容
 
内容为 [Message](/wiki/develop/api-v2/server-inter/message/template/model.html#message) 对象
 
### 示例
 

```json
{
  "author": {
    "avatar": "http://thirdqq.qlogo.cn/0",
    "bot": false,
    "id": "1234",
    "username": "abc"
  },
  "channel_id": "100010",
  "content": "ndnnd",
  "guild_id": "18700000000001",
  "id": "0812345677890abcdef",
  "member": {
    "joined_at": "2021-04-12T16:34:42+08:00",
    "roles": ["1"]
  },
  "timestamp": "2021-05-20T15:14:58+08:00",
  "seq": 101
}
```

## DIRECT_MESSAGE_CREATE（intents DIRECT_MESSAGE）
  
### 发送时机
 - 用户通过私信发消息给机器人时
 - 由于私信场景无法设置沙箱频道，目前私信事件不支持沙箱环境，开发者可以通过用户 id 白名单的方式来调试私信

 
### 内容
 
内容为 [Message](/wiki/develop/api-v2/server-inter/message/template/model.html#message) 对象
 
### 示例
 

```json
{
    "author": {
        "avatar": "http://thirdqq.qlogo.cn/0",
        "bot": false,
        "id": "1234",
        "username": "abc"
    },
    "channel_id": "100010",
    "content": "ndnnd",
    "guild_id": "18700000000001",
    "id": "0812345677890abcdef",
    "member": {
        "joined_at": "2021-04-12T16:34:42+08:00",
        "roles": [
            "1"
        ]
    },
    "timestamp": "2021-05-20T15:14:58+08:00"
}
```

## 消息审核事件
 
### MESSAGE_AUDIT_PASS（intents MESSAGE_AUDIT）
  
#### 发送时机
 - 消息审核通过

 
#### 内容
 
[MessageAudited](/wiki/develop/api-v2/server-inter/message/template/model.html#messageaudited)
 
### MESSAGE_AUDIT_REJECT（intents MESSAGE_AUDIT）
  
#### 发送时机
 - 消息审核不通过

 
#### 内容
 
[MessageAudited](/wiki/develop/api-v2/server-inter/message/template/model.html#messageaudited)
 
#### 示例
 

```json
{
  "audit_id": "5f60b782-d134-4628-93b8-9baa4b182f48",
  "audit_time": "2022-01-04T18:05:42+08:00",
  "channel_id": "1699792",
  "create_time": "2022-01-04T18:05:42+08:00",
  "guild_id": "46646271634786417",
  "message_id": "10d0df671a1231343431313532313831383136323933383420801e280030a0cbc4013848404148f6b7d08e0650b1acf8fa05"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/message/event.html>


---

#### 消息类型

# 消息类型
 
通过 `msg_type` 指定消息格式，不同的类型对应不同的内容字段和收发能力。
 
## 发送：msg_type
 
发送消息时通过 `msg_type` 指定格式：
                
| msg_type | 类型 | 内容字段 | 说明 |
| --- | --- | --- | --- |
| 0 | 文本 | `content` | 纯文本消息 |
| 2 | Markdown | `markdown` | 支持 Markdown 语法，详见 [Markdown 消息](/wiki/develop/api-v2/server-inter/message/type/markdown.html) |
| 7 | 富媒体 | `media` | 图片/视频/语音/文件，需先上传获取 `file_info` |
 
## 接收：message_type
 
收到用户消息时，事件体中的 `message_type` 表示消息内容类型：
            
| message_type | 含义 | 说明 |
| --- | --- | --- |
| 0 | 普通文本 | `content` 字段携带文本内容 |
| 3 | 结构化卡片 | `ark_data` 字段携带卡片数据 |
| 103 | 引用消息 | `msg_elements` 字段携带嵌套内容 |
 
> 图片、视频、语音、文件等附加内容通过 `attachments` 字段携带（`content_type` 区分具体类型），不通过 `message_type` 单独表示。
 
## 各场景支持情况
                                            
| 类型 | 单聊 | 群聊 | 频道 |
| --- | --- | --- | --- |
| 文本 | 收发 ✅ | 收发 ✅ | 收发 ✅ |
| Markdown | 发 ✅ / 收 ❌ | 收发 ✅ | 发 ✅ / 收 ❌ |
| 图片 | 收发 ✅ | 收发 ✅ | 收发 ✅ |
| 视频 | 收发 ✅ | 收发 ✅ | 收发 ✅ |
| 语音 | 收发 ✅ | 收发 ✅ | 收发 ✅ |
| 文件 | 收发 ✅ | 收发 ✅ | ❌ |
| 结构化卡片 | 发 ❌ / 收 ✅ | 发 ❌ / 收 ✅ | 发 ❌ / 收 ❌ |
| Embed | ❌ | ❌ | 发 ✅ / 收 ❌ |
| 表情表态 | ❌ | ❌ | 收发 ✅ |
| 引用消息 | 收 ✅ | 收 ✅ | 收 ✅ |
 - 发送侧只有 msg_type=0/2/3/7 四种（见上方表格）
- 富媒体上传流程见 [富媒体使用说明](/wiki/develop/api-v2/server-inter/message/rich-media.html)
- 表情表态仅频道支持，详见 [表情表态](/wiki/develop/api-v2/server-inter/message/trans/emoji.html)

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/message/type/overview.html>


---

# Markdown 消息
 
> **提示**
> 2026/04/23 能力更新说明 单聊场景、群聊场景自定义 Markdown 消息能力已开放到所有机器人均可使用，无需单独申请 Markdown 模版，频道场景目前需要内邀开通。
 
## 支持格式
 
### 标题
 

```
# 一号标题
## 二号标题
正文
```

### 文字样式
 

```
**加粗**
__下划线加粗__
_斜体_
*星号斜体*
***加粗斜体***
~~删除线~~
```

### 链接
 

```
欢迎来到：[🔗腾讯网](https://www.qq.com)  
文档可以访问<https://doc.qq.com>
```

### 图片
 
对于 markdown 消息内的图片资源，请使用可在公网访问的资源 url，开放平台会下载转存该资源。
 

```
![text #208px #320px](https://resource5-1255303497.cos.ap-guangzhou.myqcloud.com/abcmouse_word_watch/markdown/building.png)
```

### 有序列表
 

```
# 有序列表
1. 新人降落桃源岛的欢迎仪式
2. 阳光准则助力建设有温度的频道
3. 岛民分享吹水纳凉
```

### 无序列表
 

```
# 无序列表
- 新人降落桃源岛的欢迎仪式
- 阳光准则助力建设有温度的频道
- 岛民分享吹水纳凉
```

### 列表嵌套
 

```
# 有序列表标题
1. 嵌套一层
    - 列表前是普通文本，则需要在列表前用空行隔开，否则无法识别
    - 如果是段落标签比如标题，则无需用空行隔开
2. 嵌套二层
    1. 我是有序列表，二级列表前面需要空4个空格
    2. 无序列表和有序列表可以相互嵌套，但是不建议无限制嵌套。
```

### 块引用
 

```
> 青青子衿，悠悠我心，但为君故，沉吟至今
> 四月维夏，六月徂暑。先祖匪人，胡宁忍予
> 秋日凄凄，百卉具腓。乱离瘼矣，爰其适归？
诗经《小雅》
```

### 水平分割线
 

```
这是段落1
***
这是段落2
```

### 换多行
 

```
第一行

第二行

\u200B
\u200B
第三行
```

## 发送方式
 
自定义 markdown 消息使用示例：
 

```json
{
  "markdown": {
    "content": "# 标题 \n## 简介很开心 \n内容[🔗腾讯](https://www.qq.com)"
  }
}
```

markdown 模版消息的使用示例：
 

```
// 模版例子

#{{.title}}

![img#618px #249px]({{.image}})

*{{.para1}}
*{{.para2}}

## {{.desc}}

{{.content}}[{{.link_introduction}}]({{.link}})

// 发送case
{
	"markdown": {
		"custom_template_id": "101993071_1658748972",
		"params": [{
				"key": "title",
				"values": ["标题"]
			},
			{
				"key": "image",
				"values": [
					"https://resource5-1255303497.cos.ap-guangzhou.myqcloud.com/abcmouse_word_watch/other/mkd_img.png"
				]
			},
			{
				"key": "para1",
				"values": ["段落1"]
			},
			{
				"key": "para2",
				"values": ["段落2"]
			},
			{
				"key": "desc",
				"values": ["简介"]
			},
			{
				"key": "content",
				"values": ["在这个子频道非常开心"]
			},
			{
				"key": "link_introduction",
				"values": ["链接介绍"]
			},
			{
				"key": "link",
				"values": ["https://www.qq.com"]
			}
		]
	}
}
```

## 数据结构与协议
 
消息发送 markdown 字段值是一个 json object，具体字段如下：
                
| 属性 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| content | string | 否 | 自定义 markdown 文本内容 |
| custom_template_id | string | 否 | markdown 模版id，申请模版后获得 |
| params | Array | 否 | {key: xxx, values: xxx}，模版内变量与填充值的kv映射 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/message/type/markdown.html>


---

##### 富媒体

# 富媒体消息概述
 
富媒体消息支持发送图片、视频、语音、文件等类型，需先将文件上传获取 `file_info`，再通过发消息接口（`msg_type=7`）携带 `media.file_info` 发送。
 
## 支持的消息类型
            
| 图片 | 语音 | 视频 | 文件 |
| --- | --- | --- | --- |
| ![图片消息](https://qq-ai.cdn-go.cn/web/bot-docs/-/v1.28.0/assets/img/image-send.35813305.jpg) | ![语音消息](https://qq-ai.cdn-go.cn/web/bot-docs/-/v1.28.0/assets/img/voice-send.21dce8bf.jpg) | ![视频消息](https://qq-ai.cdn-go.cn/web/bot-docs/-/v1.28.0/assets/img/video-send.9416079c.jpg) | ![文件消息](https://qq-ai.cdn-go.cn/web/bot-docs/-/v1.28.0/assets/img/large-file-transfer.f49ff1e2.jpg) |
| 支持 jpg/png/gif/webp/bmp 格式，发送后直接展示图片 | 支持 silk/mp3/wav/ogg 格式，发送后展示语音条 | 支持 mp4 格式，发送后展示视频封面可播放 | 支持任意格式，发送后展示文件卡片可下载 |
 
## 文件类型与限制
                         
| file_type | 类型 | 格式 | 软限制 | 硬限制 |
| --- | --- | --- | --- | --- |
| 1 | 图片 | png / jpg | 20 MB | 200 MB |
| 2 | 视频 | mp4 | 30 MB | 200 MB |
| 3 | 语音 | silk | 20 MB | 200 MB |
| 4 | 文件 | - | 200 MB | 200 MB |
 
超过软限制会降级为文件类型上传，超过硬限制会报错。
 
## 上传方式
 
整文件上传使用 [单聊上传](/wiki/develop/api-v2/autogen/api/v2_users_user_openid_files.post.html) / [群聊上传](/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_files.post.html) 接口，直接传入文件 URL；文件较大时使用分片上传，参考 [单聊预上传](/wiki/develop/api-v2/autogen/api/v2_users_user_id_upload_prepare.post.html) 开始分片流程。
 
### 分片上传（推荐）
 
适用于大文件或本地文件。分四步完成：
 

```
1. 预上传
   调用 upload_prepare，传入文件信息和校验值
   → 获取 upload_id + block_size + 各分片预签名 URL

2. 分片 PUT
   按 block_size 将文件分片，逐片 HTTP PUT 到对应的预签名 URL

3. 确认分片
   每片 PUT 成功后调用 upload_part_finish，通知服务端该分片完成

4. 完成合并
   全部分片完成后，携带 upload_id 调用上传接口
   → 返回 file_info
```

流程图：
 

```
 upload_prepare         分片 PUT + part_finish        上传接口（合并）
┌──────────────┐    ┌─────────────────────────┐    ┌──────────────────┐
│ 获取        │    │  for each chunk:        │    │ POST .../files   │
│ upload_id   │───▶│  PUT → presigned_url    │───▶│ { upload_id }   │
│ block_size  │    │  POST → part_finish     │    │ → file_info      │
│ presigned   │    └─────────────────────────┘    └──────────────────┘
│ URLs        │
└──────────────┘
```

### URL 上传
 
适用于文件已在公网可访问的场景，直接传入文件 URL，平台自动下载转存。
 

```
POST /v2/users/{user_openid}/files
{
  "file_type": 1,
  "url": "https://example.com/image.png"
}
```

返回 `file_info`，即可用于发消息。
 
## 使用 file_info 发送
 
获取 `file_info` 后，在发消息接口中设置 `msg_type=7`，将 `file_info` 填入 `media` 字段：
 

```json
POST /v2/users/{user_openid}/messages
{
  "msg_type": 7,
  "media": {
    "file_info": "{上一步返回的 file_info}"
  }
}
```

> `srv_send_msg=true` 可在上传的同时直接发送，跳过单独调用发消息接口这一步，但会占用主动消息频次。
 
## 单聊与群聊隔离
 
单聊和群聊的文件上传接口相互独立，上传的文件不能跨场景使用：
      
| 场景 | 上传接口 |
| --- | --- |
| 单聊 | `/v2/users/{user_openid}/files` |
| 群聊 | `/v2/groups/{group_openid}/files` |
 
对应的预上传和分片接口也需使用同场景的端点。
 
## 注意事项
 - `file_info` 有有效期（`ttl`），过期后需重新上传。
 - `md5_10m`（文件前 10002432 字节，约 9.54 MB 的 MD5）可用于秒传判断，避免重复上传。
 - 分片大小默认 5MB，并发数、重试策略由服务端在 `upload_config` 中下发。
 - 上传接口超时建议设为 ≥ 5 秒。

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/message/rich-media.html>


---

# 单聊富媒体上传
 
上传图片/视频/语音到单聊，返回 file_info 用于发送消息接口的 media 字段。
用单聊接口上传的文件仅能发送到单聊。
文件类型与大小限制:
 - 1=图片(png/jpg): 软限制 20MB, 硬限制 200MB
 - 2=视频(mp4): 软限制 30MB, 硬限制 200MB
 - 3=语音(silk): 软限制 20MB, 硬限制 200MB
 - 4=文件: 软限制 200MB, 硬限制 200MB
超过软限制会降级为文件类型上传，超过硬限制会报错。

 
支持两种上传方式：
 1. URL 上传：传入 url，平台下载转存
 2. 分片上传合并：先通过 upload_prepare + upload_part_finish 完成分片上传，再携带 upload_id 调用本接口完成合并

 
推荐使用分片上传，流程如下：
 1. 调用 upload_prepare 获取 upload_id、block_size 和各分片预签名 URL
 2. 按 block_size 将文件分片，逐片 HTTP PUT 到对应的预签名 URL
 3. 每片 PUT 成功后调用 upload_part_finish 通知服务端该分片完成
 4. 全部分片完成后，携带 upload_id 调用本接口完成合并，返回 file_info

 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/users/{user_openid}/files |
| HTTP Method | POST |
| 接口频率限制 | 50 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| user_openid | string | 是 | 用户 OpenID |
 
## 请求体
                        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| file_type | integer | 否 | 媒体类型。1=图片, 2=视频, 3=语音, 4=文件 图片支持 png/jpg，视频支持 mp4，语音支持 silk |
| url | string | 否 | 媒体资源的 URL，需以 http 开头，平台会下载并转存 分片上传合并时可为空 |
| srv_send_msg | boolean | 否 | true=直接发送消息并占用主动消息频次，返回中包含消息 ID false=仅返回 file_info，用于后续发送消息接口的 media 字段 |
| file_name | string | 否 | 文件名（可选） |
| upload_id | string | 否 | 分片上传任务 ID。来自 UploadPrepare 响应的 upload_id， 传入后走分片上传合并路径，url 可为空 |
 
### 请求示例
 
URL 上传图片
 

```
POST /v2/users/A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4/files
{
  "file_type": 1,
  "url": "https://example.com/image.png",
  "srv_send_msg": false
}
```

分片上传合并
 

```
POST /v2/users/A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4/files
{
  "file_type": 2,
  "srv_send_msg": false,
  "file_name": "video.mp4",
  "upload_id": "upload_a1b2c3d4e5f6"
}
```

## 响应
 
### 响应体
                  
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| file_uuid | string | 文件唯一 ID |
| file_info | string | 文件信息，用于发送消息接口的 media.file_info 字段。 内部为序列化的二进制数据，开发者无需解析，直接透传即可 |
| ttl | integer | file_info 有效期（秒）。到期后需重新上传。 0 表示可长期使用 |
| id | string | 发送消息的唯一 ID。仅 srv_send_msg=true 时返回 |
| raw_url | string | 文件下载链接（COS 预签名 GET URL），有效期与 ttl 一致 仅分片上传合并（upload_id 路径）且 file_type 为图片/视频/语音时返回； URL 直传和文件类型(file_type=4)不返回此字段 |
 
## 响应示例
 
上传成功
 

```json
{
  "file_uuid": "uuid_a1b2c3d4e5f6",
  "file_info": "AE86C5D3F0E14B238C656C0F6DD1D0479C",
  "ttl": 300
}
```

### 错误码
                           
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 850018 | 群被禁言或者机器人被禁言 | 请检查机器人是否被禁言 |
| 850019 | 不支持的文件格式 | 请检查 file_type 是否正确 |
| 850026 | 下载原始文件失败 | 请检查 URL 是否可访问或重试 |
| 850031 | 上传文件超过大小限制 | 请减小文件大小 |
| 850027 | 发送数据超时 | 请稍后重试 |
| 10000 | 不支持的操作 | 请检查请求参数 |
| 40093001 | 文件上传失败，请重试 | 大文件分片上传中 BDH 通道异常，请重试 |
| 40093002 | 超过今天发送文件容量上限 | 请明天再试或减少文件大小 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_users_user_openid_files.post.html>


---

# 单聊富媒体预上传
 
单聊大文件分片上传前的准备工作。返回 upload_id、分片预签名 URL 和上传配置。
后续将文件按 block_size 分片，逐片 PUT 到预签名 URL，每片完成后调用分片完成接口。
 
大文件分片上传第一步。传入文件大小、MD5/SHA1 校验值，服务端返回 upload_id 和各分片预签名 URL。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/users/{user_id}/upload_prepare |
| HTTP Method | POST |
| 接口频率限制 | 10 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| user_id | string | 是 | 用户 OpenID |
 
## 请求体
                            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| file_type | integer | 是 | 业务类型。1=图片, 2=视频, 3=语音, 4=文件 |
| file_size | string | 是 | 文件大小（字节） |
| file_name | string | 是 | 文件名 |
| md5 | string | 是 | 整个文件的 MD5 |
| sha1 | string | 是 | 整个文件的 SHA1 |
| md5_10m | string | 是 | 文件前 10002432 字节（约 10MB）的 MD5 校验值 |
 
### 请求示例
 
预上传视频文件
 

```
POST /v2/users/A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4/upload_prepare
{
  "file_type": 2,
  "file_size": "31457280",
  "file_name": "demo.mp4",
  "md5": "d41d8cd98f00b204e9800998ecf8427e",
  "sha1": "da39a3ee5e6b4b0d3255bfef95601890afd80709",
  "md5_10m": "c4d8c5f3a2b1e0f9a8b7c6d5e4f3a2b1"
}
```

## 响应
 
### 响应体
               
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| upload_id | string | 上传任务 ID，后续分片上传和完成合并时需携带 |
| block_size | string | 分块大小（字节），默认 5MB。客户端按此大小对文件分片 |
| parts | []UploadPart | 分片列表，每个分片包含一个预签名上传 URL |
| upload_config | UploadConfig | 上传配置，由后台下发控制客户端上传行为 |
 
UploadPart
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| index | integer | 分片序号，从 0 开始 |
| presigned_url | string | 预签名上传 URL，客户端通过 HTTP PUT 将分片数据上传到此 URL |
| block_size | string | 该分块的大小（字节） |
 
UploadConfig
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| concurrency | integer | 上传并发数，默认 1 |
| retry_timeout | integer | 重试超时时间（秒），默认 300（5分钟） |
| retry_delay | integer | 重试延迟（秒），默认 1 |
 
## 响应示例
 
预上传成功（3 个分片）
 

```json
{
  "upload_id": "upload_a1b2c3d4e5f6",
  "block_size": "10485760",
  "parts": [
    {
      "index": 0,
      "presigned_url": "https://cos.example.com/upload?partNumber=1&sign=aaa",
      "block_size": "10485760"
    },
    {
      "index": 1,
      "presigned_url": "https://cos.example.com/upload?partNumber=2&sign=bbb",
      "block_size": "10485760"
    },
    {
      "index": 2,
      "presigned_url": "https://cos.example.com/upload?partNumber=3&sign=ccc",
      "block_size": "10485760"
    }
  ],
  "upload_config": {
    "concurrency": 1,
    "retry_timeout": 300,
    "retry_delay": 1
  }
}
```

### 错误码
                        
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 850018 | 群被禁言或者机器人被禁言 | 请检查机器人是否被禁言 |
| 850019 | 不支持的文件格式 | 请检查 file_type 是否正确 |
| 850026 | 下载原始文件失败 | 请检查 URL 是否可访问或重试 |
| 850031 | 上传文件超过大小限制 | 请减小文件大小 |
| 850027 | 发送数据超时 | 请稍后重试 |
| 10000 | 不支持的操作 | 请检查请求参数 |
| 40093001 | 文件上传失败，请重试 | 申请上传失败，请重试 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_users_user_id_upload_prepare.post.html>


---

# 单聊分片上传完成
 
通知服务端某个分片已上传完成。全部分片完成后，用 upload_id 作为 MediaUpload 的 upload_id 字段调一次上传接口完成合并
 
分片上传第二步。每个分片 PUT 到预签名 URL 成功后调用，通知服务端该分片已上传完成。
全部分片完成后，携带 upload_id 调用 /v2/users/{user_openid}/files 完成合并。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/users/{user_id}/upload_part_finish |
| HTTP Method | POST |
| 接口频率限制 | 10 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| user_id | string | 是 | 用户 OpenID |
 
## 请求体
                    
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| upload_id | string | 否 | 上传任务 ID |
| part_index | integer | 否 | 分片序号 |
| block_size | string | 否 | 分块大小（字节） |
| md5 | string | 否 | 分片 MD5 |
 
### 请求示例
 
通知分片 0 上传完成
 

```
POST /v2/users/A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4/upload_part_finish
{
  "upload_id": "upload_a1b2c3d4e5f6",
  "part_index": 0,
  "block_size": "10485760",
  "md5": "c4d8c5f3a2b1e0f9a8b7c6d5e4f3a2b1"
}
```

## 响应
 
无
 
## 响应示例
 
分片完成确认
 

```json
{}
```

### 错误码
                           
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 850018 | 群被禁言或者机器人被禁言 | 请检查机器人是否被禁言 |
| 850019 | 不支持的文件格式 | 请检查 file_type 是否正确 |
| 850026 | 下载原始文件失败 | 请检查 URL 是否可访问或重试 |
| 850031 | 上传文件超过大小限制 | 请减小文件大小 |
| 850027 | 发送数据超时 | 请稍后重试 |
| 10000 | 不支持的操作 | 请检查请求参数 |
| 40093001 | 文件上传失败，请重试 | 分片转存 BDH 通道异常，请重试 |
| 40093002 | 超过今天发送文件容量上限 | 请明天再试或减少文件大小 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_users_user_id_upload_part_finish.post.html>


---

# 群聊富媒体上传
 
上传图片/视频/语音到群聊，返回 file_info 用于发送消息接口的 media 字段。
srv_send_msg=true 时直接发送消息并占用主动消息频次；false 时仅返回 file_info。
用群接口上传的文件仅能发送到群聊。
文件类型与大小限制:
 - 1=图片(png/jpg): 软限制 20MB, 硬限制 200MB
 - 2=视频(mp4): 软限制 30MB, 硬限制 200MB
 - 3=语音(silk): 软限制 20MB, 硬限制 200MB
 - 4=文件: 软限制 200MB, 硬限制 200MB
超过软限制会降级为文件类型上传，超过硬限制会报错。

 
支持两种上传方式：
 1. URL 上传：传入 url，平台下载转存
 2. 分片上传合并：先通过 upload_prepare + upload_part_finish 完成分片上传，再携带 upload_id 调用本接口完成合并

 
推荐使用分片上传，流程如下：
 1. 调用 upload_prepare 获取 upload_id、block_size 和各分片预签名 URL
 2. 按 block_size 将文件分片，逐片 HTTP PUT 到对应的预签名 URL
 3. 每片 PUT 成功后调用 upload_part_finish 通知服务端该分片完成
 4. 全部分片完成后，携带 upload_id 调用本接口完成合并，返回 file_info

 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/files |
| HTTP Method | POST |
| 接口频率限制 | 50 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群 OpenID |
 
## 请求体
                        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| file_type | integer | 否 | 媒体类型。1=图片, 2=视频, 3=语音, 4=文件 图片支持 png/jpg，视频支持 mp4，语音支持 silk |
| url | string | 否 | 媒体资源的 URL，需以 http 开头，平台会下载并转存 分片上传合并时可为空 |
| srv_send_msg | boolean | 否 | true=直接发送消息并占用主动消息频次，返回中包含消息 ID false=仅返回 file_info，用于后续发送消息接口的 media 字段 |
| file_name | string | 否 | 文件名（可选） |
| upload_id | string | 否 | 分片上传任务 ID。来自 UploadPrepare 响应的 upload_id， 传入后走分片上传合并路径，url 可为空 |
 
### 请求示例
 
URL 上传图片
 

```
POST /v2/groups/B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5/files
{
  "file_type": 1,
  "url": "https://example.com/image.png",
  "srv_send_msg": false
}
```

分片上传合并
 

```
POST /v2/groups/B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5/files
{
  "file_type": 2,
  "srv_send_msg": false,
  "file_name": "video.mp4",
  "upload_id": "upload_a1b2c3d4e5f6"
}
```

## 响应
 
### 响应体
                  
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| file_uuid | string | 文件唯一 ID |
| file_info | string | 文件信息，用于发送消息接口的 media.file_info 字段。 内部为序列化的二进制数据，开发者无需解析，直接透传即可 |
| ttl | integer | file_info 有效期（秒）。到期后需重新上传。 0 表示可长期使用 |
| id | string | 发送消息的唯一 ID。仅 srv_send_msg=true 时返回 |
| raw_url | string | 文件下载链接（COS 预签名 GET URL），有效期与 ttl 一致 仅分片上传合并（upload_id 路径）且 file_type 为图片/视频/语音时返回； URL 直传和文件类型(file_type=4)不返回此字段 |
 
## 响应示例
 
上传成功
 

```json
{
  "file_uuid": "uuid_a1b2c3d4e5f6",
  "file_info": "AE86C5D3F0E14B238C656C0F6DD1D0479C",
  "ttl": 300
}
```

### 错误码
                           
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 850018 | 群被禁言或者机器人被禁言 | 请检查机器人是否被禁言 |
| 850019 | 不支持的文件格式 | 请检查 file_type 是否正确 |
| 850026 | 下载原始文件失败 | 请检查 URL 是否可访问或重试 |
| 850031 | 上传文件超过大小限制 | 请减小文件大小 |
| 850027 | 发送数据超时 | 请稍后重试 |
| 10000 | 不支持的操作 | 请检查请求参数 |
| 40093001 | 文件上传失败，请重试 | 大文件分片上传中 BDH 通道异常，请重试 |
| 40093002 | 超过今天发送文件容量上限 | 请明天再试或减少文件大小 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_files.post.html>


---

# 群聊富媒体预上传
 
大文件分片上传前的准备工作。返回 upload_id、分片预签名 URL 和上传配置。
后续将文件按 block_size 分片，逐片 PUT 到预签名 URL，每片完成后调用分片完成接口。
 
大文件分片上传第一步。传入文件大小、MD5/SHA1 校验值，服务端返回 upload_id 和各分片预签名 URL。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_id}/upload_prepare |
| HTTP Method | POST |
| 接口频率限制 | 10 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_id | string | 是 | 群 OpenID |
 
## 请求体
                            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| file_type | integer | 是 | 业务类型。1=图片, 2=视频, 3=语音, 4=文件 图片软限制 20MB, 视频软限制 30MB, 语音软限制 20MB, 文件软限制 200MB 超过软限制降级为文件类型，超过 200MB 硬限制报错 |
| file_size | string | 是 | 文件大小（字节） |
| file_name | string | 是 | 文件名 |
| md5 | string | 是 | 整个文件的 MD5 校验值 |
| sha1 | string | 是 | 整个文件的 SHA1 校验值 |
| md5_10m | string | 是 | 文件前 10002432 字节（约 10MB）的 MD5 校验值 |
 
### 请求示例
 
预上传视频文件
 

```
POST /v2/groups/B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5/upload_prepare
{
  "file_type": 2,
  "file_size": "31457280",
  "file_name": "demo.mp4",
  "md5": "d41d8cd98f00b204e9800998ecf8427e",
  "sha1": "da39a3ee5e6b4b0d3255bfef95601890afd80709",
  "md5_10m": "c4d8c5f3a2b1e0f9a8b7c6d5e4f3a2b1"
}
```

## 响应
 
### 响应体
               
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| upload_id | string | 上传任务 ID，后续分片上传和完成合并时需携带 |
| block_size | string | 分块大小（字节），默认 5MB。客户端按此大小对文件分片 |
| parts | []UploadPart | 分片列表，每个分片包含一个预签名上传 URL |
| upload_config | UploadConfig | 上传配置，由后台下发控制客户端上传行为 |
 
UploadPart
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| index | integer | 分片序号，从 0 开始 |
| presigned_url | string | 预签名上传 URL，客户端通过 HTTP PUT 将分片数据上传到此 URL |
| block_size | string | 该分块的大小（字节） |
 
UploadConfig
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| concurrency | integer | 上传并发数，默认 1 |
| retry_timeout | integer | 重试超时时间（秒），默认 300（5分钟） |
| retry_delay | integer | 重试延迟（秒），默认 1 |
 
## 响应示例
 
预上传成功（3 个分片）
 

```json
{
  "upload_id": "upload_a1b2c3d4e5f6",
  "block_size": "10485760",
  "parts": [
    {
      "index": 0,
      "presigned_url": "https://cos.example.com/upload?partNumber=1&sign=aaa",
      "block_size": "10485760"
    },
    {
      "index": 1,
      "presigned_url": "https://cos.example.com/upload?partNumber=2&sign=bbb",
      "block_size": "10485760"
    },
    {
      "index": 2,
      "presigned_url": "https://cos.example.com/upload?partNumber=3&sign=ccc",
      "block_size": "10485760"
    }
  ],
  "upload_config": {
    "concurrency": 1,
    "retry_timeout": 300,
    "retry_delay": 1
  }
}
```

### 错误码
                        
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 850018 | 群被禁言或者机器人被禁言 | 请检查机器人是否被禁言 |
| 850019 | 不支持的文件格式 | 请检查 file_type 是否正确 |
| 850026 | 下载原始文件失败 | 请检查 URL 是否可访问或重试 |
| 850031 | 上传文件超过大小限制 | 请减小文件大小 |
| 850027 | 发送数据超时 | 请稍后重试 |
| 10000 | 不支持的操作 | 请检查请求参数 |
| 40093001 | 文件上传失败，请重试 | 申请上传失败，请重试 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_id_upload_prepare.post.html>


---

# 群聊分片上传完成
 
通知服务端某个分片已上传完成。需在每片 PUT 成功后调用。全部分片完成后，用 upload_id 作为 MediaUpload 的 upload_id 字段调一次上传接口完成合并
 
分片上传第二步。每个分片 PUT 到预签名 URL 成功后调用，通知服务端该分片已上传完成。
全部分片完成后，携带 upload_id 调用 /v2/groups/{group_openid}/files 完成合并。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_id}/upload_part_finish |
| HTTP Method | POST |
| 接口频率限制 | 10 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_id | string | 是 | 群 OpenID |
 
## 请求体
                    
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| upload_id | string | 否 | 上传任务 ID，来自预上传响应 |
| part_index | integer | 否 | 分片序号，对应 UploadPart.index |
| block_size | string | 否 | 该分块的实际大小（字节） |
| md5 | string | 否 | 该分片的 MD5 校验值 |
 
### 请求示例
 
通知分片 0 上传完成
 

```
POST /v2/groups/B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5/upload_part_finish
{
  "upload_id": "upload_a1b2c3d4e5f6",
  "part_index": 0,
  "block_size": "10485760",
  "md5": "c4d8c5f3a2b1e0f9a8b7c6d5e4f3a2b1"
}
```

## 响应
 
无
 
## 响应示例
 
分片完成确认
 

```json
{}
```

### 错误码
                           
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 850018 | 群被禁言或者机器人被禁言 | 请检查机器人是否被禁言 |
| 850019 | 不支持的文件格式 | 请检查 file_type 是否正确 |
| 850026 | 下载原始文件失败 | 请检查 URL 是否可访问或重试 |
| 850031 | 上传文件超过大小限制 | 请减小文件大小 |
| 850027 | 发送数据超时 | 请稍后重试 |
| 10000 | 不支持的操作 | 请检查请求参数 |
| 40093001 | 文件上传失败，请重试 | 分片转存 BDH 通道异常，请重试 |
| 40093002 | 超过今天发送文件容量上限 | 请明天再试或减少文件大小 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_id_upload_part_finish.post.html>


---

#### 消息交互

# 消息交互概述
 
> **提示**
> 说明 在各种消息场景内，开发者可在消息体上实现自定义一些与用户的交互方式。
    
| 消息按钮 | 文字链 |
| --- | --- |
| ![消息按钮](https://qq-ai.cdn-go.cn/web/bot-docs/-/v1.28.0/assets/img/message-btn.94002609.jpg) | ![文字链](https://qq-ai.cdn-go.cn/web/bot-docs/-/v1.28.0/assets/img/text-chain.b2f9b0fb.jpg) |
 
## 消息按钮互动流程
 
消息按钮互动的整体流程如下：
 1. 发送带按钮的消息：机器人下发包含 `keyboard` 字段的消息，用户端看到消息底部挂载的按钮
 2. 用户点击按钮：平台推送 [`INTERACTION_CREATE`](/wiki/develop/api-v2/autogen/event/interaction_create.html) 事件给机器人
 3. 机器人响应互动：机器人调用 [PUT /interactions/{interaction_id}](/wiki/develop/api-v2/autogen/api/interactions_interaction_id.put.html) 回复用户

 
### 发送消息时携带 keyboard
 
在消息的 `keyboard` 字段中传入按钮配置，支持模板按钮和自定义按钮两种模式。
 - 发送单聊消息：[keyboard 字段参考](/wiki/develop/api-v2/autogen/api/v2_users_user_openid_messages.post.html#schema-keyboard)
 - 发送群聊消息：[keyboard 字段参考](/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_messages.post.html#schema-keyboard)

 
按钮数据示例（一处配置缓存一批按钮，动态提取生成行为按钮）：
 

```json
{
  "keyboard": {
    "id": "keyboard_id_xxx",
    "content": {
      "rows": [
        {
          "buttons": [
            {
              "id": "button_1",
              "render_data": {
                "label": "确认",
                "visited_label": "已确认",
                "style": 1
              },
              "action": {
                "type": 2,
                "permission": {
                  "type": 2,
                  "specify_role_ids": [],
                  "specify_user_ids": []
                },
                "click_limit": 1,
                "data": "/action_confirm",
                "at_bot_show_channel_list": false,
                "reply": true,
                "enter": true
              }
            }
          ]
        }
      ]
    }
  }
}
```

### 响应互动
 
收到 `INTERACTION_CREATE` 事件后，需要在规定时间内调用 [PUT /interactions/{interaction_id}](/wiki/develop/api-v2/autogen/api/interactions_interaction_id.put.html) 响应，否则会超时。
 
响应超时时间：指令回调类场景为 3 秒。建议收到事件后尽快响应，避免因超时导致用户侧无反馈。

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/message/trans/overview.html>


---

##### 按钮互动

# 互动事件
 
用户与机器人的互动操作触发此事件，包括消息按钮点击、快捷菜单回调、消息反馈、清空会话、进出故事集、切换模型、用户/群授权等。
收到事件后需调用 PUT /interactions/{interaction_id} 接口回应，否则客户端会一直 loading 直到超时。
 
仅 type=11（消息按钮）和 type=12（快捷菜单）需要调用 PUT /interactions/{interaction_id} 回应；其他类型（消息反馈、清空会话、进出故事集、切换模型、授权等）无需回应。同一 interaction_id 只能回应一次，超时后失效。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | INTERACTION_CREATE |
| Intent | INTERACTION (1<<26) |
 
### 事件体
                                          
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 事件 ID，用于被动消息发送和互动回调 |
| type | integer | 互动类型 11 - 消息按钮回调（INLINE_KEYBOARD）：用户点击消息中的内联键盘按钮 12 - 单聊快捷菜单回调（CALLBACK_COMMAND）：用户点击单聊场景下的自定义菜单 13 - 消息反馈（MESSAGE_FEEDBACK）：用户对智能体消息进行点赞/点踩反馈 14 - 清空会话（CLEAR_SESSION）：用户清空智能体会话历史 15 - 进出故事集（IN_OUT_STORY）：用户进入或退出故事集 16 - 切换模型（SWITCH_MODEL）：用户切换智能体模型 18 - 用户授权（USER_AUTHORIZE）：用户授权事件 19 - 群授权（GROUP_AUTHORIZE）：群授权事件 20 - 群授权状态变更（GROUP_AUTHORIZE_STATUS） |
| scene | string | 事件发生场景。c2c=单聊, group=群聊, guild=频道 |
| chat_type | integer | 聊天场景。0=频道, 1=群聊, 2=单聊 |
| timestamp | string | 触发时间，RFC3339 格式 |
| guild_id | string | 频道 OpenID（仅频道场景有值） |
| channel_id | string | 子频道 OpenID（仅频道场景有值） |
| user_openid | string | 用户 OpenID（仅单聊场景有值） |
| group_openid | string | 群 OpenID（仅群聊场景有值） |
| group_member_openid | string | 群成员 OpenID（仅群聊场景有值） |
| data | InteractionData | 互动数据 |
| version | integer | 版本号，默认 1 |
| application_id | string | 机器人 AppID |
 
InteractionData
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| type | integer | 互动数据类型，与外层 type 含义一致。11=消息按钮点击, 12=快捷菜单点击, 13=消息反馈点击, 14=清空会话点击, 15=故事集点击, 16=切换模型点击 |
| resolved | InteractionResolved | 解析后的互动数据 |
 
InteractionResolved
                                 
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| button_data | string | 按钮的 data 字段值（发送消息按钮时设置）；消息反馈场景下为回调数据 |
| button_id | string | 按钮的 id 字段值（发送消息按钮时设置） |
| user_id | string | 操作用户 ID（仅频道场景有值） |
| feature_id | string | 功能 ID（仅快捷菜单有值，管理端设置） |
| message_id | string | 操作的消息 ID（频道场景为消息 OpenID；消息反馈场景为机器人消息 ID） |
| feedback_opt | string | 反馈选项（仅 type=13 消息反馈）。LIKE=点赞, UNLIKE=点踩 |
| checked | integer | 反馈选项是否选中（仅 type=13 消息反馈） |
| action | string | 操作类型（type=15 故事集：ENTER_STORY=进入, QUIT_STORY=退出；type=16 切换模型：对应操作动作） |
| message_scene | InteractionMessageScene | 消息场景信息（仅 type=13 消息反馈） |
| authorize_data | AuthorizeData | 授权数据（仅 type=18/19 用户/群授权事件） |
 
InteractionMessageScene
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| ext | []string | 扩展信息键值对列表，如 "disable_net_search=1" 表示关闭联网搜索 |
 
AuthorizeData
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| opt_scene | string | 授权操作场景。setting=资料页设置, dialog=弹窗授权 |
| scope | string | 授权范围。c2c_push=C2C 主动消息推送, group_push=群主动消息推送 |
 
### 事件示例
 
示例1
 

```
{
  "application_id": "1904842048",
  "chat_type": 2,
  "data": {
    "resolved": {
      "button_data": "confirm:once",
      "button_id": "allow-once"
    },
    "type": 11
  },
  "id": "1b13d569-4610-4ab9-bc51-feecc5def6d4",
  "scene": "c2c",
  "timestamp": "2026-07-20T21:53:54+08:00",
  "type": 11,
  "user_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "version": 1
}
```

示例2
 

```
{
  "application_id": "101984245",
  "chat_type": 1,
  "data": {
    "resolved": {
      "button_data": "eyJjb21tYW5kIjogInNhbXBsZSJ9"
    },
    "type": 11
  },
  "group_member_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "group_openid": "B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5",
  "id": "06915133-7aef-46ed-94f7-c50939e285ae",
  "scene": "group",
  "timestamp": "2026-07-20T21:53:54+08:00",
  "type": 11,
  "version": 1
}
```

示例3
 

```
{
  "application_id": "102057050",
  "data": {
    "resolved": {
      "authorize_data": {
        "opt_scene": "setting",
        "scope": "c2c_push"
      }
    }
  },
  "id": "c30c003e-9454-4450-8e5e-665267c088c4",
  "scene": "c2c",
  "timestamp": "2026-07-20T21:54:38+08:00",
  "type": 18,
  "user_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "version": 1
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/interaction_create.html>


---

# 互动事件响应
 
收到 INTERACTION_CREATE 事件后需调用此接口回应，告知 QQ 后台事件已收到。
否则客户端会一直处于 loading 状态直到超时。
 
仅 type=11（消息按钮）和 type=12（快捷菜单）的互动事件需要调用此接口回应，其他类型无需回应（调用也不会报错）。需在事件触发的有效时间内回应，超时后 interaction_id 失效。同一 interaction_id 只能回应一次。code=0 时，对于 type=14（清空会话），后台会下发会话已清空小灰条提示用户。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /interactions/{interaction_id} |
| HTTP Method | PUT |
| 接口频率限制 | 50 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| interaction_id | string | 是 | 互动事件 ID，从 INTERACTION_CREATE 事件的 d.id 字段获取，注意该 ID 不带“INTERACTION_CREATE:”前缀 |
 
## 请求体
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| code | integer | 否 | 回调结果。0=成功, 1=操作失败, 2=操作频繁, 3=重复操作, 4=没有权限, 5=仅管理员操作 |
 
### 请求示例
 
互动事件响应
 

```
PUT /interactions/a1b2c3d4-e5f6-7890-abcd-ef1234567890
{
  "code": 0
}
```

## 响应
 
无
 
## 响应示例
 
成功
 

```json
{}
```

### 错误码
                           
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 630001 | param invalid | 请检查请求参数是否正确 |
| 630002 | get appid failed | 请检查 Authorization Header 是否正确 |
| 630003 | appid invalid | AppID 与 interaction_id 不匹配，请确认使用正确的 Bot Token |
| 630004 | set interaction data failed | 请稍后重试 |
| 630005 | get interaction data failed | 请稍后重试 |
| 630006 | get header appid failed | 请检查请求 Header |
| 630007 | data too large | 请减小请求体大小 |
| 630008 | interaction preprocess failed | 请检查请求参数 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/interactions_interaction_id.put.html>


---

# 文本交互
 
> **提示**
> 说明 QQBot 提供文本消息的交互能力，当开发者使用指定的格式发送消息，用户即可在消息体上进行点击交互操作，例如@某人，跳转链接等。
 
## 使用 @ 能力
 
> **提示**
> 说明 群聊&文字子频道，支持含有文本文字的消息类型，如：文本消息、图文消息、markdown 消息。
 1. @某人｜群聊、文字子频道可用

 
嵌入文本使用格式：`<qqbot-at-user id="" />`
协议：`<@userid>`即将弃用，请使用上述最新格式。
 
客户端展示为： @用户 标签
 1. @全部成员｜仅在文字子频道可用

 
嵌入文本使用格式：`<qqbot-at-everyone />`
协议：`@everyone`即将弃用，请使用上述最新格式。
 
客户端展示为： @全部成员 标签，需要机器人拥有发送 @全部成员 消息的权限，
 
## 指令操作
 
目前仅在 markdown 支持。
 
1. 回车指令格式（点击后，文本直接发送）
 
嵌入文本使用格式：
 
`<qqbot-cmd-enter text="xxx" />`
 
客户端展示为： /回车指令 用户可点击的标签，群聊和文字子频道不支持该能力。
 - `text` 用户点击后直接发送的文本，参数必填，最大限制 100 字符，传值时需要 urlencode。

 
2. 参数指令格式（点击后，文本插入输入框，用户自行编辑发送）
 
嵌入文本使用格式：
 
`<qqbot-cmd-input text="xxx" show="xxx" reference="false" />`
 
客户端展示为： /参数指令 用户可点击的标签
 - `text` 用户点击后插入输入框的文本，参数必填，最大限制 100 字符，传值时需要 urlencode。
 - `show` 用户在消息内看到的文本，参数选填，默认取 text 值，最大限制 100 字符，传值时需要 urlencode。
 - `reference` 插入输入框时是否带消息原文回复引用，参数选填，默认为 `false`，填入 `true` 时则带引用回复到输入框中。

 
## 跳转子频道
 
仅频道可用。
 
嵌入文本使用格式：`<#channel_id>`
 
客户端展示为： #XXX文字子频道 标签，点击可以跳转至子频道，仅支持当前频道内的子频道。
 
## 表情
 
仅频道可用，解析为系统表情。 具体表情id参考 [Emoji 列表](/wiki/develop/api-v2/openapi/emoji/model.html#Emoji 列表)。
 
嵌入文本使用格式：`<emoji:id>`
 - 仅支持 `type = 1` 的系统表情。
 - `type = 2` 的 emoji 表情直接按字符串填写即可。

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/message/trans/text-chain.html>


---

### 机器人

# 获取机器人详情
 
获取当前用户（机器人）的详情信息。
 - union_openid 和 union_user_account 需特殊申请并配置后才会返回
 - 这两个字段仅在单独拉取 member 信息时提供

 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /users/@me |
| HTTP Method | GET |
| 接口频率限制 | 50 QPS |
 
### 请求示例
 
获取当前用户信息
 

```
GET /users/@me
```

## 响应
 
### 响应体
                     
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 用户 ID |
| username | string | 用户名 |
| avatar | string | 头像 URL |
| bot | boolean | 是否为机器人 |
| union_openid | string | 跨应用统一用户 OpenID（需特殊申请） |
| union_user_account | string | 跨应用统一用户账号（需特殊申请） |
 
## 响应示例
 
获取当前用户信息成功
 

```json
{
  "id": "5777414462219517083",
  "username": "阳光小助手",
  "avatar": "https://thirdqq.qlogo.cn/g?b=oidb&k=AbCdEfGhIjKlMnOpQrStUv&kti=xyzABC&s=0&t=1781676795",
  "bot": true,
  "union_openid": "9F2E872045CCCC5948BEAF5B5FCCDF22",
  "union_user_account": "",
  "share_url": "https://qun.qq.com/qunpro/robot/qunshare?robot_uin=3889007780&robot_appid=102083127&biz_type=0",
  "welcome_msg": "欢迎加入我们的群聊"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/users_me.get.html>


---

# 获取机器人加入的频道列表
 
获取当前用户（机器人）所加入的频道列表，支持分页。
Bot Token 获取机器人数据，Bearer Token 获取用户数据。
 - limit 默认 100，最大 100

 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /users/@me/guilds |
| HTTP Method | GET |
| 接口频率限制 | 50 QPS |
 
### 查询参数
                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| before | string | 否 | 读取此 guild_id 之前的数据。设置时先反序再分页 |
| after | string | 否 | 读取此 guild_id 之后的数据。与 before 同时设置时 after 无效 |
| limit | integer | 否 | 每次拉取条数，默认 100，最大 100 |
 
### 请求示例
 
获取当前用户频道列表
 

```
GET /users/@me/guilds?limit=20
```

## 响应
 
### 响应体
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| guilds | []GuildInfo |  |
 
GuildInfo
                              
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 频道 ID |
| name | string | 频道名称 |
| icon | string | 频道头像 URL |
| owner_id | string | 频道创建者 ID |
| owner | boolean | 当前用户是否为频道创建者 |
| joined_at | string | 加入时间，ISO8601 格式 |
| member_count | integer | 频道成员数 |
| max_members | integer | 频道成员上限 |
| description | string | 频道简介 |
 
## 响应示例
 
获取机器人加入的频道列表成功
 

```json
[
  {
    "id": "2452178231489345741",
    "name": "读书分享会",
    "icon": "https://groupprohead.gtimg.cn/11259151665662004/40?t=1667468494556",
    "owner_id": "17481532452010052342",
    "owner": false,
    "joined_at": "2025-01-09T15:17:23+08:00",
    "member_count": 6,
    "max_members": 5000000,
    "description": "一起读书，共同成长"
  },
  {
    "id": "16038617105584902418",
    "name": "英语学习角",
    "icon": "https://groupprohead.gtimg.cn/76199361644746202/40?t=1655214551877",
    "owner_id": "12015059872407927338",
    "owner": false,
    "joined_at": "2026-05-12T20:39:33+08:00",
    "member_count": 35,
    "max_members": 5000000,
    "description": "分享英语学习资源，欢迎爱学习的伙伴来交流"
  },
  {
    "id": "9160663460093593400",
    "name": "早起打卡群",
    "icon": "https://groupprohead.gtimg.cn/89330271757059034/40?t=1781084183385",
    "owner_id": "1570904394246748593",
    "owner": true,
    "joined_at": "2026-05-15T10:57:07+08:00",
    "member_count": 13,
    "max_members": 10000,
    "description": "每天早起打卡，养成好习惯"
  }
]
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/users_me_guilds.get.html>


---

# 生成分享链接
 
生成机器人分享链接，用于邀请用户添加机器人为好友。
 
生成带自定义参数的机器人分享链接，用于邀请用户添加机器人为好友。用户通过该链接添加机器人时，callback_data 参数会透传给开发者。callback_data 最长 32 字符。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/generate_url_link |
| HTTP Method | POST |
| 接口频率限制 | 50 QPS |
 
## 请求体
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| url_link | string | 否 | 需要跳转的 URL |
 
### 请求示例
 
生成分享链接
 

```
POST /v2/generate_url_link
{
  "callback_data": "custom_data_123"
}
```

## 响应
 
### 响应体
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| url_link | string | 生成的分享链接 |
 
## 响应示例
 
生成分享链接成功
 

```json
{
  "url_link": "https://qun.qq.com/qunpro/robot/qunshare?robot_appid=1234567890&robot_uin=12345678&data=xxx"
}
```

### 错误码
                  
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 10001 | 请求参数异常 | 请检查请求参数是否正确 |
| 10002 | 请求头异常 | 请检查请求头是否正确 |
| 10003 | 查询机器人信息异常 | 请确认机器人是否存在 |
| 10044 | 从协议头获取uin失败 | 请检查 Authorization Header 是否正确 |
| 11004 | 生成分享ARK失败 | 请稍后重试 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_generate_url_link.post.html>


---

#### 自定义菜单与指令面板

# 查询全局自定义菜单
 
查询当前已设置的自定义菜单配置
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/menu |
| HTTP Method | GET |
| 接口频率限制 | 30 QPM |
 
### 请求示例
 
查询当前菜单
 

```
GET /v2/menu
```

## 响应
 
### 响应体
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| version | integer | 当前菜单的版本号 |
| menu | Menu | 当前生效的菜单配置。未设置过菜单时该字段为空 |
 
Menu
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| items | []MenuItem | 菜单项列表，最多 10 个，按列表顺序从左到右展示 |
 
MenuItem
                     
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| name | string | 按钮名称，最多 10 个字符，一个中文汉字算2个字符 |
| type | string | 按钮类型，可选值：switch（开关）、send_message（发送消息）、link（链接跳转）、menu（含子菜单的折叠项） |
| sub_menu_items | []SubMenuItem | 子菜单列表，仅 type=menu 时有效。子菜单最多 5 个，不支持再嵌套子菜单 |
| send_message | string | 发送的内容，仅 type=send_message 时有效。用户点击后该文本会自动填入聊天输入框 |
| link | string | 跳转链接 URL，仅 type=link 时有效。用户点击后跳转到该地址，链接必须以https://开头 |
| switch | Switch | 开关配置，仅 type=switch 时有效。定义开关的标识和默认状态 |
 
SubMenuItem
               
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| name | string | 按钮名称，最多 14 个字符，约7个中文汉字 |
| type | string | 按钮类型，可选值：send_message（发送消息）、link（链接跳转）。二级菜单不支持 menu 类型 |
| send_message | string | 发送的内容，仅 type=send_message 时有效。用户点击后该文本会自动填入聊天输入框 |
| link | string | 跳转链接 URL，仅 type=link 时有效。用户点击后跳转到该地址，链接必须以https://开头 |
 
Switch
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| switch_id | string | 开关唯一标识。用户切换开关状态后会发送一条消息，消息内容中会携带此字段。 例如 switch_id 为 "search" 时，用户打开开关后消息的ext字段中会携带 "search=1"的标识，关闭后不会携带这个标识 |
| default | boolean | 开关的初始状态。true 表示默认打开，false 表示默认关闭 |
 
## 响应示例
 
成功
 

```json
{
  "menu": {
    "items": [
      {
        "type": "send_message",
        "name": "帮助",
        "send_message": "/help"
      }
    ]
  },
  "version": 1
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_menu.get.html>


---

# 修改全局自定义菜单
 
修改自定义菜单。自定义菜单仅支持 C2C（单聊）场景，设置后对所有用户生效，不支持按用户维度区分
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/menu |
| HTTP Method | PUT |
| 接口频率限制 | 5 QPM |
 
## 请求体
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| menu | Menu | 否 | 菜单配置。传入后会覆盖原有的完整菜单配置 |
 
Menu
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| items | []MenuItem | 否 | 菜单项列表，最多 10 个，按列表顺序从左到右展示 |
 
MenuItem
                            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| name | string | 否 | 按钮名称，最多 10 个字符，一个中文汉字算2个字符 |
| type | string | 否 | 按钮类型，可选值：switch（开关）、send_message（发送消息）、link（链接跳转）、menu（含子菜单的折叠项） |
| sub_menu_items | []SubMenuItem | 否 | 子菜单列表，仅 type=menu 时有效。子菜单最多 5 个，不支持再嵌套子菜单 |
| send_message | string | 否 | 发送的内容，仅 type=send_message 时有效。用户点击后该文本会自动填入聊天输入框 |
| link | string | 否 | 跳转链接 URL，仅 type=link 时有效。用户点击后跳转到该地址，链接必须以https://开头 |
| switch | Switch | 否 | 开关配置，仅 type=switch 时有效。定义开关的标识和默认状态 |
 
SubMenuItem
                    
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| name | string | 否 | 按钮名称，最多 14 个字符，约7个中文汉字 |
| type | string | 否 | 按钮类型，可选值：send_message（发送消息）、link（链接跳转）。二级菜单不支持 menu 类型 |
| send_message | string | 否 | 发送的内容，仅 type=send_message 时有效。用户点击后该文本会自动填入聊天输入框 |
| link | string | 否 | 跳转链接 URL，仅 type=link 时有效。用户点击后跳转到该地址，链接必须以https://开头 |
 
Switch
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| switch_id | string | 否 | 开关唯一标识。用户切换开关状态后会发送一条消息，消息内容中会携带此字段。 例如 switch_id 为 "search" 时，用户打开开关后消息的ext字段中会携带 "search=1"的标识，关闭后不会携带这个标识 |
| default | boolean | 否 | 开关的初始状态。true 表示默认打开，false 表示默认关闭 |
 
### 请求示例
 
创建包含多种类型的菜单
 

```
{
  "menu": {
    "items": [
      {
        "type": "send_message",
        "name": "帮助",
        "send_message": "/help"
      },
      {
        "type": "link",
        "name": "官网",
        "link": "https://example.com"
      },
      {
        "type": "menu",
        "name": "更多",
        "sub_menu_items": [
          {
            "type": "send_message",
            "name": "设置",
            "send_message": "/settings"
          }
        ]
      }
    ]
  }
}
```

## 响应
 
### 响应体
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| version | integer | 本次修改后的菜单版本号，可用于后续判断配置是否有变更 |
 
## 响应示例
 
成功
 

```json
{
  "version": 1
}
```

### 错误码
                  
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 40030008 | URL 格式错误 | 确认 URL 以 https:// 开头 |
| 40030013 | 超出数量限制 | 请减少请求数量，具体限制值见返回信息中的 limit |
| 40030014 | 菜单类型不合法 | menu.type 仅支持 switch/send_message/link/menu |
| 40030016 | 必填字段缺失 | 检查必填字段是否全部正确传入 |
| 40030020 | 内容存在安全风险，请修改后重试 | 请检查菜单/面板内容是否包含敏感信息 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_menu.put.html>


---

# 查询指令面板列表
 
分页拉取指定场景下已生效的指令面板列表，按设置时间倒序排列。必须传入 scope 参数进行场景筛选
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/panels |
| HTTP Method | GET |
| 接口频率限制 | 30 QPM |
 
### 查询参数
                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| scope | string | 是 | 生效场景，可选值：c2c（单聊）、group（群聊）、channel（文字子频道）、dm（频道私信）。 按指定场景筛选面板列表 |
| cursor | string | 否 | 分页游标。首次请求不传或传空串，后续请求传入上次响应中的 next_cursor 值 |
| limit | integer | 否 | 每页拉取条数，默认 20，最大 50 |
 
### 请求示例
 
查询 c2c 场景面板（第一页）
 

```
GET /v2/panels?scope=c2c&limit=10
```

## 响应
 
### 响应体
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| records | []PanelRecord | 面板记录列表，按设置时间倒序排列 |
| next_cursor | string | 下一页游标。空串表示已到最后一页，无更多数据 |
| is_end | boolean | 是否已拉取到最后一页。true 表示无更多数据 |
 
PanelRecord
                        
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| panel_id | string | 面板 ID |
| scope | string | 生效场景，可选值：c2c（单聊）、group（群聊）、channel（文字子频道）、dm（频道私信） |
| target_type | string | 作用范围，可选值：all（全局配置）、specific（指定用户/群生效）。仅 c2c/group 场景可能为 specific |
| panel | Panel | 面板配置内容 |
| created_at | string | 面板创建时间，RFC3339 格式（如 2024-01-15T10:30:00Z） |
| updated_at | string | 面板更新时间，RFC3339 格式（如 2024-01-15T10:30:00Z） |
| version | integer | 面板版本号 |
 
Panel
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| items | []PanelItem | 面板元素列表，定义面板中展示的指令或链接项，一个指令面板里最多配置 20 个面板元素 |
| remark | string | 面板备注，用于开发者标记面板用途，最多 255 个字符，不对用户展示 |
| version | integer | 当前版本号 |
 
PanelItem
                  
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| name | string | 元素名称。type=command 时用户点击后该内容会填入聊天输入框；type=link 时仅用于面板展示 最多 14 个字符，约 7 个中文汉字 |
| desc | string | 元素描述，用于补充说明该指令或链接的功能，在面板中展示给用户 最多 30 个字符，约 15 个中文汉字 |
| type | string | 元素类型，可选值：command（指令）、link（链接跳转） |
| only_admin | boolean | 是否仅管理员可操作。true 时仅频道/群管理员可点击，false 时所有用户可点击 |
| link | string | 跳转链接 URL，仅 type=link 时有效。用户点击后在浏览器中打开该地址 |
 
## 响应示例
 
成功
 

```json
{
  "records": [
    {
      "panel_id": "p_102030405_x8k2",
      "scope": "c2c",
      "target_type": "all",
      "panel": {
        "items": [
          {
            "type": "command",
            "name": "查询天气",
            "desc": "查询当前天气"
          }
        ]
      },
      "version": 1
    }
  ],
  "next_cursor": "",
  "is_end": true
}
```

### 错误码
         
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 40030001 | 参数错误 | 检查请求参数是否正确 |
| 40030011 | 生效场景不合法 | scope 仅支持 c2c/group/channel/dm |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_panels.get.html>


---

# 创建指令面板
 
创建指令面板。支持 c2c（单聊）、group（群聊）、channel（文字子频道）、dm（频道私信）四种场景。其中 c2c 和 group 场景支持按指定用户或群生效（target_type=specific），channel 和 dm 场景仅支持全局配置（target_type=all）
 - 一个机器人最多创建 20 个指令面板

 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/panels |
| HTTP Method | POST |
| 接口频率限制 | 10 QPM |
 
## 请求体
                        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| scope | string | 是 | 生效场景，可选值：c2c（单聊）、group（群聊）、channel（文字子频道）、dm（频道私信）。 四种场景均支持创建面板，但 channel 和 dm 场景仅支持全局配置（target_type 只能为 all） |
| target_type | string | 否 | 作用范围，可选值：all（对该场景下所有用户/群生效）、specific（仅对指定用户/群生效）。 仅 c2c 和 group 场景支持 specific；channel 和 dm 场景只能传 all |
| user_openids | []string | 否 | 用户 openid 列表，仅 c2c 场景且 target_type=specific 时有效。 指定面板对这些用户生效，一次最多传 20 个。后续可通过「修改指令面板关联对象」接口增删 |
| group_openids | []string | 否 | 群 openid 列表，仅 group 场景且 target_type=specific 时有效。 指定面板对这些群生效，一次最多传 20 个。后续可通过「修改指令面板关联对象」接口增删 |
| panel | Panel | 是 | 面板配置内容，定义面板中展示的指令和链接项 |
 
Panel
                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| items | []PanelItem | 否 | 面板元素列表，定义面板中展示的指令或链接项，一个指令面板里最多配置 20 个面板元素 |
| remark | string | 否 | 面板备注，用于开发者标记面板用途，最多 255 个字符，不对用户展示 |
| version | integer | 否 | 当前版本号 |
 
PanelItem
                        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| name | string | 否 | 元素名称。type=command 时用户点击后该内容会填入聊天输入框；type=link 时仅用于面板展示 最多 14 个字符，约 7 个中文汉字 |
| desc | string | 否 | 元素描述，用于补充说明该指令或链接的功能，在面板中展示给用户 最多 30 个字符，约 15 个中文汉字 |
| type | string | 否 | 元素类型，可选值：command（指令）、link（链接跳转） |
| only_admin | boolean | 否 | 是否仅管理员可操作。true 时仅频道/群管理员可点击，false 时所有用户可点击 |
| link | string | 否 | 跳转链接 URL，仅 type=link 时有效。用户点击后在浏览器中打开该地址 |
 
### 请求示例
 
创建 c2c 全局面板
 

```
{
  "scope": "c2c",
  "target_type": "all",
  "panel": {
    "items": [
      {
        "type": "command",
        "name": "查询天气",
        "desc": "查询当前天气"
      },
      {
        "type": "link",
        "name": "更多服务",
        "link": "https://example.com"
      }
    ],
    "remark": "C2C面板"
  }
}
```

创建 group 指定群面板
 

```
{
  "scope": "group",
  "target_type": "specific",
  "group_openids": [
    "openid_group_001",
    "openid_group_002"
  ],
  "panel": {
    "items": [
      {
        "type": "command",
        "name": "群签到",
        "desc": "每日签到"
      }
    ]
  }
}
```

## 响应
 
### 响应体
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| panel_id | string | 新创建的面板 ID。后续修改、删除、查询详情均需使用此 ID |
 
## 响应示例
 
成功
 

```json
{
  "panel_id": "p_x8k2x8k2x8k2"
}
```

### 错误码
                                 
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 40030008 | URL 格式错误 | 确认 URL 以 https:// 开头 |
| 40030009 | 指令面板操作进行中，请稍后重试 | 存在并发操作冲突，请稍后重试 |
| 40030011 | 生效场景不合法 | scope 仅支持 c2c/group/channel/dm |
| 40030012 | 生效范围不合法 | target_type 仅支持 all/specific；channel/dm 场景仅支持 all |
| 40030013 | 超出数量限制 | 请减少请求数量，具体限制值见返回信息中的 limit |
| 40030015 | 面板元素类型不合法 | panel_item.type 仅支持 command/link |
| 40030016 | 必填字段缺失 | 检查必填字段是否全部正确传入 |
| 40030018 | 当前场景不支持此操作 | 检查 scope 是否支持当前操作 |
| 40030020 | 内容存在安全风险，请修改后重试 | 请检查菜单/面板内容是否包含敏感信息 |
| 40030021 | 全局面板不支持添加指定关联对象 | target_type=all 的面板不支持此操作，请使用 specific 模式 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_panels.post.html>


---

# 查询指令面板详情
 
查询指定指令面板的完整配置详情，包括面板内容、生效场景、生效范围，以及关联的用户或群 openid 列表
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/panels/{panel_id} |
| HTTP Method | GET |
| 接口频率限制 | 30 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| panel_id | string | 是 | 面板 ID |
 
### 请求示例
 
查询面板详情
 

```
GET /v2/panels/p_x8k2x8k2x8k2
```

## 响应
 
### 响应体
                              
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| panel_id | string | 面板 ID |
| scope | string | 生效场景，可选值：c2c（单聊）、group（群聊）、channel（文字子频道）、dm（频道私信） |
| target_type | string | 作用范围，可选值：all（全局配置）、specific（指定用户/群生效）。仅 c2c/group 场景可能为 specific |
| panel | Panel | 面板配置内容 |
| created_at | string | 面板创建时间，RFC3339 格式（如 2024-01-15T10:30:00Z） |
| updated_at | string | 面板更新时间，RFC3339 格式（如 2024-01-15T10:30:00Z） |
| version | integer | 面板版本号 |
| user_openids | []string | 关联的用户 openid 列表。仅 c2c 场景且 target_type=specific 时返回，最多 1000 条 |
| group_openids | []string | 关联的群 openid 列表。仅 group 场景且 target_type=specific 时返回，最多 1000 条 |
 
Panel
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| items | []PanelItem | 面板元素列表，定义面板中展示的指令或链接项，一个指令面板里最多配置 20 个面板元素 |
| remark | string | 面板备注，用于开发者标记面板用途，最多 255 个字符，不对用户展示 |
| version | integer | 当前版本号 |
 
PanelItem
                  
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| name | string | 元素名称。type=command 时用户点击后该内容会填入聊天输入框；type=link 时仅用于面板展示 最多 14 个字符，约 7 个中文汉字 |
| desc | string | 元素描述，用于补充说明该指令或链接的功能，在面板中展示给用户 最多 30 个字符，约 15 个中文汉字 |
| type | string | 元素类型，可选值：command（指令）、link（链接跳转） |
| only_admin | boolean | 是否仅管理员可操作。true 时仅频道/群管理员可点击，false 时所有用户可点击 |
| link | string | 跳转链接 URL，仅 type=link 时有效。用户点击后在浏览器中打开该地址 |
 
## 响应示例
 
成功
 

```json
{
  "panel_id": "p_x8k2x8k2x8k2",
  "scope": "group",
  "target_type": "specific",
  "panel": {
    "items": [
      {
        "type": "command",
        "name": "群签到",
        "desc": "每日签到"
      }
    ]
  },
  "version": 1,
  "user_openids": [],
  "group_openids": [
    "openid_group_001"
  ]
}
```

### 错误码
      
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 40030006 | 指令面板不存在 | 确认 panel_id 是否正确 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_panels_panel_id.get.html>


---

# 修改指令面板
 
修改指定指令面板的配置内容，包括面板元素列表和备注。不影响已关联的用户/群列表
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/panels/{panel_id} |
| HTTP Method | PUT |
| 接口频率限制 | 10 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| panel_id | string | 是 | 面板 ID |
 
## 请求体
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| panel | Panel | 是 | 面板配置内容。传入后会覆盖原有的面板元素列表和备注，不影响已关联的用户/群列表 |
 
Panel
                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| items | []PanelItem | 否 | 面板元素列表，定义面板中展示的指令或链接项，一个指令面板里最多配置 20 个面板元素 |
| remark | string | 否 | 面板备注，用于开发者标记面板用途，最多 255 个字符，不对用户展示 |
| version | integer | 否 | 当前版本号 |
 
PanelItem
                        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| name | string | 否 | 元素名称。type=command 时用户点击后该内容会填入聊天输入框；type=link 时仅用于面板展示 最多 14 个字符，约 7 个中文汉字 |
| desc | string | 否 | 元素描述，用于补充说明该指令或链接的功能，在面板中展示给用户 最多 30 个字符，约 15 个中文汉字 |
| type | string | 否 | 元素类型，可选值：command（指令）、link（链接跳转） |
| only_admin | boolean | 否 | 是否仅管理员可操作。true 时仅频道/群管理员可点击，false 时所有用户可点击 |
| link | string | 否 | 跳转链接 URL，仅 type=link 时有效。用户点击后在浏览器中打开该地址 |
 
### 请求示例
 
修改面板元素
 

```
{
  "panel": {
    "items": [
      {
        "type": "command",
        "name": "新指令",
        "desc": "更新后的指令"
      }
    ],
    "remark": "更新备注"
  }
}
```

## 响应
 
### 响应体
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| version | integer | 本次修改后的面板版本号 |
 
## 响应示例
 
成功
 

```json
{
  "version": 1
}
```

### 错误码
                              
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 40030006 | 指令面板不存在 | 确认 panel_id 是否正确 |
| 40030008 | URL 格式错误 | 确认 URL 以 https:// 开头 |
| 40030009 | 指令面板操作进行中，请稍后重试 | 存在并发操作冲突，请稍后重试 |
| 40030013 | 超出数量限制 | 请减少请求数量，具体限制值见返回信息中的 limit |
| 40030015 | 面板元素类型不合法 | panel_item.type 仅支持 command/link |
| 40030016 | 必填字段缺失 | 检查必填字段是否全部正确传入 |
| 40030018 | 当前场景不支持此操作 | 检查 scope 是否支持当前操作 |
| 40030020 | 内容存在安全风险，请修改后重试 | 请检查菜单/面板内容是否包含敏感信息 |
| 40030021 | 全局面板不支持添加指定关联对象 | target_type=all 的面板不支持此操作，请使用 specific 模式 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_panels_panel_id.put.html>


---

# 删除指令面板
 
删除指定的指令面板。删除后该面板不再对任何用户或群生效
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/panels/{panel_id} |
| HTTP Method | DELETE |
| 接口频率限制 | 10 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| panel_id | string | 是 | 面板 ID |
 
### 请求示例
 
删除面板
 

```
DELETE /v2/panels/p_x8k2x8k2x8k2
```

## 响应
 
无
 
## 响应示例
 
成功
 

```json
{}
```

### 错误码
      
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 40030006 | 指令面板不存在 | 确认 panel_id 是否正确 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_panels_panel_id.delete.html>


---

# 修改指令面板关联对象
 
对指定指令面板关联的用户或群进行添加或删除操作。c2c 场景操作用户 openid，group 场景操作群 openid。channel 和 dm 场景为全局配置，不支持此操作
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/panels/{panel_id}/target |
| HTTP Method | PUT |
| 接口频率限制 | 60 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| panel_id | string | 是 | 面板 ID |
 
## 请求体
                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| op | string | 是 | 操作类型，可选值：add（添加关联对象）、del（移除关联对象） |
| user_openids | []string | 否 | 用户 openid 列表，仅 c2c 场景有效，一次最多 20 个 |
| group_openids | []string | 否 | 群 openid 列表，仅 group 场景有效，一次最多 20 个 |
 
### 请求示例
 
添加群关联
 

```
{
  "op": "add",
  "group_openids": [
    "openid_group_003"
  ]
}
```

删除用户关联
 

```
{
  "op": "del",
  "user_openids": [
    "openid_user_001"
  ]
}
```

## 响应
 
无
 
## 响应示例
 
成功
 

```json
{}
```

### 错误码
               
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 40030013 | 超出数量限制 | 请减少请求数量，具体限制值见返回信息中的 limit |
| 40030017 | 操作类型不合法 | op 仅支持 add/del |
| 40030018 | 当前场景不支持此操作 | 检查 scope 是否支持当前操作 |
| 40030021 | 全局面板不支持添加指定关联对象 | target_type=all 的面板不支持此操作，请使用 specific 模式 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_panels_panel_id_target.put.html>


---

#### 事件

# 用户添加好友
 
通过传 scene_param 中的 callback_data 可区分不同来源的添加好友场景。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | FRIEND_ADD |
| Intent | GROUP_AND_C2C_EVENT (1<<25) |
 
### 事件体
                     
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| timestamp | integer | 添加时间戳（Unix 秒） |
| openid | string | 用户 OpenID |
| scene | integer | 加好友场景值。1000=缺省默认, 1001=网络搜索（全部tab）, 1002=网络搜索（机器人tab）, 1003=群场景, 1004=空间场景, 2001=站内分享资料页, 2002=站外分享资料页, 2003=开发者生成的分享链接（站内）, 2004=开发者生成的分享链接（站外） |
| scene_param | string | 开发者自定义的回调数据（callback_data），用于区分不同来源 |
| author | FriendAuthor | 用户信息 |
| short_code | string | 机器人分享链接的短链code |
 
FriendAuthor
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| union_openid | string | 用户统一 OpenID（跨应用标识） |
 
### 事件示例
 
用户添加好友（网络搜索场景）
 

```
{
  "openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "timestamp": 1784570523,
  "scene": 1001,
  "scene_param": "",
  "author": {
    "union_openid": "DB85A74E07BA08B5B44CD9ED332FCBD2"
  }
}
```

用户添加好友（开发者分享链接）
 

```
{
  "openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "timestamp": 1784570600,
  "scene": 2003,
  "scene_param": "callback_abc123",
  "author": {
    "union_openid": "DB85A74E07BA08B5B44CD9ED332FCBD2"
  }
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/friend_add.html>


---

# 用户删除好友
 
用户删除机器人好友时触发。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | FRIEND_DEL |
| Intent | GROUP_AND_C2C_EVENT (1<<25) |
 
### 事件体
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| timestamp | integer | 删除时间戳（Unix 秒） |
| openid | string | 用户 OpenID |
| author | FriendAuthor | 用户信息 |
 
FriendAuthor
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| union_openid | string | 用户统一 OpenID（跨应用标识） |
 
### 事件示例
 
用户删除好友
 

```
{
  "openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "timestamp": 1784570524
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/friend_del.html>


---

# 单聊消息接收开启
 
用户在机器人资料卡手动开启"主动消息"推送开关时触发。
 
用户在机器人资料卡手动开启主动消息推送开关时触发。开启后机器人可向该用户发送主动消息。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | C2C_MSG_RECEIVE |
| Intent | GROUP_AND_C2C_EVENT (1<<25) |
 
### 事件体
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| timestamp | integer | 操作时间戳（Unix 秒） |
| openid | string | 用户 OpenID |
 
### 事件示例
 
C2C消息接收开启
 

```
{
  "openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "timestamp": 1784570617
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/c2c_msg_receive.html>


---

# 单聊消息接收关闭
 
用户在机器人资料卡手动关闭"主动消息"推送时触发。
 
用户在机器人资料卡手动关闭主动消息推送时触发。关闭后机器人无法向该用户发送主动消息。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | C2C_MSG_REJECT |
| Intent | GROUP_AND_C2C_EVENT (1<<25) |
 
### 事件体
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| timestamp | integer | 操作时间戳（Unix 秒） |
| openid | string | 用户 OpenID |
 
### 事件示例
 
C2C消息接收关闭
 

```
{
  "openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "timestamp": 1784570599
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/c2c_msg_reject.html>


---

### 群聊管理

#### 接口

# 获取群基本信息
 
获取指定群的基本信息。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/info |
| HTTP Method | GET |
| 接口频率限制 | 30 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群OpenID |
 
### 请求示例
 
获取群信息
 

```
GET /v2/groups/3E5D8A1F7B2C9E4D6A0F1B3C5D7E9F2A/info
```

## 响应
 
### 响应体
                     
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| group_openid | string | 群 OpenID |
| group_name | string | 群名称 |
| group_finger_memo | string | 群简介 |
| group_class_text | string | 群分类 |
| group_tags | []string | 群标签列表 |
| group_member_num | integer | 群成员人数 |
 
## 响应示例
 
获取群信息
 

```json
{
  "group_openid": "3E5D8A1F7B2C9E4D6A0F1B3C5D7E9F2A",
  "group_name": "读书分享会",
  "group_finger_memo": "每周共读一本好书",
  "group_class_text": "文化",
  "group_tags": [
    "阅读",
    "文学",
    "成长"
  ],
  "group_member_num": 256
}
```

### 错误码
      
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 11253 | 应用无接口访问权限 | 该接口仅白名单机器人可用，请联系平台运营申请权限 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_info.get.html>


---

# 获取机器人群内状态
 
获取机器人在指定群中的状态信息。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/bot_state |
| HTTP Method | GET |
| 接口频率限制 | 30 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群OpenID |
 
### 请求示例
 
获取机器人群内状态
 

```
GET /v2/groups/3E5D8A1F7B2C9E4D6A0F1B3C5D7E9F2A/bot_state
```

## 响应
 
### 响应体
                  
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| member_openid | string | 机器人的 openid |
| joined_at | string | 入群时间戳（RFC3339格式） |
| allow_proactive_msg | boolean | 是否接收主动推送。true: 接受主动推送 |
| recv_msg_setting | string | 接受消息的类型：群内接收消息的设置：all、only_mention、mention_and_context |
| member_role | string | 群成员角色 member-普通成员，owner-群主，admin-管理员 |
 
## 响应示例
 
获取机器人群内状态
 

```json
{
  "member_openid": "7A3B9C1D5E2F4A6B8C0D1E3F5A7B9C2D",
  "joined_at": "2025-06-15T14:30:00+08:00",
  "allow_proactive_msg": false,
  "recv_msg_setting": "only_mention",
  "member_role": "member
}
```

### 错误码
      
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 11253 | 应用无接口访问权限 | 该接口仅白名单机器人可用，请联系平台运营申请权限 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_bot_state.get.html>


---

# 入群申请列表拉取
 
拉取入群申请列表，支持分页。
 
机器人需拥有群管理员身份。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/join_request_list |
| HTTP Method | GET |
| 接口频率限制 | 30 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群OpenID |
 
## 请求体
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| cursor | string | 否 | 分页游标，首次请求可不传或传空串 |
| limit | integer | 否 | 单页数量，默认 20，最大 50 |
 
### 请求示例
 

```
GET /v2/groups/30584554AA2BF4E72BD3B8F27A70339D/join_request_list
```

## 响应
 
### 响应体
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| list | []JoinRequest | 入群申请列表 |
| next_cursor | string | 下一页游标，空串表示已到末页 |
 
JoinRequest
                                 
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| join_request_id | string | 申请ID,需要在申请接口回传 |
| risk_tips | string | 安全提示语；可疑消息直接返回 warning_tips；普通消息命中 sec_risk_rules 时返回 top_tips |
| union_openid | string | 用户在应用/开放平台下的统一标识（如有） |
| member_openid | string | 申请人 openid |
| username | string | 申请人昵称 |
| apply_at | string | 申请时间戳（RFC3339 格式） |
| apply_source | string | 申请来源：self_apply 主动申请，invited 被邀请 |
| invited_by | string | 邀请人 openid（apply_source=invited 时有效） |
| bot | boolean | 是否为机器人账号 |
| verify_info | VerifyInfo | 用户入群验证方式 |
 
VerifyInfo
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| method | string | 入群验证方式：verify_message / admin_review_qa |
| verify_message | string | 验证消息内容；仅 auth_type=verify_message 时可能携带 |
| review_qa_list | []ReviewQA | 问答列表；仅 auth_type=admin_review_qa 时可能携带 |
 
ReviewQA
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| question | string | 管理员设置的问题 |
| answer | string | 申请人填写的答案 |
 
## 响应示例
 

```json
{
  "list": [
    {
      "join_request_id": "Ael-dmvlRdC9fZepnrfMhamsZgO103pSjmzwUz5SyyORaQMX-q0zkY3Q1caz71KiH2nJzehE-QWM-xCWzIsLg1i1vAPkdJfdPkUDVImXoiR8OY_s40J7OsFZGaEFUdDkIhAPs9uMXOxNpW91mGWQTlaFnmgksAxk",
      "risk_tips": "",
      "union_openid": "FE003FAF76C4817251FDC128A16753BB",
      "member_openid": "FE003FAF76C4817251FDC128A16753BB",
      "username": "痞孓小光光╮hw灰",
      "apply_at": "2026-08-05T14:19:09+08:00",
      "apply_source": "self_apply",
      "invited_by": "",
      "bot": false,
      "verify_info": {
        "method": "verify_message",
        "verify_message": "几款看看",
        "review_qa_list": []
      }
    }
  ],
  "next_cursor": "1785767153250497"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_join_request_list.get.html>


---

# 入群申请审批
 
审批入群申请：approve 通过，decline 拒绝。
 
机器人需拥有群管理员身份。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/approval_join_request/{member_openid} |
| HTTP Method | POST |
| 接口频率限制 | 60 QPM |
 
## 路径参数
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群OpenID |
| member_openid | string | 是 | 成员OpenID |
 
## 请求体
                    
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| op | string | 是 | 审批动作：approve 通过，decline 拒绝 |
| join_request_id | string | 否 | 申请ID |
| reject_reason | string | 否 | 拒绝理由，op=decline 时可填 |
| add_to_member_blacklist | boolean | 否 | 是否同时加入群黑名单，默认 false, action=decline 时可填 |
 
### 请求示例
 
通过用户审批
 

```
POST /v2/groups/30584554AA2BF4E72BD3B8F27A70339D/approval_join_request/FE003FAF76C4817251FDC128A16753BB
{
  "op": "approve",
  "join_request_id": "AURi8Rr6MfGdUNedupWf2uV5XiayURHaetzwGyOdrj6mHYOsfJFkbe9u8UjCMpLTxUouwr1SJ9IGEbxlbzDi43hPS4rw64G4i2Y4nL4DTH50U15xKPZYRsXPB7WUxZOUdceNSAv_GJtO4ffSrVZIhQxknoPD2SDT"
}
```

拒绝并拉黑
 

```
POST /v2/groups/30584554AA2BF4E72BD3B8F27A70339D/approval_join_request/FE003FAF76C4817251FDC128A16753BB
{
  "op": "decline",
  "join_request_id": "AVKiFWpdy0-q0rfCkpQFbWB9GvX7QPIe9hlsbVeO6TiurrZw1DHP0sXGnbUR4Xm79tKNpfl4zZynxeibVwwUD6h96RqiFB-4V6p5FKGXfqInOuQQSf5WwXr8lyIsn6yeaMwEI1KSuTTMBMNe6WN8bDtKg2REXTcF",
  "reject_reason": "示例拒绝：机器人自动拒绝",
  "add_to_member_blacklist": true
}
```

## 响应
 
无
 
## 响应示例
 

```json
{}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_approval_join_request_member_openid.post.html>


---

# 查询群禁言状态
 
查询群禁言状态，包含全员禁言模式与成员级禁言列表。
 
机器人需拥有群管理员身份。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/restrict_chat_setting |
| HTTP Method | GET |
| 接口频率限制 | 30 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群OpenID |
 
### 请求示例
 
查询群内有禁言状态
 

```
GET /v2/groups/30584554AA2BF4E72BD3B8F27A70339D/restrict_chat_setting

{}
```

## 响应
 
### 响应体
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| global_rule | GlobalMuteRule | 群级禁言规则（全员禁言配置） |
| members | []MemberMuteState | 当前处于禁言中的用户列表（不含已过期） |
 
GlobalMuteRule
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| mode | string | 全员禁言模式：none 未开启，always 始终禁言，schedule 定时禁言(定时和周期性) |
| schedule_rules | []MuteScheduleRule | 定时禁言规则列表（可包含多条） |
| recurring_rules | []MuteRecurringRule | 周期禁言规则列表（可包含多条） |
 
MuteScheduleRule
               
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| task_id | string | 任务ID，用于标记此定时禁言任务 |
| start_at | string | 禁言开始时间（RFC3339 格式） |
| end_at | string | 禁言结束时间（RFC3339 格式） |
| enabled | boolean | 此规则是否启用 |
 
MuteRecurringRule
                  
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| task_id | string | 任务ID，用于标记此周期禁言规则 |
| weekdays | []integer | 生效星期几列表，取值 1~7（1=周一，7=周日），可多选 |
| start_time | string | 时段开始时间，格式 HH:mm（北京时间） |
| end_time | string | 时段结束时间，格式 HH:mm（北京时间）；若小于 start_time 表示跨天到次日 |
| enabled | boolean | 此规则是否启用 |
 
MemberMuteState
               
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| member_openid | string | 被禁言成员的 openid |
| mute_expire_at | string | 禁言到期时间（RFC3339 格式） |
| username | string | 被禁言成员的昵称 |
| union_openid | string | 用户在应用/开放平台下的统一标识（如有） |
 
## 响应示例
 

```json
{
  "global_rule": {
    "mode": "schedule",
    "schedule_rules": [
      {
        "task_id": "task_7ffd5d31e2b37c1c872acb51",
        "start_at": "2026-07-22T10:44:00+08:00",
        "end_at": "2026-07-22T11:44:00+08:00",
        "enabled": false
      },
      {
        "task_id": "task_e9ca43ca9a31b539d824639c",
        "start_at": "2026-07-22T10:54:00+08:00",
        "end_at": "2026-07-22T11:54:00+08:00",
        "enabled": false
      }
    ],
    "recurring_rules": [
      {
        "task_id": "task_3a6348b8fb04bbc48b8a8709",
        "weekdays": [
          1,
          2,
          3,
          4,
          5,
          6,
          7
        ],
        "start_time": "13:05",
        "end_time": "14:05",
        "enabled": true
      }
    ]
  },
  "members": [
    {
      "member_openid": "EC58D87F598C8294A533B9D458DAAF33",
      "mute_expire_at": "2026-08-05T11:23:04+08:00",
      "username": "T小不点101",
      "union_openid": "EC58D87F598C8294A533B9D458DAAF33"
    }
  ]
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_restrict_chat_setting.get.html>


---

# 设置群成员禁言
 
设置群成员级禁言。
 
机器人需拥有群管理员身份，最大禁言时长为 30 天。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/restrict_chat_setting |
| HTTP Method | POST |
| 接口频率限制 | 60 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群OpenID |
 
## 请求体
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| members | []SetMemberMuteState | 否 | 用户禁言列表；每项通过 op 控制增/改/删， 单次设置不能超过 20 个 |
 
SetMemberMuteState
                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| op | string | 是 | 操作类型：add 增加禁言，update 更新禁言到期时间，del 解除禁言 |
| member_openid | string | 是 | 注意：增加/更新时，只能操作普通成员，不能操作群主，管理员，机器人 被禁言成员的 openid |
| mute_expire_at | string | 否 | 禁言到期时间（RFC3339 格式）；op=del 时可传空串表示立即解除禁言 |
 
### 请求示例
 
**禁言指定用户 **
 

```
POST /v2/groups/30584554AA2BF4E72BD3B8F27A70339D/restrict_chat_setting

{
    "members": [
        {
            "op": "add",
            "member_openid": "EC58D87F598C8294A533B9D458DAAF33",
            "mute_expire_at": "2026-08-05T11:23:05+08:00"
        }
    ]
}
```

## 响应
 
无
 
## 响应示例
 

```json
{}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_restrict_chat_setting.post.html>


---

##### 入群自动审批

# 查询入群自动审批策略列表
 
查询当前生效中的策略列表，按创建时间倒序，支持分页。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/join_approval_strategy |
| HTTP Method | GET |
| 接口频率限制 | 60 QPM |
 
## 请求体
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| cursor | string | 否 | 分页游标，首次请求可不传或传空串 |
| limit | integer | 否 | 单页数量，默认 20，最大 50 |
 
### 请求示例
 

```
GET /v2/groups/join_approval_strategy

{}
```

## 响应
 
### 响应体
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| strategies | []JoinApprovalStrategy | 生效中的策略列表 |
| next_cursor | string | 下一页游标，空串表示已到末页 |
 
JoinApprovalStrategy
                              
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| strategy_id | string | 策略 ID |
| group_openids | []string | 关联的群 openid 列表（创建时使用 group_openids 时返回） |
| group_ids | array | 关联的 QQ 群号列表（创建时使用 group_ids 时返回） |
| whitelist_user_count | integer | 白名单中的号码数量（估算，可能存在少量误差） |
| is_enable | string | 策略是否启用，on-启用 off-关闭 |
| expire_at | string | 过期时间（RFC3339 格式） |
| created_at | string | 创建时间（RFC3339 格式） |
| updated_at | string | 最近更新时间（RFC3339 格式） |
| remark | string | 策略备注 |
 
## 响应示例
 

```json
{
  "strategies": [
    {
      "strategy_id": "st_d83eca11e9",
      "group_openids": [],
      "group_ids": [],
      "whitelist_user_count": 2,
      "is_enable": "on",
      "expire_at": "2027-08-05T15:30:16+08:00",
      "created_at": "2026-08-05T15:30:16+08:00",
      "updated_at": "2026-08-05T15:45:28+08:00"
    },
    {
      "strategy_id": "st_7c0b77d442",
      "group_openids": [],
      "group_ids": [
        "10****499"
      ],
      "whitelist_user_count": 0,
      "is_enable": "on",
      "expire_at": "2027-08-04T11:20:40+08:00",
      "created_at": "2026-08-04T11:20:40+08:00",
      "updated_at": "2026-08-04T11:20:40+08:00"
    },
    {
      "strategy_id": "st_42cc272536",
      "group_openids": [],
      "group_ids": [
        "26****763",
        "26****978"
      ],
      "whitelist_user_count": 3,
      "is_enable": "on",
      "expire_at": "2027-07-31T11:40:21+08:00",
      "created_at": "2026-07-31T11:40:21+08:00",
      "updated_at": "2026-08-05T14:28:37+08:00"
    }
  ],
  "next_cursor": ""
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_join_approval_strategy.get.html>


---

# 创建入群自动审批策略
 
创建入群自动审批策略，指定关联群号。strategy_id 由服务端生成。一个机器人最多 20 个策略。
 
设置的规则只有当机器人需拥有群管理员身份时，才会生效会运行。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/join_approval_strategy |
| HTTP Method | POST |
| 接口频率限制 | 60 QPM |
 
## 请求体
                        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openids | []string | 否 | group_openids 与 group_ids 二选一必填，同时传入或均未传入均返回错误 关联的群 openid 列表，最多 100 个；与 group_ids 互斥 |
| group_ids | array | 否 | 关联的 QQ 群号列表（uint64），最多 100 个；与 group_openids 互斥 |
| is_enable | string | 否 | 是否启用策略，on-启用 off-关闭，默认 on |
| expire_at | string | 否 | 过期时间（RFC3339 格式）；不传默认一年过期 |
| remark | string | 否 | 策略备注，最多 255 个汉字，不必填 |
 
### 请求示例
 

```
POST /v2/groups/join_approval_strategy

{"group_openids":["\u003cxxxxxxxx1","xxxxx2\u003e"],"is_enable":"on","expire_at":""}
```

## 响应
 
### 响应体
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| strategy_id | string | 服务端生成的策略 ID |
| is_enable | string | 是否启用，on-启用 off-关闭 |
| expire_at | string | 过期时间（RFC3339 格式） |
 
## 响应示例
 

```json
{
  "strategy_id": "st_d83eca11e9",
  "is_enable": "on",
  "expire_at": "2027-08-05T15:30:16+08:00"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_join_approval_strategy.post.html>


---

# 修改入群自动审批策略
 
修改策略的生效状态、失效时间或增删关联群。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/join_approval_strategy/{strategy_id} |
| HTTP Method | PATCH |
| 接口频率限制 | 60 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| strategy_id | string | 是 | 策略 ID |
 
## 请求体
                    
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| is_enable | string | 否 | 是否启用策略，on-启用 off-关闭 |
| expire_at | string | 否 | 过期时间（RFC3339 格式） |
| group_action | GroupAction | 否 | 关联群增删操作；群标识形式须与创建时一致 |
| remark | string | 否 | 策略备注，最多 255 个汉字，不必填 |
 
GroupAction
                
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| op | string | 是 | 操作类型：add 新增关联群，del 删除关联群 |
| group_openids | []string | 否 | 待操作的群 openid 列表；与 group_ids 互斥 |
| group_ids | array | 否 | 待操作的 QQ 群号列表（uint64）；与 group_openids 互斥 |
 
### 请求示例
 
停用规则
 

```
PATCH /v2/groups/join_approval_strategy/st_d83eca11e9

 {"is_enable":"off"}
```

增加群OpenID
 

```
 {"group_action":{"op":"add","group_openids":["aBCsdfasd"]}}
```

## 响应
 
### 响应体
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| is_enable | string | 是否启用，on-启用 off-关闭 |
| expire_at | string | 过期时间（RFC3339 格式） |
 
## 响应示例
 
停用规则
 

```json
{
  "is_enable": "off",
  "expire_at": "2027-08-05T15:30:16+08:00"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_join_approval_strategy_strategy_id.patch.html>


---

# 删除入群自动审批策略
 
删除指定的入群自动审批策略。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/join_approval_strategy/{strategy_id} |
| HTTP Method | DELETE |
| 接口频率限制 | 60 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| strategy_id | string | 是 | 策略 ID |
 
### 请求示例
 

```
DELETE /v2/groups/join_approval_strategy/st_d83eca11e9

{}
```

## 响应
 
无
 
## 响应示例
 

```json
{}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_join_approval_strategy_strategy_id.delete.html>


---

# 执行入群自动审批策略
 
对策略关联的全部群发起全量扫描，命中白名单号码的入群申请自动审批通过。异步执行，约 10 分钟完成。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/join_approval_strategy/{strategy_id}/execute |
| HTTP Method | POST |
| 接口频率限制 | 60 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| strategy_id | string | 是 | 策略 ID |
 
### 请求示例
 

```
POST /v2/groups/join_approval_strategy/st_d83eca11e9/execute
{}
```

## 响应
 
无
 
## 响应示例
 

```json
{}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_join_approval_strategy_strategy_id_execute.post.html>


---

# 修改入群自动审批策略的白名单号码
 
对指定策略批量新增或删除白名单 QQ 号码，单次最多 10000 个，号码上限 10W。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/join_approval_strategy/{strategy_id}/whitelist_users |
| HTTP Method | POST |
| 接口频率限制 | 60 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| strategy_id | string | 是 | 策略 ID |
 
## 请求体
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| op | string | 是 | 操作类型：add 新增号码，del 删除号码 |
| whitelist_users | []string | 是 | QQ 号码列表，单次最多 10000 个；使用字符串类型避免 JS 精度问题 |
 
### 请求示例
 
添加白名单
 

```
POST /v2/groups/join_approval_strategy/st_d83eca11e9/whitelist_users

{"op":"add","whitelist_users":["1234567","1234568"]}
```

## 响应
 
### 响应体
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| strategy_id | string | 策略 ID |
| whitelist_user_count | integer | 操作后策略当前白名单号码数（估算） |
| updated_at | string | 策略更新时间（RFC3339 格式） |
 
## 响应示例
 

```json
{
  "strategy_id": "st_d83eca11e9",
  "whitelist_user_count": 2,
  "updated_at": "2026-08-05T15:45:28+08:00"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_join_approval_strategy_strategy_id_whitelist_users.post.html>


---

##### 群成员管理

# 获取群成员列表
 
获取群成员列表，每次最多返回 30 条，支持分页。
 
该能力正在内邀接入中，敬请期待
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/members |
| HTTP Method | GET |
| 接口频率限制 | 60 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群OpenID |
 
## 请求体
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| cursor | string | 否 | 分页游标，首次请求可不传或传空串；后续传上一次响应的 next_cursor |
 
### 请求示例
 

```
GET /v2/groups/3E5D8A1F7B2C9E4D6A0F1B3C5D7E9F2A/members?cursor=
```

## 响应
 
### 响应体
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| members | []Member | 成员列表，每次最多返回 30 条 |
| next_cursor | string | 下一页游标，空串表示已到末页 |
 
Member
                     
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| member_openid | string | 成员 OpenID |
| username | string | 用户昵称 |
| member_role | string | 群成员角色 member-普通成员，owner-群主，admin-管理员 |
| bot | boolean | 是否机器人 |
| joined_at | string | 入群时间戳（RFC3339格式） |
| union_openid | string | 用户在应用/开放平台下的统一标识（如有） |
 
## 响应示例
 

```json
{
    "members": [
        {
            "member_openid": "7A3B9C1D5E2F4A6B8C0D1E3F5A7B9C2D",
            "username": "阳光小助手",
            "member_role": "member",
            "bot": false,
            "joined_at": "2025-08-20T09:15:00+08:00",
            "union_openid": "9F2E872045CCCC5948BEAF5B5FCCDF22"
        },
        {
            "member_openid": "EC58D87F598C8294A533B9D458DAAF33",
            "username": "T小不点101",
            "member_role": "member",
            "bot": false,
            "joined_at": "2025-07-01T10:30:00+08:00",
            "union_openid": "FE003FAF76C4817251FDC128A16753BB"
        }
    ],
    "next_cursor": "bG1fNmIxOTM1NTRjNy4zMA"
}
```

### 错误码
      
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 11253 | 应用无接口访问权限 | 该接口仅白名单机器人可用，请联系平台运营申请权限 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_members.get.html>


---

# 获取群成员信息
 
获取指定群成员的详细信息。
 
该能力正在内邀接入中，敬请期待
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/members/{member_openid} |
| HTTP Method | GET |
| 接口频率限制 | 30 QPM |
 
## 路径参数
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群OpenID |
| member_openid | string | 是 | 成员OpenID |
 
### 请求示例
 
获取群成员信息
 

```
GET /v2/groups/3E5D8A1F7B2C9E4D6A0F1B3C5D7E9F2A/members/7A3B9C1D5E2F4A6B8C0D1E3F5A7B9C2D
```

## 响应
 
### 响应体
                     
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| member_openid | string | 成员 OpenID |
| username | string | 用户昵称 |
| member_role | string | 群成员角色 member-普通成员，owner-群主，admin-管理员 |
| bot | boolean | 是否机器人 |
| joined_at | string | 入群时间戳（RFC3339格式） |
| union_openid | string | 用户在应用/开放平台下的统一标识（如有） |
 
## 响应示例
 
获取群成员信息
 

```json
{
  "member_openid": "7A3B9C1D5E2F4A6B8C0D1E3F5A7B9C2D",
  "username": "小明",
  "member_role": "admin",
  "bot": false,
  "joined_at": "2025-08-20T09:15:00+08:00",
  "union_openid": "B4C6D8E0F2A4B6C8D0E2F4A6B8C0D2E4"
}
```

### 错误码
      
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 11253 | 应用无接口访问权限 | 该接口仅白名单机器人可用，请联系平台运营申请权限 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_members_member_openid.get.html>


---

# 群成员批量移除
 
批量移除群成员，单次最多 20 个，可选择同时加入黑名单。
 
该能力正在内邀接入中，敬请期待
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/batch_remove_members |
| HTTP Method | POST |
| 接口频率限制 | 30 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群OpenID |
 
## 请求体
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| member_openids | []string | 是 | 需要移除的成员 member_openid 列表，单次最多 20 个 |
| add_to_member_blacklist | boolean | 否 | 是否同时加入群黑名单，默认 false |
 
### 请求示例
 

```
POST /v2/groups/3E5D8A1F7B2C9E4D6A0F1B3C5D7E9F2A/batch_remove_members
{
    "member_openids": [
        "7A3B9C1D5E2F4A6B8C0D1E3F5A7B9C2D"
    ]
}
```

## 响应
 
### 响应体
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| remove_members_result | string | 成功时返回 success |
| add_to_member_blacklist_fail_openids | []string | 拉黑失败的 openid |
 
## 响应示例
 

```json
{
    "remove_members_result": "success",
    "add_to_member_blacklist_fail_openids": []
}
```

### 错误码
      
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 11253 | 应用无接口访问权限 | 该接口仅白名单机器人可用，请联系平台运营申请权限 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_batch_remove_members.post.html>


---

# 群黑名单查询
 
查询群黑名单列表，支持分页。
 
该能力正在内邀接入中，敬请期待
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/member_blacklist |
| HTTP Method | GET |
| 接口频率限制 | 30 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群OpenID |
 
## 请求体
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| cursor | string | 否 | 分页游标，首次请求可不传或传空串 |
| limit | integer | 否 | 单页数量，默认 20，最大 100 |
 
### 请求示例
 
群黑名单查询
 

```
GET /v2/groups/3E5D8A1F7B2C9E4D6A0F1B3C5D7E9F2A/member_blacklist
```

## 响应
 
### 响应体
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| users | []BlacklistUser | 黑名单用户列表 |
| next_cursor | string | 下一页游标，空串表示已到末页 |
 
BlacklistUser
                  
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| union_openid | string | 用户在应用/开放平台下的统一标识（如有） |
| member_openid | string | 用户 openid |
| username | string | 用户昵称 |
| banned_at | string | 拉黑时间戳（RFC3339 格式） |
| bot | boolean | 是否为机器人账号 |
 
## 响应示例
 
获取群黑名单列表成功
 

```json
{
  "users": [
    {
      "union_openid": "9F2E872045CCCC5948BEAF5B5FCCDF22",
      "member_openid": "7A3B9C1D5E2F4A6B8C0D1E3F5A7B9C2D",
      "username": "阳光少年",
      "banned_at": "2025-07-01T10:30:00+08:00",
      "bot": false
    }
  ],
  "next_cursor": ""
}
```

### 错误码
      
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 11253 | 应用无接口访问权限 | 该接口仅白名单机器人可用，请联系平台运营申请权限 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_member_blacklist.get.html>


---

# 群黑名单操作
 
群黑名单操作，只有在目标用户不在群中时才能加入群黑名单。
 
该能力正在内邀接入中，敬请期待
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /v2/groups/{group_openid}/member_blacklist |
| HTTP Method | POST |
| 接口频率限制 | 60 QPM |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| group_openid | string | 是 | 群OpenID |
 
## 请求体
            
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| op | string | 是 | 操作类型：del 移出黑名单, add 加入黑名单（目标成员在群中时无法加入黑名单） |
| member_openids | []string | 是 | 目标成员 openid 列表，单次最多 20 个 |
 
### 请求示例
 
添加群黑名单
 

```
POST /v2/groups/3E5D8A1F7B2C9E4D6A0F1B3C5D7E9F2A/member_blacklist
{
  "op": "add",
  "member_openids": [
    "7A3B9C1D5E2F4A6B8C0D1E3F5A7B9C2D"
  ]
}
```

移出群黑名单
 

```
POST /v2/groups/3E5D8A1F7B2C9E4D6A0F1B3C5D7E9F2A/member_blacklist
{
  "op": "del",
  "member_openids": [
    "7A3B9C1D5E2F4A6B8C0D1E3F5A7B9C2D"
  ]
}
```

## 响应
 
### 响应体
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| fail_openids | []string | op=add 时返回拉黑失败的 openid 列表；op=del 时同义 |
 
## 响应示例
 
操作群黑名单成功
 

```json
{
    "fail_openids": []
}
```

### 错误码
      
| 错误码 | 描述 | 排查建议 |
| --- | --- | --- |
| 11253 | 应用无接口访问权限 | 该接口仅白名单机器人可用，请联系平台运营申请权限 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/v2_groups_group_openid_member_blacklist.post.html>


---

#### 事件

# 机器人加入群聊
 
机器人被添加到群聊时触发。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | GROUP_ADD_ROBOT |
| Intent | GROUP_AND_C2C_EVENT (1<<25) |
 
### 事件体
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| timestamp | integer | 加入时间戳（Unix 秒） |
| group_openid | string | 群 OpenID |
| op_member_openid | string | 操作添加机器人进群的群成员 OpenID |
 
### 事件示例
 
机器人加入群聊
 

```
{
  "group_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "op_member_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "timestamp": 1784570534
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/group_add_robot.html>


---

# 机器人退出群聊
 
机器人被移出群聊时触发。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | GROUP_DEL_ROBOT |
| Intent | GROUP_AND_C2C_EVENT (1<<25) |
 
### 事件体
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| timestamp | integer | 移除时间戳（Unix 秒） |
| group_openid | string | 群 OpenID |
| op_member_openid | string | 操作移除机器人退群的群成员 OpenID |
 
### 事件示例
 
机器人退出群聊
 

```
{
  "group_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "op_member_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "timestamp": 1784570535
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/group_del_robot.html>


---

# 群聊消息接收开启
 
群管理员在机器人资料页操作开启通知时触发。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | GROUP_MSG_RECEIVE |
| Intent | GROUP_AND_C2C_EVENT (1<<25) |
 
### 事件体
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| timestamp | integer | 操作时间戳（Unix 秒） |
| group_openid | string | 群 OpenID |
| op_member_openid | string | 操作群成员 OpenID |
 
### 事件示例
 
群消息接收开启
 

```
{
  "timestamp": 1784276800,
  "group_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "op_member_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/group_msg_receive.html>


---

# 群聊消息接收关闭
 
群管理员在机器人资料页操作关闭通知时触发。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | GROUP_MSG_REJECT |
| Intent | GROUP_AND_C2C_EVENT (1<<25) |
 
### 事件体
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| timestamp | integer | 操作时间戳（Unix 秒） |
| group_openid | string | 群 OpenID |
| op_member_openid | string | 操作群成员 OpenID |
 
### 事件示例
 
群消息接收关闭
 

```
{
  "timestamp": 1784276810,
  "group_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4",
  "op_member_openid": "A1B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/group_msg_reject.html>


---

# 群成员加入
 
有新成员加入群聊时触发。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | GROUP_MEMBER_ADD |
| Intent | GROUP_MEMBER_EVENT (1<<24) |
 
### 事件体
               
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| timestamp | integer | 事件时间戳（Unix 秒） |
| group_openid | string | 群 OpenID |
| member_openid | string | 新加入成员的 OpenID |
| user_openid | string | 新成员的用户 OpenID（跨应用统一标识，可能为空） |
 
### 事件示例
 
示例1
 

```
{
  "timestamp": 1784276757,
  "group_openid": "B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5",
  "member_openid": "C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6",
  "user_openid": "C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/group_member_add.html>


---

# 群成员退出
 
群成员退出或被移出群聊时触发。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | GROUP_MEMBER_REMOVE |
| Intent | GROUP_MEMBER_EVENT (1<<24) |
 
### 事件体
               
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| timestamp | integer | 事件时间戳（Unix 秒） |
| group_openid | string | 群 OpenID |
| member_openid | string | 退出成员的 OpenID |
| user_openid | string | 退出成员的用户 OpenID（可能为空） |
 
### 事件示例
 
示例1
 

```
{
  "timestamp": 1784276759,
  "group_openid": "B2C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5",
  "member_openid": "C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6",
  "user_openid": "C3D4E5F6A1B2C3D4E5F6A1B2C3D4E5F6"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/group_member_remove.html>


---

# 用户申请加群事件
 
用户申请加群请求触发此事件
 
1.只有当机器人是群管理员时才可以收到此事件。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | GROUP_JOIN_REQUEST |
| Intent | GROUP_MEMBER_EVENT (1<<24) |
 
### 事件体
                                       
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| group_openid | string | 群OpenID |
| join_request_id | string | 申请ID,需要在申请接口回传 |
| risk_tips | string | 安全提示语；可疑消息直接返回 warning_tips；普通消息命中 sec_risk_rules 时返回 top_tips |
| union_openid | string | 用户在应用/开放平台下的统一标识（如有） |
| member_openid | string | 申请人 openid |
| username | string | 申请人昵称 |
| apply_at | string | 申请时间戳（RFC3339 格式） |
| apply_source | string | 申请来源：self_apply 主动申请，invited 被邀请 |
| invited_by | string | 邀请人 openid（apply_source=invited 时有效） |
| bot | boolean | 是否为机器人账号 |
| verify_info | VerifyInfo | 用户入群验证方式 |
| auto_approved | AutoAppproved | 自动审批通过的扩展信息, 只有在下行事件中会携带。 |
 
VerifyInfo
            
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| method | string | 入群验证方式：verify_message / admin_review_qa |
| verify_message | string | 验证消息内容；仅 auth_type=verify_message 时可能携带 |
| review_qa_list | []ReviewQA | 问答列表；仅 auth_type=admin_review_qa 时可能携带 |
 
ReviewQA
         
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| question | string | 管理员设置的问题 |
| answer | string | 申请人填写的答案 |
 
AutoAppproved
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| strategy_id | string | 自动审批通过的策略ID |
 
### 事件示例
 
用户申请入群申请
 

```
{
  "group_openid": "30584554AA2BF4E72BD3B8F27A70339D",
  "join_request_id": "AVKiFWpdy0-q0rfCkpQFbWB9GvX7QPIe9hlsbVeO6TiurrZw1DHP0sXGnbUR4Xm79tKNpfl4zZynxeibVwwUD6h96RqiFB-4V6p5FKGXfqInOuQQSf5WwXr8lyIsn6yeaMwEI1KSuTTMBMNe6WN8bDtKg2REXTcF",
  "member_openid": "FE003FAF76C4817251FDC128A16753BB",
  "username": "痞孓小光光╮hw灰",
  "apply_at": "2026-08-05T16:21:40+08:00",
  "apply_source": "self_apply",
  "verify_info": {
    "method": "verify_message",
    "verify_message": "就快乐了"
  }
}
```

其他用户邀请用户入群
 

```
{
  "group_openid": "30584554AA2BF4E72BD3B8F27A70339D",
  "join_request_id": "AZj4L11PQ3oFrs2xf0wyfPmJ-3ONzbTr9MZRnXCSfoGce4KkWIgaTDwtkLXJVBaPx61VW9dzQz041oPt8o-JbBSyIerWVziQp1LaxYQCoyEx8rhffLwfBp5OW1-WL5C5HNji3M9lwDfZO4h_zNT4r0lywGojY4CX",
  "member_openid": "DE538D0B23260BFEC30EA4A17C3A71B1",
  "username": "吓唬",
  "apply_at": "2026-08-05T16:36:32+08:00",
  "apply_source": "invited",
  "invited_by": "FE003FAF76C4817251FDC128A16753BB"
}
```

用户入群申请自动申请通过
 

```
{
  "group_openid": "30584554AA2BF4E72BD3B8F27A70339D",
  "join_request_id": "AZ22mGUrkPeeNy6Fzz_raGskCnpnbdy7pIq6pME7XUgS72LOXTH4TxgzGlv3FmAGmNQAelRYYhBZYKgJUEoSgu21rSJVSdKOznbSu6FdXqXvZ10SkpI5fyE_876Va8KSbuLFbWdKa8Rh9nc_hzvZYKZT0_X1W0o4",
  "member_openid": "FE003FAF76C4817251FDC128A16753BB",
  "username": "痞孓小光光╮hw灰",
  "apply_at": "2026-08-05T17:32:52+08:00",
  "apply_source": "self_apply",
  "verify_info": {
    "method": "verify_message",
    "verify_message": "健健康康"
  },
  "auto_approved": {
    "strategy_id": "st_7c0b77d442"
  }
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/group_join_request.html>


---

### 频道管理

#### 事件

# 频道创建
 
机器人被加入到某个频道时触发。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | GUILD_CREATE |
| Intent | GUILDS (1<<0) |
 
### 事件体
                              
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 频道 ID |
| name | string | 频道名称 |
| icon | string | 频道头像 URL |
| owner_id | string | 频道创建者 ID |
| member_count | integer | 频道成员数 |
| max_members | integer | 频道成员上限 |
| description | string | 频道简介 |
| joined_at | string | 加入时间，ISO8601 格式 |
| op_user_id | string | 操作人 ID |
 
### 事件示例
 
示例1
 

```
{
  "id": "123456789012345678",
  "name": "技术交流频道",
  "icon": "https://thirdqq.qlogo.cn/0",
  "owner_id": "123456789012345678",
  "member_count": 100,
  "max_members": 1000,
  "description": "专注于技术分享与交流的频道",
  "joined_at": "2026-01-01T00:00:00+08:00",
  "op_user_id": "123456789012345678"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/guild_create.html>


---

# 频道更新
 
频道信息变更时触发。事件内容为变更后的数据。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | GUILD_UPDATE |
| Intent | GUILDS (1<<0) |
 
### 事件体
                              
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 频道 ID |
| name | string | 频道名称 |
| icon | string | 频道头像 URL |
| owner_id | string | 频道创建者 ID |
| member_count | integer | 频道成员数 |
| max_members | integer | 频道成员上限 |
| description | string | 频道简介 |
| joined_at | string | 加入时间，ISO8601 格式 |
| op_user_id | string | 操作人 ID |
 
### 事件示例
 
示例1
 

```
{
  "id": "123456789012345678",
  "name": "更新后的频道",
  "owner_id": "123456789012345678",
  "icon": "https://thirdqq.qlogo.cn/0",
  "member_count": 12,
  "max_members": 1000,
  "description": "更新后的描述"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/guild_update.html>


---

# 频道解散
 
频道被解散或机器人被移除时触发。事件内容为变更前的数据。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | GUILD_DELETE |
| Intent | GUILDS (1<<0) |
 
### 事件体
                              
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 频道 ID |
| name | string | 频道名称 |
| icon | string | 频道头像 URL |
| owner_id | string | 频道创建者 ID |
| member_count | integer | 频道成员数 |
| max_members | integer | 频道成员上限 |
| description | string | 频道简介 |
| joined_at | string | 加入时间，ISO8601 格式 |
| op_user_id | string | 操作人 ID |
 
### 事件示例
 
示例1
 

```
{
  "id": "123456789012345678",
  "name": "测试频道",
  "owner_id": "123456789012345678",
  "icon": "https://thirdqq.qlogo.cn/0",
  "member_count": 10,
  "max_members": 1000,
  "description": "频道描述"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/guild_delete.html>


---

# 子频道创建
 
子频道被创建时触发。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | CHANNEL_CREATE |
| Intent | GUILDS (1<<0) |
 
### 事件体
                        
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 子频道 ID |
| guild_id | string | 所属频道 ID |
| name | string | 子频道名称 |
| type | integer | 子频道类型。0=文字, 2=语音, 4=分组, 10005=直播, 10006=应用, 10007=论坛 |
| sub_type | integer | 子频道子类型 |
| owner_id | string | 创建者 ID |
| op_user_id | string | 操作人 ID |
 
### 事件示例
 
示例1
 

```
{
  "id": "123456",
  "guild_id": "123456789012345678",
  "name": "新子频道",
  "type": 0,
  "sub_type": 0,
  "position": 1,
  "owner_id": "123456789012345678"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/channel_create.html>


---

# 子频道更新
 
子频道信息变更时触发。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | CHANNEL_UPDATE |
| Intent | GUILDS (1<<0) |
 
### 事件体
                        
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 子频道 ID |
| guild_id | string | 所属频道 ID |
| name | string | 子频道名称 |
| type | integer | 子频道类型。0=文字, 2=语音, 4=分组, 10005=直播, 10006=应用, 10007=论坛 |
| sub_type | integer | 子频道子类型 |
| owner_id | string | 创建者 ID |
| op_user_id | string | 操作人 ID |
 
### 事件示例
 
示例1
 

```
{
  "id": "123456",
  "guild_id": "123456789012345678",
  "name": "更新后的子频道",
  "type": 0,
  "sub_type": 0,
  "position": 1,
  "owner_id": "123456789012345678"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/channel_update.html>


---

# 子频道删除
 
子频道被删除时触发。
 
## 事件
      
| 字段 | 值 |
| --- | --- |
| 事件名 | CHANNEL_DELETE |
| Intent | GUILDS (1<<0) |
 
### 事件体
                        
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 子频道 ID |
| guild_id | string | 所属频道 ID |
| name | string | 子频道名称 |
| type | integer | 子频道类型。0=文字, 2=语音, 4=分组, 10005=直播, 10006=应用, 10007=论坛 |
| sub_type | integer | 子频道子类型 |
| owner_id | string | 创建者 ID |
| op_user_id | string | 操作人 ID |
 
### 事件示例
 
示例1
 

```
{
  "id": "123456",
  "guild_id": "123456789012345678",
  "name": "被删除的子频道",
  "type": 0,
  "sub_type": 0,
  "position": 1,
  "owner_id": "123456789012345678"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/event/channel_delete.html>


---

#### 频道管理

# 获取频道详情
 
获取指定频道的基本信息。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /guilds/{guild_id} |
| HTTP Method | GET |
| 接口频率限制 | 50 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| guild_id | string | 是 |  |
 
### 请求示例
 
示例1
 

```
GET /guilds/123456789012345678
```

## 响应
 
### 响应体
                              
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 频道 ID |
| name | string | 频道名称 |
| icon | string | 频道头像 URL |
| owner_id | string | 创建者用户 ID |
| owner | boolean | 当前机器人是否为创建者 |
| member_count | integer | 成员数 |
| max_members | integer | 最大成员数 |
| description | string | 频道描述 |
| joined_at | string | 加入时间，ISO8601 格式 |
 
## 响应示例
 
示例1
 

```json
{
  "id": "123456789012345678",
  "name": "技术交流频道",
  "icon": "https://thirdqq.qlogo.cn/0",
  "owner_id": "123456789012345678",
  "owner": false,
  "member_count": 100,
  "max_members": 1000,
  "description": "专注于技术分享与交流的频道",
  "joined_at": "2026-01-01T00:00:00+08:00"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/guilds_guild_id.get.html>


---

# 获取子频道列表
 
获取指定频道下的子频道列表。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /guilds/{guild_id}/channels |
| HTTP Method | GET |
| 接口频率限制 | 50 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| guild_id | string | 是 |  |
 
### 请求示例
 
示例1
 

```
GET /guilds/123456789012345678/channels
```

## 响应
 
### 响应体
      
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| channels | []Channel |  |
 
Channel
                                       
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 子频道 ID |
| guild_id | string | 所属频道 ID |
| name | string | 子频道名 |
| type | integer | 子频道类型: 0=文字, 2=语音, 4=分组, 10005=直播, 10006=应用, 10007=论坛 |
| sub_type | integer | 子频道子类型（文字子频道）: 0=闲聊, 1=公告, 2=攻略, 3=开黑 |
| position | integer | 排序值，从 1 开始 |
| parent_id | string | 所属分组 ID（仅子频道有效） |
| owner_id | string | 创建人 ID |
| private_type | integer | 子频道私密类型: 0=公开, 1=群主管理员可见, 2=群主管理员+指定成员 |
| speak_permission | integer | 子频道发言权限: 0=无效, 1=所有人, 2=群主管理员+指定成员 |
| application_id | string | 应用子频道标识 |
| permissions | string | 用户拥有的子频道权限 |
 
## 响应示例
 
示例1
 

```json
[
  {
    "id": "123456",
    "guild_id": "123456789012345678",
    "name": "文字交流区",
    "type": 0,
    "sub_type": 0,
    "position": 1,
    "parent_id": "0",
    "owner_id": "123456789012345678",
    "private_type": 0,
    "speak_permission": 1
  },
  {
    "id": "123457",
    "guild_id": "123456789012345678",
    "name": "语音聊天室",
    "type": 2,
    "sub_type": 0,
    "position": 2,
    "parent_id": "0",
    "owner_id": "123456789012345678",
    "private_type": 0,
    "speak_permission": 1
  }
]
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/guilds_guild_id_channels.get.html>


---

# 创建子频道
 
在指定频道下创建子频道。需要管理员权限。
 
需要管理员权限。私域接口，创建成功后会触发 CHANNEL_CREATE 事件。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /guilds/{guild_id}/channels |
| HTTP Method | POST |
| 接口频率限制 | 50 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| guild_id | string | 是 |  |
 
## 请求体
                                        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| name | string | 否 | 子频道名称 |
| type | integer | 否 | 子频道类型 |
| sub_type | integer | 否 | 子频道子类型 |
| position | integer | 否 | 排序值（分组类型必须 >= 2） |
| parent_id | string | 否 | 所属分组 ID |
| private_type | integer | 否 | 私密类型 |
| private_user_ids | []string | 否 | 私密成员 ID 列表 |
| speak_permission | integer | 否 | 发言权限 |
| application_id | string | 否 | 应用子频道 AppID |
 
### 请求示例
 
创建文字子频道
 

```
POST /guilds/123456789012345678/channels
{
  "name": "公告区",
  "type": 0,
  "sub_type": 1,
  "position": 3,
  "parent_id": "0",
  "private_type": 0,
  "speak_permission": 1
}
```

创建语音子频道
 

```
POST /guilds/123456789012345678/channels
{
  "name": "开黑房",
  "type": 2,
  "sub_type": 3,
  "position": 4,
  "parent_id": "0"
}
```

## 响应
 
### 响应体
                                       
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 子频道 ID |
| guild_id | string | 所属频道 ID |
| name | string | 子频道名 |
| type | integer | 子频道类型: 0=文字, 2=语音, 4=分组, 10005=直播, 10006=应用, 10007=论坛 |
| sub_type | integer | 子频道子类型（文字子频道）: 0=闲聊, 1=公告, 2=攻略, 3=开黑 |
| position | integer | 排序值，从 1 开始 |
| parent_id | string | 所属分组 ID（仅子频道有效） |
| owner_id | string | 创建人 ID |
| private_type | integer | 子频道私密类型: 0=公开, 1=群主管理员可见, 2=群主管理员+指定成员 |
| speak_permission | integer | 子频道发言权限: 0=无效, 1=所有人, 2=群主管理员+指定成员 |
| application_id | string | 应用子频道标识 |
| permissions | string | 用户拥有的子频道权限 |
 
## 响应示例
 
示例1
 

```json
{
  "id": "123458",
  "guild_id": "123456789012345678",
  "name": "公告区",
  "type": 0,
  "sub_type": 1,
  "position": 3,
  "parent_id": "0",
  "owner_id": "123456789012345678",
  "private_type": 0,
  "speak_permission": 1
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/guilds_guild_id_channels.post.html>


---

# 获取子频道详情
 
获取指定子频道的基本信息。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /channels/{channel_id} |
| HTTP Method | GET |
| 接口频率限制 | 50 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| channel_id | string | 是 |  |
 
### 请求示例
 
示例1
 

```
GET /channels/123456
```

## 响应
 
### 响应体
                                       
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 子频道 ID |
| guild_id | string | 所属频道 ID |
| name | string | 子频道名 |
| type | integer | 子频道类型: 0=文字, 2=语音, 4=分组, 10005=直播, 10006=应用, 10007=论坛 |
| sub_type | integer | 子频道子类型（文字子频道）: 0=闲聊, 1=公告, 2=攻略, 3=开黑 |
| position | integer | 排序值，从 1 开始 |
| parent_id | string | 所属分组 ID（仅子频道有效） |
| owner_id | string | 创建人 ID |
| private_type | integer | 子频道私密类型: 0=公开, 1=群主管理员可见, 2=群主管理员+指定成员 |
| speak_permission | integer | 子频道发言权限: 0=无效, 1=所有人, 2=群主管理员+指定成员 |
| application_id | string | 应用子频道标识 |
| permissions | string | 用户拥有的子频道权限 |
 
## 响应示例
 
示例1
 

```json
{
  "id": "123456",
  "guild_id": "123456789012345678",
  "name": "文字交流区",
  "type": 0,
  "sub_type": 0,
  "position": 1,
  "parent_id": "0",
  "owner_id": "123456789012345678",
  "private_type": 0,
  "speak_permission": 1,
  "permissions": "0"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/channels_channel_id.get.html>


---

# 修改子频道
 
修改子频道信息。需要管理员权限。
 
需要管理员权限。私域接口，只需传入要修改的字段，修改成功后会触发 CHANNEL_UPDATE 事件。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /channels/{channel_id} |
| HTTP Method | PATCH |
| 接口频率限制 | 50 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| channel_id | string | 是 |  |
 
## 请求体
                        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| name | string | 否 | 子频道名 |
| position | integer | 否 | 排序 |
| parent_id | string | 否 | 分组 ID |
| private_type | integer | 否 | 私密类型 |
| speak_permission | integer | 否 | 发言权限 |
 
### 请求示例
 
修改子频道名称和排序
 

```
PATCH /channels/123456
{
  "name": "公告区（已改名）",
  "position": 5,
  "parent_id": "0"
}
```

## 响应
 
### 响应体
                                       
| 名称 | 类型 | 描述 |
| --- | --- | --- |
| id | string | 子频道 ID |
| guild_id | string | 所属频道 ID |
| name | string | 子频道名 |
| type | integer | 子频道类型: 0=文字, 2=语音, 4=分组, 10005=直播, 10006=应用, 10007=论坛 |
| sub_type | integer | 子频道子类型（文字子频道）: 0=闲聊, 1=公告, 2=攻略, 3=开黑 |
| position | integer | 排序值，从 1 开始 |
| parent_id | string | 所属分组 ID（仅子频道有效） |
| owner_id | string | 创建人 ID |
| private_type | integer | 子频道私密类型: 0=公开, 1=群主管理员可见, 2=群主管理员+指定成员 |
| speak_permission | integer | 子频道发言权限: 0=无效, 1=所有人, 2=群主管理员+指定成员 |
| application_id | string | 应用子频道标识 |
| permissions | string | 用户拥有的子频道权限 |
 
## 响应示例
 
示例1
 

```json
{
  "id": "123456",
  "guild_id": "123456789012345678",
  "name": "公告区（已改名）",
  "type": 0,
  "sub_type": 0,
  "position": 5,
  "parent_id": "0",
  "owner_id": "123456789012345678",
  "private_type": 0,
  "speak_permission": 1
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/channels_channel_id.patch.html>


---

# 删除子频道
 
删除子频道。需要管理员权限。成功返回 HTTP 200。
 
需要管理员权限。私域接口，删除成功后会触发 CHANNEL_DELETE 事件。子频道删除后无法恢复。
 
## 请求
 
### 基础信息
        
| 字段 | 值 |
| --- | --- |
| HTTP URL | /channels/{channel_id} |
| HTTP Method | DELETE |
| 接口频率限制 | 50 QPS |
 
## 路径参数
        
| 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| channel_id | string | 是 |  |
 
### 请求示例
 
示例1
 

```
DELETE /channels/123456
```

## 响应
 
无
 
## 响应示例
 
示例1
 

```json
{}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/autogen/api/channels_channel_id.delete.html>


---

#### 频道成员

# 获取子频道在线成员数
 
## 接口
 

```http
GET /channels/{channel_id}/online_nums
```

## 功能描述
 
用于查询音视频/直播子频道 `channel_id` 的在线成员数。
 
## Content-Type
 

```http
application/json
```

## 返回
 
成功返回空对象。
 

```json
{
  "online_nums": 1
}
```

## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```http
GET /channels/123456/online_nums
```

响应数据包
 

```json
{
  "online_nums": 1
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role/get_online_nums.html>


---

# 获取频道成员列表
 
## 接口
 

```http
GET /guilds/{guild_id}/members
```

## 功能描述
 
用于获取 `guild_id` 指定的频道中所有成员的详情列表，支持分页。
 - 公域机器人暂不支持申请，仅私域机器人可用，选择私域机器人后默认开通。
- 注意: 开通后需要先将机器人从频道移除，然后重新添加，方可生效。

> **警告**
> 注意
 
## Content-Type
 

```http
application/json
```

## 参数
         
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| after | string | 上一次回包中最后一个`member`的`user id`， 如果是第一次请求填 0，默认为 0 |
| limit | uint32 | 分页大小，1-400，默认是 1。成员较多的频道尽量使用较大的`limit`值，以减少请求数 |
 
## 返回
 
返回 [Member](/wiki/develop/api-v2/server-inter/channel/role/member/model.html#member) 对象数组。
 
## 有关返回结果的说明
 1. 在每次翻页的过程中，可能会返回上一次请求已经返回过的`member`信息，需要调用方自己根据`user id`来进行去重。
 2. 每次返回的`member`数量与`limit`不一定完全相等。翻页请使用最后一个`member`的`user id`作为下一次请求的after参数，直到回包为空，拉取结束。

 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求
 

```shell
GET /guilds/123456/members?limit=2
```

响应数据包
 

```json
[
  {
    "user": {
      "id": "xxxxxx",
      "username": "xxxx",
      "avatar": "xxxxxx",
      "bot": false,
      "public_flags": 0,
      "system": false,
      "union_openid": "xxxxxx",
      "union_user_account": ""
    },
    "nick": "",
    "roles": ["1"],
    "joined_at": "2021-12-09T15:53:41+08:00",
    "deaf": false,
    "mute": false,
    "pending": false
  },
  {
    "user": {
      "id": "xxxxxx",
      "username": "秦时明月",
      "avatar": "xxxxxx",
      "bot": false,
      "public_flags": 0,
      "system": false,
      "union_openid": "xxxxxx",
      "union_user_account": ""
    },
    "nick": "",
    "roles": ["4"],
    "joined_at": "2021-12-02T15:19:00+08:00",
    "deaf": false,
    "mute": false,
    "pending": false
  }
]
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role/member/get_members.html>


---

# 获取频道身份组成员列表
 
## 接口
 

```http
GET /guilds/{guild_id}/roles/{role_id}/members
```

## 功能描述
 
用于获取 `guild_id` 频道中指定`role_id`身份组下所有成员的详情列表，支持分页。
 - 公域机器人暂不支持申请，仅私域机器人可用，选择私域机器人后默认开通。
- 注意: 开通后需要先将机器人从频道移除，然后重新添加，方可生效。

> **警告**
> 注意
 
## Content-Type
 

```http
application/json
```

## 参数
         
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| start_index | string | 将上一次回包中`next`填入， 如果是第一次请求填 0，默认为 0 |
| limit | uint32 | 分页大小，1-400，默认是 1。成员较多的频道尽量使用较大的`limit`值，以减少请求数 |
 
## 返回
         
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| data | [Member](/wiki/develop/api-v2/server-inter/channel/role/member/model.html#member) 对象数组 | 一组用户信息对象 |
| next | string | 下一次请求的分页标识 |
 
## 有关返回结果的说明
 
每次返回的member数量与limit不一定完全相等。特定管理身份组下的成员可能存在一次性返回全部的情况
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求
 

```http
GET /guilds/123456/roles/4/members?limit=2
```

响应数据包
 

```json
{
  "data": [
    {
      "user": {
        "id": "xxx",
        "username": "xxx",
        "avatar": "xxx",
        "bot": false
      },
      "nick": "xxx",
      "joined_at": "2021-11-03T20:41:36+08:00"
    }
  ],
  "next": "0"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role/member/get_role_members.html>


---

# 获取频道成员详情
 
## 接口
 

```http
GET /guilds/{guild_id}/members/{user_id}
```

## 功能描述
 
用于获取 `guild_id` 指定的频道中 `user_id` 对应成员的详细信息。
 
## Content-Type
 

```http
application/json
```

## 返回
 
返回[Member](/wiki/develop/api-v2/server-inter/channel/role/member/model.html#member) 成员对象。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```shell
GET /guilds/123456/members/112233
```

响应数据包
 

```json
{
  "user": {
    "id": "2823701233424295228",
    "username": "xxx",
    "avatar": "https://qqchannel-profile-1251316161.file.myqcloud.com/xxxxxxx",
    "bot": false,
    "union_openid": "",
    "union_user_account": ""
  },
  "nick": "",
  "roles": [
    "1"
  ],
  "joined_at": "2021-12-05T14:08:29+08:00"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role/member/get_member.html>


---

# 删除频道成员
 
## 接口
 

```http
DELETE /guilds/{guild_id}/members/{user_id}
```

## 功能描述
 
用于删除 `guild_id` 指定的频道下的成员 `user_id`。
 - 需要使用的 `token` 对应的用户具备踢人权限。如果是机器人，要求被添加为管理员。
 - 操作成功后，会触发频道成员删除事件。
 - 无法移除身份为管理员的成员

 - 公域机器人暂不支持申请，仅私域机器人可用，选择私域机器人后默认开通。
- 注意: 开通后需要先将机器人从频道移除，然后重新添加，方可生效。

> **警告**
> 注意
 
## Content-Type
 

```http
application/json
```

## 参数
         
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| add_blacklist | bool | 删除成员的同时，将该用户添加到频道黑名单中 |
| delete_history_msg_days | int | 删除成员的同时，撤回该成员的消息，可以指定撤回消息的时间范围 |
 
注：消息撤回时间范围仅支持固定的天数：`3`，`7`，`15`，`30`。 特殊的时间范围：`-1: 撤回全部消息`。默认值为`0`不撤回任何消息。
 
## 返回
 
成功返回 HTTP 状态码 `204`。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```shell
DELETE /guilds/123456/members/112233
{
    "add_blacklist": true,
    "delete_history_msg_days": -1
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role/member/delete_member.html>


---

# 频道成员事件
 
## 内容
 
在 [MemberWithGuildID](/wiki/develop/api-v2/server-inter/channel/role/member/model.html#MemberWithGuildID) 基础上，增加 `op_user_id` 代表操作人。
 
注：此事件由于开发较早，尚有一些字段未标准化处理，如 `joined_at`, `roles` 请开发者适配的时候注意。晚些时候我们也会将这些字段标准化处理。
 
## GUILD_MEMBER_ADD
 
### 发送时机
 - 新用户加入频道

 
### 示例
 

```json
{
    "guild_id": "200000000",
    "joined_at": "2021-10-21T11:20:18+08:00",
    "nick": "",
    "op_user_id": "100000000",
    "roles": [
      "1"
    ],
    "user": {
      "avatar": "http://thirdqq.qlogo.cn/g?b=oidb&k=IU4JJatZtNXCVrf44eshNg&s=0&t=1638261405",
      "bot": true,
      "id": "8834102668809967837",
      "username": "b站机器人"
    }
}
```

## GUILD_MEMBER_UPDATE
 
### 发送时机
 - 用户的频道属性发生变化，如频道昵称，或者身份组

 
### 示例
 

```json
{
  "guild_id": "200000000",
  "joined_at": "2021-10-21T11:20:18+08:00",
  "nick": "",
  "op_user_id": "8834102668809967837",
  "roles": ["2"],
  "user": {
   "avatar": "http://thirdqq.qlogo.cn/g?b=oidb&k=IU4JJatZtNXCVrf44eshNg&s=0&t=1638261405",
   "bot": true,
   "id": "8834102668809967837",
   "username": "b站机器人"
  }
}
```

## GUILD_MEMBER_REMOVE
 
### 发送时机
 - 用户离开频道

 
### 示例
 

```json
{
    "guild_id": "200000000",
    "joined_at": "2021-10-21T11:20:18+08:00",
    "nick": "",
    "op_user_id": "100000000",
    "roles": [
      "1"
    ],
    "user": {
      "avatar": "http://thirdqq.qlogo.cn/g?b=oidb&k=IU4JJatZtNXCVrf44eshNg&s=0&t=1638261405",
      "bot": true,
      "id": "8834102668809967837",
      "username": "b站机器人"
    }
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role/guild_member.html>


---

# 音视频/直播子频道成员进出事件
 
## AUDIO_OR_LIVE_CHANNEL_MEMBER_ENTER
 
### 发送时机
 - 用户进入音视频/直播子频道时

 
### 示例
 

```json
{
  "guild_id": "47129941624960822",
  "channel_id": "1661124",
  "channel_type": 2, // 2-音视频子频道 5-直播子频道
  "user_id": "144115218182563108"
}
```

## AUDIO_OR_LIVE_CHANNEL_MEMBER_EXIT
 
### 发送时机
 - 用户离开音视频/直播子频道时

 
### 示例
 

```json
{
  "guild_id": "47129941624960822",
  "channel_id": "1661124",
  "channel_type": 2, // 2-音视频子频道 5-直播子频道
  "user_id": "144115218182563108"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role/audio_or_live_channel_member.html>


---

#### 身份组与权限管理

# 获取频道身份组列表
 
## 接口
 

```http
GET /guilds/{guild_id}/roles
```

## 功能描述
 
用于获取 `guild_id`指定的频道下的身份组列表。
 
## Content-Type
 

```http
application/json
```

## 返回
            
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| guild_id | string | 频道 ID |
| roles | [Role](/wiki/develop/api-v2/server-inter/channel/role/member/role_model.html#role) 对象数组 | 一组频道身份组对象 |
| role_num_limit | string | 默认分组上限 |
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```shell
GET /guilds/123456/roles
```

响应数据包
 

```json
{
  "guild_id": "123456",
  "roles": [
    {
      "id": "4",
      "name": "创建者",
      "color": 4294927682,
      "hoist": 1,
      "number": 1,
      "member_limit": 1
    },
    {
      "id": "2",
      "name": "管理员",
      "color": 4280276644,
      "hoist": 1,
      "number": 5,
      "member_limit": 50
    }
  ],
  "role_num_limit": "30"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role-group/get_guild_roles.html>


---

# 创建频道身份组
 
## 接口
 

```http
POST /guilds/{guild_id}/roles
```

## 功能描述
 
用于在`guild_id` 指定的频道下创建一个身份组。
 - 需要使用的 `token` 对应的用户具备创建身份组权限。如果是机器人，要求被添加为管理员。
 - 参数为非必填，但至少需要传其中之一，默认为空或 `0`。

 
## Content-Type
 

```http
application/json
```

## 参数
            
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| name | string | 名称(非必填) |
| color | uint32 | ARGB 的 HEX 十六进制颜色值转换后的十进制数值(非必填) |
| hoist | int32 | 在成员列表中单独展示: 0-否, 1-是(非必填) |
 
## 返回
         
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| role_id | string | 身份组 ID |
| role | [Role](/wiki/develop/api-v2/server-inter/channel/role/member/role_model.html#role) 对象 | 所创建的频道身份组对象 |
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{
  "name": "test",
  "color": 99999,
  "hoist": "1"
}
```

响应数据包
 

```json
{
  "role_id": "10177739",
  "role": {
    "id": "10177739",
    "name": "test",
    "color": 99999,
    "hoist": 1,
    "number": 0,
    "member_limit": 2000
  }
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role-group/post_guild_role.html>


---

# 修改频道身份组
 
## 接口
 

```http
PATCH /guilds/{guild_id}/roles/{role_id}
```

## 功能描述
 
用于修改频道 `guild_id` 下 `role_id` 指定的身份组。
 - 需要使用的 `token` 对应的用户具备修改身份组权限。如果是机器人，要求被添加为管理员。
 - 接口会修改传入的字段，不传入的默认不会修改，至少要传入一个参数。

 
## Content-Type
 

```http
application/json
```

## 参数
            
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| name | string | 名称(非必填) |
| color | uint32 | ARGB 的 HEX 十六进制颜色值转换后的十进制数值(非必填) |
| hoist | int32 | 在成员列表中单独展示: 0-否, 1-是(非必填) |
 
## 返回
            
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| guild_id | string | 频道 ID |
| role_id | string | 身份组 ID |
| role | [Role](/wiki/develop/api-v2/server-inter/channel/role/member/role_model.html#role) 对象 | 修改后的频道身份组对象 |
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{
  "name": "test",
  "color": 99999,
  "hoist": "1"
}
```

响应数据包
 

```json
{
  "guild_id": "3489223429684602178",
  "role_id": "10177739",
  "role": {
    "id": "10177739",
    "name": "test",
    "color": 99999,
    "hoist": 1,
    "number": 1,
    "member_limit": 2000
  }
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role-group/patch_guild_role.html>


---

# 删除频道身份组
 
## 接口
 

```http
DELETE /guilds/{guild_id}/roles/{role_id}
```

## 功能描述
 
用于删除频道`guild_id`下 `role_id` 对应的身份组。
 - 需要使用的 `token` 对应的用户具备删除身份组权限。如果是机器人，要求被添加为管理员。

 
## Content-Type
 

```http
application/json
```

## 返回
 
成功返回 HTTP 状态码 `204`。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```shell
DELETE /guilds/123456/roles/112233
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role-group/delete_guild_role.html>


---

# 创建频道身份组成员
 
## 接口
 

```http
PUT /guilds/{guild_id}/members/{user_id}/roles/{role_id}
```

## 功能描述
 
用于将频道`guild_id`下的用户 `user_id` 添加到身份组 `role_id` 。
 - 需要使用的 `token` 对应的用户具备增加身份组成员权限。如果是机器人，要求被添加为管理员。
 - 如果要增加的身份组 `ID` 是`5-子频道管理员`，需要增加 `channel` 对象来指定具体是哪个子频道。

 
## Content-Type
 

```http
application/json
```

## 参数
      
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| channel | [Channel](/wiki/develop/api-v2/server-inter/channel/manage/channel/model.html#Channel) 对象 | 接收一个只填充了子频道 id 字段的对象 |
 
## 返回
 
成功返回 HTTP 状态码 `204`。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{
	"channel": {
		"id": "1744939"
	}
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role-group/put_guild_member_role.html>


---

# 删除频道身份组成员
 
## 接口
 

```http
DELETE /guilds/{guild_id}/members/{user_id}/roles/{role_id}
```

## 功能描述
 
用于将 用户 `user_id` 从 频道 `guild_id` 的 `role_id` 身份组中移除。
 - 需要使用的 `token` 对应的用户具备删除身份组成员权限。如果是机器人，要求被添加为管理员。
 - 如果要删除的身份组 `ID` 是`5-子频道管理员`，需要增加 channel 对象来指定具体是哪个子频道。

 
## Content-Type
 

```http
application/json
```

## 参数
      
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| channel | [Channel](/wiki/develop/api-v2/server-inter/channel/manage/channel/model.html#Channel) 对象 | 接收一个只填充了子频道 id 字段的对象 |
 
## 返回
 
成功返回 HTTP 状态码 `204`。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```shell
DELETE /guilds/123456/members/112233/roles/445566
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role-group/delete_guild_member_role.html>


---

# 获取子频道用户权限
 
## 接口
 

```http
GET /channels/{channel_id}/members/{user_id}/permissions
```

## 功能描述
 
用于获取 子频道`channel_id` 下用户 `user_id` 的权限。
 - 获取子频道用户权限。
 - 要求操作人具有管理子频道的权限，如果是机器人，则需要将机器人设置为管理员。

 
## Content-Type
 

```http
application/json
```

## 返回
 
返回 [ChannelPermissions](/wiki/develop/api-v2/server-inter/channel/role-group/channel_permissions/model.html#channelpermissions) 对象。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```shell
GET /channels/123456/members/112233/permissions
```

响应数据包
 

```json
{
  "channel_id": "123456",
  "user_id": "112233",
  "permissions": "4"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role-group/channel_permissions/get_channel_permissions.html>


---

# 修改子频道用户权限
 
## 接口
 

```http
PUT /channels/{channel_id}/members/{user_id}/permissions
```

## 功能描述
 
用于修改子频道 `channel_id` 下用户 `user_id` 的权限。
 - 要求操作人具有`管理子频道`的权限，如果是机器人，则需要将机器人设置为管理员。
 - 参数包括`add`和`remove`两个字段，分别表示授予的权限以及删除的权限。要授予用户权限即把`add`对应位置 1，删除用户权限即把`remove`对应位置 1。当两个字段同一位都为 1，表现为删除权限。
 - 本接口不支持修改`可管理子频道`权限。

 
## Content-Type
 

```http
application/json
```

## 参数
         
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| [add](/wiki/develop/api-v2/server-inter/channel/role-group/channel_permissions/model.html#permission) | string | 字符串形式的位图表示赋予用户的权限 |
| [remove](/wiki/develop/api-v2/server-inter/channel/role-group/channel_permissions/model.html#permission) | string | 字符串形式的位图表示删除用户的权限 |
 
## 返回
 
成功返回 HTTP 状态码 `204`。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{
  "add": "1",
  "remove": "4"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role-group/channel_permissions/put_channel_permissions.html>


---

# 获取子频道身份组权限
 
## 接口
 

```http
GET /channels/{channel_id}/roles/{role_id}/permissions
```

## 功能描述
 
用于获取子频道 `channel_id` 下身份组 `role_id` 的权限。
 - 要求操作人具有管理子频道的权限，如果是机器人，则需要将机器人设置为管理员。

 
## Content-Type
 

```http
application/json
```

## 返回
 
返回 [ChannelPermissions](/wiki/develop/api-v2/server-inter/channel/role-group/channel_permissions/model.html#channelpermissions) 对象。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```shell
GET /channels/123456/roles/112233/permissions
```

响应数据包
 

```json
{
  "channel_id": "123456",
  "role_id": "112233",
  "permissions": "5"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role-group/channel_permissions/get_channel_roles_permissions.html>


---

# 修改子频道身份组权限
 
## 接口
 

```http
PUT /channels/{channel_id}/roles/{role_id}/permissions
```

## 功能描述
 
用于修改子频道 channel_id 下身份组 role_id 的权限。
 - 要求操作人具有`管理子频道`的权限，如果是机器人，则需要将机器人设置为管理员。
 - 参数包括`add`和`remove`两个字段，分别表示授予的权限以及删除的权限。要授予身份组权限即把`add`对应位置 1，删除身份组权限即把`remove`对应位置 1。当两个字段同一位都为 1，表现为删除权限。
 - 本接口不支持修改`可管理子频道`权限。

 
## Content-Type
 

```http
application/json
```

## 参数
         
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| [add](/wiki/develop/api-v2/server-inter/channel/role-group/channel_permissions/model.html#permission) | string | 字符串形式的位图表示赋予用户的权限 |
| [remove](/wiki/develop/api-v2/server-inter/channel/role-group/channel_permissions/model.html#permission) | string | 字符串形式的位图表示删除用户的权限 |
 
## 返回
 
成功返回 HTTP 状态码 `204`。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{
  "add": "1",
  "remove": "4"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/role-group/channel_permissions/put_channel_roles_permissions.html>


---

#### 接口授权管理

# 获取机器人在频道可用权限列表
 
## 接口
 

```http
GET /guilds/{guild_id}/api_permission
```

## 功能描述
 
用于获取机器人在频道 `guild_id` 内可以使用的权限列表。
 
## Content-Type
 

```http
application/json
```

## 返回
      
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| apis | [APIPermission](/wiki/develop/api-v2/server-inter/channel/api_permissions/model.html#APIPermission) 对象数组 | 机器人可用权限列表 |
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
响应数据包
 

```json
{
  "apis": [
    {
      "path": "/guilds/{guild_id}/members/{user_id}",
      "method": "GET",
      "desc": "获取当前频道成员信息",
      "auth_status": 0
    },
    {
      "path": "/channels/{channel_id}/messages",
      "method": "POST",
      "desc": "创建消息",
      "auth_status": 1
    }
  ]
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/api_permissions/get_guild_api_permission.html>


---

# 发送机器人在频道接口权限的授权链接
 
## 接口
 

```http
POST /guilds/{guild_id}/api_permission/demand
```

## 功能描述
 
用于创建 API 接口权限授权链接，该链接指向`guild_id`对应的频道 。
 - 每天只能在一个频道内发 `3` 条（默认值）频道权限授权链接。

 
## 示例图
 ![创建频道API接口权限授权](https://qq-ai.cdn-go.cn/web/bot-docs/-/v1.28.0/assets/img/post_api_permission_demand.0e7274cb.png) 
## Content-Type
 

```http
application/json
```

## 参数
            
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| channel_id | string | 授权链接发送的子频道 id |
| api_identify | [APIPermissionDemandIdentify](/wiki/develop/api-v2/server-inter/channel/api_permissions/model.html#APIPermissionDemandIdentify) 对象 | api 权限需求标识对象 |
| desc | string | 机器人申请对应的 API 接口权限后可以使用功能的描述 |
 
## 返回
 
返回[APIPermissionDemand](/wiki/develop/api-v2/server-inter/channel/api_permissions/model.html#APIPermissionDemand) 对象。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{
  "channel_id": "123456",
  "api_identify": {
    "path": "/guilds/{guild_id}",
    "method": "GET"
  },
  "desc": "显示频道信息"
}
```

响应数据包
 

```json
{
  "guild_id": "xxxxxx",
  "channel_id": "123456",
  "api_identify": {
    "path": "/guilds/{guild_id}",
    "method": "GET"
  },
  "title": "王者机器人申请授权频道信息接口权限",
  "desc": "申请权限后才能正常使用机器人显示频道信息功能"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/api_permissions/post_api_permission_demand.html>


---

#### 发言管理

# 获取频道消息频率的设置详情
 
## 接口
 

```http
GET /guilds/{guild_id}/message/setting
```

## 功能描述
 
用于获取机器人在频道 `guild_id` 内的消息频率设置。
 
## Content-Type
 

```http
application/json
```

## 返回
 
返回[MessageSetting](/wiki/develop/api-v2/server-inter/channel/speak/setting/model.html#MessageSetting) 对象。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
响应数据包
 

```json
{
  "disable_create_dm": true,
  "disable_push_msg": false,
  "channel_ids": [
    "1146313",
    "2651849",
    "2651149"
  ],
  "channel_push_max_num": 12
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/speak/setting/message_setting.html>


---

# 频道全员禁言
 
## 接口
 

```http
PATCH /guilds/{guild_id}/mute
```

## 功能描述
 
用于将频道的全体成员（非管理员）禁言。
 - 需要使用的 `token` 对应的用户具备管理员权限。如果是机器人，要求被添加为管理员。

 
该接口同样可用于解除禁言，具体使用见解除全员禁言。
 
## Content-Type
 

```http
application/json
```

## 参数
         
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| mute_end_timestamp | string | 禁言到期时间戳，绝对时间戳，单位：秒（与 mute_seconds 字段同时赋值的话，以该字段为准） |
| mute_seconds | string | 禁言多少秒（两个字段二选一，默认以 mute_end_timestamp 为准） |
 
### 解除禁言
 
该接口同样支持解除全员禁言，将`mute_end_timestamp`或`mute_seconds`传值为字符串`'0'`即可。
 
## 返回
 
成功返回 HTTP 状态码 `204`。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{
  "mute_end_timestamp": "1641916800",
  "mute_seconds": "120"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/speak/patch_guild_mute.html>


---

# 频道指定成员禁言
 
## 接口
 

```http
PATCH /guilds/{guild_id}/members/{user_id}/mute
```

## 功能描述
 
用于禁言频道 `guild_id` 下的成员 `user_id`。
 - 需要使用的 `token` 对应的用户具备管理员权限。如果是机器人，要求被添加为管理员。

 
该接口同样可用于解除禁言，具体使用见解除指定成员禁言。
 
## Content-Type
 

```http
application/json
```

## 参数
         
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| mute_end_timestamp | string | 禁言到期时间戳，绝对时间戳，单位：秒（与 mute_seconds 字段同时赋值的话，以该字段为准） |
| mute_seconds | string | 禁言多少秒（两个字段二选一，默认以 mute_end_timestamp 为准） |
 
### 解除禁言
 
该接口同样支持解除指定成员禁言，将`mute_end_timestamp`或`mute_seconds`传值为字符串`'0'`即可。
 
## 返回
 
成功返回 HTTP 状态码 `204`。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{
  "mute_end_timestamp": "1641916800",
  "mute_seconds": "120"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/speak/patch_guild_member_mute.html>


---

# 频道批量成员禁言
 
## 接口
 

```http
PATCH /guilds/{guild_id}/mute
```

## 功能描述
 
用于将频道的指定批量成员（非管理员）禁言。
 - 需要使用的 `token` 对应的用户具备管理员权限。如果是机器人，要求被添加为管理员。

 
该接口同样可用于批量解除禁言，具体使用见批量解除禁言。
 
## Content-Type
 

```http
application/json
```

## 参数
            
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| mute_end_timestamp | string | 禁言到期时间戳，绝对时间戳，单位：秒（与 mute_seconds 字段同时赋值的话，以该字段为准） |
| mute_seconds | string | 禁言多少秒（两个字段二选一，默认以 mute_end_timestamp 为准） |
| user_ids | string列表 | 禁言成员的user_id列表，即[User](/wiki/develop/api-v2/openapi/user/model.html#user)的id |
 
### 批量解除禁言
 
该接口同样支持批量解除禁言，将`mute_end_timestamp`或`mute_seconds`传值为字符串`'0'`即可，及需要批量解除禁言的成员的`user_id` 列表`user_ids`。
 
## 返回
 
成功返回 HTTP 状态码 `200`，并返回设置成功的成员`user_ids`。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{
  "mute_end_timestamp": "1641916800",
  "mute_seconds": "120",
  "user_ids": ["1201318637970874066","1201318637970874067"]
}
```

响应数据包
 

```json
{
  "user_ids": ["1201318637970874066"]
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/speak/patch_guild_mute_multi_member.html>


---

#### 内容管理

# 创建频道公告
 
## 接口
 

```http
POST /guilds/{guild_id}/announces
```

## 功能描述
 
用于创建频道全局公告，公告类型分为 消息类型的频道公告 和 推荐子频道类型的频道公告 。
 - 当请求参数 `message_id` 有值时，优先创建消息类型的频道公告， 消息类型的频道公告只能创建成员公告类型的频道公告。
 - 创建推荐子频道类型的频道全局公告请将 `message_id` 设置为空，并设置对应的 `announces_type` 和 `recommend_channels` 请求参数，会一次全部替换推荐子频道公司。
 - 推荐子频道和消息类型全局公告不能同时存在，会互相顶替设置。
 - 同频道内推荐子频道最多只能创建 `3` 条。
 - 只有子频道权限为全体成员可见才可设置为推荐子频道。
 - 删除推荐子频道类型的频道公告请使用 [删除频道公告](/wiki/develop/api-v2/server-inter/channel/content/announces/delete_guild_announces.html),并将 `message_id` 设置为 `all`。

 
## Content-Type
 

```http
application/json
```

## 参数
               
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| message_id | string | 选填，消息 id，message_id 有值则优选将某条消息设置为成员公告 |
| channel_id | string | 选填，子频道 id，message_id 有值则为必填。 |
| announces_type | uint32 | 选填，公告类别 0:成员公告，1:欢迎公告，默认为成员公告 |
| recommend_channels | [RecommendChannel](/wiki/develop/api-v2/server-inter/channel/content/announces/model.html#RecommendChannel) 数组 | 选填，推荐子频道列表，会一次全部替换推荐子频道列表 |
 
## 返回
 
返回[Announces](/wiki/develop/api-v2/server-inter/channel/content/announces/model.html#Announces) 对象。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
创建频道公告请求数据包
 

```json
{
  "channel_id": "123456",
  "message_id": "xxxxxx"
}
```

创建频道公告响应数据包
 

```json
{
  "guild_id": "xxxxxx",
  "channel_id": "123456",
  "message_id": "xxxxxx",
  "announces_type": 0,
  "recommend_channels":[]
}
```

创建推荐子频道类型的频道公告请求数据包
 

```json
{
 "announces_type": 1,
 "recommend_channels": [{
  "channel_id": "xxxx",
  "introduce": "推荐语"
 }, {
  "channel_id": "xxxx",
  "introduce": "推荐语"
 }]
}
```

创建推荐子频道类型的频道公告响应数据包
 

```json
{
	"guild_id": "xxxxxx",
	"channel_id": "xxxxx",
    "message_id": "",
	"announces_type": 1,
	"recommend_channels": [{
		"channel_id": "xxxx",
		"introduce": "推荐语"
	}, {
		"channel_id": "xxxx",
		"introduce": "推荐语"
	}]
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/announces/post_guild_announces.html>


---

# 删除频道公告
 
## 接口
 

```http
DELETE /guilds/{guild_id}/announces/{message_id}
```

## 功能描述
 
用于删除频道 `guild_id` 下指定 `message_id` 的全局公告。
 - `message_id` 有值时，会校验 `message_id` 合法性，若不校验校验 `message_id`，请将 `message_id` 设置为 `all`。

 
## Content-Type
 

```http
application/json
```

## 返回
 
成功返回 HTTP 状态码 `204`。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```code
DELETE /guilds/123456/announces/112233
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/announces/delete_guild_announces.html>


---

# 添加精华消息
 
## 接口
 

```http
PUT /channels/{channel_id}/pins/{message_id}
```

## 功能描述
 
用于添加子频道 `channel_id` 内的精华消息。
 - 精华消息在一个子频道内最多只能创建 `20` 条。
 - 只有可见的消息才能被设置为精华消息。
 - 接口返回对象中 `message_ids` 为当前请求后子频道内所有精华消息 `message_id` 数组。

 
## Content-Type
 

```http
application/json
```

## 返回
 
返回 [PinsMessage](/wiki/develop/api-v2/server-inter/channel/content/pins/model.html#PinsMessage) 对象。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```code
PUT /channels/123456/pins/112233
```

响应数据包
 

```json
{
  "guild_id": "xxxxxx",
  "channel_id": "xxxxxx",
  "message_ids": ["xxxxx"]
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/pins/put_pins_message.html>


---

# 删除精华消息
 
## 接口
 

```http
DELETE /channels/{channel_id}/pins/{message_id}
```

## 功能描述
 
用于删除子频道 `channel_id` 下指定 `message_id` 的精华消息。
 - 删除子频道内全部精华消息，请将 `message_id` 设置为 `all`。

 
## Content-Type
 

```http
application/json
```

## 返回
 
成功返回 HTTP 状态码 `204`。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```code
DELETE /channels/123456/pins/112233
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/pins/delete_pins_message.html>


---

# 获取精华消息
 
## 接口
 

```http
GET /channels/{channel_id}/pins
```

## 功能描述
 
用于获取子频道 `channel_id` 内的精华消息。
 
## Content-Type
 

```http
application/json
```

## 返回
 
返回 [PinsMessage](/wiki/develop/api-v2/server-inter/channel/content/pins/model.html#PinsMessage) 对象。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
响应数据包
 

```json
{
  "guild_id": "xxxxxx",
  "channel_id": "xxxxxx",
  "message_ids": ["xxxxx"]
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/pins/get_pins_message.html>


---

# 获取频道日程列表
 
## 接口
 

```http
GET /channels/{channel_id}/schedules
```

## 功能描述
 
用于获取`channel_id`指定的子频道中当天的日程列表。
 - 若带了参数 `since`，则返回结束时间在 `since` 之后的日程列表；若未带参数 `since`，则默认返回当天的日程列表。

 
## Content-Type
 

```http
application/json
```

## 参数
      
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| since | uint64 | 起始时间戳(ms) |
 
## 返回
 
返回 [Schedule](/wiki/develop/api-v2/server-inter/channel/content/schedule/model.html#schedule) 对象数组。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{
  "since": 1642076400000
}
```

响应数据包
 

```json
[
  {
    "id": "xxxxxx",
    "name": "上王者",
    "start_timestamp": "1642076400000",
    "end_timestamp": "1642083600000",
    "creator": {
      "user": {
        "id": "xxxxxx",
        "username": "xxxxxx",
        "bot": true
      },
      "nick": "",
      "joined_at": "2022-01-11T10:24:13+08:00"
    },
    "jump_channel_id": "0",
    "remind_type": "0"
  }
]
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/schedule/get_schedules.html>


---

# 获取日程详情
 
## 接口
 

```http
GET /channels/{channel_id}/schedules/{schedule_id}
```

## 功能描述
 
获取日程子频道 `channel_id` 下 `schedule_id` 指定的的日程的详情。
 
## Content-Type
 

```http
application/json
```

## 返回
 
返回 [Schedule](/wiki/develop/api-v2/server-inter/channel/content/schedule/model.html#schedule) 对象。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```shell
GET /channels/123455/schedules/112233
```

响应数据包
 

```json
{
  "id": "112233",
  "name": "上王者",
  "start_timestamp": "1642076400000",
  "end_timestamp": "1642083600000",
  "creator": {
    "user": {
      "id": "xxxxxx",
      "username": "xxxxxx",
      "bot": true
    },
    "nick": "",
    "joined_at": "2022-01-11T10:24:13+08:00"
  },
  "jump_channel_id": "0",
  "remind_type": "0"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/schedule/get_schedule.html>


---

# 创建日程
 
## 接口
 

```http
POST /channels/{channel_id}/schedules
```

## 功能描述
 
用于在 `channel_id` 指定的`日程子频道`下创建一个日程。
 - 要求操作人具有`管理频道`的权限，如果是机器人，则需要将机器人设置为管理员。
 - 创建成功后，返回创建成功的日程对象。
   - 单个管理员每天限`10`次。
   - 单个频道每天`100`次。
  - 单个频道每天`100`次。

 
## Content-Type
 

```http
application/json
```

## 参数
      
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| schedule | [Schedule](/wiki/develop/api-v2/server-inter/channel/content/schedule/model.html#schedule) | 日程对象，不需要带 `id` |
 
## 返回
 
返回[Schedule](/wiki/develop/api-v2/server-inter/channel/content/schedule/model.html#schedule) 对象。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{
  "schedule": {
    "name": "上王者",
    "start_timestamp": "1642076453000",
    "end_timestamp": "1642083653000",
    "jump_channel_id": "0",
    "remind_type": "0"
  }
}
```

响应数据包
 

```json
{
  "id": "xxxxxx",
  "name": "上王者",
  "start_timestamp": "1642076400000",
  "end_timestamp": "1642083600000",
  "creator": {
    "user": {
      "id": "xxxxxx",
      "username": "xxxxxx",
      "bot": true
    },
    "nick": "",
    "joined_at": "2022-01-11T10:24:13+08:00"
  },
  "jump_channel_id": "0",
  "remind_type": "0"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/schedule/post_schedule.html>


---

# 修改日程
 
## 接口
 

```http
PATCH /channels/{channel_id}/schedules/{schedule_id}
```

## 功能描述
 
用于修改日程子频道 `channel_id` 下 `schedule_id` 指定的日程的详情。
 - 要求操作人具有`管理频道`的权限，如果是机器人，则需要将机器人设置为管理员。

 
## Content-Type
 

```http
application/json
```

## 参数
      
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| schedule | [Schedule](/wiki/develop/api-v2/server-inter/channel/content/schedule/model.html#schedule) | 日程对象，不需要带 id |
 
## 返回
 
返回 [Schedule](/wiki/develop/api-v2/server-inter/channel/content/schedule/model.html#schedule) 对象。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{
  "schedule": {
    "name": "今晚八点上王者",
    "start_timestamp": "1642076453000",
    "end_timestamp": "1642083653000",
    "jump_channel_id": "0",
    "remind_type": "0"
  }
}
```

响应数据包
 

```json
{
  "id": "xxxxxx",
  "name": "今晚八点上王者",
  "start_timestamp": "1642076453000",
  "end_timestamp": "1642083653000",
  "creator": {
    "user": {
      "id": "xxxxxx",
      "username": "xxxxxx",
      "bot": true
    },
    "nick": "",
    "joined_at": "2022-01-13T11:02:21+08:00"
  },
  "jump_channel_id": "0",
  "remind_type": "0"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/schedule/patch_schedule.html>


---

# 删除日程
 
## 接口
 

```http
DELETE /channels/{channel_id}/schedules/{schedule_id}
```

## 功能描述
 
用于删除日程子频道 `channel_id` 下 `schedule_id` 指定的日程。
 - 要求操作人具有`管理频道`的权限，如果是机器人，则需要将机器人设置为管理员。

 
## Content-Type
 

```http
application/json
```

## 返回
 
成功返回 HTTP 状态码 `204`。
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```shell
DELETE /channels/123456/schedules/112233
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/schedule/delete_schedule.html>


---

# 音频控制
 
## 接口
 

```http
POST /channels/{channel_id}/audio
```

## 功能描述
 
用于控制子频道 `channel_id` 下的音频。
 - 音频接口：仅限音频类机器人才能使用，后续会根据机器人类型自动开通接口权限，现如需调用，需联系平台申请权限。

 
## Content-Type
 

```http
application/json
```

## 参数
 
参照 [AudioControl](/wiki/develop/api-v2/server-inter/channel/content/audio/model.html#audiocontrol)。
 
## 返回
 
成功返回空对象。
 

```json
{}
```

## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{
  "audio_url": "http:/xxxxx.mp3",
  "text": "xxx",
  "status": 0
}
```

响应数据包
 

```json
{}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/audio/audio_control.html>


---

# 机器人上麦
 
## 接口
 

```http
PUT /channels/{channel_id}/mic
```

## 功能描述
 
机器人在 `channel_id` 对应的语音子频道上麦。
 
音频接口：仅限音频类机器人才能使用，后续会根据机器人类型自动开通接口权限，现如需调用，需联系平台申请权限。
 
## Content-Type
 

```http
application/json
```

## 参数
 
url参数：channel_id
 
## 返回
 
成功返回空对象。
 

```json
{}
```

## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{}
```

响应数据包
 

```json
{}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/audio/put_mic.html>


---

# 机器人下麦
 
## 接口
 

```http
DELETE /channels/{channel_id}/mic
```

## 功能描述
 
机器人在 `channel_id` 对应的语音子频道下麦。
 
音频接口：仅限音频类机器人才能使用，后续会根据机器人类型自动开通接口权限，现如需调用，需联系平台申请权限。
 
## Content-Type
 

```http
application/json
```

## 参数
 
url参数：channel_id
 
## 返回
 
成功返回空对象。
 

```json
{}
```

## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 
请求数据包
 

```json
{}
```

响应数据包
 

```json
{}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/audio/delete_mic.html>


---

# 获取帖子列表
 
## 接口
 

```http
GET /channels/{channel_id}/threads
```

## 功能描述
 - 该接口用于获取子频道下的帖子列表。

 - 公域机器人暂不支持申请，仅私域机器人可用，选择私域机器人后默认开通。
- 注意: 开通后需要先将机器人从频道移除，然后重新添加，方可生效。

> **警告**
> 注意
 
## Content-Type
 

```http
application/json
```

## 返回
         
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| threads | [Thread](/wiki/develop/api-v2/server-inter/channel/content/forum/model.html#Thread) | 帖子列表对象（返回值里面的content字段，可参照[RichText](/wiki/develop/api-v2/server-inter/channel/content/forum/model.html#RichText)结构） |
| is_finish | uint32 | 是否拉取完毕(0:否；1:是) |
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 

```json
{
  "threads": [{
    "guild_id": "75827011639035987",
    "channel_id": "2324603",
    "author_id": "144115218680332809",
    "thread_info": {
      "thread_id": "B_59101362700301001441152186803328090X60-1645416537",
      "title": "帖子标题1",
      "content": "{\"paragraphs\":[{\"elems\":[{\"text\":{\"text\":\"发送消息 | QQ机器人文档\"},\"type\":1}],\"props\":{}},{\"elems\":[{\"text\":{\"text\":\"• 主动消息：发送消息时，未填充msg_id 字段的消息。\"},\"type\":1}],\"props\":{}}]}",
      "date_time": "2022-02-21T12:08:57+08:00"
    }
  },
    {
      "guild_id": "75827011639035987",
      "channel_id": "2324603",
      "author_id": "144115218680332809",
      "thread_info": {
        "thread_id": "B_79051362477c03001441152186803328090X60-1645413753",
        "title": "帖子标题2",
        "content": "{\"paragraphs\":[{\"elems\":[{\"text\":{\"text\":\"发送消息 | QQ机器人文档\"},\"type\":1}],\"props\":{}},{\"elems\":[{\"text\":{\"text\":\"• 主动消息：发送消息时，未填充msg_id 字段的消息。\"},\"type\":1}],\"props\":{}}]}",
        "date_time": "2022-02-21T11:22:33+08:00"
      }
    }
  ],
  "is_finish": 1
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/forum/get_threads_list.html>


---

# 获取帖子详情
 
## 接口
 

```http
GET /channels/{channel_id}/threads/{thread_id}
```

## 功能描述
 - 该接口用于获取子频道下的帖子详情。

 - 公域机器人暂不支持申请，仅私域机器人可用，选择私域机器人后默认开通。
- 注意: 开通后需要先将机器人从频道移除，然后重新添加，方可生效。

> **警告**
> 注意
 
## Content-Type
 

```http
application/json
```

## 返回
      
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| thread | [ThreadInfo](/wiki/develop/api-v2/server-inter/channel/content/forum/model.html#ThreadInfo) | 帖子详情对象（返回值里面的content字段，可参照[RichText](/wiki/develop/api-v2/server-inter/channel/content/forum/model.html#RichText)结构） |
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 示例
 

```json
{
  "thread":{
    "guild_id":"75827011639035987",
    "channel_id":"2324603",
    "author_id":"144115218680332809",
    "thread_info":{
      "thread_id":"B_79051362477c03001441152186803328090X60-1645413753",
      "title":"帖子标题",
      "content":"{\"paragraphs\":[{\"elems\":[{\"text\":{\"text\":\"发送消息 | QQ机器人文档\"},\"type\":1}],\"props\":{}},{\"elems\":[{\"text\":{\"text\":\"• 主动消息：发送消息时，未填充msg_id 字段的消息。\"},\"type\":1}],\"props\":{}}]}",
      "date_time":"2022-02-21T11:22:33+08:00"
    }
  }
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/forum/get_thread.html>


---

# 发表帖子
 
## 接口
 

```http
PUT /channels/{channel_id}/threads
```

## 功能描述
 - 创建成功后，返回创建成功的任务ID。

 - 公域机器人暂不支持申请，仅私域机器人可用，选择私域机器人后默认开通。
- 注意: 开通后需要先将机器人从频道移除，然后重新添加，方可生效。

> **警告**
> 注意
 
## Content-Type
 

```http
application/json
```

## 参数
            
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| title | string | 帖子标题 |
| content | string | 帖子内容 |
| format | uint32 | 帖子文本格式 |
 
### Format
 - 帖子文本格式

               
| 字段名 | 值 | 描述 |
| --- | --- | --- |
| FORMAT_TEXT | 1 | 普通文本 |
| FORMAT_HTML | 2 | HTML |
| FORMAT_MARKDOWN | 3 | Markdown |
| FORMAT_JSON | 4 | JSON（content参数可参照[RichText](/wiki/develop/api-v2/server-inter/channel/content/forum/model.html#RichText)结构） |
 
## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 返回
         
| 字段名 | 类型 | 描述 |
| --- | --- | --- |
| task_id | string | 帖子任务ID |
| create_time | string | 发帖时间戳，单位：秒 |
 
## 示例
 
请求数据包
 

```json
{
    "title": "title",
    "content": "<html lang=\"en-US\"><body><a href=\"https://bot.q.qq.com/wiki\" title=\"QQ机器人文档Title\">QQ机器人文档</a>\n<ul><li>主动消息：发送消息时，未填msg_id字段的消息。</li><li>被动消息：发送消息时，填充了msg_id字段的消息。</li></ul></body></html>",
    "format": 2
}
```

响应数据包
 

```json
{
    "task_id": "1645413752912602306",
    "create_time": "1645503180"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/forum/put_thread.html>


---

# 删除帖子
 
## 接口
 

```http
DELETE /channels/{channel_id}/threads/{thread_id}
```

## 功能描述
 - 该接口用于删除指定子频道下的某个帖子。

 - 公域机器人暂不支持申请，仅私域机器人可用，选择私域机器人后默认开通。
- 注意: 开通后需要先将机器人从频道移除，然后重新添加，方可生效。

> **警告**
> 注意
 
## Content-Type
 

```http
application/json
```

## 错误码
 
详见[错误码](/wiki/develop/api-v2/openapi/error/error.html)。
 
## 返回
 
HTTP 状态码 `204`

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/forum/delete_thread.html>


---

# 论坛事件对象(ForumEvent)
 
## FORUM_EVENT（intents FORUM_EVENT）
 
## 发送时机
 - 用户在话题子频道内发帖、评论、回复评论时产生该事件

 
## 主题事件
 - FORUM_THREAD_CREATE
 - FORUM_THREAD_UPDATE
 - FORUM_THREAD_DELETE

 
事件内容为 [Thread](/wiki/develop/api-v2/server-inter/channel/content/forum/model.html#Thread) 对象
 
## 示例
 

```json
{
  "guild_id": 47129941624960822,
  "channel_id": 1661124,
  "author_id": 144115218182563108,
  "thread_info": {
    "thread_id": "B_7c02cb615f8904001441152181825631080X60",
    "title": [{
      "type": 1,
      "text_info": {
        "text": "Test"
      }
    }],
    "content": [{
      "type": 1,
      "text_info": {
        "text": "tencent "
      }
    }, {
      "type": 5,
      "channel_info": {
        "channel_id": 1505272,
        "channel_name": "#隐私子频道"
      }
    }, {
      "type": 1,
      "text_info": {
        "text": " "
      }
    }, {
      "type": 3,
      "url_info": {
        "url": "https://apple.com",
        "display_text": "Apple"
      }
    }, {
      "type": 1,
      "text_info": {
        "text": ""
      }
    }],
    "date_time": "2021-12-30T15:17:34+08:00"
  }
}
```

## 帖子事件
 - FORUM_POST_CREATE
 - FORUM_POST_DELETE

 
事件内容为 [Post](/wiki/develop/api-v2/server-inter/channel/content/forum/model.html#Post) 对象
 
## 示例
 

```json
{
  "guild_id": "47129941624960822",
  "channel_id": "1661124",
  "author_id": "144115218182563108",
  "post_info": {
    "thread_id": "B_6d02bb61e45b0d001441152181867088220X60",
    "post_id": "c_1500cb611f950a001441152181825631080X60",
    "content": [{
      "type": 1,
      "text_info": {
        "text": "test"
      }
    }, {
      "type": 4,
      "emoji_info": {
        "id": 109,
        "type": "1"
      }
    }, {
      "type": 1,
      "text_info": {
        "text": "111"
      }
    }, {
      "type": 4,
      "emoji_info": {
        "id": 13,
        "type": "1"
      }
    }],
    "date_time": "2021-12-30T15:17:34+08:00"
  }
}
```

## 回复事件
 - FORUM_REPLY_CREATE
 - FORUM_REPLY_DELETE

 
事件内容为 [Reply](/wiki/develop/api-v2/server-inter/channel/content/forum/model.html#Reply) 对象
 
## 示例
 

```json
{
  "guild_id": 47129941624960822,
  "channel_id": 1661124,
  "author_id": 144115218182563108,
  "reply_info": {
    "thread_id": "B_8914b26116bb03001441152181867088220X60",
    "post_id": "c_39bab261d2b907001441152181867088220X60",
    "reply_id": "r_e701cb6128dc0b001441152181825631080X60",
    "content": [{
      "type": 1,
      "text_info": {
        "text": "Apple"
      }
    }],
    "date_time": "2021-12-30T15:17:34+08:00"
  }
}
```

## 帖子审核事件
 - FORUM_PUBLISH_AUDIT_RESULT

 
事件内容为 [AuditResult](/wiki/develop/api-v2/server-inter/channel/content/forum/model.html#AuditResult) 对象
 

```json
{
  "guild_id": 47129941624960822,
  "channel_id": 1661124,
  "author_id": 144115218182563108,
  "type": 1,
  "result":0,
  "err_msg": "",
  "thread_id": "B_8914b26116bb03001441152181867088220X60",
  "post_id": "c_39bab261d2b907001441152181867088220X60",
  "reply_id": "r_e701cb6128dc0b001441152181825631080X60"
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/forum/forum.html>


---

# 开放论坛事件对象(OpenForumEvent)
 
## OEPN_FORUM_EVENT（intents OPEN_FORUM_EVENT）
 
发送时机
 - 用户在话题子频道内发帖、评论、回复评论时产生该事件

 
## 主题事件
 - OPEN_FORUM_THREAD_CREATE
 - OPEN_FORUM_THREAD_UPDATE
 - OPEN_FORUM_THREAD_DELETE

 
### 示例
 

```json
{
  "guild_id": "47129941624960822",
  "channel_id": "1661124",
  "author_id": "144115218182563108",
}
```

## 帖子事件
 - OPEN_FORUM_POST_CREATE
 - OPEN_FORUM_POST_DELETE

 
### 示例
 

```json
{
  "guild_id": "47129941624960822",
  "channel_id": "1661124",
  "author_id": "144115218182563108",
}
```

## 回复事件
 - OPEN_FORUM_REPLY_CREATE
 - OPEN_FORUM_REPLY_DELETE

 
### 示例
 

```json
{
  "guild_id": "47129941624960822",
  "channel_id": "1661124",
  "author_id": "144115218182563108",
}
```


> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/content/forum/open_forum.html>


---

#### 小程序相关

# 开放数据域加密
 
## 背景
 
由于小程序没有用于跟平台接口进行后台鉴权使用的用户票据。
所以开发者在小程序前端鉴权会后，如果还需要将鉴权结果传递给自己的后台，做后台鉴权，这个时候在后台中需要机遇 session key 针对 rawData 进行签名验证来保证数据没有被篡改过。
 
## 开放数据加密-参考文档
 
https://q.qq.com/wiki/develop/game/frame/open-ability/signature.html

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/miniapp/opendata.html>


---

# 获取频道和当前人信息
 
适用场景：
 
1.机器人服务打开小程序后（机器人服务需在机器人开发者端-服务配置）
 
2.机器人发出的`ark` 打开小程序后（`ark`模版的跳转`link`可以带上对应的参数）
 
## 从 extendData 中获取频道ID
 
### 机器人服务打开小程序
 
开发者在开发者平台配置服务功能的时候，在 `extData` 支持使用占位符来获取`频道ID`，`子频道ID`。
 
如：`guildID=$OPENGUILDID$&channelID=$CHANNELID$`
 
平台会在频道中打开机器人面板的时候，对占位符进行替换。开发者可以在 `onLaunch` 的时候从 `options.extendData` 中获取数据。
 
### 机器人发出的ark打开小程序
 
由于机器人发送消息到频道的时候，是知道 `$OPENGUILDID$` 和 `$CHANNELID$` 的，所以可以在发送消息的时候将对应参数的值直接带到小程序地址上用于打开的时候调用小程序接口
 
## 获取频道信息与当前人身份
 
`qq.getGuildInfo(Object object)`
 
### 调用参数 Object object
                                    
| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本 |
| --- | --- | --- | --- | --- | --- |
| open_guild_id | string |  | 是 | 频道在机器人场景的 [Guild](/wiki/develop/api-v2/server-inter/channel/manage/guild/model.html#guild) id | 1.40.0 |
| channel_id | string |  | 否 | 子频道Id | 1.40.0 |
| success | function |  | 否 | 接口调用成功的回调函数 | 1.40.0 |
| fail | function |  | 否 | 接口调用失败的回调函数 | 1.40.0 |
| complete | function |  | 否 | 接口调用结束的回调函数（调用成功、失败都会执行） | 1.40.0 |
 
`open_guild_id` 从小程序的 `extendData` 上获取，即开发者在机器人平台配置小程序服务时候提示到的 `$OPENGUILDID$`
 
### Object.success 回调函数参数 Object res
 
#### 解密前
 
res 得到的是加密之后的数据，需要开发者解密，解密方案参考: [开放数据校验与解密  (opens new window)](https://q.qq.com/wiki/develop/game/frame/open-ability/signature.html)
            
| 属性 | 类型 | 说明 |
| --- | --- | --- |
| encryptedData | string | 加密之后的数据，需要解密 |
| iv | string | 对称解密算法初始向量(base64) |
| signature | string | 签名(base64) |
 
### encryptedData 解密后的数据
                     
| 属性 | 类型 | 说明 |
| --- | --- | --- |
| guild_name | string | 频道名称 |
| member_role | number | 当前成员角色 0成员/1管理员/2频道主 |
| channel_info | Object | 子频道信息，只在请求上有channel_id的时候才会返回 |
| member_userid | string | 当前用户在机器人场景的 [User](/wiki/develop/api-v2/openapi/user/model.html#user) id |
| member_nick | string | 当前用户在频道内的昵称 |
| open_guild_id | string | [Guild](/wiki/develop/api-v2/server-inter/channel/manage/guild/model.html#guild) id |
 
### Object channel_info 子频道信息
            
| 属性 | 类型 | 说明 |
| --- | --- | --- |
| channel_name | string | 子频道名称 |
| channel_type | number | 子频道类型 |
| is_accessible | number | 是否可以访问该子频道，0不可访问、1可访问 |

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/server-inter/channel/miniapp/interface.html>


---

## 变更记录

# 变更记录
 
## 20260903
 
### 新增
     - 获取群成员列表
     - 获取群成员信息
     - 群成员批量移除
     - 群黑名单查询
     - 群黑名单操作
    - 群黑名单操作
    - 群黑名单操作

 
### 优化
 - 修改了部分接口描述。

 
## 20260812
 
### 新增
   - 新增查询、修改全局自定义菜单接口。
  - 新增查询、修改全局自定义菜单接口。
   - 新增指令面板管理接口，支持查询列表、创建、查询详情、修改、删除及修改关联对象。
  - 新增指令面板管理接口，支持查询列表、创建、查询详情、修改、删除及修改关联对象。

 
## 20260810
 
### 优化
 - 接口调用域名统一：所有接口调用域名统一为 `api.bot.qq.com`。

 
### 新增
   - 发送 Markdown 消息：新增可选参数 `force_verify_image_resource`。开启后，当图片资源转存失败时，将中断消息发送并返回失败（默认关闭，保持原有行为）。
  - 发送 Markdown 消息：新增可选参数 `force_verify_image_resource`。开启后，当图片资源转存失败时，将中断消息发送并返回失败（默认关闭，保持原有行为）。
     - 查询用户禁言状态
     - 设置用户禁言
    - 设置用户禁言
     - 拉取入群申请列表
     - 审批入群请求
    - 审批入群请求
   - 新增入群自动审批策略相关接口。
  - 新增入群自动审批策略相关接口。
   - 新增用户入群申请事件。
  - 新增用户入群申请事件。

> 📖 原文链接：<https://bot.q.qq.com/wiki/develop/api-v2/changelog.html>


---
