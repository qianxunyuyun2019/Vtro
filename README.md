# Vtro ![Vtro](./tray.ico)

[![GitHub license](https://img.shields.io/github/license/wk989898/Vtro)](https://github.com/wk989898/Vtro/blob/master/LICENSE)
[![codecov](https://codecov.io/gh/wk989898/Vtro/branch/master/graph/badge.svg)](https://codecov.io/gh/wk989898/Vtro)

## 介绍

trojan 的 windows 图形界面

## 注意

- 可以订阅和添加节点,更新订阅时会删除原有所有节点
- 默认[配置](extra-trojan/config.json) ssl 验证为`false` 其它保持默认，如果其他选项里没有则需要请自行更改  
  ❗ 每次启动设置默认 
- 支持 ping,tcp-ping,url-test
- 流量统计由trojan输出数据得出
- 建议搭配[SwitchyOmega](https://github.com/FelisCatus/SwitchyOmega)使用
- pac更新可以[自行更新](./proxy/fetchPAC.js)  
出现错误==>[还原文件](./proxy/_proxy.pac)


## Feature

### 根据当前时间改变节点 , 适用于晚上网络拥堵时自动更改连接节点

`开始结束时间相同视为关闭 默认：'19:30'-'00:30',`

## Conf [配置](./extra-trojan/conf.json)

- nodes `array<node>` 节点列表
- sub `array` 订阅组
- config `object` 配置
  - mode `string` default: `day`  
    &nbsp;&nbsp;`night | day`
  - proxy `string` default: `pac`  
    &nbsp;&nbsp;`pac | global | off`  
    |type|host|port|
    |---|----|----|
    |pac|localhost|1082/pac|
    |http|-|1081|
    |socks5|-|1080|
    > 设置 off 后会开启 socks5 端口 ❗
  - listen `array` default: `[1080,1081,1082]` 监听端口(改变端口后需自行重新连接)
  - time `object`
  - startTime default: `'19:30'`
  - endTime default: `'00:30'`
  - day `node` 白天节点
  - night `node` 夜间节点

## 运行

```shell
npm install
npm run dist
cd dist
```

## 下载

[点击这里](https://github.com/wk989898/Vtro/releases/)

## Todo

- [x] 更改单个节点
- [x] 新的交互设计
- [x] 分享节点
- [x] 更改监听端口
- [x] 统计流量  
- [x] 代理更新订阅
- [x] 更新pac
- [ ] 更加新的交互设计🙄

## Credits

[trojan](https://github.com/trojan-gfw/trojan)  
[privoxy](https://www.privoxy.org/)  
[v2rayN](https://github.com/2dust/v2rayN)  
[QRCode](https://github.com/davidshimjs/qrcodejs)

### 本软件仅作学习使用，任何个人或集体不得使用本软件进行任何违反相关法律法规的活动
