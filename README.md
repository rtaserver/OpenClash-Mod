<h1 align="center">
  <img src="https://raw.githubusercontent.com/vernesong/OpenClash/dev/img/logo.png" alt="Clash" width="200">
  <br>OpenClash-Mod<br>

</h1>

  <p align="center">
	<a target="_blank" href="https://github.com/Dreamacro/clash/releases/tag/v1.13.0">
    <img src="https://img.shields.io/badge/Clash-v1.13.0-blue.svg">
    </a>
  </p>
  

<p align="center">
This plug-in is a plug-in that can run on OpenWrt<a href="https://github.com/Dreamacro/clash" target="_blank"> Clash </a>client
</p>
<p align="center">
Compatible with Shadowsocks, ShadowsocksR, Vmess, Trojan, Snell and other protocols, and implements policy proxying based on flexible rule configuration
</p>
<p align="center">
- Thanks to <a href="https://github.com/frainzy1477" target="_blank"> frainzy1477 </a>, this plug-in is based on <a href="https://github.com/frainzy1477/luci-app -clash" target="_blank"> Luci For Clash </a> for secondary development -
</p>

User manual
---


* [Wiki](https://github.com/vernesong/OpenClash/wiki)


Download address
---


* IPK [Go to download](https://github.com/vernesong/OpenClash/releases)


rely
---

* luci
* luci-base
* dnsmasq-full
* coreutils
* coreutils-nohup
* bash
* curl
* ca-certificates
* ipset
* ip-full
* libcap
* libcap-bin
* ruby
* ruby-yaml
* unzip
* iptables(iptables)
* kmod-ipt-nat(iptables)
* iptables-mod-tproxy(iptables)
* iptables-mod-extra(iptables)
* kmod-tun (TUN mode)
* luci-compat(Luci >= 19.07)
* ip6tables-mod-nat(iptables-ipv6)
* kmod-inet-diag(PROCESS-NAME)
* kmod-nft-tproxy(Firewall4)


compile
---


from OpenWrt of [SDK](https://archive.openwrt.org/chaos_calmer/15.05.1/ar71xx/generic/OpenWrt-SDK-15.05.1-ar71xx-generic_gcc-4.8-linaro_uClibc-0.9.33.2.Linux-x86_64.tar.bz2) compile
```bash
# Unzip the downloaded SDK
curl -SLk --connect-timeout 30 --retry 2 "https://archive.openwrt.org/chaos_calmer/15.05.1/ar71xx/generic/OpenWrt-SDK-15.05.1-ar71xx-generic_gcc-4.8-linaro_uClibc-0.9.33.2.Linux-x86_64.tar.bz2" -o "/tmp/SDK.tar.bz2"
cd \tmp
tar xjf SDK.tar.bz2
cd OpenWrt-SDK-15.05.1-*

# Clone project
mkdir package/luci-app-openclash
cd package/luci-app-openclash
git init
git remote add -f origin https://github.com/vernesong/OpenClash.git
git config core.sparsecheckout true
echo "luci-app-openclash" >> .git/info/sparse-checkout
git pull --depth 1 origin master
git branch --set-upstream-to=origin/master master

# Compile po2lmo (skip if po2lmo is available)
pushd luci-app-openclash/tools/po2lmo
make && sudo make install
popd

# Start compiling

# Go back to the SDK main directory first
cd ../..
make package/luci-app-openclash/luci-app-openclash/compile V=99

# IPK file location
./bin/ar71xx/packages/base/luci-app-openclash_*-beta_all.ipk
```

```bash
# Sync source code
cd package/luci-app-openclash/luci-app-openclash
git pull

# You can also directly copy `luci-app-openclash` folder to other `OpenWrt` project `Package` Compiled with the firmware in the directory

make menuconfig
# Select the package to compile LuCI -> Applications -> luci-app-openclash

```


license
---


* [MIT License](https://github.com/vernesong/OpenClash/blob/master/LICENSE)
* Kernel [clash](https://github.com/Dreamacro/clash) by [Dreamacro](https://github.com/Dreamacro)
* This project code is based on [Luci For Clash](https://github.com/frainzy1477/luci-app-clash) by [frainzy1477](https://github.com/frainzy1477)
* GEOIP database [GeoLite2](https://dev.maxmind.com/geoip/geoip2/geolite2/) by [MaxMind](https://www.maxmind.com)
* IP check [MyIP](https://github.com/SukkaW/MyIP) by [SukkaW](https://github.com/SukkaW)
* control Panel [clash-dashboard](https://github.com/Dreamacro/clash-dashboard) by [Dreamacro](https://github.com/Dreamacro)
* control Panel [yacd](https://github.com/haishanh/yacd) by [haishanh](https://github.com/haishanh)
* lhie1 rules [lhie1-Rules](https://github.com/lhie1/Rules) by [lhie1](https://github.com/lhie1)
* ConnersHua Rules [ConnersHua-Rules](https://github.com/ConnersHua/Profiles/tree/master) by [ConnersHua](https://github.com/ConnersHua)
* game rules [SSTap-Rule](https://github.com/FQrabbit/SSTap-Rule) by [FQrabbit](https://github.com/FQrabbit)
* Streaming Unlock Detection [RegionRestrictionCheck](https://github.com/lmc999/RegionRestrictionCheck) by [lmc999](https://github.com/lmc999)

Ask the author for a cup of coffee
---

* PayPal
<p align="left">
    <a href="https://ko-fi.com/vernesong"><img width="300" src="https://www.ko-fi.com/img/githubbutton_sm.svg"> </a>
</p>

* USDT-TRC20
<p align="left">
    <img width="300" src="https://github.com/vernesong/OpenClash/raw/master/img/USDT-Wallet.png">
</p>

* Bitcoin-BTC
<p align="left">
    <img width="300" src="https://github.com/vernesong/OpenClash/raw/master/img/BTC-Wallet.png">
</p>

* Ethereum-ETH
<p align="left">
    <img width="300" src="https://github.com/vernesong/OpenClash/raw/master/img/ETH-Wallet.png">
</p>


Preview
---


* Running status
<p align="center">
    <img src="https://github.com/vernesong/OpenClash/raw/master/img/state.png">
</p>

* Global settings
<p align="center">
    <img src="https://github.com/vernesong/OpenClash/raw/master/img/settings.png">
</p>

* Server & Policy Group
<p align="center">
    <img src="https://github.com/vernesong/OpenClash/raw/master/img/servers.png">
</p>

* Rules & Policy Group
<p align="center">
    <img src="https://github.com/vernesong/OpenClash/raw/master/img/game-settings.png">
</p>

* Profile subscription
<p align="center">
    <img src="https://github.com/vernesong/OpenClash/raw/master/img/config-subscribe.png">
</p>

* Profile management
<p align="center">
    <img src="https://github.com/vernesong/OpenClash/raw/master/img/config.png">
</p>

* Run log
<p align="center">
    <img src="https://github.com/vernesong/OpenClash/raw/master/img/log.png">
</p>

