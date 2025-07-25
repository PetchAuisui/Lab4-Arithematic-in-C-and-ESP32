# 1.เปลี่ยนจำนวนของเล่น
```c
// หาบรรทัดนี้ในโค้ด:
int toys_at_home = 8;      // ของเล่นที่บ้าน
int toys_give_away = 3;    // ของเล่นที่แจก

// ลองเปลี่ยนเป็น:
int toys_at_home = 15;     // เพิ่มเป็น 15 ชิ้น
int toys_give_away = 7;    // แจกไป 7 ชิ้น
```
## Result
```c
I (13265) TOYS_MATH: 🧮 ขั้นตอนการคิด:
I (13265) TOYS_MATH:    ของเล่นที่มี - ของเล่นที่แจก
I (13265) TOYS_MATH:    = 17 - 5
I (13265) TOYS_MATH:    = 12 ชิ้น
I (13265) TOYS_MATH: 
I (13265) TOYS_MATH: ✅ คำตอบ:
I (13265) TOYS_MATH:    น้องเหลือของเล่น 12 ชิ้น
I (13265) TOYS_MATH:
I (13265) TOYS_MATH: 🎨 ภาพประกอบ:
I (13265) TOYS_MATH:    ของเล่นเดิม: 🧸🚗🎲🧩🎮🧸🚁🎯🧸🚗🎲🧩🎮🧸🚁 (17 ชิ้น)
I (13265) TOYS_MATH:    แจกให้เพื่อน: 🧸🚗🎲🧩🎮 (5 ชิ้น)
I (13265) TOYS_MATH:    เหลืออยู่:   🧸🚗🎲🧩🎮🧸🚁🎯🧸🚗🎲🧩 (12 ชิ้น)
I (13265) TOYS_MATH: 
I (13265) TOYS_MATH: 💡 ตัวอย่างเพิ่มเติม:
I (13265) TOYS_MATH:    ถ้าน้องมีของเล่น 15 ชิ้น และแจกไป 7 ชิ้น
I (13265) TOYS_MATH:    จะเหลือ 15 - 7 = 8 ชิ้น
I (13265) TOYS_MATH:
I (13265) TOYS_MATH:    ถ้าน้องมีของเล่น 5 ชิ้น และแจกไปหมด 5 ชิ้น
I (13265) TOYS_MATH:    จะเหลือ 5 - 5 = 0 ชิ้น (ไม่เหลือเลย)
I (13265) TOYS_MATH:
I (13265) TOYS_MATH: 🔄 เปรียบเทียบกับการบวก:
I (13265) TOYS_MATH:    การบวก: เพิ่มจำนวน (เช่น ไข่ 4 + 2 = 6)
I (13265) TOYS_MATH:    การลบ: ลดจำนวน (เช่น ของเล่น 8 - 3 = 5)
I (13265) TOYS_MATH:    ข้อแตกต่าง: การลบต้องระวังไม่ให้ติดลบ!
I (13265) TOYS_MATH:
I (13265) TOYS_MATH: ⚠️  กรณีที่ต้องระวัง:
I (13265) TOYS_MATH:    ถ้าน้องมีของเล่น 3 ชิ้น แต่จะแจก 5 ชิ้น
I (13265) TOYS_MATH:    จะได้ 3 - 5 = -2 (ผลลัพธ์เป็นลบ!)
I (13265) TOYS_MATH:    ในชีวิตจริง: น้องไม่สามารถแจกของเล่นมากกว่าที่มีได้
I (13265) TOYS_MATH:
I (13275) TOYS_MATH: 📚 สิ่งที่เรียนรู้:
I (13275) TOYS_MATH:    1. การลบเลข (Subtraction): a - b = c
I (13275) TOYS_MATH:    2. การตรวจสอบเงื่อนไข (if statement)
I (13275) TOYS_MATH:    3. การจัดการกรณีพิเศษ (edge cases)
I (13275) TOYS_MATH:    4. ความแตกต่างระหว่างการบวกและการลบ
I (13275) TOYS_MATH:    5. การป้องกันผลลัพธ์ที่ไม่สมเหตุสมผล
I (13275) TOYS_MATH:
I (13275) TOYS_MATH: 🎉 จบโปรแกรมนับของเล่นของน้อง!
I (13275) TOYS_MATH: 📖 อ่านต่อในโปรเจคถัดไป: 03_multiplication_candies
I (15275) main_task: Returned from app_main()
```
<img width="1920" height="1032" alt="image" src="https://github.com/user-attachments/assets/9c9fdb77-2f2b-4ad8-9d13-db09a5fe4cda" />


# 2. เพิ่มการตรวจสอบ
เพิ่มการตรวจสอบว่าของเล่นพอแจกไหม:
```c
// เพิ่มหลังบรรทัด int toys_remaining;
if (toys_at_home >= toys_give_away) {
    ESP_LOGI(TAG, "✅ ของเล่นพอแจก");
} else {
    ESP_LOGI(TAG, "❌ ของเล่นไม่พอ! ขาดไป %d ชิ้น", 
             toys_give_away - toys_at_home);
}
```
## Result
```c
I (13664) TOYS_MATH: ✅ ของเล่นพอแจก
I (13664) TOYS_MATH: 🧮 ขั้นตอนการคิด:
I (13664) TOYS_MATH:    ของเล่นที่มี - ของเล่นที่แจก
I (13664) TOYS_MATH:    = 17 - 5
I (13664) TOYS_MATH:    = 12 ชิ้น
I (13664) TOYS_MATH:
I (13664) TOYS_MATH: ✅ คำตอบ:
I (13664) TOYS_MATH:    น้องเหลือของเล่น 12 ชิ้น
I (13664) TOYS_MATH: 
I (13664) TOYS_MATH: 🎨 ภาพประกอบ:
I (13664) TOYS_MATH:    ของเล่นเดิม: 🧸🚗🎲🧩🎮🧸🚁🎯🧸🚗🎲🧩🎮🧸🚁 (17 ชิ้น)
I (13664) TOYS_MATH:    แจกให้เพื่อน: 🧸🚗🎲🧩🎮 (5 ชิ้น)
I (13664) TOYS_MATH:    เหลืออยู่:   🧸🚗🎲🧩🎮🧸🚁🎯🧸🚗🎲🧩 (12 ชิ้น)
I (13664) TOYS_MATH: 
I (13664) TOYS_MATH: 💡 ตัวอย่างเพิ่มเติม:
I (13664) TOYS_MATH:    ถ้าน้องมีของเล่น 15 ชิ้น และแจกไป 7 ชิ้น
I (13664) TOYS_MATH:    จะเหลือ 15 - 7 = 8 ชิ้น
I (13664) TOYS_MATH: 
I (13664) TOYS_MATH:    ถ้าน้องมีของเล่น 5 ชิ้น และแจกไปหมด 5 ชิ้น
I (13664) TOYS_MATH:    จะเหลือ 5 - 5 = 0 ชิ้น (ไม่เหลือเลย)
I (13664) TOYS_MATH: 
I (13664) TOYS_MATH: 🔄 เปรียบเทียบกับการบวก:
I (13674) TOYS_MATH:    การบวก: เพิ่มจำนวน (เช่น ไข่ 4 + 2 = 6)
I (13674) TOYS_MATH:    การลบ: ลดจำนวน (เช่น ของเล่น 8 - 3 = 5)
I (13674) TOYS_MATH:    ข้อแตกต่าง: การลบต้องระวังไม่ให้ติดลบ!
I (13674) TOYS_MATH:
I (13674) TOYS_MATH: ⚠️  กรณีที่ต้องระวัง:
I (13674) TOYS_MATH:    ถ้าน้องมีของเล่น 3 ชิ้น แต่จะแจก 5 ชิ้น
I (13684) TOYS_MATH:    จะได้ 3 - 5 = -2 (ผลลัพธ์เป็นลบ!)
I (13684) TOYS_MATH:    ในชีวิตจริง: น้องไม่สามารถแจกของเล่นมากกว่าที่มีได้
I (13684) TOYS_MATH:
I (13684) TOYS_MATH: 📚 สิ่งที่เรียนรู้:
I (13684) TOYS_MATH:    1. การลบเลข (Subtraction): a - b = c
I (13684) TOYS_MATH:    2. การตรวจสอบเงื่อนไข (if statement)
I (13684) TOYS_MATH:    3. การจัดการกรณีพิเศษ (edge cases)
I (13684) TOYS_MATH:    4. ความแตกต่างระหว่างการบวกและการลบ
I (13684) TOYS_MATH:    5. การป้องกันผลลัพธ์ที่ไม่สมเหตุสมผล
I (13684) TOYS_MATH:
I (13684) TOYS_MATH: 🎉 จบโปรแกรมนับของเล่นของน้อง!
I (13684) TOYS_MATH: 📖 อ่านต่อในโปรเจคถัดไป: 03_multiplication_candies
I (15684) main_task: Returned from app_main()
```
<img width="1920" height="1032" alt="image" src="https://github.com/user-attachments/assets/2df49222-436a-4f40-8785-24461a06058f" />

# 3.เพิ่มของเล่นประเภทอื่น
เพิ่มตุ๊กตา และหุ่นยนต์:
```c
int dolls = 5;        // ตุ๊กตา
int robots = 2;       // หุ่นยนต์
int total_toys = toys_at_home + dolls + robots;

ESP_LOGI(TAG, "🪆 ตุ๊กตา: %d ตัว", dolls);
ESP_LOGI(TAG, "🤖 หุ่นยนต์: %d ตัว", robots);
ESP_LOGI(TAG, "🎯 ของเล่นทั้งหมด: %d ชิ้น", total_toys);
```
## Result
```c
I (13516) TOYS_MATH: 🧮 ขั้นตอนการคิด:
I (13516) TOYS_MATH:    ของเล่นที่มี - ของเล่นที่แจก
I (13516) TOYS_MATH:    = 17 - 5
I (13516) TOYS_MATH:    = 12 ชิ้น
I (13516) TOYS_MATH: 
I (13516) TOYS_MATH: ✅ คำตอบ:
I (13516) TOYS_MATH:    น้องเหลือของเล่น 12 ชิ้น
I (13516) TOYS_MATH:
I (13516) TOYS_MATH: 🎨 ภาพประกอบ:
I (13516) TOYS_MATH:    ของเล่นเดิม: 🧸🚗🎲🧩🎮🧸🚁🎯🧸🚗🎲🧩🎮🧸🚁 (17 ชิ้น)
I (13516) TOYS_MATH:    แจกให้เพื่อน: 🧸🚗🎲🧩🎮 (5 ชิ้น)
I (13516) TOYS_MATH:    เหลืออยู่:   🧸🚗🎲🧩🎮🧸🚁🎯🧸🚗🎲🧩 (12 ชิ้น)
I (13516) TOYS_MATH: 🪆 ตุ๊กตา: 5 ตัว
I (13516) TOYS_MATH: 🤖 หุ่นยนต์: 2 ตัว
I (13516) TOYS_MATH: 🎯 ของเล่นทั้งหมด: 24 ชิ้น
I (13516) TOYS_MATH:
I (13516) TOYS_MATH: 💡 ตัวอย่างเพิ่มเติม:
I (13516) TOYS_MATH:    ถ้าน้องมีของเล่น 15 ชิ้น และแจกไป 7 ชิ้น
I (13516) TOYS_MATH:    จะเหลือ 15 - 7 = 8 ชิ้น
I (13516) TOYS_MATH:
I (13516) TOYS_MATH:    ถ้าน้องมีของเล่น 5 ชิ้น และแจกไปหมด 5 ชิ้น
I (13516) TOYS_MATH:    จะเหลือ 5 - 5 = 0 ชิ้น (ไม่เหลือเลย)
I (13516) TOYS_MATH:
I (13516) TOYS_MATH: 🔄 เปรียบเทียบกับการบวก:
I (13516) TOYS_MATH:    การบวก: เพิ่มจำนวน (เช่น ไข่ 4 + 2 = 6)
I (13516) TOYS_MATH:    การลบ: ลดจำนวน (เช่น ของเล่น 8 - 3 = 5)
I (13516) TOYS_MATH:    ข้อแตกต่าง: การลบต้องระวังไม่ให้ติดลบ!
I (13516) TOYS_MATH:
I (13526) TOYS_MATH: ⚠️  กรณีที่ต้องระวัง:
I (13526) TOYS_MATH:    ถ้าน้องมีของเล่น 3 ชิ้น แต่จะแจก 5 ชิ้น
I (13526) TOYS_MATH:    จะได้ 3 - 5 = -2 (ผลลัพธ์เป็นลบ!)
I (13526) TOYS_MATH:    ในชีวิตจริง: น้องไม่สามารถแจกของเล่นมากกว่าที่มีได้
I (13526) TOYS_MATH:
I (13526) TOYS_MATH: 📚 สิ่งที่เรียนรู้:
I (13526) TOYS_MATH:    1. การลบเลข (Subtraction): a - b = c
I (13526) TOYS_MATH:    2. การตรวจสอบเงื่อนไข (if statement)
I (13526) TOYS_MATH:    3. การจัดการกรณีพิเศษ (edge cases)
I (13526) TOYS_MATH:    4. ความแตกต่างระหว่างการบวกและการลบ
I (13526) TOYS_MATH:    5. การป้องกันผลลัพธ์ที่ไม่สมเหตุสมผล
I (13526) TOYS_MATH:
I (13526) TOYS_MATH: 🎉 จบโปรแกรมนับของเล่นของน้อง!
I (13526) TOYS_MATH: 📖 อ่านต่อในโปรเจคถัดไป: 03_multiplication_candies
I (15526) main_task: Returned from app_main()
```
<img width="1920" height="1032" alt="image" src="https://github.com/user-attachments/assets/f53e1158-adbd-46f3-ad27-806eb9bf039b" />

# 4.คำถามให้คิด
### - หากน้องอยากแจกของเล่นให้เพื่อน 10 คน คนละ 2 ชิ้น:
- ต้องมีของเล่นกี่ชิ้น?
- ถ้ามี 15 ชิ้น จะขาดกี่ชิ้น?
