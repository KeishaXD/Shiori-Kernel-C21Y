![Isagi Celebrating](isagi.png)

# Realme C21Y (RMX3261 / RMX3263) Kernel – RED8D1

Custom kernel source for the Realme C21Y, built from the **RED8D1** official source tree.

> ⚠️ **Note**: This is **not** the source for the Kaiju kernel release, which includes additional performance patches and other changes.

---

## Highlights & Modifications

- **Removed YAML dependency in DTC**
  - Avoids `libyaml` linking errors during kernel compilation.
- **SELinux set to permissive**
  - If you want enforcing mode, replace the following files with those from the official Realme source:
    - `hooks.c`
    - `selinuxfs.c`
- **Fixed internal error dialog**
  - Resolved: _"There is an internal problem with your device. Please contact your manufacturer."_
- **Other small patches**
  - Minor stability and compatibility improvements (some undocumented).
- **Module signature checking & modversion disabled**
  - In `realme3263_defconfig`, both kernel module signature verification and `CONFIG_MODVERSIONS` are disabled to simplify development and loading of custom modules.
-  **Stock defconfig included**
  - An extracted stock defconfig is included under the `config/` directory as `stock_defconfig`.
  - ⚠️ **Note:** The stock defconfig does not align 1:1 with this source tree. For example, `oppo_device_ifno` has been renamed to `oplus_device_ifno`, and other vendor-specific differences may exist.
  - **Not recommended** for building — use `realme3263_defconfig` instead.

---

## 🧰 Compiler Compatibility

- ✅ **Clang:** `clang-r383902b` (**required**)
- ✅ **GCC:**
  - Android GCC 4.9 ✅
  - ARM GNU Toolchain 14.3 or earlier (**recommended**) ✅

---

**You can get notified about Kaiju kernel builds:** Telegram channel [here](https://t.me/kaijukernel).
