# MIUIThermalNolimits
Magisk module.

~~Replace all thermal conf with Nolimits confs on MIUI for MI 11 Pro (`mars`) and MI 11 Ultra (`star`), so that the limit for maximum CPU frequency of all cores is lifted. This will enforce maximum charging speed while screen is on, instead of official fast charge when the screen is off only. **Supports MIUI 12 and MIUI 13.**~~

Based on [HankAviator/MIUIThermalNolimits](https://github.com/HankAviator/MIUIThermalNolimits)

## Fork Changes
Replace all thermal confs with Nolimits conf on MIUI for K40 Pro/Mi 11i/haydn (SD888). Might work on K40 Pro Plus too (?, since I heard that the inner stuffs are the same as K40 Pro but I don't have one to test).

Due to its nature, the approach used by this module might also be suitable for forcing other (custom) thermal confs. You just need to modify the code in the `customize.sh` file (hint: scroll to the bottom) and replace the nolimits confs with your own confs. It's only a few lines of code. Also, if the nolimit thermal conf files in your phone have different names, you can also edit the name to achieve the same goal on your phone. The available thermal conf files are located in `/system/vendor/etc` (look for the files that start with `thermal-` and end with `.conf` using a root file manager such as Material Files).

I am not responsible for any damage caused by this module. Use at your own risk.

Recommended to use `conservative` governor for daily use to prolong battery life.

## If you wish to read on from here, prepare for a long rage message from me

This module is **OPEN-SOURCE, MALWARE FREE, AND DOES NOT DO ANYTHING OTHER THAN WHAT IT IS SUPPOSED TO DO.** I have seen some **Thermal Unlocker** modules which either have malware by including a sus binary file inside the module which literally have total control over your phone thanks to Magisk root priviledge (dude was trying to steal my money by hijacking my bank OTP and possibly other things on my phone too and I pretty much did some reverse engineering (intercepting the outgoing requests and use mitm to decode the encrypted ones) since I wanted to know what those mtfk were interested in and what their f**king IP address was. After knowing what I wanted, I did not bother to go further than that. Then uninstalled the module, and to make sure, did a full wipe from head to toe on my phone and flashed a new ROM. I had my suspicion ever since I found out my SELinux became Permissive after flashing the module but ignored it and paid the price. Thankfully, they just made some (quite a few) small purchases of 10 ~ 20USD on some random US stores. (Why though?)).

Now, most of the **Thermal Unlocker** modules I have found also tinkered with other stuffs on my phone too, such as trying to modify the delays or zrams, etc. This module does **None** of that. I believe the module should do only what it is supposed to do. Some modules disabled the thermal throttling by replacing the thermal services with dummy files but I found it to be a questionable approach. Google did some [Thermal Mitigation](https://source.android.com/docs/core/power/thermal-mitigation) post Android 9 (which might be irrelevant since these modules still work but I'm pretty sure they modified the 1.0 service files) so it might affect these modules. Either way, since I want to increase the chance of the approach to work on future MIUI versions and lower the chance of bootloops due to the system cannot do what it wants to do (since the service/bin files are now dummy), I decided to go with the approach of replacing the thermal conf files instead of the services.