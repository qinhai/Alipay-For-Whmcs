# Alipay-For-Whmcs
WHMCS 修正 By 秦海传媒-姜
date:2015-08-01
mail:s@qinhai.us

readme:
修正whmcs 6.0下不能到账错误

===============More============


WHMCS 支付宝接口详细安装说明
2010/5/1    Bendy  
67052[at]QQ.com

文件解压后..直接上传到whmcs的modules/gateways 目录下..
文件包内具体文件介绍
readme.txt                        ------本文件
alipay.php                        ------主处理文件(重要)
callback/alipay_callback.php      ------接收支付宝服务器发来的同步数据(重要)
callback/alipay_return.htm        ------支付完成后返回的页面(不处理数据,纯HTML页面)
callback/alipay.gif               ------支付页面上使用的支付宝图标文件

上传文件后..
先到管理员后台进行货币设置.
本接口设计时,只支持RMB作为货币单位,所以.你在WHMCS一定要先设置正确...
具体设置位置是管理员后台的CONFIGURATION =>  CURRENCIES
这个货币设置可能新手不太明白...
我分二种情况说明
一,只使用RMB一种货币...那直接填一个就OK了...不用费心.
二,使用二种以上的货币...那就要涉及一个换算的地方.
填表的几个英文解析如下
Currency Code  (货币代码,,,RMB或者USD之类的)
Prefix	       (货币代号...$或者￥)
Suffix	       (货币名称...代号..比如"圆""刀"...我建议使用代码一致)
Format	       (金额格式...默认就OK了)
Base Conv. Rate	 (这个要注意,是转换比率.使用二种以上货币时要设置.先假定一个基本货币.比如RMB..那设置RMB时候.这里填1..而设置USD的时候.这里就填6.85)
Update Pricing  (更新价格)

设置完货币后..就可以启用接口了.
具体设置位置是CONFIGURATION => PAYMENT GATEWAYS
先在支付接口列表中找到alipay并按activite激活
几个设置详细说明:
==============
Show on Order Form	 (在订单中显示使用本支付接口..前提是你要设置好相应的货币转换及金额.这个具体意义是"需要以RMB支付的时候,使用这个支付接口在订单里面)
Visible Name	      (支付接口名称)
卖家支付宝帐户	    (你用来收款的支付宝帐号)
合作伙伴ID	        (合作ID和安全码..都在支付宝签约商家后台中找到.....什么?你还未签约???找支付宝吧.别找我)
安全检验码	
测试模式	 测试模式(暂时不可用)
Convert To For Processing	  (转换货币...这里一定要有RMB.并选择RMB..否则支付接口不可用)
==============


OK....完工...心情享受吧.

2010/5/1    Bendy  
67052[at]QQ.com
