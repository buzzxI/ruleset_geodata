#  ruleset 规则集文件说明
对原项目的生成文件进行了剪裁, 仅生成适用于 mihomo core 的规则集
## 1. 文件类型
Clash ruleset 规则集文件，格式为 `.yaml`（`format: yaml`）、`.list`（`format: text`）
## 2. 数据源
① 每天凌晨 3 点（北京时间 UTC+8）自动构建，根据 [Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules) 和 [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip) 进行深度定制，可点击查看包含的[域名列表](https://github.com/DustinWin/domain-list-custom/tree/domains)和 [IP 段列表](https://github.com/DustinWin/geoip/tree/ips)  
② `rule-set,fakeip-filter,📌 fakeip 过滤` 源采用 [ShellCrash/public/fake_ip_filter.list](https://github.com/juewuy/ShellCrash/blob/dev/public/fake_ip_filter.list)（搭载 mihomo 内核或 sing-box PuerNya 版内核时，可使该规则集内的域名走 realip）  
③ `rule-set,applications,🖥️ 直连软件` 源采用 [blackmatrix7/ios_rule_script/Download](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Download) 和 [Loyalsoldier/clash-rules/applications.txt](https://github.com/Loyalsoldier/clash-rules/blob/release/applications.txt) 组合  
④ `rule-set,private,🔒 私有网络` 源采用 [blackmatrix7/ios_rule_script/Lan](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Lan)（仅域名）和 [TrackersList](https://github.com/XIU2/TrackersListCollection/blob/master/all.txt)（仅域名）组合，并添加主流 [Clash dashboard 在线面板](https://github.com/DustinWin/clash_singbox-tools/tree/main/Clash-dashboard)域名（`clash.metacubex.one`、`yacd.haishan.me`、`yacd.metacubex.one`、`d.metacubex.one`、`metacubex.github.io` 和 `metacubexd.pages.dev`）  
⑤ `rule-set,ads,🛑 广告拦截` 源采用 [privacy-protection-tools/anti-AD](https://github.com/privacy-protection-tools/anti-AD)  
⑥ `rule-set,microsoft-cn,🪟 微软服务` 源采用 [v2fly/domain-list-community/microsoft@cn](https://github.com/v2fly/domain-list-community/blob/master/data/microsoft)  
⑦ `rule-set,apple-cn,🍎 苹果服务` 源采用 [v2fly/domain-list-community/apple@cn](https://github.com/v2fly/domain-list-community/blob/master/data/apple)  
⑧ `rule-set,google-cn,🇬 谷歌服务` 源采用 [v2fly/domain-list-community/google@cn](https://github.com/v2fly/domain-list-community/blob/master/data/google)  
⑨ `rule-set,games-cn,🎮 游戏服务` 源采用 [v2fly/domain-list-community/category-games@cn](https://github.com/v2fly/domain-list-community/blob/master/data/category-games)、[blackmatrix7/ios_rule_script/SteamCN](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/SteamCN) 和 [blackmatrix7/ios_rule_script/GameDownloadCN](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Game/GameDownloadCN) 组合  
⑩ `rule-set,netflix,🎥 奈飞视频` 源采用 [blackmatrix7/ios_rule_script/Netflix](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Netflix)（仅域名）  
⑪ `rule-set,disney,📽️ 迪士尼+` 源采用 [blackmatrix7/ios_rule_script/Disney](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Disney)  
⑫ `rule-set,max,🎞️ Max` 源采用 [blackmatrix7/ios_rule_script/HBO](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/HBO)  
⑬ `rule-set,primevideo,🎬 Prime Video` 源采用 [blackmatrix7/ios_rule_script/PrimeVideo](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/PrimeVideo)  
⑭ `rule-set,appletv,🍎 Apple TV+` 源采用 [blackmatrix7/ios_rule_script/AppleTV](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/AppleTV)  
⑮ `rule-set,youtube,📹 油管视频` 源采用 [blackmatrix7/ios_rule_script/YouTube](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/YouTube)  
⑯ `rule-set,tiktok,🎵 TikTok` 源采用 [blackmatrix7/ios_rule_script/TikTok](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/TikTok)  
⑰ `rule-set,bilibili,📺 哔哩哔哩` 源采用 [blackmatrix7/ios_rule_script/BiliBili](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/BiliBili)  
⑱ `rule-set,ai,🤖 人工智能` 源采用 [blackmatrix7/ios_rule_script/OpenAI](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/OpenAI)、[blackmatrix7/ios_rule_script/Copilot](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Copilot)、[blackmatrix7/ios_rule_script/Gemini](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Gemini) 和 [blackmatrix7/ios_rule_script/Claude](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Claude) 组合  
⑲ `rule-set,networktest,📈 网络测试` 源采用 [blackmatrix7/ios_rule_script/Speedtest](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Speedtest) 和 IPv6 测试域名关键字（`keyword`，包括：`ipv6-test`、`test-ipv6`、`ipv6test` 和 `testipv6`）组合  
⑳ `rule-set,proxy,🪜 代理域名` 源采用 [v2fly/domain-list-community/geolocation-!cn](https://github.com/v2fly/domain-list-community/blob/master/data/geolocation-!cn)（删除了带有 `@cn` 和 `@ads` 的域名，并新增了 [gfwlist](https://github.com/gfwlist/gfwlist) 和 v2fly/domain-list-community/cn 中带有 `@!cn` 的域名）和 [blackmatrix7/ios_rule_script/Global](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Global) 组合, 额外添加了 [mihomo wiki](https://wiki.metacubex.one/) 与 [hysteria wiki](https://v2.hysteria.network/)
㉑ `rule-set,cn,🇨🇳 直连域名` 源采用 [v2fly/domain-list-community/cn](https://github.com/v2fly/domain-list-community/blob/master/data/cn)（删除了带有 `@!cn` 和 `@ads` 的域名，并新增了 v2fly/domain-list-community/geolocation-!cn 中带有 `@cn` 的域名）和 [blackmatrix7/ios_rule_script/ChinaMax](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/ChinaMax)（仅域名）  
㉒ `rule-set,netflixip,🎥 奈飞视频` 源采用 [GeoLite2-ASN-CSV/Netflix](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data) 和 [blackmatrix7/ios_rule_script/Netflix](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Netflix)（Netflix_IP.txt）组合  
㉓ `rule-set,telegramip,📲 电报消息` 源采用 [GeoLite2-ASN-CSV/Telegram](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data) 和 [Telegram IP 段](https://core.telegram.org/resources/cidr.txt)组合  
㉔ `rule-set,privateip,🔒 私有网络` 源采用 [DustinWin/geoip/config.json](https://github.com/DustinWin/geoip/blob/master/config.json) 中的 `input.type:private` 和 [TrackersList](https://github.com/XIU2/TrackersListCollection/blob/master/all.txt)（仅 IP）组合  
㉕ `rule-set,cnip,🇨🇳 直连 IP` 源采用 [GeoLite2-Country-CSV/CN](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data)、[17mon/china_ip_list](https://github.com/17mon/china_ip_list)、[gaoyifan/china-operator-ip](https://github.com/gaoyifan/china-operator-ip)、[APNIC/CN](http://ftp.apnic.net/stats/apnic/delegated-apnic-latest) 和 [blackmatrix7/ios_rule_script/ChinaASN](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Surge/ChinaASN) 组合
㉖ `rule-set,emby,Emby` 源采用 [blackmatrix7/ios_rule_script/Emby](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Emby)
## 3. 文件使用
<details>
<summary>mihomo core</summary>

- 注：经测试, 同样适配于基于 clash premium 内核的 stash

```
proxy-groups:
  - {name: 🚀 节点选择, type: select, proxies: [🇭🇰 香港节点, 🇹🇼 台湾节点, 🇯🇵 日本节点, 🇰🇷 韩国节点, 🇸🇬 新加坡节点, 🇺🇸 美国节点]}
  - {name: 🐟 漏网之鱼, type: select, proxies: [🚀 节点选择, 🎯 全球直连]}
  - {name: 📈 网络测试, type: select, proxies: [🎯 全球直连, 🇭🇰 香港节点, 🇹🇼 台湾节点, 🇯🇵 日本节点, 🇰🇷 韩国节点, 🇸🇬 新加坡节点, 🇺🇸 美国节点]}
  - {name: 🤖 人工智能, type: select, proxies: [🚀 节点选择, 🇭🇰 香港节点, 🇯🇵 日本节点, 🇸🇬 新加坡节点, 🇺🇸 美国节点]}
  - {name: 🎮 游戏服务, type: select, proxies: [🎯 全球直连, 🚀 节点选择]}
  - {name: 🪟 微软服务, type: select, proxies: [🎯 全球直连, 🚀 节点选择]}
  - {name: 🇬 谷歌服务, type: select, proxies: [🎯 全球直连, 🚀 节点选择]}
  - {name: 🍎 苹果服务, type: select, proxies: [🎯 全球直连, 🚀 节点选择]}
  - {name: 🎥 奈飞视频, type: select, proxies: [🚀 节点选择, 🇭🇰 香港节点, 🇯🇵 日本节点, 🇸🇬 新加坡节点]}
  - {name: 📽️ 迪士尼+, type: select, proxies: [🚀 节点选择, 🇭🇰 香港节点, 🇯🇵 日本节点, 🇸🇬 新加坡节点]}
  - {name: 🎞️ Max, type: select, proxies: [🚀 节点选择, 🇭🇰 香港节点, 🇯🇵 日本节点, 🇸🇬 新加坡节点]}
  - {name: 🎬 Prime Video, type: select, proxies: [🚀 节点选择, 🇭🇰 香港节点, 🇯🇵 日本节点, 🇸🇬 新加坡节点]}
  - {name: 🍎 Apple TV+, type: select, proxies: [🚀 节点选择, 🇭🇰 香港节点, 🇯🇵 日本节点, 🇸🇬 新加坡节点]}
  - {name: 📹 油管视频, type: select, proxies: [🚀 节点选择, 🇭🇰 香港节点, 🇯🇵 日本节点, 🇸🇬 新加坡节点]}
  - {name: 🎵 TikTok, type: select, proxies: [🚀 节点选择, 🇭🇰 香港节点, 🇯🇵 日本节点, 🇸🇬 新加坡节点]}
  - {name: 📺 哔哩哔哩, type: select, proxies: [🎯 全球直连, 🚀 节点选择, 🇭🇰 香港节点, 🇯🇵 日本节点, 🇸🇬 新加坡节点]}
  - {name: 🇨🇳 直连域名, type: select, proxies: [🎯 全球直连, 🚀 节点选择]}
  - {name: 🇨🇳 直连 IP, type: select, proxies: [🎯 全球直连, 🚀 节点选择]}
  - {name: 🪜 代理域名, type: select, proxies: [🚀 节点选择, 🎯 全球直连]}
  - {name: 📲 电报消息, type: select, proxies: [🚀 节点选择]}
  - {name: 🖥️ 直连软件, type: select, proxies: [🎯 全球直连]}
  - {name: 🔒 私有网络, type: select, proxies: [🎯 全球直连]}
  - {name: 🛑 广告拦截, type: select, proxies: [REJECT]}
  - {name: 🎯 全球直连, type: select, proxies: [DIRECT]}

rule-providers:
  fakeip-filter:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/fakeip-filter.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/fakeip-filter.yaml"
    interval: 86400

  applications:
    type: http
    behavior: classical
    format: text
    path: ./rules/applications.list
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/applications.list"
    interval: 86400

  private:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/private.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/private.yaml"
    interval: 86400

  ads:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/ads.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/ads.yaml"
    interval: 86400

  microsoft-cn:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/microsoft-cn.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/microsoft-cn.yaml"
    interval: 86400

  apple-cn:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/apple-cn.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/apple-cn.yaml"
    interval: 86400

  google-cn:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/google-cn.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/google-cn.yaml"
    interval: 86400

  games-cn:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/games-cn.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/games-cn.yaml"
    interval: 86400

  netflix:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/netflix.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/netflix.yaml"
    interval: 86400

  disney:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/disney.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/disney.yaml"
    interval: 86400

  max:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/max.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/max.yaml"
    interval: 86400

  primevideo:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/primevideo.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/primevideo.yaml"
    interval: 86400

  appletv:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/appletv.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/appletv.yaml"
    interval: 86400

  youtube:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/youtube.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/youtube.yaml"
    interval: 86400

  tiktok:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/tiktok.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/tiktok.yaml"
    interval: 86400

  bilibili:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/bilibili.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/bilibili.yaml"
    interval: 86400

  ai:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/ai.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/ai.yaml"
    interval: 86400

  networktest:
    type: http
    behavior: classical
    format: text
    path: ./rules/networktest.list
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/networktest.list"
    interval: 86400

  proxy:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/proxy.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/proxy.yaml"
    interval: 86400

  cn:
    type: http
    behavior: domain
    format: yaml
    path: ./rules/cn.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/cn.yaml"
    interval: 86400

  netflixip:
    type: http
    behavior: ipcidr
    format: yaml
    path: ./rules/netflixip.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/netflixip.yaml"
    interval: 86400

  telegramip:
    type: http
    behavior: ipcidr
    format: yaml
    path: ./rules/telegramip.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/telegramip.yaml"
    interval: 86400

  privateip:
    type: http
    behavior: ipcidr
    format: yaml
    path: ./rules/privateip.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/privateip.yaml"
    interval: 86400

  cnip:
    type: http
    behavior: ipcidr
    format: yaml
    path: ./rules/cnip.yaml
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/cnip.yaml"
    interval: 86400

rules:
  - RULE-SET,applications,🖥️ 直连软件
  - RULE-SET,private,🔒 私有网络
  - RULE-SET,ads,🛑 广告拦截
  - RULE-SET,microsoft-cn,🪟 微软服务
  - RULE-SET,apple-cn,🍎 苹果服务
  - RULE-SET,google-cn,🇬 谷歌服务
  - RULE-SET,games-cn,🎮 游戏服务
  - RULE-SET,netflix,🎥 奈飞视频
  - RULE-SET,disney,📽️ 迪士尼+
  - RULE-SET,max,🎞️ Max
  - RULE-SET,primevideo,🎬 Prime Video
  - RULE-SET,appletv,🍎 Apple TV+
  - RULE-SET,youtube,📹 油管视频
  - RULE-SET,tiktok,🎵 TikTok
  - RULE-SET,bilibili,📺 哔哩哔哩
  - RULE-SET,ai,🤖 人工智能
  - RULE-SET,networktest,📈 网络测试
  - RULE-SET,proxy,🪜 代理域名
  - RULE-SET,cn,🇨🇳 直连域名
  - RULE-SET,netflixip,🎥 奈飞视频,no-resolve
  - RULE-SET,telegramip,📲 电报消息,no-resolve
  - RULE-SET,privateip,🔒 私有网络,no-resolve
  - RULE-SET,cnip,🇨🇳 直连 IP
```
</details>
