# ryzentosh-msi-modern-15-b7m
msi modern 15 b7m (R5 7530U) hackintosh

![добрый вечер я диспетчер](https://github.com/user-attachments/assets/e5568407-cd6d-449b-b8a8-8741f0deac1a)

<a href="https://drive.google.com/file/d/1bkfjiVjOvsQkADeyKQms7r9SnuctIsxf/view?usp">
  <img src="https://img.shields.io/badge/Sonoma-14.0-5B8266">
</a>
<a href="https://github.com/acidanthera/OpenCorePkg">
  <img src="https://img.shields.io/badge/OpenCore-0.9.5-4381C1">
</a>
<a href="https://github.com/saeidex/ryzentosh-msi-modern-15">
  <img src="https://img.shields.io/badge/saeidex-ryzentosh--msi--modern--15-388697">
</a>

## русский

### состояние компонентов:
| **компонент** | **состояние** |
| --------------- | :-----------------: |
| **ryzen 5 7530u `amd`**        | ✓  |
| **radeon graphics `amd`**      | ✓  |
| **ssd nvme `kingston`**        | ✓  |
| **звуковая карта `realtek`**   | ✓  |
| **микрофон `realtek`**         | ✗  |
| **вход для наушников**         | ✓  |
| **wifi/bluetooth `mtk rz608`** | ✗  |
| **картридер `realtek`**        | ✓  |
| **вебкамера `msi`**            | ✓  |
| **клавиатура `ps2`**           | ✓  |
| **трекпад `i2c`**              | ✓  |
| **tethering `usb`**            | ✓  |

### вход для наушников (работает только с патчем):
```
git clone https://github.com/lvs1974/ComboJack.git
bash ComboJack/ComboJack_Installer/install.sh
rm -rf ComboJack
```

### wifi
и все же, завести rz608 под macos пока не удалось

но эти usb wifi адаптеры работают с <a href="https://github.com/chris1111/Wireless-USB-Big-Sur-Adapter/releases/download/V18/Wireless.USB.Big.Sur.Adapter-V18.zip">драйвером</a> (chris1111/Wireless-USB-Big-Sur-Adapter)
|:-------------------------:|
|Acer UWA5                  |
|Alfa AWUS036AC             |
|Alfa AWUS036ACH            |
|Archer T2U Plus `AC600`    |
|Archer T2U Nano            |
|Archer T3U                 |
|Archer T3U Plus            |
|Archer T2U MINI V3         |
|ArcherT4U V1, V2, V3       |
|Archer T9UH V1, V2         |
|ASUS USB AC68              |
|ASUS USB-N13               |
|ASUS USB Nano-AC53         |
|BrosTrend FBA_AC3          |
|COMFAST CF-811AC           |
|COMFAST CF-812AC           |
|Comfast CF-WU810N          |
|Comfast CF-758F            |
|Cudy WU1300S               | 
|Cudy WU700                 |
|CXFTEOXK                   |
|DLink DWA-121 `N150`       |
|DLink DWA-131 E            |
|DLink DWA-171 C            |
|DLink DWA-182 D            |
|DLink DWA-192 A            |
|EDIMAX EW-7611UCB          |
|EDIMAX EW-7722UTn V2       |
|EDIMAX_EW-7822ULC          |
|EDIMAX EW-7833UAC          |
|EDIMAX EW-7612Uan V2       |
|EDIMAX N300                |
|EDIMAX EW-7811Un `N150`    |
|EDUP EP-AC1689             |
|Fenvi AC1300 `RTL8812bu`   |
|FILOWA USB WiFi-RTL8812BU  | 
|Foktech AC600 Nano         |
|Jensen Eagle 100-AC        |
|Kextech MINI USB RTL8192   |
|Linksys WUSB6300 V2        |
|Linksys WUSB6400M          |
|Netgear A6100              |
|Netgear A6150              |
|Netgear A7000              |
|Netis WF2120 N Nano USB    |
|M-Tech UW-01 USB           |
|Mercusys MW300UM           |
|Plexgear AC1200            |
|Raimadim AC1300 `RTL8822BU`|
|Sitecom WLA7100            |
|TechKey AC1200             |
|TL-WN823Nv1/v2/v3          |
|TL-WN725Nv3                | 
|TL-WN723Nv2/v3             |
|TL-WN722Nv2/v3             |
|TL-WN821Nv6                |
|TL-WN822Nv4/v5             |
|TENDA W311-MINI            |
|TENDA U12                  |
|TRENDnet N150 Micro        |
|TRENDnet TEW-808UBM        |
|TRENDnet TEW-908UB         |
|UGreen CM448               |
|YUNCLOUD `RTL8814AU`       |
|ZAPO W58L `RTL881lAU`      |
|Zyxel NWD6602              |
|Zyxel NWD6605              |

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
* подготовка
  + создать раздел для установки macOS (из windows, отформатировать в NTFS)
  + так как wifi не работает, а ethernet порта в ноутбуке нет - нам нужен <a href="https://drive.google.com/file/d/1bkfjiVjOvsQkADeyKQms7r9SnuctIsxf/view?usp">полный офлайн установщик</a>  (этот записывается на usb накопитель с помощью <a href="https://www.drive-image.com/downloads/RDriveImage7.exe">r-drive image</a>)
    - на накопитель обязательно перенести оба (!!!) раздела из образа
    - далее:\
      пример:
      ```
      C:\Windows\System32>diskpart
      DISKPART> list disk
          Диск ###   Состояние   Размер        Свободно   Дин   GPT
          --------   ---------   ----------    --------   ---   ---
          Диск 0     В сети      240 Gбайт     1024 Кбайт        *
          Диск 1     В сети      32 Gбайт      1024 Кбайт        *
      DISKPART> sel disk 1
      DISKPART> list part
          Раздел ###   Тип         Размер      Смещение
          ----------   ---------   ---------   ----------
          Раздел 0     Системный   200 Мбайт   1024 Кбайт
          Раздел 1     Основной     14 Гбайт    200 Мбайт
      DISKPART> sel part 0
      DISKPART> assign letter X
      DiskPart: назначение имени диска или точки подключения выполнено успешно.
      DISKPART> exit
      C:\Windows\System32>X:
      X:> rd X:\
      ```
    - копировать на раздел X:\ папку EFI из EFI.zip\
      теперь с созданного накопителя можно загрузить установщик, если все сделано правильно
* установка
  + открыть дисковую утилиту и стереть раздел, созданный на 1 этапе в файловую систему APFS
  + запустить установку
* после установки
  + из windows создать раздел EFI:
    - сначала нужно немного нераспределенного пространства на диске (300-400 мб)
    - далее:
      ```
      C:\Windows\System32>diskpart
      DISKPART> sel disk 0
      DISKPART> create part efi size=300
      DiskPart: указанный раздел успешно создан.
      DISKPART> format fs=fat32
         Завершено (в процентах): 100
      DiskPart: указанный раздел успешно отформатирован.
      DISKPART> assign letter X
      DiskPart: назначение имени диска или точки подключения выполнено успешно.
      DISKPART> exit
      C:\Windows\System32>X:
      X:>
      ```
    - копировать папку EFI из EFI.zip в C:
    - далее:
      ```
      X:>C:
      C:>xcopy -s C:\EFI X:\EFI
      Что означает X:\EFI:
      имя файла или каталога
      (F = файл, D = каталог)? D
      X:>
      ```
    - теперь на диске есть загрузочный раздел opencore
    - в bios нужно выбрать этот раздел (он будет называтся UEFI OS) как основной загрузочный

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
| **ryzen 5 7530u `amd`**         | ✓  |
| **radeon graphics `amd`**       | ✓  |
| **ssd nvme `kingston`**         | ✓  |
| **speaker `realtek`**           | ✓  |
| **mic `realtek`**               | ✗  |
| **combojack**                   | ✓  |
| **wifi/bluetooth `mtk rz608`**  | ✗  |
| **cardreader `realtek`**        | ✓  |
| **webcamera `msi`**             | ✓  |
| **keyboard `ps2`**              | ✓  |
| **touchpad `i2c`**              | ✓  |
| **tethering `usb`**             | ✓  |

### combojack (works only with this patch):
```
git clone https://github.com/lvs1974/ComboJack.git
bash ComboJack/ComboJack_Installer/install.sh
rm -rf ComboJack
```

### wifi
and yet, I haven't been able to get the rz608 on macos yet.

but these usb wifi adapters work with this <a href="https://github.com/chris1111/Wireless-USB-Big-Sur-Adapter/releases/download/V18/Wireless.USB.Big.Sur.Adapter-V18.zip">driver</a> (chris1111/Wireless-USB-Big-Sur-Adapter)
|:-------------------------:|
|Acer UWA5                  |
|Alfa AWUS036AC             |
|Alfa AWUS036ACH            |
|Archer T2U Plus `AC600`    |
|Archer T2U Nano            |
|Archer T3U                 |
|Archer T3U Plus            |
|Archer T2U MINI V3         |
|ArcherT4U V1, V2, V3       |
|Archer T9UH V1, V2         |
|ASUS USB AC68              |
|ASUS USB-N13               |
|ASUS USB Nano-AC53         |
|BrosTrend FBA_AC3          |
|COMFAST CF-811AC           |
|COMFAST CF-812AC           |
|Comfast CF-WU810N          |
|Comfast CF-758F            |
|Cudy WU1300S               | 
|Cudy WU700                 |
|CXFTEOXK                   |
|DLink DWA-121 `N150`       |
|DLink DWA-131 E            |
|DLink DWA-171 C            |
|DLink DWA-182 D            |
|DLink DWA-192 A            |
|EDIMAX EW-7611UCB          |
|EDIMAX EW-7722UTn V2       |
|EDIMAX_EW-7822ULC          |
|EDIMAX EW-7833UAC          |
|EDIMAX EW-7612Uan V2       |
|EDIMAX N300                |
|EDIMAX EW-7811Un `N150`    |
|EDUP EP-AC1689             |
|Fenvi AC1300 `RTL8812bu`   |
|FILOWA USB WiFi-RTL8812BU  | 
|Foktech AC600 Nano         |
|Jensen Eagle 100-AC        |
|Kextech MINI USB RTL8192   |
|Linksys WUSB6300 V2        |
|Linksys WUSB6400M          |
|Netgear A6100              |
|Netgear A6150              |
|Netgear A7000              |
|Netis WF2120 N Nano USB    |
|M-Tech UW-01 USB           |
|Mercusys MW300UM           |
|Plexgear AC1200            |
|Raimadim AC1300 `RTL8822BU`|
|Sitecom WLA7100            |
|TechKey AC1200             |
|TL-WN823Nv1/v2/v3          |
|TL-WN725Nv3                | 
|TL-WN723Nv2/v3             |
|TL-WN722Nv2/v3             |
|TL-WN821Nv6                |
|TL-WN822Nv4/v5             |
|TENDA W311-MINI            |
|TENDA U12                  |
|TRENDnet N150 Micro        |
|TRENDnet TEW-808UBM        |
|TRENDnet TEW-908UB         |
|UGreen CM448               |
|YUNCLOUD `RTL8814AU`       |
|ZAPO W58L `RTL881lAU`      |
|Zyxel NWD6602              |
|Zyxel NWD6605              |


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
* preparations
  + create partiton for macOS (from windows, format - NTFS)
  + since the wifi doesnt work and the laptop doesnt have an ethernet port, we're need <a href="https://drive.google.com/file/d/1bkfjiVjOvsQkADeyKQms7r9SnuctIsxf/view?usp">full offline installer</a>  (this one is written to a usb drive using <a href="https://www.drive-image.com/downloads/RDriveImage7.exe">r-drive image</a>)
    - be sure to transfer both (!!!) partitions from the image to the drive
    - next:\
      example:
      ```
      C:Windows/System32>diskpart
      DISKPART> list disk
          Disk ### Status     Size          Free          Dyn   GPT
          -------- ---------  ----------    -----------   ---   ---
          Disk 0   Online     240 Gbytes    1024 Kbytes          *
          Disk 1   Online      32 Gbytes    1024 Kbytes          *
      DISKPART> sel disk 1
      DISKPART> list part
          Partition ###   Type        Size        Offset
          -------------   ---------   ---------   -----------
          Partition 0     System      200 Mbyte   1024 Kbytes
          Partition 1     Primary     14 Gbytes   200 Mbytes
      DISKPART> sel part 0
      DISKPART> assign letter X
      DiskPart: assignment of disk name or connection point was successful.
      DISKPART> exit
      C:Windows\System32>X:
      X:> rd X:\
      ```
    - copy the EFI folder from EFI.zip\ to the X:\ partition.
      now you can boot the installer from the created drive, if everything is done correctly.
* installer
  + open disk utility and erase the partition created in step 1 to APFS file system
  + run the installation
* after installation
  + from windows create an EFI partition:
    - first you need some unallocated disk space (300-400 mb)
    - next:
      ```
      C:Windows/System32>diskpart
      DISKPART> sel disk 0
      
      DISKPART> create part efi size=300
      DiskPart: the specified partition was successfully created.
      DISKPART> format fs=fat32
         Completed (percentage): 100
      DiskPart: the specified partition was successfully formatted.
      DISKPART> assign letter X
      DiskPart: assignment of disk name or connection point was successful.
      DISKPART> exit
      C:Windows\System32>X:
      X:>
      ```
    - copy the EFI folder from EFI.zip to C:
    - next:
      ```
      X:>C:
      C:>xcopy -s C:\EFI X:\EFI
      Which means X:\EFI:
      File or directory name
      (F = file, D = directory)? D
      X:>
      ```
    - now there is an opencore boot partition on the disk.
    - in bios you need to select this partition (it will be called UEFI OS) as the primary boot partition.

### problems:
- all component problems are described in [component situation table](#components-situation)
- if you don't understand/want to change opencore settings - you'll have to live with “6-ядерный” instead of “6-core” in the about this mac menu
  
<br>
i used the EFI from <a href="https://github.com/saeidex/ryzentosh-msi-modern-15">saeidex/ryzentosh-msi-modern-15</a> as a basis
