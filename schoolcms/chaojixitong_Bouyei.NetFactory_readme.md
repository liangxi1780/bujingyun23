#Bouyei.NetFactory 基于.net framework 4.5.1+

#Bouyei.NetFactoryCore 基于.net core 2.2+

#Bystd.NetFactory 基于.net standard 2.1+

#客户端、服务端连接例子

	int port = 12346;
	//服务端
	INetServerProvider serverSocket = NetServerProvider.CreateProvider();      
	//接收到数据包事件
	serverSocket.ReceiveOffsetHandler = new OnReceiveOffsetHandler((sToken, buff, offset, count) =>
	{
		try
		{
			string info = Encoding.UTF8.GetString(buff, offset, count);
			Console.WriteLine(info);
		}
		catch (Exception ex)
		{
			Console.WriteLine(ex.ToString());
		}
	});
	//接收到客户端连接
	serverSocket.AcceptHandler = new OnAcceptHandler((sToken) =>
	{
		serverSocket.Send(new SegmentOffsetToken()
		{
			sToken = sToken,
			dataSegment = new SegmentOffset()
			{
				buffer = Encoding.Default.GetBytes("welcome" + DateTime.Now.ToString())
			}
		}, false);

		Console.WriteLine("accept" + sToken.TokenIpEndPoint);
	});
	//收到断开连接
	serverSocket.DisconnectedHandler = new OnDisconnectedHandler((stoken) =>
	{
		Console.WriteLine("disconnect" + stoken.TokenId);
	});
	bool isOk = serverSocket.Start(port);
	if (isOk)
	{
		Console.WriteLine("已启动服务。。。");
		//客户端
		INetClientProvider clientSocket = NetClientProvider.CreateProvider();

		//异步连接
		clientSocket.ReceiveOffsetHandler = new OnReceiveOffsetHandler((sToken, buff, offset, count) =>
		{
			try
			{
				Console.WriteLine("rec:" + Encoding.Default.GetString(buff,offset,count));
			}
			catch (Exception ex)
			{

			}
		});
		clientSocket.DisconnectedHandler = new OnDisconnectedHandler((stoken) =>
		{
			Console.WriteLine("clinet discount");
		});
		again:
		bool rt = clientSocket.ConnectTo(port, "127.0.0.1");/* 10.152.0.71*/
		if (rt)
		{
			for (int i = 0; i   {
        Console.WriteLine("accepted:" + sToken.TokenIpEndPoint);
    });
    wsService.Disconnected = new Disconnected((SocketToken sToken) => {
        Console.WriteLine("disconnect:" + sToken.TokenIpEndPoint.ToString());
    });
    wsService.Received = new Received((SocketToken sToken, string content) => {

        Console.WriteLine("receive:" + content);
        wsService.Send(sToken, "hello websocket client! you said:" + content);

    });
    wsService.ReceivedBytes = new ReceivedBytes((SegmentOffset data) => {
        Console.WriteLine("receive bytes:" + data.size);
    });
    bool isOk = wsService.Start(65531);
    if (isOk)
	{
	   Console.WriteLine("waiting for accept...");
	}


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e1f04b7315208a48c3169e2992cef8ea86e1b5780ebcde26015e19e089e4acbbf6d7dfc96d6b0ae8a177901701060e7f5b36b3c84bd1b138551c0ed4f983f60c6)