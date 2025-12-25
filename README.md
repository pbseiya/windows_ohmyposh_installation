# คู่มือการติดตั้งและปรับแต่ง Oh My Posh สำหรับ Windows PowerShell ให้สวยและเก่งเหมือน Zsh (ฉบับจับมือทำ)

เอกสารนี้จะพาคุณเปลี่ยนหน้าจอ **Windows PowerShell** เดิมๆ ให้สวยงามและทำงานได้ฉลาดขึ้น โดยการติดตั้ง **Oh My Posh** และเครื่องมือต่างๆ ให้มีฟีเจอร์เหมือนกับระบบ Zsh ของ Linux/Mac

---

## เราจะติดตั้งโปรแกรมอะไรบ้าง?
1.  **Oh My Posh**: ตกแต่ง Prompt ให้สวยงาม บอกสถานะ Git, Path, etc.
2.  **PSReadLine**: ช่วยเดาคำสั่ง (Autosuggestions) และแยกสีคำสั่ง (Syntax Highlighting)
3.  **Nerd Font (MesloLGS NF)**: ฟอนต์ที่มีรูปไอคอน เพื่อให้แสดงผลกราฟิกได้ถูกต้อง

---

## ขั้นตอนการติดตั้ง (Installation Steps)

### ขั้นตอนที่ 1: ติดตั้ง Oh My Posh
เลือกวิธีติดตั้งได้ตามความสะดวก (แนะนำวิธีที่ 1.1 ก่อน)

#### 1.1 วิธีแนะนำ (Official / Winget)
วิธีนี้ง่ายที่สุดและเป็นวิธีมาตรฐานจาก Official
1.  เปิด **PowerShell** หรือ **Terminal**
2.  พิมพ์คำสั่งต่อไปนี้แล้วกด Enter:
    ```powershell
    winget install JanDeDobbeleer.OhMyPosh -s winget
    ```
3.  รอจนติดตั้งเสร็จ ปิด Terminal แล้วเปิดใหม่

#### 1.2 วิธีสำรอง (Manual)
หากเครื่องติด Policy ให้ใช้วิธีนี้:
1.  ไปที่ `C:\Users\ชื่อเครื่องของคุณ\AppData\Local\Programs` สร้างโฟลเดอร์ `oh-my-posh\bin`
2.  ดาวน์โหลดไฟล์ [posh-windows-amd64.exe](https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest)
3.  เปลี่ยนชื่อเป็น `oh-my-posh.exe` แล้วนำไปวางในโฟลเดอร์ `bin`

---

### ขั้นตอนที่ 2: ติดตั้ง Theme
1.  ไปที่โฟลเดอร์ผู้ใช้ `C:\Users\ชื่อผู้ใช้ของคุณ\` สร้างโฟลเดอร์ `.poshthemes`
2.  ดาวน์โหลดไฟล์ [vibrant-python.omp.json](https://raw.githubusercontent.com/pbseiya/oh-my-posh-python-theme/main/vibrant-python.omp.json) ลงไปในโฟลเดอร์นั้น

---

### ขั้นตอนที่ 3: ติดตั้ง Font (ตามวิธี Official)

เพื่อให้เห็นไอคอนถูกต้อง เราต้องติดตั้ง **Nerd Font** แนะนำให้ใช้คำสั่งของ Oh My Posh โดยตรงครับ (อ้างอิงจาก [Official Docs](https://ohmyposh.dev/docs/installation/fonts))

#### วิธีที่ 1: ใช้คำสั่งอัตโนมัติ (แนะนำ)
1.  เปิด PowerShell (Run as Administrator จะดีที่สุด เพื่อให้ติดตั้งได้ทั้งเครื่อง)
2.  รันคำสั่ง:
    ```powershell
    oh-my-posh font install
    ```
3.  จะมีรายการฟอนต์ขึ้นมาให้เลือก ให้ใช้ลูกศรเลื่อนหา **CodeNewRoman** (หรือฟอนต์ที่ชอบ)
    *   *Tip: ถ้าอยากได้ Meslo ให้เลือก `Meslo`*
4.  กด Enter เพื่อติดตั้ง

#### วิธีที่ 2: ดาวน์โหลดเอง (Manual)
หากวิธีแรกไม่ได้ผล ให้ดาวน์โหลดเอง:
1.  ไปที่ [Nerd Fonts Downloads](https://www.nerdfonts.com/font-downloads)
2.  หาฟอนต์ **CodeNewRoman Nerd Font** แล้วกด Download
3.  แตกไฟล์ Zip แล้วเลือกไฟล์ `.ttf` ทั้งหมด คลิกขวาเลือก **Install**

---

### ขั้นตอนที่ 4: ตั้งค่า Font ให้แสดงผล (Configuring Font)
หลังจากติดตั้งฟอนต์แล้ว ต้องเข้าไปตั้งค่าใน Windows Terminal

#### 4.1 ตั้งค่าใน Windows Terminal (settings.json)
1.  เปิด Windows Terminal กด `Ctrl` + `Shift` + `,` เพื่อเปิดไฟล์ Settings (JSON)
2.  หรือเข้าเมนู **Settings > Windows PowerShell > Appearance**
3.  เปลี่ยน **Font face** เป็น:
    *   **"CodeNewRoman Nerd Font"** (ถ้าเลือก CodeNewRoman)
    *   **"MesloLGS NF"** (ถ้าเลือก Meslo)

#### 4.2 ตั้งค่าใน VS Code
1.  ไปที่ Settings (`Ctrl` + `,`)
2.  ค้นหา `terminal.integrated.fontFamily`
3.  ใส่ชื่อฟอนต์ลงไปเป็นลำดับแรก:
    ```text
    'CodeNewRoman Nerd Font', Consolas, 'Courier New', monospace
    ```

---

### ขั้นตอนที่ 5: ตั้งค่า Profile และ Update PSReadLine
ทำเหมือนเดิมเพื่อให้โหลดทุกครั้ง:
1.  `notepad $PROFILE`
2.  ใส่ Script เรียกใช้งาน:
    ```powershell
    $env:Path += ";$env:LOCALAPPDATA\Programs\oh-my-posh\bin" # กรณี Manual Install
    $env:POSH_THEME = "$env:USERPROFILE\.poshthemes\vibrant-python.omp.json"
    oh-my-posh init powershell --config $env:POSH_THEME | Invoke-Expression
    
    Import-Module PSReadLine
    Set-PSReadLineOption -PredictionSource History
    Set-PSReadLineOption -PredictionViewStyle InlineView
    Set-PSReadLineKeyHandler -Key Tab -Function MenuComplete
    Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
    Set-PSReadLineKeyHandler -Key DownArrow -Function HistorySearchForward
    ```
3.  รัน `Install-Module PSReadLine -Force -Scope CurrentUser` ใน PowerShell

**เสร็จสิ้น! พร้อมใช้งาน 😎**
