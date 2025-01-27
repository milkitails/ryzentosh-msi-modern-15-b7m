# ryzentosh-msi-modern-15-b7m (R5 7530U)

![добрый вечер я диспетчер](https://github.com/user-attachments/assets/e5568407-cd6d-449b-b8a8-8741f0deac1a)

<a href="https://drive.google.com/file/d/1bkfjiVjOvsQkADeyKQms7r9SnuctIsxf/view?usp">
  <img src="https://img.shields.io/badge/Sonoma-14.0-5B8266">
</a>
<br>
<a href="https://github.com/acidanthera/OpenCorePkg">
  <img src="https://img.shields.io/badge/OpenCore-0.9.5-4381C1">
</a>
<br>
<a href="https://github.com/saeidex/ryzentosh-msi-modern-15">
  <img src="https://img.shields.io/badge/saeidex-ryzentosh--msi--modern--15-388697">
</a>

## русский

### состояние компонентов
| **тип**            | **компонент**                    | **состояние** |
| ------------------ | -------------------------------- | :-----------: |
| процессор          | **amd ryzen 5 7530u**            |       ✓       |
| графика            | **amd radeon graphics**          |       ✓       |
| дисплей            | **регулировка подсветки экрана** |       ✓       |
| диск               | **kingston ssd nvme**            |       ✓       |
| звуковая карта     | **realtek alc256**               |       ✓       |
| микрофон           | **realtek alc256**               |       ✗       |
| вход для наушников | **комбинированный 3.5**          |       ✓       |
| wifi/bluetooth     | **mkt rz608 ( mt7921 )**         |       ✗       |
| картридер          | **realtek pci-e card reader**    |       ✓       |
| вебкамера          | **msi**                          |       ✓       |
| клавиатура         | **ps2 keyboard**                 |       ✓       |
| трекпад            | **i2c trackpad**                 |       ✓       |
| usb tethering      | **tethering**                    |       ✓       |


### wifi
и все же, завести rz608 под macos пока не удалось

но <a href="https://github.com/chris1111/Wireless-USB-Big-Sur-Adapter#%EF%B8%8E---known-working-and-testing-adapter">эти</a> usb wifi адаптеры работают с <a href="https://github.com/chris1111/Wireless-USB-Big-Sur-Adapter/releases/download/V18/Wireless.USB.Big.Sur.Adapter-V18.zip">драйвером</a> (chris1111/Wireless-USB-Big-Sur-Adapter)


### настройка bios
чтобы редактировать эти настройки, нужно нажать `левый alt+правый ctrl+правый shift+f2` в bios, который открывается с помощью `delete` при загрузке

**выключить:**

- boot/fast boot
- security/secure boot/secure boot support
- advanced/pci subsystem settings/re-size bar support

**включить:**

- advanced/pci subsystem settings/above 4g decoding

**настройка видеопамяти (опционально):**

- advanced/amd cbs/nbio common options/gfx configuration/igpu configuration -> uma_specified
- advanced/amd cbs/nbio common options/gfx configuration/uma frame buffer size -> ваш выбор

### установка
* подготовка
  + создать раздел для установки macOS (из windows, отформатировать в NTFS)
  + так как wifi не работает, а ethernet порта в ноутбуке нет - нам нужен <a href="https://drive.google.com/file/d/1bkfjiVjOvsQkADeyKQms7r9SnuctIsxf/view?usp">полный офлайн установщик</a>  (этот записывается на usb накопитель с помощью <a href="https://www.drive-image.com/downloads/RDriveImage7.exe">r-drive image</a>)
    - на накопитель обязательно перенести оба (!!!) раздела из образа
    - удалить все с EFI раздела на usb накопителе
    - копировать папку EFI из EFI.zip на EFI раздел usb накопителя
* установка
  + открыть дисковую утилиту и стереть раздел, созданный на 1 этапе в файловую систему APFS
  + запустить установку
* после установки
  + из windows создать раздел EFI:
    - ищи в интернете как создать. мне лень писать.
  + фикс для комбинированного джека 3.5
    - ```
      git clone https://github.com/lvs1974/ComboJack.git
      bash ComboJack/ComboJack_Installer/install.sh
      rm -rf ComboJack
      ```

### проблемы
- все проблемы с компонентами описаны в [таблице состояния компонентов](#состояние-компонентов)

<br>
я взял за основу EFI из <a href="https://github.com/saeidex/ryzentosh-msi-modern-15">saeidex/ryzentosh-msi-modern-15</a>

<br>
<br>
<br>

## english

### components situation
| **type**           | **component**                    | **situation** |
| ------------------ | -------------------------------- | :-----------: |
| cpu                | **amd ryzen 5 7530u**            |       ✓       |
| gpu (integrated)   | **amd radeon graphics**          |       ✓       |
| display            | **screen backlight adjustment**  |       ✓       |
| drive              | **kingston ssd nvme**            |       ✓       |
| sound card         | **realtek alc256**               |       ✓       |
| mic                | **realtek alc256**               |       ✗       |
| combojack          | **combojack 3.5**                |       ✓       |
| wifi/bluetooth     | **mkt rz608 ( mt7921 )**         |       ✗       |
| card reader        | **realtek pci-e card reader**    |       ✓       |
| webcamera          | **msi**                          |       ✓       |
| keyboard           | **ps2 keyboard**                 |       ✓       |
| trackpad           | **i2c trackpad**                 |       ✓       |
| usb tethering      | **tethering**                    |       ✓       |


### wifi
and yet, I haven't been able to get the rz608 on macos yet.

but <a href="https://github.com/chris1111/Wireless-USB-Big-Sur-Adapter#%EF%B8%8E---known-working-and-testing-adapter">these</a> usb wifi adapters work with this <a href="https://github.com/chris1111/Wireless-USB-Big-Sur-Adapter/releases/download/V18/Wireless.USB.Big.Sur.Adapter-V18.zip">driver</a> (chris1111/Wireless-USB-Big-Sur-Adapter)


### bios settings
to be able to edit these settings, you need to press `left alt+right ctrl+right shift+f2` in bios, which is opens with `delete` at boot

**disable:**

- boot/fast boot
- security/secure boot/secure boot support
- advanced/pci subsystem settings/re-size bar support

**enable:**

- advanced/pci subsystem settings/above 4g decoding

**video-memory setting (optional):**

- advanced/amd cbs/nbio common options/gfx configuration/igpu configuration -> uma_specified
- advanced/amd cbs/nbio common options/gfx configuration/uma frame buffer size -> your choice

### installing
* preparations
  + create partiton for macOS (from windows, format - NTFS)
  + since the wifi doesnt work and the laptop doesnt have an ethernet port, we're need <a href="https://drive.google.com/file/d/1bkfjiVjOvsQkADeyKQms7r9SnuctIsxf/view?usp">full offline installer</a>  (this one is written to a usb drive using <a href="https://www.drive-image.com/downloads/RDriveImage7.exe">r-drive image</a>)
    - be sure to transfer both (!!!) partitions from the image to the drive
    - delete everything from EFI on usb
    - copy EFI folder from EFI.zip to EFI on usb
* installation
  + open disk utility and erase the partition created in step 1 to APFS file system
  + run the installation
* post-install
  + create an EFI partition on drive:
    - search the internet for guides. i'm too lazy to write one.
  + fix for combojack
    - ```
      git clone https://github.com/lvs1974/ComboJack.git
      bash ComboJack/ComboJack_Installer/install.sh
      rm -rf ComboJack
      ```

### problems
- all component problems are described in [component situation table](#components-situation)
- if you don't understand/want to change opencore settings - you'll have to live with “6-ядерный” instead of “6-core” in the about this mac menu
  + fix:
    - config.plist: NVRAM/4D1FDA02-38C7-4A6A-9CC6-4BCCA8B30102/revcpuname -> 6-core AMD Ryzen 5
    - reset nvram
  
<br>
i used the EFI from <a href="https://github.com/saeidex/ryzentosh-msi-modern-15">saeidex/ryzentosh-msi-modern-15</a> as a basis
