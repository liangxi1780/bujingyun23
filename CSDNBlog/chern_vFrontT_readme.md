项目文件目录
zhaocaizhu
    ---build
    ---config
    ---dist
    ---src
        ---api
        ---assets
            ---css
                ---reset  css reset
                ---utilities css组件文件夹
                    ---chanage_mint_ui   mintUi默认样式修改
                    ---decoration_base   css装饰
                    ---icon_font  iconfont
                    ---position_base  基础定位
                    ---theme  主题色
                    ---transform css3动画集合
                    ---txt_base   文本样式
                    ---weui   微信weui部分样式
                ---style  全项目通用样式
                ---main  项目局部页面通用样式
                ---variable_gather  变量集合引入
            ---fonts
                ---iconfont  iconfontjs文件  采用svg方式
            ---image  静态图片资源
        ---components
            ---general  通用组件
            ---partly  页面中小模块
        ---router 路由首页
            ---router_client 客户端路由
            ---router_manager 管理端路由
        ---shared
            ---components 公共UI组件
                ---iconSvg icon
                ---steps 进度步骤(头部横向)
                ---upload 上传组件
                    ---image_upload 图片上传
                    ---image_upload_crop 图片裁剪并上传
                    ---video_upload 音频文件上传
                ---col 响应式布局
                ---gesture_verify 手势验证
                ---number_box  数字增减
                ---Pic 图片
                ---picker_area 三级地区选择
                ---picker_area_two 两级地区选择
                ---preview 图片预览(点击放大轮播)
                ---rater 评分
                ---row 响应式布局
                ---scratch_card 刮刮乐
                ---scroll_div 滚动加载
                ---shark_off 手机摇一摇
                ---sticky sticky
                ---timer_task 60s倒计时
                ---video_player 视频播放
                --search 点击搜索
                --file_view 单张图片点击放大并删除(用于上传图片的取消)
            ---directive 指令集合
                ---sticky  sticky定位
                ---validator input表单输入校验
                ---waves  点击波纹效果(增强交互感)
                ---prevent_double_click 防止连击
        ---store
            ---modules
                ---client 客户端
                ---manager 管理端
            ---index 状态管理主体
        ---util
            ---dynamicEffect 交互动效
                ---scrollTop直达顶部
            ---lib 基础依赖文件(偏静态)
                ---baseData  地区数据信息(三级和两级)
                ---data_extend  data扩展方法
                ---location 地理定位
                ---modules modules
                ---weixin   weixinSDK集合
            ---filter vue过滤指令
            ---remex  扩展的js工具方法集
            ---storage sesseion方法封装
            ---util  基于vue的一些方法和dom操作方法
        ---views
            ---app  hybrid部分
            ---client 微信客户端部分
            ---general 微信通用部分
            ---manager 微信管理端部分
            ---team  营销推广页面(h5)
            ---test 测试页
        ---App.vue
        ---main.js
    ---static
        ---images
        ---third
            ---exif ios上传选择校对
            ---flexible 响应式布局
            ---luckyCard  刮刮乐
            ---nativeShare 非微信分享
            ---video video.js
    --test
        ---e2e
        ---unit




*rem = 750的设计图尺寸/100 例如，页面总宽为7.5rem

文件夹命名采用驼峰命名，文件采用中间_方式，如'my_tail'

项目插件引用说明

指令
启动  npm run dev
打包测试 npm run build




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5703533751c8128ffb88aa3a7a083f58969d7c5efe2de57b4fc3644dca826366a52e20459e825dcea30cc51658bfbbe8)