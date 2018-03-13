
____

# 📣问题:有objectionable(反感的讨厌的) and offensive(不愉快的)被拒绝

**苹果邮件描述**<br>
Your app includes content that many users would find objectionable(反感的讨厌订单) and offensive(冒犯).
Specifically, your app facilitate paids(付费) companionship(陪同 伙伴) which is not appropriate for the App Store.
We've attached screenshot(s) for your reference.
Please remove all objectionable content from your app and submit your revised binary for review. 
苹果截图

 <img src="Picture/offensive/offensive_1.png" width="30%"> <img src="Picture/offensive/offensive_2.png" width="30%">


## 解决方案:
看到上文的汉字和红色箭头大致知道什么问题了
苹果认为付费陪玩不符合苹果审核指南

解决方案:上图中的45元/15分钟  调用后台接口,当在审核的时候隐藏

____



____

# 📣问题:如何隐藏部分功能
每次app 登陆掉一个接口 返回yes 或者no

<img src="Picture/offensive/howtoHide.png" width="80%">

**有的公司设个时间,超过了一定的时间比如7天后,某个界面的功能才正常显示,否则这个界面就隐藏部分内容,这样没有接口控制灵活不推荐**
这种隐藏普遍被使用,一经被苹果发现会被警告或者被封开发者账号,有公司隐藏被发现的
____

# 隐藏会不会发现
会被发现概率很低,博主知道的是小于3% 的概率会被发现,下面的案例是一个约单 app (将一个tabbar隐藏发现了)
<img src="Picture/hide_some_content.png" width="80%">

# 隐藏被暴露后的审核邮件示例

We discovered that your app contains hidden features. Specifically，xxxxxx（被发现的隐藏功能描述，审核结果可能会描述也可能不描述）

The next submission of this app may require a longer review time, and this app will not be eligible for an expedited review until this issue is resolved.

# 导致此审核结果的可能原因
- 之前提交过一些违法审核指南条款的功能，你按要求修改，移除这些代码后，没有在解决方案中心（或者审核备注中）向审核人员说明。
- 检查商店预览图是否和提审版本的界面有出入，预览图有的东西，如果在提审版本上找不到，也可能导致这个审核结果。
- [做了大量的代码混淆，也有可能被认定为想隐藏某些功能。](http://www.cocoachina.com/bbs/read.php?tid-1723101-page-1.html)出现这个情况，可以尝试移除代码混淆再次提审。
- 项目中，有某些第三方的SDK，但是其功能没有得到体现。[比如你的应用有内购，但是项目里有支付宝或者微信的SDK](https://www.zhihu.com/question/51743363)。
- 通过后端接口云控，被发现了。

# 提升后端接口云控隐蔽性（几点供参考）

- 接口上行下行统统加密
- 存储云控开关的变量使用多个，虽然变量的值都来源于后端接口，但是在不同的页面不同的逻辑上，使用不同的开关变量
- 用户界面内容的视图，不要先创建，然后根据开关来控制隐藏显示，而是审核时不创建这些视图
- 审核页面与用户页面（审核通过后）使用不同的控制器来做，而不是在一个控制器中，通过判断审核开关，在同一个控制器执行不同的界面逻辑

# 隐藏部分功能的加强版
- 动态下发代码(使用AOP、ReactNative，或者JSPatch、Weex的『修改版本』)。

# 隐藏被暴露之后怎么办 (几点供参考)
- 按照苹果规则来
- 支付宝隐藏 换内购,按照苹果爸爸的意见来
- 约炮按钮隐藏了 ? 显示出来
- 企业账号发布,可以为所欲为,只是适合初期的创业公司
- 找产品经理老板改需求
- 更换账号继续隐藏上传



