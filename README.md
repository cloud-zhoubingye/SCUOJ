# SCUOJ
An online judge system eespecially designed for competitions in colleges.
This is the frontend code for users.


# Data propagated to backend
User
|URL|Data Form|Description|
|---|---------|-----------|
|/user/login|loginForm={ username: '', password: ''}|用户登录时，post至数据库查询用户的用户名和密码。|
|/user/isExist|{ username: value }或{ email: value }|用户注册时，value为用户输入的用户名或邮箱，需要向数据库发送get请求来查询是否已经存在，若response.data.code === 0，则用户不存在，可以正常注册，若用户存在，应返回查询失败|
|/user/register|dataForm={ username: '', email: '', password: '', studentId: '' }|用户注册时，将写入数据库的资料（原代码中还有captcha: '', captchaId: ''两个字段）post至数据库，如信息有误，则抛出异常|
|/user/forgetPassword|dataForm={ username: '', email: '', captcha: '', captchaId: '' }|重置密码，post至数据库，实际的输入中username和email只会有一个，这取决于用户输入的是哪个。若成功重置，后端需向用户邮箱发送链接，用户使用链接重置密码，若重置失败则抛出异常|
|/user/resetPassword|dataForm={token: '', password: '', captcha: '', captchaId: '' }|将重新设置密码的请求post至数据库，这种模式下直接修改数据库中的密码为post的新密码，若失败则抛出异常|

Group
|URL|Data Form|Description|
|---|---------|-----------|
|/group/query|||
|/group/page|{ pageNow: this.pageNow, pageSize: this.pageSize, title: this.title }||
