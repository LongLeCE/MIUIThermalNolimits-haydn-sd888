# MIUIThermalNolimits
Magisk module.

~~Replace all thermal conf with Nolimits confs on MIUI for MI 11 Pro (`mars`) and MI 11 Ultra (`star`), so that the limit for maximum CPU frequency of all cores is lifted. This will enforce maximum charging speed while screen is on, instead of official fast charge when the screen is off only. **Supports MIUI 12 and MIUI 13.**~~

Based on [HankAviator/MIUIThermalNolimits](https://github.com/HankAviator/MIUIThermalNolimits)

## Fork Changes
Replace all thermal confs with Nolimits conf on MIUI for K40 Pro/Mi 11i/haydn (SD888). Might work on K40 Pro Plus too (?, since I heard that the inner stuffs are the same as K40 Pro but I don't have one to test).

Due to its nature, the approach used by this module might also be suitable for forcing other (custom) thermal confs. You just need to modify the code in the `customize.sh` file (hint: scroll to the bottom) and replace the nolimits confs with your own confs. It's only a few lines of code. Also, if the nolimit thermal conf files in your phone have different names, you can also edit the name to achieve the same goal on your phone. The available thermal conf files are located in `/system/vendor/etc` (look for the files that start with `thermal-` and end with `.conf` using a root file manager such as Material Files).

I am not responsible for any damage caused by this module. Use at your own risk.

Recommended to use `conservative` governor for daily use to prolong battery life.
