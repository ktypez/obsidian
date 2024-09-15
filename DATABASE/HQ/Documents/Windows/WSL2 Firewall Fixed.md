∆ [[HQ]] | [[Documents]] ✓

It happens because the default WSL interface name is renamed from "vEthernet (WSL)" to "vEthernet (WSL (Hyper-V firewall))".

The current workaround is to turn off the new Hyper-V firewall by creating `.wslconfig` file in `%USERPROFILE%` directory with the following content and restarting the computer:

```json
[experimental]
firewall=false
```

---

There are two possible solutions.

1. Disable the experimental network adapter as mentioned by [@dbielik](https://github.com/dbielik) above. **(Recommended)**
2. You can also rename the adapter `Rename-NetAdapter -name "vEthernet (WSL (Hyper-V firewall))" -newname "vEthernet (WSL)" -IncludeHidden`

#windows #docs