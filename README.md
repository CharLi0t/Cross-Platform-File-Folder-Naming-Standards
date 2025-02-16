# Cross-Platform-File-Folder-Naming-Standards

The "Cross-Platform File & Folder Naming Standards" is a naming convention designed to ensure compatibility across all major operating systems, including Windows, Linux, macOS, and Cloud Storage. It helps avoid common issues caused by platform-specific limitations, such as restricted characters, maximum filename length, case sensitivity differences, and reserved system names.

This guideline enhances file management efficiency, reduces cross-platform compatibility issues, and ensures that files can be shared, transferred, or synced across different systems without errors.

# แนวทางการตั้งชื่อไฟล์ที่รองรับทั้ง Windows และ Linux

## 1. หลีกเลี่ยงตัวอักษรต้องห้าม
- **Windows** และ **Linux** มีข้อกำหนดที่แตกต่างกัน แต่ถ้าต้องการให้ใช้งานได้ทั้งสองระบบ ให้หลีกเลี่ยงตัวอักษรเหล่านี้:
  - **ห้ามใช้:** `\ / : * ? " < > |` (Windows)
  - **ควรหลีกเลี่ยง:** `; & # $ \` ' ( ) { } [ ] !` (Linux และบาง shell อาจใช้เป็นคำสั่ง)

## 2. ห้ามใช้ชื่อสงวนของ Windows
- Windows มีชื่อที่ไม่สามารถใช้ได้เพราะสงวนไว้สำหรับอุปกรณ์ระบบ เช่น:
  - `CON, PRN, AUX, NUL`
  - `COM1 - COM9`
  - `LPT1 - LPT9`
- **ทางเลือกที่ดี:** ใช้ชื่อที่ไม่ตรงกับชื่อสงวน เช่น `config_file.txt` แทน `CON.txt`

## 3. หลีกเลี่ยงช่องว่าง (Space)
- ช่องว่าง (` `) อาจทำให้เกิดปัญหาใน Linux shell และ command-line tools ต้องใช้ `\` หรือ `"` ครอบเมื่อต้องพิมพ์ชื่อไฟล์
- **แนะนำให้ใช้ขีดกลาง (`-`) หรือขีดล่าง (`_`) แทน**
  - ❌ `My File.txt`
  - ✅ `My_File.txt`
  - ✅ `My-File.txt`

## 4. หลีกเลี่ยงชื่อที่เป็นตัวพิมพ์ใหญ่ทั้งหมด
- Linux แยกแยะตัวพิมพ์ใหญ่-เล็ก (`FILE.TXT` ≠ `file.txt`) แต่ Windows ไม่แยกแยะ
- **แนวทางที่ดี:**
  - ใช้ตัวพิมพ์เล็กทั้งหมด: `project_report.pdf`
  - ใช้ CamelCase หรือ Snake_Case: `ProjectReport.pdf`, `project_report.pdf`

## 5. หลีกเลี่ยงชื่อไฟล์ลงท้ายด้วยจุด (.)
- Windows ไม่อนุญาตให้ชื่อไฟล์ลงท้ายด้วยจุด (.) แต่ Linux อนุญาต
- **แก้ไขโดยการไม่ใส่จุดที่ท้ายชื่อไฟล์**
  - ❌ `myfile.`
  - ✅ `myfile.txt`

## 6. จำกัดความยาวของชื่อไฟล์
- Windows จำกัด 255 ตัวอักษร
- Linux รองรับ 4096 ตัวอักษร
- **แนะนำให้ใช้ชื่อไม่เกิน 100-150 ตัวอักษร เพื่อให้สามารถโอนย้ายได้สะดวก**

## 7. ใช้รูปแบบนามสกุลไฟล์ให้ถูกต้อง
- บาง OS อาจไม่รองรับไฟล์ที่ไม่มีนามสกุล (extension) เช่น Windows อาศัยนามสกุลไฟล์เพื่อระบุประเภทของไฟล์
- **ใช้รูปแบบมาตรฐาน เช่น:**
  - `document.pdf`
  - `data.csv`
  - `script.sh`
  - `config.json`

## 8. หลีกเลี่ยงการใช้ตัวเลขเป็นชื่อไฟล์หลัก
- การตั้งชื่อไฟล์เป็นตัวเลขอย่างเดียว เช่น `1234.txt` อาจทำให้เกิดปัญหากับบางโปรแกรม
- **แนะนำให้เพิ่มคำอธิบายหรือ prefix**
  - ❌ `1234.txt`
  - ✅ `report_1234.txt`

## 9. หลีกเลี่ยงการใช้ชื่อไฟล์ซ้ำ
- Linux อนุญาตให้มีไฟล์ชื่อเดียวกันแต่ตัวพิมพ์ต่างกัน เช่น `file.txt` และ `File.txt` แต่ Windows ไม่รองรับ
- **แนะนำให้ใช้ชื่อที่ไม่ซ้ำและเป็นมาตรฐาน**
  - ❌ `report.txt` และ `Report.txt` (Windows ไม่รองรับ)
  - ✅ `report_2024.txt` และ `summary_2024.txt`

## 10. หลีกเลี่ยงการใช้สัญลักษณ์ที่มีความหมายพิเศษใน Linux
- Linux ใช้สัญลักษณ์บางอย่างใน command-line เช่น:
  - `& (and), ; (command separator), * (wildcard), ? (wildcard), $ (variable), \` (command substitution)`
- **ใช้ขีดกลางหรือขีดล่างแทน**
  - ❌ `data&analysis.txt`
  - ✅ `data_analysis.txt`

# แนวทางการตั้งชื่อไฟล์ที่เหมาะสม (Best Practices)
- **ใช้รูปแบบที่อ่านง่าย (Readable Format)**
- **ใช้ตัวพิมพ์เล็กหรือ CamelCase**
- **ใช้ขีดล่าง (`_`) หรือขีดกลาง (`-`) แทนเว้นวรรค**
- **ใช้คำอธิบายสั้น ๆ แต่ชัดเจน**

## ตัวอย่างชื่อไฟล์ที่ดี:
- `project_report_2024.pdf`
- `backup_2024-02-16.zip`
- `config_settings.json`
- `invoice_#12345.pdf` (แต่ควรเลี่ยง `#` ในบางกรณี)
- `UserDataExport-2024.csv`

## ตัวอย่างชื่อไฟล์ที่ไม่ดี:
- `My File Name.txt` (มีช่องว่าง อาจใช้ไม่ได้บน Linux)
- `Report:2024.pdf` (มี `:` ใช้ไม่ได้บน Windows)
- `Backup/2024.zip` (มี `/` ใช้ไม่ได้บน Windows)
- `CON.txt` (Windows ไม่รองรับ)

# สรุปแนวทางตั้งชื่อไฟล์ที่รองรับทั้ง Windows และ Linux
- **ใช้ตัวอักษร A-Z, a-z, 0-9**
- **ใช้ ขีดกลาง (`-`) หรือ ขีดล่าง (`_`) แทนช่องว่าง**
- **ห้ามใช้ตัวอักษรพิเศษ `\ / : * ? " < > | & # $ ' ( )`**
- **ใช้ชื่อไฟล์สั้น กระชับ และสื่อความหมาย**
- **ใช้ตัวพิมพ์เล็กทั้งหมด หรือ CamelCase เพื่อป้องกันความสับสน**
- **จำกัดความยาวของชื่อไฟล์ไม่เกิน 100-150 ตัวอักษร**
- **ใช้ นามสกุลไฟล์ (extension) ให้ถูกต้อง เช่น `.txt`, `.csv`, `.json`, `.sh`**
