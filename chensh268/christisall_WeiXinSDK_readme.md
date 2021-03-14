weixinsdk
=========
  
    //作者联系方法：
    //email:loogn_0707@126.com
    //QQ群:153725186
    //支付宝:loogn2012@gmail.com (开源免费，欢迎资助~)

微信公开帐号接口

    public class WeiXinUrl : IHttpHandler
    {
        static string token = "token";
        static string AppId = "AppId";
        static string AppSecret = "AppSecret";
        public void ProcessRequest(HttpContext context)
        {
            context.Response.ContentType = "text/plain";
            var signature = context.Request["signature"] ?? string.Empty;
            var timestamp = context.Request["timestamp"] ?? string.Empty;
            var nonce = context.Request["nonce"] ?? string.Empty;
            
            //var echostr = context.Request.QueryString["echostr"] ?? string.Empty;
            if (WeiXin.CheckSignature(signature, timestamp, nonce, token))
            {
                //context.Response.Write(echostr);
                var replyMsg = WeiXin.ReplyMsg().GetXML();
                context.Response.Write(replyMsg);
            }
            else
            {
                context.Response.Write("fuck you");
            }

        }

        static WeiXinUrl()
        {
            WeiXin.ConfigGlobalCredential(AppId, AppSecret);
            //消息通知事件
            WeiXin.OnReceiveMsgEvent += new WeiXin.ReceiveMsg(WeiXin_OnReceiveMsgEvent);
            
            WeiXin.RegisterMsgHandler (msg =>
            {
                return new ReplyTextMsg { Content = "你说：" + msg.Content };
            });

            WeiXin.RegisterEventHandler (msg =>
            {
                return new ReplyTextMsg { Content = "谢谢关注！" };
            });
        }

        
        //消息通知事件处理处理程序
        static void WeiXin_OnReceiveMsgEvent(string xml,Dictionary  dict)
        {
            if (dict.ContainsKey("Event"))
            {
               

            }
            else if (dict.ContainsKey("MsgId"))
            {

              
            }
        }
        
        public bool IsReusable
        {
            get
            {
                return false;
            }
        }
    }


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee1dada7380a3828fe210e1304d72f40ed6d29531265937f81fb95517c5996f57a7d659565e40cdfd32996b7657c028c4)