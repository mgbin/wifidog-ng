# Add feeds
    
    echo 'src-git wifidog_ng https://github.com/zhaojh329/wifidog-ng.git;openwrt-18' >> feeds.conf.default

# Update feeds

    ./scripts/feeds uninstall -a
    ./scripts/feeds update wifidog_ng
    ./scripts/feeds install -a -f -p wifidog_ng
    ./scripts/feeds install -a

# Select wifidog-ng in menuconfig and compile new image.

    Network  --->
        Captive Portals  --->
            <*> wifidog-ng-mbedtls............................ Next generation WifiDog implemented in Lua (mbedtls)
            < > wifidog-ng-nossl............................... Next generation WifiDog implemented in Lua (NO SSL)
            < > wifidog-ng-openssl............................ Next generation WifiDog implemented in Lua (openssl)
            < > wifidog-ng-wolfssl............................ Next generation WifiDog implemented in Lua (wolfssl)
