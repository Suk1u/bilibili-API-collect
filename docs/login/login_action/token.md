# APP 端令牌管理

## 刷新令牌

> https://passport.bilibili.com/api/oauth2/refreshToken

*请求方式：POST*

鉴权方式：APP（access_key），需要 APP 签名，签名算法见 [APP API 签名](../../misc/sign/APP.md)

用于在 `access_token` 过期前获取新的令牌，刷新成功后旧令牌失效

**正文参数（application/x-www-form-urlencoded）：**

| 参数名        | 类型 | 内容           | 必要性 | 备注 |
|---------------|-----|----------------|--------|------|
| access_token  | str | 当前登录令牌   | 必要   |      |
| refresh_token | str | 当前刷新令牌   | 必要   |      |

除此之外还需传入 APP 签名公共参数（`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`），详见 [APP API 签名](../../misc/sign/APP.md)

**json回复：**

根对象：

| 字段   | 类型 | 内容     | 备注    |
|--------|-----|----------|---------|
| code   | num | 返回值   | 0：成功 |
| message | str | 错误信息 | 默认为0 |
| data   | obj | 令牌信息 |         |

`data`对象：

| 字段          | 类型 | 内容           | 备注     |
|---------------|-----|----------------|----------|
| mid           | num | 用户 mid       |          |
| access_token  | str | 新的登录令牌   |          |
| refresh_token | str | 新的刷新令牌   |          |
| expires_in    | num | 有效时长       | 单位为秒 |

**示例：**

```shell
curl 'https://passport.bilibili.com/api/oauth2/refreshToken' \
--data-urlencode 'access_token=xxx' \
--data-urlencode 'refresh_token=xxx' \
--data-urlencode 'appkey=xxx' \
--data-urlencode 'build=xxx' \
--data-urlencode 'mobi_app=android' \
--data-urlencode 'platform=android' \
--data-urlencode 'ts=0' \
--data-urlencode 'sign=xxx'
```

## 查询令牌信息

> https://passport.bilibili.com/api/oauth2/info

*请求方式：GET*

鉴权方式：APP（access_key），需要 APP 签名，签名算法见 [APP API 签名](../../misc/sign/APP.md)

可用于校验 `access_token` 是否有效，以及判断是否需要刷新令牌

**url参数：**

| 参数名       | 类型 | 内容         | 必要性 | 备注 |
|--------------|-----|--------------|--------|------|
| access_token | str | 登录令牌     | 必要   |      |

除此之外还需传入 APP 签名公共参数（`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`），详见 [APP API 签名](../../misc/sign/APP.md)

**json回复：**

根对象：

| 字段   | 类型 | 内容     | 备注                          |
|--------|-----|----------|-------------------------------|
| code   | num | 返回值   | 0：成功<br />非 0：令牌无效   |
| message | str | 错误信息 | 默认为0                       |
| data   | obj | 令牌信息 |                               |

`data`对象：

| 字段   | 类型 | 内容               | 备注                       |
|--------|-----|--------------------|----------------------------|
| refresh | bool | 是否需要刷新令牌   |                            |

注：`data` 中其余字段作用尚不明确，响应结构待补充

**示例：**

```shell
curl -G 'https://passport.bilibili.com/api/oauth2/info' \
--data-urlencode 'access_token=xxx' \
--data-urlencode 'appkey=xxx' \
--data-urlencode 'build=xxx' \
--data-urlencode 'mobi_app=android' \
--data-urlencode 'platform=android' \
--data-urlencode 'ts=0' \
--data-urlencode 'sign=xxx'
```

## 令牌转Cookie（SSO）

> https://passport.bilibili.com/api/login/sso

*请求方式：GET*

鉴权方式：APP（access_key），需要 APP 签名，签名算法见 [APP API 签名](../../misc/sign/APP.md)

用于将 APP 端 `access_key` 登录态同步为 Web 端 Cookie 登录态

**url参数：**

| 参数名     | 类型 | 内容         | 必要性 | 备注 |
|------------|-----|--------------|--------|------|
| access_key | str | 登录令牌     | 必要   |      |

除此之外还需传入 APP 签名公共参数（`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`），详见 [APP API 签名](../../misc/sign/APP.md)

**回复：**

接口通过重定向（`Location` 响应头）返回携带 cookie 相关字段的跳转 url，用于跨端同步登录状态（依据第三方客户端 biliuwp 源码注释推断，未经验证）

响应结构待补充

**示例：**

```shell
curl -G 'https://passport.bilibili.com/api/login/sso' \
--data-urlencode 'access_key=xxx' \
--data-urlencode 'appkey=xxx' \
--data-urlencode 'build=xxx' \
--data-urlencode 'mobi_app=android' \
--data-urlencode 'platform=android' \
--data-urlencode 'ts=0' \
--data-urlencode 'sign=xxx'
```

## Cookie转令牌（第三方授权）

> https://passport.bilibili.com/login/app/third

*请求方式：GET*

认证方式：Cookie（SESSDATA）

鉴权方式：APP，需要 APP 签名，签名算法见 [APP API 签名](../../misc/sign/APP.md)

用于将 Web 端 Cookie 登录态转换为指定 `appkey` 的 APP 端 `access_key`

**url参数：**

| 参数名 | 类型 | 内容                 | 必要性 | 备注                                     |
|--------|-----|----------------------|--------|------------------------------------------|
| appkey | str | APP密钥              | 必要   |                                           |
| api    | str | 第三方回跳地址       | 必要   | 一般为 `http://link.acg.tv/forum.php`     |
| sign   | str | APP签名              | 必要   | 对`api`参数串进行 APP 签名得到            |

**json回复：**

根对象：

| 字段   | 类型 | 内容     | 备注    |
|--------|-----|----------|---------|
| code   | num | 返回值   | 0：成功 |
| message | str | 错误信息 | 默认为0 |
| data   | obj | 授权信息 |         |

`data`对象：

| 字段         | 类型 | 内容                   | 备注                                       |
|--------------|-----|------------------------|--------------------------------------------|
| api_host     | str | 第三方授权域名         |                                            |
| has_login    | num | 是否已登录             |                                            |
| direct_login | num | 是否直接登录           |                                            |
| confirm_uri  | str | 授权确认页面 url       | 需携带当前 Cookie 再次请求                 |

取得 `confirm_uri` 后，携带 Cookie 请求该地址并跟随重定向，最终落地 url 的 query 中即包含 `access_key`（依据第三方客户端 biliuwp 源码逻辑）

**示例：**

```shell
curl -G 'https://passport.bilibili.com/login/app/third' \
--data-urlencode 'appkey=xxx' \
--data-urlencode 'api=http://link.acg.tv/forum.php' \
--data-urlencode 'sign=xxx' \
-b 'SESSDATA=xxx'
```
