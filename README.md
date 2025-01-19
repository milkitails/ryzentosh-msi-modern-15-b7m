# ryzentosh-msi-modern-15-b7m
msi modern 15 b7m (R5 7530U) hackintosh

![image](https://github.com/user-attachments/assets/2839fc84-cae9-4b0c-9d2b-140e277a2bb7)

<a href="https://www.apple.com/macos">
  <img src="https://img.shields.io/badge/Sonoma-14.0-informational.svg">
</a>
<a href="https://github.com/acidanthera/OpenCorePkg">
  <img src="https://img.shields.io/badge/OpenCore-0.9.5-informational.svg">
</a>

## русский

### состояние компонентов:
| **компонент** | **состояние** |
| --------------- | :-----------------: |
| **ryzen 5 7530u `amd`**      | ✓  |
| **radeon graphics `amd`**    | ✓  |
| **ssd nvme `kingston`**      | ✓  |
| **звуковая карта `realtek`** | ✓  |
| **микрофон `realtek`**       | ✗  |
| **вход для наушников**       | ✓  |
| **wifi/bluetooth `rz608`**   | ✗  |
| **картридер `realtek`**      | ✓  |
| **вебкамера `msi`**          | ✓  |
| **клавиатура `ps2`**         | ✓  |
| **трекпад `i2c`**            | ✓  |
| **usb tethering `android`**  | ✓  |

### вход для наушников (работает только с патчем):
```
git clone https://github.com/lvs1974/ComboJack.git
bash ComboJack/ComboJack_Installer/install.sh
rm -rf ComboJack
```

### настройка bios:
чтобы редактировать эти настройки, нужно нажать `левый alt+правый ctrl+правый shift+f2` в bios, который открывается с помощью `delete` при загрузке

**выключить:**

- boot/fast boot
- security/secure boot/secure boot mode -> custom
- security/secure boot/secure boot support
- advanced/pci subsystem settings/re-size bar support

**включить:**

- advanced/pci subsystem settings/above 4g decoding

**настройка видеопамяти (опционально):**

- advanced/amd cbs/nbio common options/gfx_configuration/igpu configuration -> uma_specified
- advanced/amd cbs/nbio common options/gfx_configuration/uma frame buffer size -> ваш выбор

### установка:
так как wifi не работает, а ethernet порта в ноутбуке нет - нам нужен <a href="https://drive.google.com/file/d/1bkfjiVjOvsQkADeyKQms7r9SnuctIsxf/view?usp">полный офлайн установщик</a>  (этот записывается на usb накопитель с помощью <a href="https://www.drive-image.com/downloads/RDriveImage7.exe">r-drive image</a>)

### проблемы:
- все проблемы с компонентами описаны в [таблице состояния компонентов](#состояние-компонентов)

<br>
я взял за основу EFI из <a href="https://github.com/saeidex/ryzentosh-msi-modern-15">saeidex/ryzentosh-msi-modern-15</a>

<br>
<br>
<br>

## english

### components situation:
| **component** | **situation** |
| --------------- | :-----------------: |
| **ryzen 5 7530u `amd`**     | ✓  |
| **radeon graphics `amd`**   | ✓  |
| **ssd nvme `kingston`**     | ✓  |
| **speaker `realtek`**       | ✓  |
| **mic `realtek`**           | ✗  |
| **combojack**               | ✓  |
| **wifi/bluetooth `rz608`**  | ✗  |
| **cardreader `realtek`**    | ✓  |
| **webcamera `msi`**         | ✓  |
| **keyboard `ps2`**          | ✓  |
| **touchpad `i2c`**          | ✓  |
| **usb tethering `android`** | ✓  |

### combojack (works only with this patch):
```
git clone https://github.com/lvs1974/ComboJack.git
bash ComboJack/ComboJack_Installer/install.sh
rm -rf ComboJack
```

### bios settings:
to be able to edit these settings, you need to press `left alt+right ctrl+right shift+f2` in bios, which is opens with `delete` at boot

**disable:**

- boot/fast boot
- security/secure boot/secure boot mode -> custom
- security/secure boot/secure boot support
- advanced/pci subsystem settings/re-size bar support

**enable:**

- advanced/pci subsystem settings/above 4g decoding

**video-memory setting (optional):**

- advanced/amd cbs/nbio common options/gfx_configuration/igpu configuration -> uma_specified
- advanced/amd cbs/nbio common options/gfx_configuration/uma frame buffer size -> your choice

### installing:
since the wifi doesnt work and the laptop doesnt have an ethernet port, we're need <a href="https://drive.google.com/file/d/1bkfjiVjOvsQkADeyKQms7r9SnuctIsxf/view?usp">full offline installer</a>  (this one is written to a usb drive using <a href="https://www.drive-image.com/downloads/RDriveImage7.exe">r-drive image</a>)

### problems:
- all component problems are described in [component situation table](#component-situation)
- if you don't understand/want to change opencore settings - you'll have to live with “6-ядерный” instead of “6-core” in the about this mac menu
  
<br>
i used the EFI from <a href="https://github.com/saeidex/ryzentosh-msi-modern-15">saeidex/ryzentosh-msi-modern-15</a> as a basis
