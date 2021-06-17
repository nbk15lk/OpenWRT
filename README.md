# OpenWRT
Custom OpenWRT Configurations  for WRT32X devices


# Credit
All credit goes to:  https://divested.dev/unofficial-openwrt-builds/mvebu-linksys/
These are just minor modifications that suit my specific needs

# How to Build
git clone https://git.openwrt.org/openwrt/openwrt.git
git clone https://github.com/divestedcg/Divested-WRT.git
cd openwrt
git config pull.rebase true
./scripts/feeds update -a
./scripts/feeds install -a
wget -O .config https://divested.dev/unofficial-openwrt-builds/mvebu-linksys/latest/config
git am ../Divested-WRT/patches/*.patch
make defconfig  # make nconfig # make your changes and save
# sed -i "s/CONFIG_TARGET_PREINIT_IP.*/CONFIG_TARGET_PREINIT_IP=\"192.168.1.5\"/" .config
make download -j4
make -j16

