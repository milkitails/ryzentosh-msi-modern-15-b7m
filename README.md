# ryzentosh-msi-modern-15-b7m
MSI Modern 15 B7M (R5 7530U) Hackintosh

![image](https://github.com/user-attachments/assets/7437545d-bc7e-485d-9d6d-ff1a18b01171)

<a href="https://www.apple.com/macos">
  <img src="https://img.shields.io/badge/Sonoma-14.0-informational.svg">
</a>
<a href="https://github.com/acidanthera/OpenCorePkg">
  <img src="https://img.shields.io/badge/OpenCore-0.9.5-informational.svg">
</a>

## русский

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

### вход для наушников работает только с патчем:
```
git clone https://github.com/lvs1974/ComboJack.git
bash ComboJack/ComboJack_Installer/install.sh
rm -rf ComboJack
```

### настройка bios

**выключить:**

- fast boot
- com/serial/parallel
- secure boot
- resize gpu bars

**включить:**

- above 4G decoding

<br>

### установка:
так как wifi не работает, а ethernet порта в ноутбуке нет - нам нужен <a href="https://drive.google.com/file/d/1bkfjiVjOvsQkADeyKQms7r9SnuctIsxf/view?usp">полный офлайн установщик</a>  (этот записывается на usb накопитель с помощью <a href="https://www.drive-image.com/downloads/RDriveImage7.exe">r-drive image</a>)

<br>
я взял за основу EFI от <a href="https://github.com/saeidex/ryzentosh-msi-modern-15">saeidex</a>

<br>
<br>
<br>

## english

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

### combojack works only with this patch:
```
git clone https://github.com/lvs1974/ComboJack.git
bash ComboJack/ComboJack_Installer/install.sh
rm -rf ComboJack
```

### bios settings

**disable:**

- fast boot
- com/serial/parallel
- secure boot
- resize gpu bars

**enable:**

- above 4G decoding

<br>

### installing:
since the wifi doesnt work and the laptop doesnt have an ethernet port, we're need <a href="https://drive.google.com/file/d/1bkfjiVjOvsQkADeyKQms7r9SnuctIsxf/view?usp">full offline installer</a>  (this one is written to a usb drive using <a href="https://www.drive-image.com/downloads/RDriveImage7.exe">r-drive image</a>)

<br>
i used the EFI from <a href="https://github.com/saeidex/ryzentosh-msi-modern-15">saeidex</a> as a basis
