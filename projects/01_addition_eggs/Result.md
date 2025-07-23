# 1. เปลี่ยนจำนวนไข่ได้
```c
// หาบรรทัดนี้ในโค้ด:
int eggs_already_have = 4;    // ไข่ไก่ที่แม่มีอยู่แล้ว
int eggs_new_today = 2;       // ไข่ไก่ที่ไก่ออกวันนี้

// ลองเปลี่ยนเป็น:
int eggs_already_have = 8;    // เพิ่มเป็น 8 ฟอง
int eggs_new_today = 3;       // เพิ่มเป็น 3 ฟอง
```
## Result
```c
I (15128) EGGS_MATH: 🧮 ขั้นตอนการคิด:
I (15128) EGGS_MATH:    ไข่ไก่ที่มีอยู่ + ไข่ไก่ที่ออกใหม่
I (15128) EGGS_MATH:    = 8 + 3
I (15128) EGGS_MATH:    = 11 ฟอง
I (15128) EGGS_MATH: 
I (15128) EGGS_MATH: ✅ คำตอบ:
I (15128) EGGS_MATH:    วันนี้แม่มีไข่ไก่ทั้งหมด 11 ฟอง
I (15128) EGGS_MATH:
I (15128) EGGS_MATH: 🎨 ภาพประกอบ:
I (15128) EGGS_MATH:    ไข่เดิม: 🥚🥚🥚🥚🥚🥚🥚🥚 (8 ฟอง)
I (15128) EGGS_MATH:    ไข่ใหม่: 🥚🥚🥚 (3 ฟอง)
I (15128) EGGS_MATH:    รวม:   🥚🥚🥚🥚🥚🥚🥚🥚🥚🥚🥚 (11 ฟอง)
I (15128) EGGS_MATH: 
I (15128) EGGS_MATH: 💡 ตัวอย่างเพิ่มเติม:
I (15128) EGGS_MATH:    ถ้าแม่มีไข่ 7 ฟอง และไก่ออกไข่ 3 ฟอง
I (15128) EGGS_MATH:    จะได้ไข่ทั้งหมด 7 + 3 = 10 ฟอง
I (15128) EGGS_MATH: 
I (15128) EGGS_MATH:    ถ้าแม่มีไข่ 10 ฟอง และไก่ออกไข่ 5 ฟอง
I (15128) EGGS_MATH:    จะได้ไข่ทั้งหมด 10 + 5 = 15 ฟอง
I (15128) EGGS_MATH: 
I (15128) EGGS_MATH: 📚 สิ่งที่เรียนรู้:
I (15128) EGGS_MATH:    1. การบวกเลข (Addition): a + b = c
I (15128) EGGS_MATH:    2. การใช้ตัวแปร (Variables) เก็บค่า
I (15128) EGGS_MATH:    3. การแสดงผลด้วย ESP_LOGI
I (15128) EGGS_MATH:    4. การแก้โจทย์แบบมีขั้นตอน
I (15128) EGGS_MATH:
I (15128) EGGS_MATH: 🎉 จบโปรแกรมนับไข่ไก่ของแม่!
I (15128) EGGS_MATH: 📖 อ่านต่อในโปรเจคถัดไป: 02_subtraction_toys
I (17128) main_task: Returned from app_main()
```
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/f94e7b64-3779-4677-a6fd-8785d0ec7573" />


# 2. เพิ่มไข่เป็ดได้
เพิ่มโค้ดนี้หลังบรรทัด `int total_eggs;`:
```c
int duck_eggs = 3;            // ไข่เป็ดที่แม่มี
int total_all_eggs;           // ไข่ทั้งหมด (ไก่ + เป็ด)
```

แล้วเพิ่มการคำนวณหลังบรรทัด `total_eggs = eggs_already_have + eggs_new_today;`:
```c
total_all_eggs = total_eggs + duck_eggs;

// แสดงผลไข่เป็ด
ESP_LOGI(TAG, "🦆 และแม่มีไข่เป็ด: %d ฟอง", duck_eggs);
ESP_LOGI(TAG, "🥚 ไข่ทั้งหมด (ไก่+เป็ด): %d ฟอง", total_all_eggs);
```
## Result
```c
I (15128) EGGS_MATH: 🧮 ขั้นตอนการคิด:
I (15128) EGGS_MATH:    ไข่ไก่ที่มีอยู่ + ไข่ไก่ที่ออกใหม่
I (15128) EGGS_MATH:    = 8 + 3
I (15128) EGGS_MATH:    = 11 ฟอง
I (15128) EGGS_MATH: 
I (15128) EGGS_MATH: 🎨 ภาพประกอบ:
I (15128) EGGS_MATH:    ไข่เดิม: 🐔🥚🥚🥚🥚🥚🥚🥚🥚(8 ฟอง)
I (15128) EGGS_MATH:    ไข่ใหม่: 🐔🥚🥚🥚 (3 ฟอง)
I (15128) EGGS_MATH:    รวม:   🐔🥚🥚🥚🥚🥚🥚🥚🥚🥚🥚🥚 (11 ฟอง)
I (15128) EGGS_MATH:    ไข่เป็ด: 🦆🥚🥚🥚 (3 ฟอง)
I (15128) EGGS_MATH:    รวมทั้งหมด: 🥚🥚🥚🥚🥚🥚🥚🥚🥚🥚🥚🥚🥚🥚 (14 ฟอง)
I (15128) EGGS_MATH:
I (15128) EGGS_MATH: 💡 ตัวอย่างเพิ่มเติม:
I (15128) EGGS_MATH:    ถ้าแม่มีไข่ 7 ฟอง และไก่ออกไข่ 3 ฟอง
I (15128) EGGS_MATH:    จะได้ไข่ทั้งหมด 7 + 3 = 10 ฟอง
I (15128) EGGS_MATH: 
I (15128) EGGS_MATH:    ถ้าแม่มีไข่ 10 ฟอง และไก่ออกไข่ 5 ฟอง
I (15128) EGGS_MATH:    จะได้ไข่ทั้งหมด 10 + 5 = 15 ฟอง
I (15128) EGGS_MATH: 
I (15128) EGGS_MATH: 📚 สิ่งที่เรียนรู้:
I (15128) EGGS_MATH:    1. การบวกเลข (Addition): a + b = c
I (15128) EGGS_MATH:    2. การใช้ตัวแปร (Variables) เก็บค่า
I (15138) EGGS_MATH:    3. การแสดงผลด้วย ESP_LOGI
I (15138) EGGS_MATH:    4. การแก้โจทย์แบบมีขั้นตอน
I (15138) EGGS_MATH:
I (15138) EGGS_MATH: 🎉 จบโปรแกรมนับไข่ไก่ของแม่!
I (15138) EGGS_MATH: 📖 อ่านต่อในโปรเจคถัดไป: 02_subtraction_toys
I (17138) main_task: Returned from app_main()
```
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/fd031f1e-60cc-48f5-aa61-25f8ac7d805b" />

# 3. สร้างโจทย์ใหม่ได้
ลองเปลี่ยนเป็นโจทย์อื่น เช่น:
- 🍎 แอปเปิ้ลในตะกร้า
- 📚 หนังสือบนชั้น  
- 🚗 รถในลานจอด
- 🌟 ดาวในท้องฟ้า

## Result
### 🍎 แอปเปิ้ลในตะกร้า
```c
I (15125) APPLE_MATH: 🧮 ขั้นตอนการคิด:
I (15125) APPLE_MATH:    แอปเปิ้ลที่มีอยู่ + แอปเปิ้ลที่เก็บเพิ่ม
I (15125) APPLE_MATH:    = 3 + 5
I (15125) APPLE_MATH:    = 8 ผล
I (15125) APPLE_MATH: 
I (15125) APPLE_MATH: ✅ คำตอบ:
I (15125) APPLE_MATH:    ตอนนี้ในตะกร้ามีแอปเปิ้ลทั้งหมด 8 ผล
I (15125) APPLE_MATH:
I (15125) APPLE_MATH: 🎨 ภาพประกอบ:
I (15125) APPLE_MATH:    แอปเปิ้ลเดิม: 🍎🍎🍎 (3 ผล)
I (15125) APPLE_MATH:    แอปเปิ้ลใหม่: 🍎🍎🍎🍎🍎 (5 ผล)
I (15125) APPLE_MATH:    รวม: 🍎🍎🍎🍎🍎🍎🍎🍎 (8 ผล)
I (15125) APPLE_MATH:
I (15125) APPLE_MATH: 💡 ตัวอย่างเพิ่มเติม:
I (15125) APPLE_MATH:    ถ้ามีแอปเปิ้ล 7 ผล และเก็บเพิ่ม 3 ผล
I (15125) APPLE_MATH:    จะได้แอปเปิ้ลทั้งหมด 7 + 3 = 10 ผล
I (15125) APPLE_MATH:
I (15125) APPLE_MATH:    ถ้ามีแอปเปิ้ล 10 ผล และเก็บเพิ่ม 5 ผล
I (15125) APPLE_MATH:    จะได้แอปเปิ้ลทั้งหมด 10 + 5 = 15 ผล
I (15125) APPLE_MATH:
I (15125) APPLE_MATH: 📚 สิ่งที่เรียนรู้:
I (15125) APPLE_MATH:    1. การบวกเลข (Addition): a + b = c
I (15125) APPLE_MATH:    2. การใช้ตัวแปร (Variables) เก็บค่า
I (15125) APPLE_MATH:    3. การแสดงผลด้วย ESP_LOGI
I (15125) APPLE_MATH:    4. การแก้โจทย์แบบมีขั้นตอน
I (15125) APPLE_MATH:
I (15125) APPLE_MATH: 🎉 จบโปรแกรมนับแอปเปิ้ลในตะกร้า!
I (15125) APPLE_MATH: 📖 อ่านต่อในโปรเจคถัดไป: 02_subtraction_oranges
I (15125) main_task: Returned from app_main()
```
<img width="1920" height="1032" alt="image" src="https://github.com/user-attachments/assets/041ab2f9-e9b0-479c-a015-abbf07c622ca" />


### 📚 หนังสือบนชั้น
```c
  I (15605) APPLE_MATH: 🧮 ขั้นตอนการคิด:
I (15605) APPLE_MATH:    หนังสือเดิมที่มีอยู่ + หนังสือที่ซื้อมาใหม่
I (15605) APPLE_MATH:    = 3 + 5
I (15605) APPLE_MATH:    = 8 ผล
I (15605) APPLE_MATH: 
I (15605) APPLE_MATH: ✅ คำตอบ:
I (15605) APPLE_MATH:    ตอนนี้บนชั้นมีหนังสือ📚ทั้งหมด 8 เล่ม
I (15605) APPLE_MATH:
I (15605) APPLE_MATH: 🎨 ภาพประกอบ:
I (15605) APPLE_MATH:    บนชั้นมีหนังสือ: 📚📚📚 (3 ผล)
I (15605) APPLE_MATH:    ซื้อหนังสือมาเพิ่ม: 📚📚📚📚📚 (5 ผล)
I (15605) APPLE_MATH:    รวม: 📚📚📚📚📚📚📚📚 (8 ผล)
I (15605) APPLE_MATH:
I (15605) APPLE_MATH: 💡 ตัวอย่างเพิ่มเติม:
I (15605) APPLE_MATH:    ถ้ามีหนังสือ 7 เล่ม ซื้อเพิ่ม 3 เล่ม
I (15605) APPLE_MATH:    จะได้หนังสือทั้งหมด 7 + 3 = 10 เล่ม
I (15605) APPLE_MATH:
I (15605) APPLE_MATH:    ถ้ามีหนังสือ 10 เล่ม ซื้อเพิ่ม 5 เล่ม
I (15605) APPLE_MATH:    จะได้หนังสือทั้งหมด 10 + 5 = 15 เล่ม
I (15605) APPLE_MATH:
I (15605) APPLE_MATH: 📚 สิ่งที่เรียนรู้:
I (15605) APPLE_MATH:    1. การบวกเลข (Addition): a + b = c
I (15605) APPLE_MATH:    2. การใช้ตัวแปร (Variables) เก็บค่า
I (15605) APPLE_MATH:    3. การแสดงผลด้วย ESP_LOGI
I (15605) APPLE_MATH:    4. การแก้โจทย์แบบมีขั้นตอน
I (15605) APPLE_MATH: 
I (15605) APPLE_MATH: 🎉 จบโปรแกรมนับแอปเปิ้ลในตะกร้า!
I (15615) APPLE_MATH: 📖 อ่านต่อในโปรเจคถัดไป: 02_subtraction_oranges
I (15615) main_task: Returned from app_main()
```
<img width="1920" height="1032" alt="image" src="https://github.com/user-attachments/assets/172b7a2d-3657-42b3-8cc2-ade0f8c844c1" />

### 🚗 รถในลานจอด

