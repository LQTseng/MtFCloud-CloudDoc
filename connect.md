## SSH连接


### 首次连接会出现接受主机密钥的弹框，根据自身情况选择`一次性接受`或是`接受并保存`

> ![FirstConnection](_media/images/first_connection_xs.png)


### 错误码1：`ssh: handshake failed`


> - Xshell
>> ![HandshakeFailedXS](_media/images/handshake_failed_xs.png)


> - FinalShell
>> ![HandshakeFailedFS](_media/images/handshake_failed_fs.png)


#### 解决方案:

##### 方案1: 先[修改SSH密码](#修改SSH密码)，再[重启](#重启)
##### 方案2: 先[重装系统](#重装系统)，再[修改SSH密码](#修改SSH密码)，最后[重启](#重启)

> 方案1无法解决问题时，再尝试方案2
>
> 也可直接尝试方案2，基本能解决`ssh: handshake failed`的问题


### 错误码2：`i/o timeout`

> - FinalShell
>
> ![IoTimeout](_media/images/io_timeout.png)


#### 解决方案:

##### 方案1: 直接[重启](#重启)
##### 方案2: 先[重装系统](#重装系统)，再[修改SSH密码](#修改SSH密码)，最后[重启](#重启)

> 方案1无法解决问题时，再尝试方案2
>
> 也可直接尝试方案2，基本能解决`i/o timeout`的问题


### 错误码3：`Connection failed` 或 `Connection timed out`

#### 情况说明：

> 一般表示IP被墙，可以自行ping测试
>
> - Xshell
>> ![IpBannedXS](_media/images/ip_banned_xs.png)

> - FinalShell
>> ![IpBannedFS](_media/images/ip_banned_fs.png)


#### 解决方案:

##### 方案1: 使用跳板机【未被墙的VPS】通过ssh命令连接
> 语法: ```ssh -p 端口 用户名@IP```
>
> 举例: ```ssh -p 1022 root-1048@157.245.196.27```
>
> ![UseSshProxySuccFS](_media/images/useSshConnect.png)


##### 方案2: 设置ssh代理
> #### Xshell
>> ![SetSshProxyXS](_media/images/set_ssh_proxy_xs.png)
>> ![UseSshProxyXS](_media/images/use_ssh_proxy_xs.png)
>> ![UseSshProxySuccXS](_media/images/use_ssh_proxy_succ_xs.png)

> #### FinalShell 【两种方法选任意一种即可】
> - 方法1. 开启智能加速，可解决一般被墙IP
>> ![SetIntelligentAccelerationFS](_media/images/set_intelligent_acceleration_fs.png)
>>
>> ![SetIntelligentAccelerationSuccFS](_media/images/set_intelligent_acceleration_succ_fs.png.png)
>
> - 方法2. 设置代理服务器，可解决大部分被墙IP
>> ![SetSshProxyFS](_media/images/set_ssh_proxy_fs.png)
>>
>> ![UseSshProxyFS](_media/images/use_ssh_proxy_fs.png)
>>
>> ![UseSshProxySuccFS](_media/images/use_ssh_proxy_succ_fs.png)


##### 方案3: 通过网页版ssh工具连接
> - `https://ssh.kjqg.gay/`
>
>> ![WebSsh](_media/images/webssh.png)


### 其他错误补充

> - 有群友反馈，`Xshell`需关闭`X11转移`功能。但我这边仅提示警告，并不影响连接，如果你在几种方案都尝试后，仍连接失败，可尝试关闭该功能。
>> ![WebSsh](_media/images/rejected_x11.png)




## 修改SSH密码

> 登录官网，点击`Dashboard`，选择`您已激活的产品/服务`
>
> 【此处以`Free Area - SG Intel NAT VPS - Q6`为例】
>
> ![Dashboard](_media/images/mtf_dashboard.png)


### 方案1: 点击产品详情页面左侧`修改密码`，按照页面提示填入新密码，保存修改后，页面提示`修改密码成功`，即可[重启](#重启)VPS
> ![DetailResetPwd](_media/images/mtf_product_details_reset_pwd.png)


### 方案2: 点击产品详情页面左侧`Enduser Panel`，在`List VPS`页面选择你要操作的VPS，进入后台管理，按照页面提示填入新密码，提交修改后，页面弹框`Success`，即可[重启](#重启)VPS
> ![EnduserPanel](_media/images/mtf_product_details_enduser_panel.png)
> ![EnduserPanelListVPS](_media/images/mtf_enduser_panel_list_vps.png)
> ![EnduserPanelResetPwd](_media/images/mtf_enduser_panel_rest_pwd.png)


### 方案3: 在产品详情的`服务器信息`下的`VPS Information`里操作，操作步骤参考方案2最后一张图



## 重启

### 方案1: 在产品详情的左侧点击"Reboot VPS"，等待页面提示"操作成功"即可
> ![EnduserPanelResetPwd](_media/images/mtf_product_details_reboot.png)

### 方案2: 点击产品详情页面左侧`Enduser Panel`，在`List VPS`页面选择你要操作的VPS，进入后台管理，点击右侧重启按钮，页面弹框`Success`，即表示重启成功
> ![EnduserPanel](_media/images/mtf_product_details_enduser_panel.png)
> ![EnduserPanelListVPS](_media/images/mtf_enduser_panel_list_vps.png)
> ![EnduserPanelReboot](_media/images/mtf_enduser_panel_reboot.png)
> ![EnduserPanelRebootSucc](_media/images/mtf_enduser_panel_reboot_succ.png)


### 方案3: 在产品详情的`服务器信息`下的`VPS Information`里操作，点击重启按钮，页面弹框`Success`，即表示重启成功
> ![DetailVpsInfoReboot](_media/images/mtf_product_details_info_reboot.png)
> ![DetailVpsInfoRebootSucc](_media/images/mtf_product_details_info_reboot_succ.png)


## 重装系统

### 方案1: 点击产品详情页面左侧`Enduser Panel`，在`List VPS`页面选择你要操作的VPS，进入后台管理，选择`Install`，根据自己需求进行重装

> ![EnduserPanel](_media/images/mtf_product_details_enduser_panel.png)
> ![EnduserPanelListVPS](_media/images/mtf_enduser_panel_list_vps.png)
> ![EnduserPanelReboot](_media/images/mtf_enduser_panel_reinstall.png)


### 方案2: 在产品详情的`服务器信息`下的`VPS Information`里操作，操作步骤参考方案1最后一张图


### 提示: 重装系统可能会花费几分钟，可刷新页面查看VPS状态
