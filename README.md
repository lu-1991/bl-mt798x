# ATF and u-boot for mt798x.

![](/u-boot.gif)

# Prepare
```
sudo apt install gcc-aarch64-linux-gnu
export CROSS_COMPILE=aarch64-linux-gnu-
```

# Build together using scripts
```
SOC=mt7986 BOARD=re-cp-03 FIXED_MTDPARTS=0 MULTI_LAYOUT=0 ./build.sh
SOC=mt7981 BOARD=cmcc_rax3000m_emmc FIXED_MTDPARTS=0 MULTI_LAYOUT=0 ./build.sh
```
The target file are bl2.img and fip.bin located in:
bl-mt798x/atf-20220606-637ba581b/build/mt7986/release

# Or Build separately
## Build u-boot
```
make mt7986_re-cp-03_defconfig
make
```
## Build ATF
```
cp ../uboot-mtk-20220606/u-boot.bin .
make mt7986_re-cp-03_defconfig
make
```
