# 1 เปลี่ยนจำนวนถุงลูกอม
```c
// หาบรรทัดนี้ในโค้ด:
int candy_bags = 5;         // จำนวนถุง
int candies_per_bag = 6;    // ลูกอมต่อถุง

// ลองเปลี่ยนเป็น:
int candy_bags = 7;         // เพิ่มเป็น 7 ถุง
int candies_per_bag = 8;    // ลูกอมถุงละ 8 เม็ด
```
### Result
```c
I (15767) CANDIES_MATH: 🧮 ขั้นตอนการคิด:
I (15767) CANDIES_MATH:    จำนวนถุง × ลูกอมต่อถุง
I (15767) CANDIES_MATH:    = 7 × 8
I (15767) CANDIES_MATH:    = 56 เม็ด
I (15767) CANDIES_MATH: 
I (15767) CANDIES_MATH: ✅ คำตอบ:
I (15767) CANDIES_MATH:    มีลูกอมทั้งหมด 56 เม็ด
I (15767) CANDIES_MATH:
I (15767) CANDIES_MATH: 🎨 ภาพประกอบ:
I (15767) CANDIES_MATH:    ถุงที่ 1: 🍬🍬🍬🍬🍬🍬🍬🍬 (8 เม็ด)
I (15767) CANDIES_MATH:    ถุงที่ 2: 🍬🍬🍬🍬🍬🍬🍬🍬 (8 เม็ด)
I (15767) CANDIES_MATH:    ถุงที่ 3: 🍬🍬🍬🍬🍬🍬🍬🍬 (8 เม็ด)
I (15767) CANDIES_MATH:    ถุงที่ 4: 🍬🍬🍬🍬🍬🍬🍬🍬 (8 เม็ด)
I (15767) CANDIES_MATH:    ถุงที่ 5: 🍬🍬🍬🍬🍬🍬🍬🍬(8 เม็ด)
I (15767) CANDIES_MATH:    รวม:     56 เม็ด
I (15767) CANDIES_MATH: 
I (15767) CANDIES_MATH: 🔄 เปรียบเทียบกับการบวกซ้ำๆ:
I (15767) CANDIES_MATH:    การคูณ: 7 × 8 = 56
I (15767) CANDIES_MATH:    การบวกซ้ำๆ: 
I (15767) CANDIES_MATH:                   8
I (15767) CANDIES_MATH:                 + 8
I (15767) CANDIES_MATH:                 + 8
I (15767) CANDIES_MATH:                 + 8
I (15767) CANDIES_MATH:                 + 8
I (15767) CANDIES_MATH:                 + 8
I (15767) CANDIES_MATH:                 + 8 = 56
I (15777) CANDIES_MATH:    ผลลัพธ์เหมือนกัน! การคูณคือการบวกซ้ำๆ
I (15777) CANDIES_MATH:
I (15777) CANDIES_MATH: 📊 ตารางสูตรคูณ 8:
I (15777) CANDIES_MATH:    1 × 8 = 8
I (16077) CANDIES_MATH:    2 × 8 = 16
I (16377) CANDIES_MATH:    3 × 8 = 24
I (16677) CANDIES_MATH:    4 × 8 = 32
I (16977) CANDIES_MATH:    5 × 8 = 40
I (17277) CANDIES_MATH:    6 × 8 = 48
I (17577) CANDIES_MATH:    7 × 8 = 56
I (17877) CANDIES_MATH:    8 × 8 = 64
I (18177) CANDIES_MATH:    9 × 8 = 72
I (18477) CANDIES_MATH:    10 × 8 = 80
I (18777) CANDIES_MATH:
I (18777) CANDIES_MATH: 💡 ตัวอย่างเพิ่มเติม:
I (18777) CANDIES_MATH:    ถ้ามีถุงลูกอม 3 ถุง ถุงละ 8 เม็ด
I (18777) CANDIES_MATH:    จะได้ลูกอม 3 × 8 = 24 เม็ด
I (18777) CANDIES_MATH:
I (18777) CANDIES_MATH:    ถ้ามีถุงลูกอม 7 ถุง ถุงละ 4 เม็ด
I (18777) CANDIES_MATH:    จะได้ลูกอม 7 × 4 = 28 เม็ด
I (18777) CANDIES_MATH:
I (18777) CANDIES_MATH: 🔄 เปรียบเทียบการดำเนินการ:
I (18777) CANDIES_MATH:    การบวก (+): เพิ่มจำนวน (เช่น ไข่ 4 + 2 = 6)
I (18777) CANDIES_MATH:    การลบ (-): ลดจำนวน (เช่น ของเล่น 8 - 3 = 5)
I (18777) CANDIES_MATH:    การคูณ (×): บวกซ้ำๆ (เช่น ลูกอม 5 × 6 = 30)
I (18777) CANDIES_MATH:
I (18777) CANDIES_MATH: 🎓 แนวคิดขั้นสูง:
I (18777) CANDIES_MATH:    1. การคูณมีคุณสมบัติการสับเปลี่ยน:
I (18777) CANDIES_MATH:       7 × 8 = 8 × 7 = 56
I (18777) CANDIES_MATH:    2. การคูณด้วย 0 จะได้ 0 เสมอ:
I (18777) CANDIES_MATH:       7 × 0 = 0 (ไม่มีถุงลูกอม)
I (18777) CANDIES_MATH:    3. การคูณด้วย 1 จะได้ตัวเลขเดิม:
I (18777) CANDIES_MATH:       8 × 1 = 8 (มีถุงเดียว)
I (18777) CANDIES_MATH:
I (18777) CANDIES_MATH: 📚 สิ่งที่เรียนรู้:
I (18777) CANDIES_MATH:    1. การคูณเลข (Multiplication): a × b = c
I (18777) CANDIES_MATH:    2. การใช้ for loop สำหรับการทำซ้ำ
I (18777) CANDIES_MATH:    3. ความสัมพันธ์ระหว่างการคูณและการบวกซ้ำๆ
I (18777) CANDIES_MATH:    4. คุณสมบัติพิเศษของการคูณ
I (18777) CANDIES_MATH:    5. การแสดงผลแบบตาราง
I (18777) CANDIES_MATH:
I (18777) CANDIES_MATH: 🎉 จบโปรแกรมนับลูกอมในถุง!
I (18777) CANDIES_MATH: 📖 อ่านต่อในโปรเจคถัดไป: 04_division_cookies
I (20787) main_task: Returned from app_main()
```
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/040b5d32-dd67-413c-9172-fbc03984d94d" />


