	#DelphiWebMVC框架下的微信公众号管理平台
	完成公众号文本，图文，声音等消息的处理。

	当前封装的功能
	property access_token: string read Faccess_token write Setaccess_token;
    /// 获取时间戳 
    function GetStampTime(d: TDateTime): Int64;
    /// 微信对服务器的验证 
    function checktoken(token, signature, timestamp, nonce, echostr: string): string;
    /// 获取access_token值 
    function token(grant_type, appid, secret: string): string;
     /// 获取用户列表/summary>
    function user_get(next_openid: string): string;
     /// 获取分组 
    function groups_get(): string;
     /// 获取access_token值 
    function message_mass_preview(): string;
    ///  
    /// 解析数据到接收消息对象
    ///  
    function message_Parser(xml: string; var message_: TMessage_Receive): Boolean;
    ///  
    /// 解析发送数据对象为xml结构
    ///  
    function message_to_xml(message_: TMessage_Send): string;
    //---------------------begin素材管理begin-------------------
    ///  
    /// 获取素材列表
    ///  
    function material_batchget_material(json: string): string;
    ///  获取素材总数 
    function material_get_materialcount(): string;
    ///  
    /// 新增临时素材
    ///  
    function media_upload(filetype: string; filepath: string): string;
    ///  
    ///  获取临时素材
    ///  
    function media_get(media_id: string): string;
    ///  
    ///  新增其他类型永久素材
    ///  
    function media_add_material(filetype: string; filepath: string): string;
    ///  
    /// 获取永久素材  {"media_id":MEDIA_ID} 
    ///  
    function material_get_material(json: string): string;
    ///  
    /// 删除永久素材 {"media_id":MEDIA_ID} 
    ///  
    function material_del_material(json: string): string;
    ///  
    /// 修改永久图文素材
    ///  
    function material_update_news(json: string): string;
    //----------------------end素材管理end--------------------------

    //---------------------begin用户标签管理begin-------------------
    ///  
    /// 创建标签
    ///  
    function tags_create(json: string): string;
    ///  
    /// 获取公众号已创建的标签
    ///  
    function tags_get(): string;
    ///  
    /// 编辑标签
    ///  
    function tags_update(json: string): string;
    ///  
    /// 删除标签
    ///  
    function tags_delete(json: string): string;
    ///  
    /// 获取标签下粉丝列表
    ///  
    function user_tag_get(json: string): string;
    ///  
    /// 批量为用户打标签 标签功能目前支持公众号为用户打上最多20个标签。
    ///  
    function tags_members_batchtagging(json: string): string;
    ///  
    /// 批量为用户取消标签
    ///  
    function tags_members_batchuntagging(json: string): string;
    ///  
    /// 获取用户身上的标签列表
    ///  
    function tags_getidlist(json: string): string;
    ///  
    /// 获取公众号的黑名单列表
    ///  
    function tags_members_getblacklist(json: string): string;
    ///  
    /// 拉黑用户
    ///  
    function tags_members_batchblacklist(json: string): string;
    ///  
    /// 取消拉黑用户
    ///  
    function tags_members_batchunblacklist(json: string): string;
    //-----------------------end用户标签管理end----------------------
     ///  
    /// 自定义菜单创建
    ///  
    function menu_create(json: string): string;
     ///  
    /// 自定义菜单查询
    ///  
    function menu_get(): string;
     ///  
    /// 自定义菜单删除
    ///  
    function menu_delete(): string;
     ///  
    /// 创建个性化菜单
    ///  
    function menu_addconditional(json:string): string;
     ///  
    /// 创建个性化菜单
    ///  
    function menu_delconditional(json:string): string;
     ///  
    /// 创建个性化菜单
    ///  
    function menu_trymatch(json:string): string;
     ///  
    /// 获取自定义菜单配置接口
    ///  
    function get_current_selfmenu_info(): string;



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e3af6a9519a3c079349305d249c44250a7b1a3bbd092ad010ea6926cbc451a94a0d79b33453d4cbb52c928d27115d523b)