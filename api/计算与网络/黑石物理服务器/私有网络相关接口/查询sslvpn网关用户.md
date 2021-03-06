## 功能描述
DescribeBmSshSslVpnUser 用于查询黑石sslvpn网关用户。

接口请求域名：bmvpc.api.qcloud.com


## 请求

语法示例：
```
GET https://bmvpc.api.qcloud.com/v2/index.php/?Action=DescribeBmSshSslVpnUser
    &<公共请求参数>
	&vpnGwId=<sslvpn网关唯一ID>
```

### 请求参数
以下请求参数列表仅列出了接口请求参数，正式调用时需要加上公共请求参数，见<a href="/doc/api/372/4153" title="公共请求参数">公共请求参数</a>页面。其中，此接口的Action字段为 DescribeBmSshSslVpnUser。

| 参数名称 | 必选  | 类型 | 描述 |
|---------|---------|---------|---------|
| vpnGwId | 是 | string | 网关唯一ID |



## 响应
响应示例：
```
{
    "code": 0,
    "message": "",
    "codeDesc": "Success",
    "data": [
        {
            "userName": "sddddd",
            "domain": "206001"
        }
    ],
    "totalCount": 1
}
```
### 响应参数
| 参数名称 | 类型 | 描述 |
|---------|---------|---------|
| code | int | 错误码。0：成功, 其他值：失败|
| message | string | 错误信息|
| data | array | 返回的sslvpn网关所有的用户列表 |
| data.n.userName | String | 用户名, 用于vpn客户端登录的用户名。|
| data.n.domain | String | 用户所在域, 用于vpn客户端登录的域。 |


## 错误码
以下错误码表仅列出了该接口的业务逻辑错误码，更多公共错误码详见<a href="https://cloud.tencent.com/doc/api/245/4924" title="VPC错误码">VPC错误码</a>。
 
| 错误代码 | 英文提示 | 错误描述 |
|---------|---------|---------|
| 10001 | BmVpc.InvalidParameterValue | 参数设置错误，具体错误信息可查看返回的message信息 |
| -3264 | BmVpc.SslVpnNotExist | 私有网络下sslvpn网关不存在。 |


## 实际案例
### 请求
```
GET https://bmvpc.api.qcloud.com/v2/index.php?
	Action=DescribeBmSshSslVpnUser
	&SecretId=AKIDlfdHxN0ntSVt4KPH0xXWnGl21UUFNoO5
	&Nonce=11362
	&Timestamp=1515570588
	&Region=sh
	&vpnGwId=sshvpngw-hm6uj2yu
	&vpnGwName=testma111
	&userName=ssdfffffA
	&Signature=tvpK%2BxnptHI1O0WgnMG6C9pVBxc%3D
```

### 响应
```
{
    "code": 0,
    "message": "",
    "codeDesc": "Success",
    "data": [
        {
            "userName": "sddddd",
            "domain": "206001"
        }
    ],
    "totalCount": 1
}
```