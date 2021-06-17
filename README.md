# OpenWRT
Custom OpenWRT Configurations  for WRT32X devices


# Credit
All credit goes to:  https://divested.dev/unofficial-openwrt-builds/mvebu-linksys/
These are just minor modifications that suit my specific needs

# How to Build
```
git clone https://git.openwrt.org/openwrt/openwrt.git
git clone https://github.com/divestedcg/Divested-WRT.git
git clone https://github.com/nbk15lk/OpenWRT.git
cd openwrt
git config pull.rebase true
./scripts/feeds update -a
./scripts/feeds install -a
cp ../OpenWRT/latest/config .config
git am ../OpenWRT/patches/*.patch
make defconfig  # make nconfig # make your changes and save
make download -j4
make -j16
```

