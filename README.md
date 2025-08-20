# FX Widget (Thai Guide)

ไฟล์พร้อมใช้งาน:
- `exchange-widget.html` — วิดเจ็ตเรทค่าเงินแบบฝังด้วย iframe
- `index.html` — หน้าเดโม แสดงตัวอย่างการฝัง
- อัปโหลดทั้งสองไฟล์ขึ้นโฮสติ้งแบบ Static (ไม่มีเซิร์ฟเวอร์ก็ได้)

## วิธีใช้งานแบบเร็ว
1) อัปโหลดไฟล์ไปยังโฮสติ้ง เช่น Netlify / Vercel / Cloudflare Pages / GitHub Pages / โฮสติ้งที่มีแค่ `public_html` ก็ได้
2) ใช้ URL ของ `exchange-widget.html` ไปฝังในเว็บอื่นผ่าน `<iframe>`

ตัวอย่างการฝัง:
```html
<iframe
  src="https://yourdomain.com/exchange-widget.html?base=THB&symbols=USD,EUR,JPY,GBP,CNY&refresh=60&theme=light"
  width="380"
  height="360"
  style="border:1px solid #e5e7eb; border-radius:12px"
  loading="lazy"
></iframe>
```

## ปรับแต่งผ่านพารามิเตอร์
- `base` — สกุลเงินตั้งต้น เช่น `THB`, `USD`, `EUR`
- `symbols` — รายการสกุลเงินเป้าหมาย คั่นด้วยคอมมา เช่น `USD,EUR,JPY`
- `refresh` — วินาทีในการรีเฟรชข้อมูล (ขั้นต่ำ 10 วินาที) เช่น `30`
- `theme` — ธีม `light` หรือ `dark`

## แหล่งข้อมูล
วิดเจ็ตเรียกข้อมูลจาก `exchangerate.host` (อ้างอิง ECB) ซึ่งอัปเดตรายวัน หากต้องการแบบเรียลไทม์เป็นวินาที ให้เปลี่ยน URL ไปยังผู้ให้บริการที่รองรับ Real-time (มักต้องสมัคร API key) โดยโครงสร้างสคริปต์ยังใช้ต่อได้

## หมายเหตุ
- ตัววิดเจ็ตเป็นไฟล์ Static ธรรมดา จึงนำไปใช้กับบริการ Static Hosting ได้ทั้งหมด
- พื้นหลังโปร่งใส (transparent) เพื่อกลืนกับเว็บปลายทาง สามารถปรับสไตล์ใน `<style>` ได้
