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
I (15583) CANDIES_MATH: 🧮 ขั้นตอนการคิด:
I (15583) CANDIES_MATH:    จำนวนถุง × ลูกอมต่อถุง
I (15583) CANDIES_MATH:    = 5 × 6
I (15583) CANDIES_MATH:    = 30 เม็ด
I (15583) CANDIES_MATH: 
I (15583) CANDIES_MATH: ✅ คำตอบ:
I (15583) CANDIES_MATH:    มีลูกอมทั้งหมด 30 เม็ด
I (15583) CANDIES_MATH: 
I (15583) CANDIES_MATH: 🎨 ภาพประกอบ:
I (15583) CANDIES_MATH:    ถุงที่ 1: 🍬🍬🍬🍬🍬🍬 (6 เม็ด)
I (15583) CANDIES_MATH:    ถุงที่ 2: 🍬🍬🍬🍬🍬🍬 (6 เม็ด)
I (15583) CANDIES_MATH:    ถุงที่ 3: 🍬🍬🍬🍬🍬🍬 (6 เม็ด)
I (15583) CANDIES_MATH:    ถุงที่ 4: 🍬🍬🍬🍬🍬🍬 (6 เม็ด)
I (15583) CANDIES_MATH:    ถุงที่ 5: 🍬🍬🍬🍬🍬🍬 (6 เม็ด)
I (15583) CANDIES_MATH:    รวม:     30 เม็ด
I (15583) CANDIES_MATH:
I (15583) CANDIES_MATH: 🔄 เปรียบเทียบกับการบวกซ้ำๆ:
I (15583) CANDIES_MATH:    การคูณ: 5 × 6 = 30
I (15583) CANDIES_MATH:    การบวกซ้ำๆ: 
I (15583) CANDIES_MATH:                   6
I (15583) CANDIES_MATH:                 + 6
I (15583) CANDIES_MATH:                 + 6
I (15583) CANDIES_MATH:                 + 6
I (15583) CANDIES_MATH:                 + 6 = 30
I (15583) CANDIES_MATH:    ผลลัพธ์เหมือนกัน! การคูณคือการบวกซ้ำๆ
I (15583) CANDIES_MATH: 
I (15583) CANDIES_MATH: 📊 ตารางสูตรคูณ 6:
I (15583) CANDIES_MATH:    1 × 6 = 6
I (15883) CANDIES_MATH:    2 × 6 = 12
I (16183) CANDIES_MATH:    3 × 6 = 18
I (16483) CANDIES_MATH:    4 × 6 = 24
I (16783) CANDIES_MATH:    5 × 6 = 30
I (17083) CANDIES_MATH:    6 × 6 = 36
I (17383) CANDIES_MATH:    7 × 6 = 42
I (17683) CANDIES_MATH:    8 × 6 = 48
I (17983) CANDIES_MATH:    9 × 6 = 54
I (18283) CANDIES_MATH:    10 × 6 = 60
I (18583) CANDIES_MATH: 
I (18583) CANDIES_MATH: 💡 ตัวอย่างเพิ่มเติม:
I (18583) CANDIES_MATH:    ถ้ามีถุงลูกอม 3 ถุง ถุงละ 8 เม็ด
I (18583) CANDIES_MATH:    จะได้ลูกอม 3 × 8 = 24 เม็ด
I (18583) CANDIES_MATH:
I (18583) CANDIES_MATH:    ถ้ามีถุงลูกอม 7 ถุง ถุงละ 4 เม็ด
I (18583) CANDIES_MATH:    จะได้ลูกอม 7 × 4 = 28 เม็ด
I (18583) CANDIES_MATH: 
I (18583) CANDIES_MATH: 🔄 เปรียบเทียบการดำเนินการ:
I (18583) CANDIES_MATH:    การบวก (+): เพิ่มจำนวน (เช่น ไข่ 4 + 2 = 6)
I (18583) CANDIES_MATH:    การลบ (-): ลดจำนวน (เช่น ของเล่น 8 - 3 = 5)
I (18583) CANDIES_MATH:    การคูณ (×): บวกซ้ำๆ (เช่น ลูกอม 5 × 6 = 30)
I (18583) CANDIES_MATH:
I (18583) CANDIES_MATH: 🎓 แนวคิดขั้นสูง:
I (18583) CANDIES_MATH:    1. การคูณมีคุณสมบัติการสับเปลี่ยน:
I (18583) CANDIES_MATH:       5 × 6 = 6 × 5 = 30
I (18583) CANDIES_MATH:    2. การคูณด้วย 0 จะได้ 0 เสมอ:
I (18583) CANDIES_MATH:       5 × 0 = 0 (ไม่มีถุงลูกอม)
I (18583) CANDIES_MATH:    3. การคูณด้วย 1 จะได้ตัวเลขเดิม:
I (18583) CANDIES_MATH:       6 × 1 = 6 (มีถุงเดียว)
I (18583) CANDIES_MATH:
I (18583) CANDIES_MATH: 📚 สิ่งที่เรียนรู้:
I (18583) CANDIES_MATH:    1. การคูณเลข (Multiplication): a × b = c
I (18593) CANDIES_MATH:    2. การใช้ for loop สำหรับการทำซ้ำ
I (18593) CANDIES_MATH:    3. ความสัมพันธ์ระหว่างการคูณและการบวกซ้ำๆ
I (18593) CANDIES_MATH:    4. คุณสมบัติพิเศษของการคูณ
I (18593) CANDIES_MATH:    5. การแสดงผลแบบตาราง
I (18593) CANDIES_MATH:
I (18593) CANDIES_MATH: 🎉 จบโปรแกรมนับลูกอมในถุง!
I (18593) CANDIES_MATH: 📖 อ่านต่อในโปรเจคถัดไป: 04_division_cookies
I (20593) main_task: Returned from app_main()
```
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/1becaa46-1e66-4cfc-97d3-1de72a7770da" />

