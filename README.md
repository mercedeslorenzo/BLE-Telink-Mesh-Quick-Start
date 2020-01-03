← [Back to Menu](https://telinkgithub.github.io/Telink/ "Menu")
![header-telink](https://i.imgur.com/5kRG6CF.jpg)

## Introduction

8266, 8267, 8269 and 8258 support Telink proprietary BLE mesh, and they are covered in the same Telink mesh SDK. Telink Mesh is a proprietary mesh solution based on BLE technology, it can be used for various smart home and smart control applications such as lighting, sensors, controls, and switch.

The Telink BLE Mesh Development Kit includes:

* Multiple USB dongles (826x/825x) for emulating mesh nodes or gateways
* Remote control PCBA for emulating remote controller, wall switch, and also for demonstrating group controls
* Burning EVK
* PC tools (burning tools, tools for controlling mesh nodes)
* Reference Android or iOS APPs

BLE Telink mesh demo uses lighting application as an example to demonstrate the mesh functionalities and is presented in 4 different ways:

* Node Control by APP with OTA
* Node Control by Gateway
* Node Control by Remote
* Node Control by Master Dongle

Demo required bin files are included in the “SDK and Tools” download firmware folder release zip.

For further info, please refer to Telink mesh Development Manual under 826x and 8x5x chipset wiki page.


## Node Control by APP with OTA

In this demo, two 8267 dongles are used to emulate light bulb node. Bin file is generated by “light_8267” project with “light_8267” compile option as indicated in following diagram.

![Node Control by APP with OTA-1](https://telinkgithub.github.io/Assets/14_BLE-Telink-Mesh-Quick-Start/tsdk.png)

Launch Telink “MeshDemo” app as shown in following page. The two blue colored light bulbs indicate the two demo dongle connecting with an iPhone in this example. Tapping the icon would toggle light on/off.

![Node Control by APP with OTA-2](https://telinkgithub.github.io/Assets/14_BLE-Telink-Mesh-Quick-Start/tdemo.png)

Holding bulb icon enters following control panel. Brightness and color temperature can be adjusted. Group assignment can be “Add” or “Remove”. Each node can even be “KickOut” of the mesh network connecting with APP. OTA can also be executed by selecting “OTA” on upper right corner.

![Node Control by APP with OTA-3](https://telinkgithub.github.io/Assets/14_BLE-Telink-Mesh-Quick-Start/tappcontrol.png)


## Node Control by Gateway

Node control by gateway demo requires 3 pieces of HW as shown below: 2 pieces of light bulb and 1 piece of gateway dongle，all by 8267.

![Node Control by Gateway-1](https://telinkgithub.github.io/Assets/14_BLE-Telink-Mesh-Quick-Start/mesh_demo_hw.png)

8267 gateway dongle in this example is programmed by using “light_gateway” project in SDK and “light_gateway_8267” compile option; and light bulb bin is the same as in APP demo. After being programmed, gateway dongle must be plugged in USB port of PC and light bulbs can be powered by any USB port. The light bulbs, if has been provisioned previously, need to reset by having 3 short power cycling (on/off each 1s) followed by 2 long power cycling (on/off each 3-5s). Successful reset would trigger 3 blinks.

Now launch “tl_ble_phone_mesh2” tool under tools/telink-ble-phone/ dir. Click off “secuirity” check box. Then click on “Scan” followed by “Connect” to gateway itself labelled with “telink_mesh1”. Make sure the mesh network name is now “telink_mesh1”. Using “All_on” and “All_off” command on left pane would turn on/off the lights respectively.

![Node Control by Gateway-2](https://telinkgithub.github.io/Assets/14_BLE-Telink-Mesh-Quick-Start/tmeshtool.png)

Now continue clicking on “Mesh” button. This will bring out the light control UI as shown below. Click on “Online Status”, light bulbs is listed in the “Mesh” pane on left side of the window with corresponding MAC address in blue rectangular, top one in black is gateway. By clicking on and highlight a specific light node, this particular light can be assigned to desired group by checking on green area. Once group assignment is done, each group can be turned off/on by itself.

![Node Control by Gateway-3](https://telinkgithub.github.io/Assets/14_BLE-Telink-Mesh-Quick-Start/tmesh.png)



## Node Control with Remote

Continuing with the setup from “Node control with Gateway”, a 8269 remote as shown below is programmed by “light_switch” project in SDK using “light_switch_8269” compile option. Button A and B would turn all 2 lighting dongles on and off, respectively.

![Node Control with Remote](https://telinkgithub.github.io/Assets/14_BLE-Telink-Mesh-Quick-Start/light_rcu.png)



## Node Control by Master Dongle

Now program the gateway dongle into master dongle using “ble_master” project in SDK and “ble_master_dongle_8267_69” compile option.

When launching PC tool, “security” box needs to be checked as shown below. Now “Scan” and “Connect” to the lighting node, and click “Login”. Lighting control and group assignment is the same as gateway demo.

“Network Name” can be changed followed by “Set”, 2 lighting nodes in this example needs to be done one by one.

![Node Control by Master Dongle](https://telinkgithub.github.io/Assets/14_BLE-Telink-Mesh-Quick-Start/tmaster.png)



← [View the Project on GitHub](https://github.com/TelinkGithub/BLE-Telink-Mesh-Quick-Start)


![footer-telink](https://telinkgithub.github.io/Assets/General/footer.jpg)



