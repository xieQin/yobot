# 作为 nonebot 插件运行

使用前提：已经安装好[nonebot](https://nonebot.cqp.moe/)（或者其衍生物），创建好插件目录，并且**可以正常运行**

[nonebot介绍](../usage/nonebot-introductions.md)

[nonebot教程](https://nonebot.cqp.moe/)

如果你还没有为 nonebot 建立仓库，请在 nonebot 工作目录下执行 `git init` 新建一个仓库。  

进入 nonebot 插件目录，添加 git 的子模块：  
`git submodule add https://github.com/yuudi/yobot.git`  
（或者使用国内源`https://gitee.com/yobot/yobot.git`）

安装依赖`pip install -r yobot/src/client/requirements.txt`，重新加载nonebot插件，安装完成

**兼容性**：请在 `nonebot` 启用时的 `nonebot.run` 中添加如下的三个额外参数

```python {4-6}
nonebot.run(
    host=host,
    port=port,
    debug=False,
    use_reloader=False,
    loop=asyncio.get_event_loop(),
)
```

向机器人发送“version”、“帮助”，即可开始使用

## 注意事项

作为nonebot插件运行时，配置项中的`host`、`port`、`access_token`不会生效，这些配置会沿用nonebot中的设置

为了开启web模式，请配置nonebot的`host`字段为`0.0.0.0`，yobot的`yobot_data/yobot_config.json`中`public_address`内的端口号与nonebot配置中的`port`对应（如果你使用了反向代理，则`public_address`为代理后的地址）

## 常见问题

见[FAQ](../usage/faq.md)
