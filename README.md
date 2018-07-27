# Add feeds
    
    echo 'src-git wifidog_ng https://github.com/zhaojh329/wifidog-ng.git;openwrt-14.04' >> feeds.conf.default

# Update feeds

    ./scripts/feeds uninstall -a
    ./scripts/feeds update wifidog_ng
    ./scripts/feeds install -a -f -p wifidog_ng
    ./scripts/feeds install -a

# Select wifidog-ng in menuconfig and compile new image.

    Network  --->
        Captive Portals  --->
            <*> wifidog-ng-polarssl............................ Next generation WifiDog implemented in Lua (polarssl)
            < > wifidog-ng-nossl............................... Next generation WifiDog implemented in Lua (NO SSL)
            < > wifidog-ng-openssl............................ Next generation WifiDog implemented in Lua (openssl)
            < > wifidog-ng-cyassl............................ Next generation WifiDog implemented in Lua (cyassl)