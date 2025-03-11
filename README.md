# About
This repository provides a keymap for the Lenovo KU-1255 (ThinkPad Compact USB Keyboard with TrackPoint) firmware. The firmware stores key-specific values, generated by XORing the HID Usage ID with 0x5A, at specific offsets within the binary. By modifying these XORed IDs, you can remap any key on the KU-1255. A GUI tool to easily create a key-remapped firmware is also provided.

# Disclaimer
The data in this table is generated from automated firmware analysis using `keymap_offset_finder.py`. **The result accuracy is not assured. Use at your own risk.**

# GUI Tool Usage
1. Download the latest firmware `tp_compact_usb_kb_with_trackpoint_fw.exe` from the [Lenovo official website](https://support.lenovo.com/ca/en/solutions/pd026745).
2. Download the [released application](https://github.com/haborite/ku1255-firmware-keymap/releases/download/v0.5.0/ku1255-fw-remapper-win-0.5.0.zip) and unzip it.
3. Run `ku1255-fw-remapper.exe` in the unzipped directory (It will take a bit time to launch).

<img width="640" alt="gui-overview" src="https://github.com/haborite/ku1255-firmware-keymap/blob/main/img/gui-overview.png">

5. Click "1. Select Original Firmware" and select the downloaded firmware `tp_compact_usb_kb_with_trackpoint_fw.exe`.
6. Confirm that the original SHA256 hash is `7116a3819ee094857d21e4671cb6cf953d582372126f0f6728f6b2421eda7bd4`.
7. Click "2. Select Key Remap csv" and select a key-remap csv file (e.g. Use `examples\Swap-Fn-Ctrl.csv` to just swap `Fn` and `LeftControl`). If you want to create or modify key-remapping csv files, please see the "Offset & XORed ID table" described below.  
5. Click "3. Modify and Save New Firmware", and specify the filename and path of the new firmware.
6. Check SH256 hash (e.g. If you use `Swap-Fn-Ctrl.csv`, it should be `123143092dab578550c87a62526b07a6c5f06c047f2455be87971aa51577e300`).
7. Close the app.

# Offset & XORed ID table
Only keys in `Keyboard/Keypad Page (0x07)` are listed. Keys with no `Byte_Offset` value are not originally assigned in KU-1255.
| ID | Byte_Offset | XORed_ID | Usage Name | 0B47190 (US) | 0B47208 (JIS) | ISO |
| --- | --- | --- | --- | --- | --- | --- |
| 01 |  | 5B | ErrorRollOver |  |  |  |
| 02 |  | 58 | POSTFail |  |  |  |
| 03 |  | 59 | ErrorUndefined |  |  |  |
| 04 | 73FDA | 5E | a and A | a and A | a and A | a and A |
| 05 | 7401E | 5F | b and B | b and B | b and B | b and B |
| 06 | 73FEC | 5C | c and C | c and C | c and C | c and C |
| 07 | 73FEA | 5D | d and D | d and D | d and D | d and D |
| 08 | 73FE6 | 52 | e and E | e and E | e and E | e and E |
| 09 | 7401A | 53 | f and F | f and F | f and F | f and F |
| 0A | 74012 | 50 | g and G | g and G | g and G | g and G |
| 0B | 74022 | 51 | h and H | h and H | h and H | h and H |
| 0C | 74036 | 56 | i and I | i and I | i and I | i and I |
| 0D | 7402A | 57 | j and J | j and J | j and J | j and J |
| 0E | 7403A | 54 | k and K | k and K | k and K | k and K |
| 0F | 7404A | 55 | l and L | l and L | l and L | l and L |
| 10 | 7402C | 4A | m and M | m and M | m and M | m and M |
| 11 | 7402E | 4B | n and N | n and N | n and N | n and N |
| 12 | 74046 | 48 | o and O | o and O | o and O | o and O |
| 13 | 74056 | 49 | p and P | p and P | p and P | p and P |
| 14 | 73FD6 | 4E | q and Q | q and Q | q and Q | q and Q |
| 15 | 74016 | 4F | r and R | r and R | r and R | r and R |
| 16 | 73FFA | 4C | s and S | s and S | s and S | s and S |
| 17 | 74020 | 4D | t and T | t and T | t and T | t and T |
| 18 | 74026 | 42 | u and U | u and U | u and U | u and U |
| 19 | 7401C | 43 | v and V | v and V | v and V | v and V |
| 1A | 73FF6 | 40 | w and W | w and W | w and W | w and W |
| 1B | 73FFC | 41 | x and X | x and X | x and X | x and X |
| 1C | 74030 | 46 | y and Y | y and Y | y and Y | y and Y |
| 1D | 73FDC | 47 | z and Z | z and Z | z and Z | z and Z |
| 1E | 73FD8 | 44 | 1 and ! | 1 and ! | 1 and ! | 1 and ! |
| 1F | 73FF8 | 45 | 2 and @ | 2 and @ | 2 and " | 2 and @ |
| 20 | 73FE8 | 7A | 3 and # | 3 and # | 3 and # | 3 and £ |
| 21 | 74018 | 7B | 4 and $ | 4 and $ | 4 and $ | 4 and $ |
| 22 | 74014 | 78 | 5 and % | 5 and % | 5 and % | 5 and % |
| 23 | 74024 | 79 | 6 and ^ | 6 and ^ | 6 and & | 6 and ^ |
| 24 | 74028 | 7E | 7 and & | 7 and & | 7 and ' | 7 and & |
| 25 | 74038 | 7F | 8 and * | 8 and * | 8 and ( | 8 and * |
| 26 | 74048 | 7C | 9 and ( | 9 and ( | 9 and ) | 9 and ( |
| 27 | 74058 | 7D | 0 and ) | 0 and ) | 0 | 0 and ) |
| 28 | 7407C | 72 | Return (ENTER) | Enter | Enter | Enter |
| 29 | 73FD2 | 73 | ESCAPE | Escape | Escape | Escape |
| 2A | 74080 | 70 | DELETE (Backspace) | Backspace | Backspace | Backspace |
| 2B | 73FE0 | 71 | Tab | Tab | Tab | Tab |
| 2C | 7407E | 76 | Spacebar | Spacebar | Spacebar | Spacebar |
| 2D | 74054 | 77 | ー and Underscore | ー and _ | ー and = | ー and _ |
| 2E | 74034 | 74 | = and + | = and + | ^ and ~ | = and + |
| 2F | 74060 | 75 | [ and { | [ and { | @ and ` | [ and { |
| 30 | 74040 | 6A | ] and } | ] and } | [ and { | ] and } |
| 31 | 7407A | 6B | \ and &#124; | \ and &#124; |  |  |
| 32 | 7405C | 68 | NonーUS # and ~ |  | ] and } | # and ~ |
| 33 | 7405A | 69 | ; and : | ; and : | ; and + | ; and : |
| 34 | 74052 | 6E | ' and " | ' and " | : and * | ' and " |
| 35 | 73FD4 | 6F | Grave Accent and Tilde | ` and ~ | 半角 / 全角 | ` and ¬ |
| 36 | 7403C | 6C | Comma and < | , and < | , and < | , and < |
| 37 | 7404C | 6D | . and > | . and > | . and > | . and > |
| 38 | 7405E | 62 | / and ? | / and ? | / and ? | / and ? |
| 39 | 74000 | 63 | Caps Lock | Caps Lock | 英数 / Caps Lock | Caps Lock |
| 3A | 73FF4 | 60 | F1 | F1 | F1 | F1 |
| 3B | 73FE4 | 61 | F2 | F2 | F2 | F2 |
| 3C | 73FF0 | 66 | F3 | F3 | F3 | F3 |
| 3D | 73FE2 | 67 | F4 | F4 | F4 | F4 |
| 3E | 74072 | 64 | F5 | F5 | F5 | F5 |
| 3F | 74032 | 65 | F6 | F6 | F6 | F6 |
| 40 | 74050 | 1A | F7 | F7 | F7 | F7 |
| 41 | 74044 | 1B | F8 | F8 | F8 | F8 |
| 42 | 74074 | 18 | F9 | F9 | F9 | F9 |
| 43 | 74078 | 19 | F10 | F10 | F10 | F10 |
| 44 | 74088 | 1E | F11 | F11 | F11 | F11 |
| 45 | 740A8 | 1F | F12 | F12 | F12 | F12 |
| 46 | 740CA | 1C | PrintScreen | PrintScreen | PrintScreen | PrintScreen |
| 47 |  | 1D | Scroll Lock | Scroll Lock | Scroll Lock | Scroll Lock |
| 48 | 740BC | 12 | Pause | Pause | Pause | Pause |
| 49 | 740C8 | 13 | Insert | Insert | Insert | Insert |
| 4A | 74084 | 10 | Home | Home | Home | Home |
| 4B | 740CC | 11 | PageUp | PgUp | PgUp | PgUp |
| 4C | 740C4 | 16 | Delete Forward | Delete | Delete | Delete |
| 4D | 740B8 | 17 | End | End | End | End |
| 4E | 740CE | 14 | PageDown | PgDn | PgDn | PgDn |
| 4F | 740AE | 15 | RightArrow | Right | Right | Right |
| 50 | 740BE | A | LeftArrow | Left | Left | Left |
| 51 | 7408E | B | DownArrow | Down | Down | Down |
| 52 | 740B2 | 8 | UpArrow | Up | Up | Up |
| 53 |  | 9 | Keypad Num Lock and Clear | Num Lock | Num Lock | Num Lock |
| 54 |  | E | Keypad Forward Slash | KPー/ | KPー/ | KPー/ |
| 55 |  | F | Keypad * | KPー* | KPー* | KPー* |
| 56 |  | C | Keypad ー | KPー— | KPー— | KPー— |
| 57 |  | D | Keypad + | KPー+ | KPー+ | KPー+ |
| 58 |  | 2 | Keypad ENTER | KPーEnter | KPーEnter | KPーEnter |
| 59 |  | 3 | Keypad 1 and End | KPー1 and End | KPー1 and End | KPー1 and End |
| 5A |  | 0 | Keypad 2 and Down Arrow | KPー2 and Down | KPー2 and Down | KPー2 and Down |
| 5B |  | 1 | Keypad 3 and PageDn | KPー3 and PgDn | KPー3 and PgDn | KPー3 and PgDn |
| 5C |  | 6 | Keypad 4 and Left Arrow | KPー4 and Left | KPー4 and Left | KPー4 and Left |
| 5D |  | 7 | Keypad 5 | KPー5 | KPー5 | KPー5 |
| 5E |  | 4 | Keypad 6 and Right Arrow | KPー6 and Right | KPー6 and Right | KPー6 and Right |
| 5F |  | 5 | Keypad 7 and Home | KPー7 and Home | KPー7 and Home | KPー7 and Home |
| 60 |  | 3A | Keypad 8 and Up Arrow | KPー8 and Up | KPー8 and Up | KPー8 and Up |
| 61 |  | 3B | Keypad 9 and PageUp | KPー9 and PgUp | KPー9 and PgUp | KPー9 and PgUp |
| 62 |  | 38 | Keypad 0 and Insert | KPー0 and Insert | KPー0 and Insert | KPー0 and Insert |
| 63 |  | 39 | Keypad . and Delete | KPー. and Delete | KPー. and Delete | KPー. and Delete |
| 64 | 73FF2 | 3E | NonーUS Slash Bar |  |  | \ and &#124; |
| 65 |  | 3F | Application | App | App | App |
| 66 |  | 3C | Power | Power | Power | Power |
| 67 |  | 3D | Keypad = |  |  |  |
| 68 |  | 32 | F13 |  |  |  |
| 69 |  | 33 | F14 |  |  |  |
| 6A |  | 30 | F15 |  |  |  |
| 6B |  | 31 | F16 |  |  |  |
| 6C |  | 36 | F17 |  |  |  |
| 6D |  | 37 | F18 |  |  |  |
| 6E |  | 34 | F19 |  |  |  |
| 6F |  | 35 | F20 |  |  |  |
| 70 |  | 2A | F21 |  |  |  |
| 71 |  | 2B | F22 |  |  |  |
| 72 |  | 28 | F23 |  |  |  |
| 73 |  | 29 | F24 |  |  |  |
| 74 |  | 2E | Execute |  |  |  |
| 75 |  | 2F | Help |  |  |  |
| 76 |  | 2C | Menu |  |  |  |
| 77 |  | 2D | Select |  |  |  |
| 78 |  | 22 | Stop |  |  |  |
| 79 |  | 23 | Again |  |  |  |
| 7A |  | 20 | Undo |  |  |  |
| 7B |  | 21 | Cut |  |  |  |
| 7C |  | 26 | Copy |  |  |  |
| 7D |  | 27 | Paste |  |  |  |
| 7E |  | 24 | Find |  |  |  |
| 7F |  | 25 | Mute |  |  |  |
| 80 |  | DA | Volume Up |  |  |  |
| 81 |  | DB | Volume Down |  |  |  |
| 82 |  | D8 | Locking Caps Lock |  |  |  |
| 83 |  | D9 | Locking Numb Lock |  |  |  |
| 84 |  | DE | Locking Scroll Lock |  |  |  |
| 85 |  | DF | Keypad Comma |  |  |  |
| 86 |  | DC | Keypad Equal Sign |  |  |  |
| 87 | 7403E | DD | International1 |  | \ and _ |  |
| 88 | 7404E | D2 | International2 |  | カタカナ / ひらがな |  |
| 89 | 74076 | D3 | International3 |  | ¥ and &#124; |  |
| 8A | 74042 | D0 | International4 |  | 変換 |  |
| 8B | 73FDE | D1 | International5 |  | 無変換 |  |
| 8C |  | D6 | International6 |  |  |  |
| 8D |  | D7 | International7 |  |  |  |
| 8E |  | D4 | International8 |  |  |  |
| 8F |  | D5 | International9 |  |  |  |
| 90 |  | CA | LANG1 |  | かな |  |
| 91 |  | CB | LANG2 |  | 英数 |  |
| 92 |  | C8 | LANG3 |  |  |  |
| 93 |  | C9 | LANG4 |  |  |  |
| 94 |  | CE | LANG5 |  |  |  |
| 95 |  | CF | LANG6 |  |  |  |
| 96 |  | CC | LANG7 |  |  |  |
| 97 |  | CD | LANG8 |  |  |  |
| 98 |  | C2 | LANG9 |  |  |  |
| 99 |  | C3 | Alternate Erase |  |  |  |
| 9A |  | C0 | SysReq/Attention |  |  |  |
| 9B |  | C1 | Cancel |  |  |  |
| 9C |  | C6 | Clear |  |  |  |
| 9D |  | C7 | Prior |  |  |  |
| 9E |  | C4 | Return |  |  |  |
| 9F |  | C5 | Separator |  |  |  |
| A0 |  | FA | Out |  |  |  |
| A1 |  | FB | Oper |  |  |  |
| A2 |  | F8 | Clear/Again |  |  |  |
| A3 |  | F9 | CrSel/Props |  |  |  |
| A4 |  | FE | ExSel |  |  |  |
| A5 |  | FF | Reserved |  |  |  |
| A6 |  | FC | Reserved |  |  |  |
| A7 |  | FD | Reserved |  |  |  |
| A8 |  | F2 | Reserved |  |  |  |
| A9 |  | F3 | Reserved |  |  |  |
| AA |  | F0 | Reserved |  |  |  |
| AB |  | F1 | Reserved |  |  |  |
| AC |  | F6 | Reserved |  |  |  |
| AD |  | F7 | Reserved |  |  |  |
| AE |  | F4 | Reserved |  |  |  |
| AF | 740BA | F5 | Fn | Fn | Fn | Fn |
| B0 |  | EA | Keypad 00 |  |  |  |
| B1 |  | EB | Keypad 000 |  |  |  |
| B2 |  | E8 | Thousands Separator |  |  |  |
| B3 |  | E9 | Decimal Separator |  |  |  |
| B4 |  | EE | Currency Unit |  |  |  |
| B5 |  | EF | Currency Subーunit |  |  |  |
| B6 |  | EC | Keypad ( |  |  |  |
| B7 |  | ED | Keypad ) |  |  |  |
| B8 |  | E2 | Keypad { |  |  |  |
| B9 |  | E3 | Keypad } |  |  |  |
| BA |  | E0 | Keypad Tab |  |  |  |
| BB |  | E1 | Keypad Backspace |  |  |  |
| BC |  | E6 | Keypad A |  |  |  |
| BD |  | E7 | Keypad B |  |  |  |
| BE |  | E4 | Keypad C |  |  |  |
| BF |  | E5 | Keypad D |  |  |  |
| C0 |  | 9A | Keypad E |  |  |  |
| C1 |  | 9B | Keypad F |  |  |  |
| C2 |  | 98 | Keypad XOR |  |  |  |
| C3 |  | 99 | Keypad ^ |  |  |  |
| C4 |  | 9E | Keypad % |  |  |  |
| C5 |  | 9F | Keypad < |  |  |  |
| C6 |  | 9C | Keypad > |  |  |  |
| C7 |  | 9D | Keypad & |  |  |  |
| C8 |  | 92 | Keypad && |  |  |  |
| C9 |  | 93 | Keypad | |  |  |  |
| CA |  | 90 | Keypad || |  |  |  |
| CB |  | 91 | Keypad : |  |  |  |
| CC |  | 96 | Keypad # |  |  |  |
| CD |  | 97 | Keypad Space |  |  |  |
| CE |  | 94 | Keypad @ |  |  |  |
| CF |  | 95 | Keypad ! |  |  |  |
| D0 |  | 8A | Keypad Memory Store |  |  |  |
| D1 |  | 8B | Keypad Memory Recall |  |  |  |
| D2 |  | 88 | Keypad Memory Clear |  |  |  |
| D3 |  | 89 | Keypad Memory Add |  |  |  |
| D4 |  | 8E | Keypad Memory Subtract |  |  |  |
| D5 |  | 8F | Keypad Memory Multiply |  |  |  |
| D6 |  | 8C | Keypad Memory Divide |  |  |  |
| D7 |  | 8D | Keypad +/ー |  |  |  |
| D8 |  | 82 | Keypad Clear |  |  |  |
| D9 |  | 83 | Keypad Clear Entry |  |  |  |
| DA |  | 80 | Keypad Binary |  |  |  |
| DB |  | 81 | Keypad Octal |  |  |  |
| DC |  | 86 | Keypad Decimal |  |  |  |
| DD |  | 87 | Keypad Hexadecimal |  |  |  |
| DE |  | 84 | Reserved |  |  |  |
| DF |  | 85 | Reserved |  |  |  |
| E0 | 74004 | BA | LeftControl | LCtrl | LCtrl | LCtrl |
| E1 | 74070 | BB | LeftShift | LShift | LShift | LShift |
| E2 | 74092 | B8 | LeftAlt | LAlt | LAlt | LAlt |
| E3 | 740B0 | B9 | Left GUI | LWin | LWin | LWin |
| E4 | 7400C | BE | RightControl | RCtrl | RCtrl | RCtrl |
| E5 | 7406C | BF | RightShift | RShift | RShift | RShift |
| E6 | 7409E | BC | RightAlt | RAlt | RAlt | RAlt |
| E7 |  | BD | Right GUI | RWin | RWin | RWin |

# Format of a remap CSV
For each row, specify the key ID before and after the change.

e.g.) Swap-Fn-Ctrl.csv
```Swap-Fn-Ctrl.csv
Before_ID,After_ID
E0,AF
AF,E0
```

# Acknowledgements
The firmware binary analysis methodology employed in this project is based on the discussion in the following thread, with particular acknowledgement to @federvieh's insightful comment:
- https://github.com/lentinj/tp-compact-keyboard/issues/32#issuecomment-687659110
- https://github.com/lentinj/tp-compact-keyboard/issues/32

The reffered table of Usage IDs and names
- https://bsakatu.net/doc/usb-hid-to-scancode/
