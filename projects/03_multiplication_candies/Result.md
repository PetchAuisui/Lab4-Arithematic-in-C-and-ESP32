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

# 2.เพิ่มลูกอมหลายรส
- เพิ่มลูกอมหลายรส:
```c
int strawberry_bags = 3;    // ถุงรสสตรอเบอร์รี่
int orange_bags = 2;        // ถุงรสส้ม
int grape_bags = 4;         // ถุงรสองุ่น

int total_bags = strawberry_bags + orange_bags + grape_bags;
int total_candies = total_bags * candies_per_bag;

ESP_LOGI(TAG, "🍓 สตรอเบอร์รี่: %d ถุง = %d เม็ด", 
         strawberry_bags, strawberry_bags * candies_per_bag);
ESP_LOGI(TAG, "🍊 รสส้ม: %d ถุง = %d เม็ด", 
         orange_bags, orange_bags * candies_per_bag);
ESP_LOGI(TAG, "🍇 รสองุ่น: %d ถุง = %d เม็ด", 
         grape_bags, grape_bags * candies_per_bag);
```
## Code
```c
#include <stdio.h>
#include "esp_log.h"
#include "freertos/FreeRTOS.h"
#include "freertos/task.h"

static const char *TAG = "CANDIES_MATH";

void app_main(void)
{
    ESP_LOGI(TAG, "🍬 เริ่มต้นโปรแกรมนับลูกอมในถุง 🍬");
    ESP_LOGI(TAG, "====================================");
    
    // ประกาศตัวแปรเก็บจำนวนลูกอม

    int candies_per_bag = 8;       // ลูกอมต่อถุง
    int strawberry_bags = 3;    // ถุงรสสตรอเบอร์รี่
    int orange_bags = 2;        // ถุงรสส้ม
    int grape_bags = 4;         // ถุงรสองุ่น


    // คำนวณผลรวม (การคูณ)
    int total_bags = strawberry_bags + orange_bags + grape_bags;
    int total_candies = total_bags * candies_per_bag;   


    // แสดงข้อมูลเริ่มต้น
    ESP_LOGI(TAG, "📖 โจทย์:");
    ESP_LOGI(TAG, "   มีถุงลูกอม: %d ถุง", total_bags);
    ESP_LOGI(TAG, "   ถุงละ: %d เม็ด", candies_per_bag);
    ESP_LOGI(TAG, "   ❓ มีลูกอมทั้งหมดกี่เม็ด?");
    ESP_LOGI(TAG, "");
    
    vTaskDelay(3000 / portTICK_PERIOD_MS);
    
    
    // แสดงขั้นตอนการคิด
    ESP_LOGI(TAG, "🧮 ขั้นตอนการคิด:");
    ESP_LOGI(TAG, "มีลูกอม🍓สตรอเบอร์รี่ %d ถุง แต่ละถุงมี %d เม็ด", strawberry_bags, candies_per_bag);
    ESP_LOGI(TAG, "จะมีลูกอม🍓สตรอเบอร์รี่ทั้งหมด %d × %d = %d เม็ด", strawberry_bags, candies_per_bag,strawberry_bags * candies_per_bag);

    ESP_LOGI(TAG, "มีลูกอม🍊ส้ม %d ถุง แต่ละถุงมี %d เม็ด", orange_bags, candies_per_bag);
    ESP_LOGI(TAG, "จะมีลูกอม🍊ส้มทั้งหมด %d × %d = %d เม็ด", orange_bags, candies_per_bag, orange_bags* candies_per_bag);

    ESP_LOGI(TAG, "มีลูกอม🍇องุ่น %d ถุง แต่ละถุงมี %d เม็ด", grape_bags, candies_per_bag);
    ESP_LOGI(TAG, "จะมีลูกอม🍇องุ่นทั้งหมด %d × %d = %d เม็ด", grape_bags, candies_per_bag, grape_bags* candies_per_bag);

    ESP_LOGI(TAG, "รวมลูกอม🍓🍊🍇ทั้งหมด %d + %d + %d = %d เม็ด", strawberry_bags * candies_per_bag, orange_bags* candies_per_bag, grape_bags* candies_per_bag, total_candies);

    
    // แสดงคำตอบ
    ESP_LOGI(TAG, "✅ คำตอบ:");
    ESP_LOGI(TAG, "   มีลูกอมทั้งหมด %d เม็ด", total_candies);
    ESP_LOGI(TAG, "");
    
    // แสดงภาพประกอบ
    ESP_LOGI(TAG, "🎨 ภาพประกอบ:");
    ESP_LOGI(TAG, "   ถุง🍓ที่ 1: 🍬🍬🍬🍬🍬🍬🍬🍬 (%d เม็ด)", candies_per_bag);
    ESP_LOGI(TAG, "   ถุง🍓ที่ 2: 🍬🍬🍬🍬🍬🍬🍬🍬 (%d เม็ด)", candies_per_bag);
    ESP_LOGI(TAG, "   ถุง🍓ที่ 3: 🍬🍬🍬🍬🍬🍬🍬🍬 (%d เม็ด)", candies_per_bag);
    ESP_LOGI(TAG, "   ถุง🍊ที่ 4: 🍬🍬🍬🍬🍬🍬🍬🍬 (%d เม็ด)", candies_per_bag);
    ESP_LOGI(TAG, "   ถุง🍊ที่ 5: 🍬🍬🍬🍬🍬🍬🍬🍬 (%d เม็ด)", candies_per_bag);
    ESP_LOGI(TAG, "   ถุง🍇ที่ 6: 🍬🍬🍬🍬🍬🍬🍬🍬 (%d เม็ด)", candies_per_bag);
    ESP_LOGI(TAG, "   ถุง🍇ที่ 7: 🍬🍬🍬🍬🍬🍬🍬🍬 (%d เม็ด)", candies_per_bag);
    ESP_LOGI(TAG, "   ถุง🍇ที่ 7: 🍬🍬🍬🍬🍬🍬🍬🍬 (%d เม็ด)", candies_per_bag);
    ESP_LOGI(TAG, "   ถุง🍇ที่ 7: 🍬🍬🍬🍬🍬🍬🍬🍬 (%d เม็ด)", candies_per_bag);
    ESP_LOGI(TAG, "   รวม:     %d เม็ด", total_candies);
    ESP_LOGI(TAG, "");
    
    
    // ตัวอย่างเพิ่มเติม
    ESP_LOGI(TAG, "💡 ตัวอย่างเพิ่มเติม:");
    
    // ตัวอย่างที่ 1
    int ex1_bags = 3;
    int ex1_candies = 8;
    int ex1_total = ex1_bags * ex1_candies;
    ESP_LOGI(TAG, "   ถ้ามีถุงลูกอม %d ถุง ถุงละ %d เม็ด", ex1_bags, ex1_candies);
    ESP_LOGI(TAG, "   จะได้ลูกอม %d × %d = %d เม็ด", ex1_bags, ex1_candies, ex1_total);
    ESP_LOGI(TAG, "");
    
    // ตัวอย่างที่ 2
    int ex2_bags = 7;
    int ex2_candies = 4;
    int ex2_total = ex2_bags * ex2_candies;
    ESP_LOGI(TAG, "   ถ้ามีถุงลูกอม %d ถุง ถุงละ %d เม็ด", ex2_bags, ex2_candies);
    ESP_LOGI(TAG, "   จะได้ลูกอม %d × %d = %d เม็ด", ex2_bags, ex2_candies, ex2_total);
    ESP_LOGI(TAG, "");
    
    // เปรียบเทียบกับการดำเนินการก่อนหน้า
    ESP_LOGI(TAG, "🔄 เปรียบเทียบการดำเนินการ:");
    ESP_LOGI(TAG, "   การบวก (+): เพิ่มจำนวน (เช่น ไข่ 4 + 2 = 6)");
    ESP_LOGI(TAG, "   การลบ (-): ลดจำนวน (เช่น ของเล่น 8 - 3 = 5)");
    ESP_LOGI(TAG, "   การคูณ (×): บวกซ้ำๆ (เช่น ลูกอม 5 × 6 = 30)");
    ESP_LOGI(TAG, "");
    
    // แนวคิดขั้นสูง
    ESP_LOGI(TAG, "🎓 แนวคิดขั้นสูง:");
    ESP_LOGI(TAG, "   1. การคูณมีคุณสมบัติการสับเปลี่ยน:");
    ESP_LOGI(TAG, "      %d × %d = %d × %d = %d", 
             total_bags, candies_per_bag, candies_per_bag, total_bags,total_candies);
    ESP_LOGI(TAG, "   2. การคูณด้วย 0 จะได้ 0 เสมอ:");
    ESP_LOGI(TAG, "      %d × 0 = 0 (ไม่มีถุงลูกอม)",total_bags);
    ESP_LOGI(TAG, "   3. การคูณด้วย 1 จะได้ตัวเลขเดิม:");
    ESP_LOGI(TAG, "      %d × 1 = %d (มีถุงเดียว)", candies_per_bag, candies_per_bag);
    ESP_LOGI(TAG, "");
    
    // สรุปการเรียนรู้
    ESP_LOGI(TAG, "📚 สิ่งที่เรียนรู้:");
    ESP_LOGI(TAG, "   1. การคูณเลข (Multiplication): a × b = c");
    ESP_LOGI(TAG, "   2. การใช้ for loop สำหรับการทำซ้ำ");
    ESP_LOGI(TAG, "   3. ความสัมพันธ์ระหว่างการคูณและการบวกซ้ำๆ");
    ESP_LOGI(TAG, "   4. คุณสมบัติพิเศษของการคูณ");
    ESP_LOGI(TAG, "   5. การแสดงผลแบบตาราง");
    ESP_LOGI(TAG, "");
    
    ESP_LOGI(TAG, "🎉 จบโปรแกรมนับลูกอมในถุง!");
    ESP_LOGI(TAG, "📖 อ่านต่อในโปรเจคถัดไป: 04_division_cookies");
    
    vTaskDelay(2000 / portTICK_PERIOD_MS);
}
```
## Result
```c
I (16082) CANDIES_MATH: 🧮 ขั้นตอนการคิด:
I (16082) CANDIES_MATH: มีลูกอม🍓สตรอเบอร์รี่ 3 ถุง แต่ละถุงมี 8 เม็ด
I (16082) CANDIES_MATH: จะมีลูกอม🍓สตรอเบอร์รี่ทั้งหมด 3 × 8 = 24 เม็ด
I (16082) CANDIES_MATH: มีลูกอม🍊ส้ม 2 ถุง แต่ละถุงมี 8 เม็ด
I (16082) CANDIES_MATH: จะมีลูกอม🍊ส้มทั้งหมด 2 × 8 = 16 เม็ด
I (16082) CANDIES_MATH: มีลูกอม🍇องุ่น 4 ถุง แต่ละถุงมี 8 เม็ด
I (16082) CANDIES_MATH: จะมีลูกอม🍇องุ่นทั้งหมด 4 × 8 = 32 เม็ด
I (16082) CANDIES_MATH: รวมลูกอม🍓🍊🍇ทั้งหมด 24 + 16 + 32 = 72 เม็ด
I (16082) CANDIES_MATH: ✅ คำตอบ:
I (16082) CANDIES_MATH:    มีลูกอมทั้งหมด 72 เม็ด
I (16082) CANDIES_MATH: 
I (16082) CANDIES_MATH: 🎨 ภาพประกอบ:
I (16082) CANDIES_MATH:    ถุง🍓ที่ 1: 🍬🍬🍬🍬🍬🍬🍬🍬 (8 เม็ด)
I (16082) CANDIES_MATH:    ถุง🍓ที่ 2: 🍬🍬🍬🍬🍬🍬🍬🍬 (8 เม็ด)
I (16082) CANDIES_MATH:    ถุง🍓ที่ 3: 🍬🍬🍬🍬🍬🍬🍬🍬 (8 เม็ด)
I (16082) CANDIES_MATH:    ถุง🍊ที่ 4: 🍬🍬🍬🍬🍬🍬🍬🍬 (8 เม็ด)
I (16082) CANDIES_MATH:    ถุง🍊ที่ 5: 🍬🍬🍬🍬🍬🍬🍬🍬 (8 เม็ด)
I (16082) CANDIES_MATH:    ถุง🍇ที่ 6: 🍬🍬🍬🍬🍬🍬🍬🍬 (8 เม็ด)
I (16082) CANDIES_MATH:    ถุง🍇ที่ 7: 🍬🍬🍬🍬🍬🍬🍬🍬 (8 เม็ด)
I (16082) CANDIES_MATH:    ถุง🍇ที่ 7: 🍬🍬🍬🍬🍬🍬🍬🍬 (8 เม็ด)
I (16082) CANDIES_MATH:    ถุง🍇ที่ 7: 🍬🍬🍬🍬🍬🍬🍬🍬 (8 เม็ด)
I (16082) CANDIES_MATH:    รวม:     72 เม็ด
I (16092) CANDIES_MATH:
I (16092) CANDIES_MATH: 💡 ตัวอย่างเพิ่มเติม:
I (16092) CANDIES_MATH:    ถ้ามีถุงลูกอม 3 ถุง ถุงละ 8 เม็ด
I (16092) CANDIES_MATH:    จะได้ลูกอม 3 × 8 = 24 เม็ด
I (16092) CANDIES_MATH:
I (16092) CANDIES_MATH:    ถ้ามีถุงลูกอม 7 ถุง ถุงละ 4 เม็ด
I (16092) CANDIES_MATH:    จะได้ลูกอม 7 × 4 = 28 เม็ด
I (16092) CANDIES_MATH: 
I (16092) CANDIES_MATH: 🔄 เปรียบเทียบการดำเนินการ:
I (16092) CANDIES_MATH:    การบวก (+): เพิ่มจำนวน (เช่น ไข่ 4 + 2 = 6)
I (16092) CANDIES_MATH:    การลบ (-): ลดจำนวน (เช่น ของเล่น 8 - 3 = 5)
I (16092) CANDIES_MATH:    การคูณ (×): บวกซ้ำๆ (เช่น ลูกอม 5 × 6 = 30)
I (16092) CANDIES_MATH:
I (16092) CANDIES_MATH: 🎓 แนวคิดขั้นสูง:
I (16092) CANDIES_MATH:    1. การคูณมีคุณสมบัติการสับเปลี่ยน:
I (16092) CANDIES_MATH:       9 × 8 = 8 × 9 = 72
I (16092) CANDIES_MATH:    2. การคูณด้วย 0 จะได้ 0 เสมอ:
I (16092) CANDIES_MATH:       9 × 0 = 0 (ไม่มีถุงลูกอม)
I (16092) CANDIES_MATH:    3. การคูณด้วย 1 จะได้ตัวเลขเดิม:
I (16092) CANDIES_MATH:       8 × 1 = 8 (มีถุงเดียว)
I (16092) CANDIES_MATH: 
I (16092) CANDIES_MATH: 📚 สิ่งที่เรียนรู้:
I (16092) CANDIES_MATH:    1. การคูณเลข (Multiplication): a × b = c
I (16092) CANDIES_MATH:    2. การใช้ for loop สำหรับการทำซ้ำ
I (16092) CANDIES_MATH:    3. ความสัมพันธ์ระหว่างการคูณและการบวกซ้ำๆ
I (16092) CANDIES_MATH:    4. คุณสมบัติพิเศษของการคูณ
I (16092) CANDIES_MATH:    5. การแสดงผลแบบตาราง
I (16092) CANDIES_MATH:
I (16102) CANDIES_MATH: 🎉 จบโปรแกรมนับลูกอมในถุง!
I (16102) CANDIES_MATH: 📖 อ่านต่อในโปรเจคถัดไป: 04_division_cookies
I (18102) main_task: Returned from app_main()
```

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/0d5f5c79-6a2f-47e9-ab25-9cd162e22220" />

