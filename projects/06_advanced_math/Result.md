# 1.คำนวณพื้นที่สามเหลี่ยม
## Code
```c
#include <stdio.h>
#include <math.h>
#include "esp_log.h"
#include "freertos/FreeRTOS.h"
#include "freertos/task.h"

// 🏷️ Tag สำหรับ Log
static const char *TAG = "ADVANCED_MATH";

// 🔢 ค่าคงที่ทางคณิตศาสตร์
#define PI 3.14159265359
#define SQUARE_METERS_TO_RAI 1600.0  // 1 ไร่ = 1,600 ตร.ม.

// 📐 โครงสร้างข้อมูลรูปทรง
typedef struct {
    char name[50];
    double length;      // ความยาว/รัศมี
    double width;       // ความกว้าง
    double height;      // ความสูง/ความลึก
} shape_t;

// 🏟️ ฟังก์ชันคำนวณสี่เหลี่ยม
void calculate_rectangle(shape_t shape) {
    double area = shape.length * shape.width;
    double perimeter = 2 * (shape.length + shape.width);
    double area_in_rai = area / SQUARE_METERS_TO_RAI;
    
    ESP_LOGI(TAG, "╔══════════════════════════════════════╗");
    ESP_LOGI(TAG, "║          %s           ║", shape.name);
    ESP_LOGI(TAG, "╠══════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 📏 ความยาว: %.2f เมตร", shape.length);
    ESP_LOGI(TAG, "║ 📏 ความกว้าง: %.2f เมตร", shape.width);
    ESP_LOGI(TAG, "║ 📐 พื้นที่: %.2f × %.2f = %.2f ตร.ม.", 
             shape.length, shape.width, area);
    ESP_LOGI(TAG, "║ 🔄 ปริเมตร: 2×(%.0f+%.0f) = %.2f ม.", 
             shape.length, shape.width, perimeter);
    ESP_LOGI(TAG, "║ 🌾 เท่ากับ: %.4f ไร่", area_in_rai);
    ESP_LOGI(TAG, "╚══════════════════════════════════════╝");
}

// 🏊‍♀️ ฟังก์ชันคำนวณวงกลม
void calculate_circle(shape_t shape) {
    double radius = shape.length;  // ใช้ length เป็น radius
    double surface_area = PI * radius * radius;
    double circumference = 2 * PI * radius;
    double volume = surface_area * shape.height;  // ปริมาตรทรงกระบอก
    
    ESP_LOGI(TAG, "╔══════════════════════════════════════╗");
    ESP_LOGI(TAG, "║          %s            ║", shape.name);
    ESP_LOGI(TAG, "╠══════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 📏 รัศมี: %.2f เมตร", radius);
    ESP_LOGI(TAG, "║ 📏 ความลึก: %.2f เมตร", shape.height);
    ESP_LOGI(TAG, "║ 🌊 พื้นที่ผิวน้ำ: π × %.0f² = %.2f ตร.ม.", 
             radius, surface_area);
    ESP_LOGI(TAG, "║ ⭕ เส้นรอบวง: 2π × %.0f = %.2f ม.", 
             radius, circumference);
    ESP_LOGI(TAG, "║ 💧 ปริมาตรน้ำ: %.2f × %.2f = %.2f ลบ.ม.", 
             surface_area, shape.height, volume);
    ESP_LOGI(TAG, "╚══════════════════════════════════════╝");
}

// 🎁 ฟังก์ชันคำนวณทรงผีเสื้อ
void calculate_box(shape_t shape) {
    double volume = shape.length * shape.width * shape.height;
    double surface_area = 2 * (shape.length * shape.width + 
                               shape.width * shape.height + 
                               shape.length * shape.height);
    
    ESP_LOGI(TAG, "╔══════════════════════════════════════╗");
    ESP_LOGI(TAG, "║          %s          ║", shape.name);
    ESP_LOGI(TAG, "╠══════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 📏 ความยาว: %.2f ซม.", shape.length);
    ESP_LOGI(TAG, "║ 📏 ความกว้าง: %.2f ซม.", shape.width);
    ESP_LOGI(TAG, "║ 📏 ความสูง: %.2f ซม.", shape.height);
    ESP_LOGI(TAG, "║ 📦 ปริมาตร: %.0f×%.0f×%.0f = %.2f ลบ.ซม.", 
             shape.length, shape.width, shape.height, volume);
    ESP_LOGI(TAG, "║ 🎀 พื้นที่ผิว: %.2f ตร.ซม.", surface_area);
    ESP_LOGI(TAG, "║ 📐 เท่ากับ: %.6f ลิตร", volume / 1000.0);
    ESP_LOGI(TAG, "╚══════════════════════════════════════╝");
}

// 📊 ฟังก์ชันเปรียบเทียบผลลัพธ์
void compare_results(void) {
    ESP_LOGI(TAG, "\n🔍 การเปรียบเทียบผลลัพธ์:");
    ESP_LOGI(TAG, "╔════════════════════════════════════╗");
    ESP_LOGI(TAG, "║  สนามฟุตบอล vs สระน้ำ vs กล่อง    ║");
    ESP_LOGI(TAG, "╠════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 🏟️ สนาม: ใหญ่ที่สุด (6,000 ตร.ม.)  ║");
    ESP_LOGI(TAG, "║ 🏊‍♀️ สระ: กลาง (78.54 ตร.ม.)       ║");
    ESP_LOGI(TAG, "║ 🎁 กล่อง: เล็กที่สุด (300 ลบ.ซม.)  ║");
    ESP_LOGI(TAG, "╚════════════════════════════════════╝");
}

// 🎓 ฟังก์ชันแสดงความรู้เพิ่มเติม
void show_math_facts(void) {
    ESP_LOGI(TAG, "\n📚 ความรู้ทางคณิตศาสตร์:");
    ESP_LOGI(TAG, "╔═══════════════════════════════════════╗");
    ESP_LOGI(TAG, "║           สูตรคณิตศาสตร์             ║");
    ESP_LOGI(TAG, "╠═══════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 📐 สี่เหลี่ยม: พื้นที่ = ยาว × กว้าง   ║");
    ESP_LOGI(TAG, "║ ⭕ วงกลม: พื้นที่ = π × r²           ║");
    ESP_LOGI(TAG, "║ 📦 ทรงผีเสื้อ: ปริมาตร = ย×ก×ส       ║");
    ESP_LOGI(TAG, "║ 💡 π (pi) ≈ 3.14159                  ║");
    ESP_LOGI(TAG, "║ 🌾 1 ไร่ = 1,600 ตารางเมตร          ║");
    ESP_LOGI(TAG, "╚═══════════════════════════════════════╝");
}

// 🎯 ฟังก์ชันท้าทาย - คำนวณสามเหลี่ยม
void calculate_triangle_bonus(void) {
    double base = 10.0;     // ฐาน
    double height = 8.0;    // สูง
    double side1 = 10.0;    // ด้านที่ 1
    double side2 = 8.0;     // ด้านที่ 2
    double side3 = 6.0;     // ด้านที่ 3
    
    double area = 0.5 * base * height;
    double perimeter = side1 + side2 + side3;
    
    ESP_LOGI(TAG, "\n🎯 โบนัส: สามเหลี่ยม");
    ESP_LOGI(TAG, "╔═══════════════════════════════════════╗");
    ESP_LOGI(TAG, "║         สามเหลี่ยม                   ║");
    ESP_LOGI(TAG, "╠═══════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 📏 ฐาน: %.2f ซม.", base);
    ESP_LOGI(TAG, "║ 📏 สูง: %.2f ซม.", height);
    ESP_LOGI(TAG, "║ 📐 พื้นที่: ½×%.0f×%.0f = %.2f ตร.ซม.", 
             base, height, area);
    ESP_LOGI(TAG, "║ 🔄 ปริเมตร: %.0f+%.0f+%.0f = %.2f ซม.", 
             side1, side2, side3, perimeter);
    ESP_LOGI(TAG, "╚═══════════════════════════════════════╝");
}

void app_main(void) {
    ESP_LOGI(TAG, "🚀 เริ่มต้นโปรแกรมคณิตศาสตร์ขั้นสูง!");
    ESP_LOGI(TAG, "📐 การคำนวณพื้นที่และปริมาตร\n");
    
    // รอสักครู่เพื่อให้ระบบเริ่มต้นเสร็จสิ้น
    vTaskDelay(pdMS_TO_TICKS(1000));
    
    // 🏟️ สนามฟุตบอล
    shape_t football_field = {
        .name = "สนามฟุตบอล",
        .length = 100.0,
        .width = 60.0,
        .height = 0.0
    };
    
    // 🏊‍♀️ สระน้ำกลม
    shape_t swimming_pool = {
        .name = "สระน้ำกลม",
        .length = 5.0,    // รัศมี
        .width = 0.0,
        .height = 2.0     // ความลึก
    };
    
    // 🎁 กล่องของขวัญ
    shape_t gift_box = {
        .name = "กล่องของขวัญ",
        .length = 20.0,
        .width = 15.0,
        .height = 10.0
    };
    
    // 🎨 ASCII Art
    ESP_LOGI(TAG, "   🏟️     🏊‍♀️     🎁");
    ESP_LOGI(TAG, " ┌─────┐  ╭─────╮  ┌─────┐");
    ESP_LOGI(TAG, " │ ⚽  │  │ 💧💧 │  │ 🎀  │");
    ESP_LOGI(TAG, " │     │  │     │  │     │");
    ESP_LOGI(TAG, " └─────┘  ╰─────╯  └─────┘\n");
    
    // คำนวณแต่ละรูปทรง
    calculate_rectangle(football_field);
    vTaskDelay(pdMS_TO_TICKS(2000));
    
    calculate_circle(swimming_pool);
    vTaskDelay(pdMS_TO_TICKS(2000));
    
    calculate_box(gift_box);
    vTaskDelay(pdMS_TO_TICKS(2000));
    
    // เปรียบเทียบผลลัพธ์
    compare_results();
    vTaskDelay(pdMS_TO_TICKS(2000));
    
    // แสดงความรู้เพิ่มเติม
    show_math_facts();
    vTaskDelay(pdMS_TO_TICKS(2000));
    
    // โบนัสท้าทาย
    calculate_triangle_bonus();
    
    ESP_LOGI(TAG, "\n✅ เสร็จสิ้นการคำนวณทั้งหมด!");
    ESP_LOGI(TAG, "🎓 ได้เรียนรู้: คณิตศาสตร์ขั้นสูง, struct, #define, และฟังก์ชันคณิตศาสตร์");
}

```
## Result
```c
I (13628) ADVANCED_MATH: ╔══════════════════════════════════════╗
I (13628) ADVANCED_MATH: ║          สระน้ำกลม            ║
I (13628) ADVANCED_MATH: ╠══════════════════════════════════════╣
I (13628) ADVANCED_MATH: ║ 📏 รัศมี: 5.00 เมตร
I (13628) ADVANCED_MATH: ║ 📏 ความลึก: 2.00 เมตร
I (13628) ADVANCED_MATH: ║ 🌊 พื้นที่ผิวน้ำ: π × 5² = 78.54 ตร.ม.
I (13628) ADVANCED_MATH: ║ ⭕ เส้นรอบวง: 2π × 5 = 31.42 ม.
I (13628) ADVANCED_MATH: ║ 💧 ปริมาตรน้ำ: 78.54 × 2.00 = 157.08 ลบ.ม.
I (13628) ADVANCED_MATH: ╚══════════════════════════════════════╝
I (15628) ADVANCED_MATH: ╔══════════════════════════════════════╗
I (15628) ADVANCED_MATH: ║          กล่องของขวัญ          ║
I (15628) ADVANCED_MATH: ╠══════════════════════════════════════╣
I (15628) ADVANCED_MATH: ║ 📏 ความยาว: 20.00 ซม.
I (15628) ADVANCED_MATH: ║ 📏 ความกว้าง: 15.00 ซม.
I (15628) ADVANCED_MATH: ║ 📏 ความสูง: 10.00 ซม.
I (15628) ADVANCED_MATH: ║ 📦 ปริมาตร: 20×15×10 = 3000.00 ลบ.ซม.
I (15628) ADVANCED_MATH: ║ 🎀 พื้นที่ผิว: 1300.00 ตร.ซม.
I (15628) ADVANCED_MATH: ║ 📐 เท่ากับ: 3.000000 ลิตร
I (15628) ADVANCED_MATH: ╚══════════════════════════════════════╝
I (17628) ADVANCED_MATH: 
🔍 การเปรียบเทียบผลลัพธ์:
I (17628) ADVANCED_MATH: ╔════════════════════════════════════╗
I (17628) ADVANCED_MATH: ║  สนามฟุตบอล vs สระน้ำ vs กล่อง    ║
I (17628) ADVANCED_MATH: ╠════════════════════════════════════╣
I (17628) ADVANCED_MATH: ║ 🏟️ สนาม: ใหญ่ที่สุด (6,000 ตร.ม.)  ║
I (17628) ADVANCED_MATH: ║ 🏊‍♀️ สระ: กลาง (78.54 ตร.ม.)       ║
I (17628) ADVANCED_MATH: ║ 🎁 กล่อง: เล็กที่สุด (300 ลบ.ซม.)  ║
I (17628) ADVANCED_MATH: ╚════════════════════════════════════╝
I (19628) ADVANCED_MATH: 
📚 ความรู้ทางคณิตศาสตร์:
I (19628) ADVANCED_MATH: ╔═══════════════════════════════════════╗
I (19628) ADVANCED_MATH: ║           สูตรคณิตศาสตร์             ║
I (19628) ADVANCED_MATH: ╠═══════════════════════════════════════╣
I (19628) ADVANCED_MATH: ║ 📐 สี่เหลี่ยม: พื้นที่ = ยาว × กว้าง   ║
I (19628) ADVANCED_MATH: ║ ⭕ วงกลม: พื้นที่ = π × r²           ║
I (19628) ADVANCED_MATH: ║ 📦 ทรงผีเสื้อ: ปริมาตร = ย×ก×ส       ║
I (19628) ADVANCED_MATH: ║ 💡 π (pi) ≈ 3.14159                  ║
I (19628) ADVANCED_MATH: ║ 🌾 1 ไร่ = 1,600 ตารางเมตร          ║
I (19628) ADVANCED_MATH: ╚═══════════════════════════════════════╝
I (21628) ADVANCED_MATH: 
🎯 โบนัส: สามเหลี่ยม
I (21628) ADVANCED_MATH: ╔═══════════════════════════════════════╗
I (21628) ADVANCED_MATH: ║         สามเหลี่ยม                   ║
I (21628) ADVANCED_MATH: ╠═══════════════════════════════════════╣
I (21628) ADVANCED_MATH: ║ 📏 ฐาน: 10.00 ซม.
I (21628) ADVANCED_MATH: ║ 📏 สูง: 8.00 ซม.
I (21628) ADVANCED_MATH: ║ 📐 พื้นที่: ½×10×8 = 40.00 ตร.ซม.
I (21628) ADVANCED_MATH: ║ 🔄 ปริเมตร: 10+8+6 = 24.00 ซม.
I (21628) ADVANCED_MATH: ╚═══════════════════════════════════════╝
I (21628) ADVANCED_MATH:
✅ เสร็จสิ้นการคำนวณทั้งหมด!
I (21628) ADVANCED_MATH: 🎓 ได้เรียนรู้: คณิตศาสตร์ขั้นสูง, struct, #define, และฟังก์ชันคณิตศาสตร์
I (21628) main_task: Returned from app_main()
```

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/fbd56e08-8420-4d61-8c0b-7da11cd92348" />

# 2.คำนวณปริมาตรทรงกรวย
## Code
```c
#include <stdio.h>
#include <math.h>
#include "esp_log.h"
#include "freertos/FreeRTOS.h"
#include "freertos/task.h"

// 🔖 TAG สำหรับ Log
static const char *TAG = "MATH_PROGRAM";

// 📏 ค่าคงที่
#define PI 3.14159265359
#define SQUARE_METERS_PER_RAI 1600.0

// 🧱 โครงสร้างข้อมูลรูปทรง
typedef struct {
    char name[50];
    double length;
    double width;
    double height;
} shape_t;

// 🔷 คำนวณพื้นที่สี่เหลี่ยม
void calculate_rectangle(shape_t shape) {
    double area = shape.length * shape.width;
    double perimeter = 2 * (shape.length + shape.width);
    double area_in_rai = area / SQUARE_METERS_PER_RAI;

    ESP_LOGI(TAG, "\n📦 สี่เหลี่ยม");
    ESP_LOGI(TAG, "╔════════════════════════════════════╗");
    ESP_LOGI(TAG, "║ 🔷 %s", shape.name);
    ESP_LOGI(TAG, "╠════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 📏 ยาว: %.2f ม.", shape.length);
    ESP_LOGI(TAG, "║ 📏 กว้าง: %.2f ม.", shape.width);
    ESP_LOGI(TAG, "║ 📐 พื้นที่: %.2f ตร.ม.", area);
    ESP_LOGI(TAG, "║ 🔄 ปริเมตร: %.2f ม.", perimeter);
    ESP_LOGI(TAG, "║ 🌾 เท่ากับ: %.4f ไร่", area_in_rai);
    ESP_LOGI(TAG, "╚════════════════════════════════════╝");
}

// ⭕ คำนวณวงกลม
void calculate_circle(shape_t shape) {
    double r = shape.length;
    double area = PI * r * r;
    double circumference = 2 * PI * r;
    double volume = area * shape.height;

    ESP_LOGI(TAG, "\n⭕ วงกลม");
    ESP_LOGI(TAG, "╔════════════════════════════════════╗");
    ESP_LOGI(TAG, "║ 🔷 %s", shape.name);
    ESP_LOGI(TAG, "╠════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 📏 รัศมี: %.2f ม.", r);
    ESP_LOGI(TAG, "║ 📏 ลึก: %.2f ม.", shape.height);
    ESP_LOGI(TAG, "║ 📐 พื้นที่: %.2f ตร.ม.", area);
    ESP_LOGI(TAG, "║ ⭕ เส้นรอบวง: %.2f ม.", circumference);
    ESP_LOGI(TAG, "║ 💧 ปริมาตร: %.2f ลบ.ม.", volume);
    ESP_LOGI(TAG, "╚════════════════════════════════════╝");
}

// 📦 คำนวณกล่อง
void calculate_box(shape_t shape) {
    double volume = shape.length * shape.width * shape.height;
    double surface_area = 2 * (shape.length * shape.width +
                               shape.width * shape.height +
                               shape.length * shape.height);

    ESP_LOGI(TAG, "\n📦 กล่อง");
    ESP_LOGI(TAG, "╔════════════════════════════════════╗");
    ESP_LOGI(TAG, "║ 🔷 %s", shape.name);
    ESP_LOGI(TAG, "╠════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 📏 ยาว: %.2f ซม.", shape.length);
    ESP_LOGI(TAG, "║ 📏 กว้าง: %.2f ซม.", shape.width);
    ESP_LOGI(TAG, "║ 📏 สูง: %.2f ซม.", shape.height);
    ESP_LOGI(TAG, "║ 🎁 ปริมาตร: %.2f ลบ.ซม.", volume);
    ESP_LOGI(TAG, "║ 📐 พื้นที่ผิว: %.2f ตร.ซม.", surface_area);
    ESP_LOGI(TAG, "║ 💧 เท่ากับ: %.3f ลิตร", volume / 1000.0);
    ESP_LOGI(TAG, "╚════════════════════════════════════╝");
}

// 🔺 คำนวณพื้นที่สามเหลี่ยม
void calculate_triangle(void) {
    double base = 10.0;
    double height = 8.0;
    double area = 0.5 * base * height;

    ESP_LOGI(TAG, "\n🔺 สามเหลี่ยม");
    ESP_LOGI(TAG, "╔════════════════════════════════════╗");
    ESP_LOGI(TAG, "║ 📏 ฐาน: %.2f ซม.", base);
    ESP_LOGI(TAG, "║ 📏 สูง: %.2f ซม.", height);
    ESP_LOGI(TAG, "║ 📐 พื้นที่: %.2f ตร.ซม.", area);
    ESP_LOGI(TAG, "╚════════════════════════════════════╝");
}


// 🍦 คำนวณปริมาตรทรงกรวย
void calculate_cone(void) {
    double radius = 7.0;
    double height = 12.0;
    double base_area = PI * radius * radius;
    double volume = (1.0 / 3.0) * base_area * height;

    ESP_LOGI(TAG, "\n🍦 ทรงกรวย");
    ESP_LOGI(TAG, "╔══════════════════════════════════════╗");
    ESP_LOGI(TAG, "║           ทรงกรวย                 ║");
    ESP_LOGI(TAG, "╠══════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 📏 รัศมี: %.2f ซม.", radius);
    ESP_LOGI(TAG, "║ 📏 ความสูง: %.2f ซม.", height);
    ESP_LOGI(TAG, "║ 📐 พื้นที่ฐาน: π×%.0f² = %.2f ตร.ซม.",
             radius, base_area);
    ESP_LOGI(TAG, "║ 🔺 ปริมาตร: ⅓×%.2f×%.2f = %.2f ลบ.ซม.",
             base_area, height, volume);
    ESP_LOGI(TAG, "║ 💧 เท่ากับ: %.3f ลิตร", volume / 1000.0);
    ESP_LOGI(TAG, "╚══════════════════════════════════════╝");
}


// 🚀 จุดเริ่มต้นโปรแกรม
void app_main(void) {
    ESP_LOGI(TAG, "🚀 เริ่มต้นโปรแกรมคณิตศาสตร์\n");

    shape_t field = {"สนามฟุตบอล", 100.0, 60.0, 0.0};
    shape_t pool = {"สระน้ำกลม", 5.0, 0.0, 2.0};
    shape_t box = {"กล่องของขวัญ", 20.0, 15.0, 10.0};

    vTaskDelay(pdMS_TO_TICKS(500));

    calculate_rectangle(field);
    vTaskDelay(pdMS_TO_TICKS(1000));

    calculate_circle(pool);
    vTaskDelay(pdMS_TO_TICKS(1000));

    calculate_box(box);
    vTaskDelay(pdMS_TO_TICKS(1000));

    calculate_triangle();
    vTaskDelay(pdMS_TO_TICKS(1000));

    calculate_cone();
    vTaskDelay(pdMS_TO_TICKS(1000));




    ESP_LOGI(TAG, "\n✅ เสร็จสิ้นการคำนวณทั้งหมด!");
}
```
## Result
```c
I (12356) MATH_PROGRAM: 
⭕ วงกลม
I (12356) MATH_PROGRAM: ╔════════════════════════════════════╗
I (12356) MATH_PROGRAM: ║ 🔷 สระน้ำกลม
I (12356) MATH_PROGRAM: ╠════════════════════════════════════╣
I (12356) MATH_PROGRAM: ║ 📏 รัศมี: 5.00 ม.
I (12356) MATH_PROGRAM: ║ 📏 ลึก: 2.00 ม.
I (12356) MATH_PROGRAM: ║ 📐 พื้นที่: 78.54 ตร.ม.
I (12356) MATH_PROGRAM: ║ ⭕ เส้นรอบวง: 31.42 ม.
I (12356) MATH_PROGRAM: ║ 💧 ปริมาตร: 157.08 ลบ.ม.
I (12356) MATH_PROGRAM: ╚════════════════════════════════════╝
I (13356) MATH_PROGRAM: 
📦 กล่อง
I (13356) MATH_PROGRAM: ╔════════════════════════════════════╗
I (13356) MATH_PROGRAM: ║ 🔷 กล่องของขวัญ
I (13356) MATH_PROGRAM: ╠════════════════════════════════════╣
I (13356) MATH_PROGRAM: ║ 📏 ยาว: 20.00 ซม.
I (13356) MATH_PROGRAM: ║ 📏 กว้าง: 15.00 ซม.
I (13356) MATH_PROGRAM: ║ 📏 สูง: 10.00 ซม.
I (13356) MATH_PROGRAM: ║ 🎁 ปริมาตร: 3000.00 ลบ.ซม.
I (13356) MATH_PROGRAM: ║ 📐 พื้นที่ผิว: 1300.00 ตร.ซม.
I (13356) MATH_PROGRAM: ║ 💧 เท่ากับ: 3.000 ลิตร
I (13356) MATH_PROGRAM: ╚════════════════════════════════════╝
I (14356) MATH_PROGRAM: 
🔺 สามเหลี่ยม
I (14356) MATH_PROGRAM: ╔════════════════════════════════════╗
I (14356) MATH_PROGRAM: ║ 📏 ฐาน: 10.00 ซม.
I (14356) MATH_PROGRAM: ║ 📏 สูง: 8.00 ซม.
I (14356) MATH_PROGRAM: ║ 📐 พื้นที่: 40.00 ตร.ซม.
I (14356) MATH_PROGRAM: ╚════════════════════════════════════╝
I (15356) MATH_PROGRAM: 
🍦 ทรงกรวย
I (15356) MATH_PROGRAM: ╔══════════════════════════════════════╗
I (15356) MATH_PROGRAM: ║           ทรงกรวย                 ║
I (15356) MATH_PROGRAM: ╠══════════════════════════════════════╣
I (15356) MATH_PROGRAM: ║ 📏 รัศมี: 7.00 ซม.
I (15356) MATH_PROGRAM: ║ 📏 ความสูง: 12.00 ซม.
I (15356) MATH_PROGRAM: ║ 📐 พื้นที่ฐาน: π×7² = 153.94 ตร.ซม.
I (15356) MATH_PROGRAM: ║ 🔺 ปริมาตร: ⅓×153.94×12.00 = 615.75 ลบ.ซม.
I (15356) MATH_PROGRAM: ║ 💧 เท่ากับ: 0.616 ลิตร
I (15356) MATH_PROGRAM: ╚══════════════════════════════════════╝
I (16356) MATH_PROGRAM: 
✅ เสร็จสิ้นการคำนวณทั้งหมด!
I (16356) main_task: Returned from app_main()
```
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/33661a30-de1a-4557-9245-2c623d68880c" />

# 3.แปลงหน่วย (เมตร → ตารางเมตร → ไร่)
## Code
```c
#include <stdio.h>
#include <math.h>
#include "esp_log.h"
#include "freertos/FreeRTOS.h"
#include "freertos/task.h"

// 🔖 TAG สำหรับ Log
static const char *TAG = "MATH_PROGRAM";

// 📏 ค่าคงที่
#define PI 3.14159265359
#define SQUARE_METERS_PER_RAI 1600.0

// 🧱 โครงสร้างข้อมูลรูปทรง
typedef struct {
    char name[50];
    double length;
    double width;
    double height;
} shape_t;

// 🔷 คำนวณพื้นที่สี่เหลี่ยม
void calculate_rectangle(shape_t shape) {
    double area = shape.length * shape.width;
    double perimeter = 2 * (shape.length + shape.width);
    double area_in_rai = area / SQUARE_METERS_PER_RAI;

    ESP_LOGI(TAG, "\n📦 สี่เหลี่ยม");
    ESP_LOGI(TAG, "╔════════════════════════════════════╗");
    ESP_LOGI(TAG, "║ 🔷 %s", shape.name);
    ESP_LOGI(TAG, "╠════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 📏 ยาว: %.2f ม.", shape.length);
    ESP_LOGI(TAG, "║ 📏 กว้าง: %.2f ม.", shape.width);
    ESP_LOGI(TAG, "║ 📐 พื้นที่: %.2f ตร.ม.", area);
    ESP_LOGI(TAG, "║ 🔄 ปริเมตร: %.2f ม.", perimeter);
    ESP_LOGI(TAG, "║ 🌾 เท่ากับ: %.4f ไร่", area_in_rai);
    ESP_LOGI(TAG, "╚════════════════════════════════════╝");
}

// ⭕ คำนวณวงกลม
void calculate_circle(shape_t shape) {
    double r = shape.length;
    double area = PI * r * r;
    double circumference = 2 * PI * r;
    double volume = area * shape.height;

    ESP_LOGI(TAG, "\n⭕ วงกลม");
    ESP_LOGI(TAG, "╔════════════════════════════════════╗");
    ESP_LOGI(TAG, "║ 🔷 %s", shape.name);
    ESP_LOGI(TAG, "╠════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 📏 รัศมี: %.2f ม.", r);
    ESP_LOGI(TAG, "║ 📏 ลึก: %.2f ม.", shape.height);
    ESP_LOGI(TAG, "║ 📐 พื้นที่: %.2f ตร.ม.", area);
    ESP_LOGI(TAG, "║ ⭕ เส้นรอบวง: %.2f ม.", circumference);
    ESP_LOGI(TAG, "║ 💧 ปริมาตร: %.2f ลบ.ม.", volume);
    ESP_LOGI(TAG, "╚════════════════════════════════════╝");
}

// 📦 คำนวณกล่อง
void calculate_box(shape_t shape) {
    double volume = shape.length * shape.width * shape.height;
    double surface_area = 2 * (shape.length * shape.width +
                               shape.width * shape.height +
                               shape.length * shape.height);

    ESP_LOGI(TAG, "\n📦 กล่อง");
    ESP_LOGI(TAG, "╔════════════════════════════════════╗");
    ESP_LOGI(TAG, "║ 🔷 %s", shape.name);
    ESP_LOGI(TAG, "╠════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 📏 ยาว: %.2f ซม.", shape.length);
    ESP_LOGI(TAG, "║ 📏 กว้าง: %.2f ซม.", shape.width);
    ESP_LOGI(TAG, "║ 📏 สูง: %.2f ซม.", shape.height);
    ESP_LOGI(TAG, "║ 🎁 ปริมาตร: %.2f ลบ.ซม.", volume);
    ESP_LOGI(TAG, "║ 📐 พื้นที่ผิว: %.2f ตร.ซม.", surface_area);
    ESP_LOGI(TAG, "║ 💧 เท่ากับ: %.3f ลิตร", volume / 1000.0);
    ESP_LOGI(TAG, "╚════════════════════════════════════╝");
}

// 🔺 คำนวณพื้นที่สามเหลี่ยม
void calculate_triangle(void) {
    double base = 10.0;
    double height = 8.0;
    double area = 0.5 * base * height;

    ESP_LOGI(TAG, "\n🔺 สามเหลี่ยม");
    ESP_LOGI(TAG, "╔════════════════════════════════════╗");
    ESP_LOGI(TAG, "║ 📏 ฐาน: %.2f ซม.", base);
    ESP_LOGI(TAG, "║ 📏 สูง: %.2f ซม.", height);
    ESP_LOGI(TAG, "║ 📐 พื้นที่: %.2f ตร.ซม.", area);
    ESP_LOGI(TAG, "╚════════════════════════════════════╝");
}


// 🍦 คำนวณปริมาตรทรงกรวย
void calculate_cone(void) {
    double radius = 7.0;
    double height = 12.0;
    double base_area = PI * radius * radius;
    double volume = (1.0 / 3.0) * base_area * height;

    ESP_LOGI(TAG, "\n🍦 ทรงกรวย");
    ESP_LOGI(TAG, "╔══════════════════════════════════════╗");
    ESP_LOGI(TAG, "║           ทรงกรวย                 ║");
    ESP_LOGI(TAG, "╠══════════════════════════════════════╣");
    ESP_LOGI(TAG, "║ 📏 รัศมี: %.2f ซม.", radius);
    ESP_LOGI(TAG, "║ 📏 ความสูง: %.2f ซม.", height);
    ESP_LOGI(TAG, "║ 📐 พื้นที่ฐาน: π×%.0f² = %.2f ตร.ซม.",
             radius, base_area);
    ESP_LOGI(TAG, "║ 🔺 ปริมาตร: ⅓×%.2f×%.2f = %.2f ลบ.ซม.",
             base_area, height, volume);
    ESP_LOGI(TAG, "║ 💧 เท่ากับ: %.3f ลิตร", volume / 1000.0);
    ESP_LOGI(TAG, "╚══════════════════════════════════════╝");
}

// 🌾 แปลงหน่วย เมตร → ตร.ม. → ไร่
void convert_area_units(void) {
    double length = 100.0;
    double width = 50.0;
    double area_m2 = length * width;
    double area_rai = area_m2 / SQUARE_METERS_PER_RAI;

    ESP_LOGI(TAG, "\n🌾 การแปลงหน่วยพื้นที่");
    ESP_LOGI(TAG, "╔════════════════════════════════════╗");
    ESP_LOGI(TAG, "║ 📏 ยาว: %.2f ม.", length);
    ESP_LOGI(TAG, "║ 📏 กว้าง: %.2f ม.", width);
    ESP_LOGI(TAG, "║ 📐 พื้นที่: %.2f ตร.ม.", area_m2);
    ESP_LOGI(TAG, "║ 🌾 เท่ากับ: %.4f ไร่", area_rai);
    ESP_LOGI(TAG, "╚════════════════════════════════════╝");
}

// 🚀 จุดเริ่มต้นโปรแกรม
void app_main(void) {
    ESP_LOGI(TAG, "🚀 เริ่มต้นโปรแกรมคณิตศาสตร์\n");

    shape_t field = {"สนามฟุตบอล", 100.0, 60.0, 0.0};
    shape_t pool = {"สระน้ำกลม", 5.0, 0.0, 2.0};
    shape_t box = {"กล่องของขวัญ", 20.0, 15.0, 10.0};

    vTaskDelay(pdMS_TO_TICKS(500));

    calculate_rectangle(field);
    vTaskDelay(pdMS_TO_TICKS(1000));

    calculate_circle(pool);
    vTaskDelay(pdMS_TO_TICKS(1000));

    calculate_box(box);
    vTaskDelay(pdMS_TO_TICKS(1000));

    calculate_triangle();
    vTaskDelay(pdMS_TO_TICKS(1000));

    calculate_cone();
    vTaskDelay(pdMS_TO_TICKS(1000));

    convert_area_units();
    vTaskDelay(pdMS_TO_TICKS(1000));


    ESP_LOGI(TAG, "\n✅ เสร็จสิ้นการคำนวณทั้งหมด!");
}
```

## Result
```c
I (13431) MATH_PROGRAM: 
⭕ วงกลม
I (13431) MATH_PROGRAM: ╔════════════════════════════════════╗
I (13431) MATH_PROGRAM: ║ 🔷 สระน้ำกลม
I (13431) MATH_PROGRAM: ╠════════════════════════════════════╣
I (13431) MATH_PROGRAM: ║ 📏 รัศมี: 5.00 ม.
I (13431) MATH_PROGRAM: ║ 📏 ลึก: 2.00 ม.
I (13431) MATH_PROGRAM: ║ 📐 พื้นที่: 78.54 ตร.ม.
I (13431) MATH_PROGRAM: ║ ⭕ เส้นรอบวง: 31.42 ม.
I (13431) MATH_PROGRAM: ║ 💧 ปริมาตร: 157.08 ลบ.ม.
I (13431) MATH_PROGRAM: ╚════════════════════════════════════╝
I (14431) MATH_PROGRAM: 
📦 กล่อง
I (14431) MATH_PROGRAM: ╔════════════════════════════════════╗
I (14431) MATH_PROGRAM: ║ 🔷 กล่องของขวัญ
I (14431) MATH_PROGRAM: ╠════════════════════════════════════╣
I (14431) MATH_PROGRAM: ║ 📏 ยาว: 20.00 ซม.
I (14431) MATH_PROGRAM: ║ 📏 กว้าง: 15.00 ซม.
I (14431) MATH_PROGRAM: ║ 📏 สูง: 10.00 ซม.
I (14431) MATH_PROGRAM: ║ 🎁 ปริมาตร: 3000.00 ลบ.ซม.
I (14431) MATH_PROGRAM: ║ 📐 พื้นที่ผิว: 1300.00 ตร.ซม.
I (14431) MATH_PROGRAM: ║ 💧 เท่ากับ: 3.000 ลิตร
I (14431) MATH_PROGRAM: ╚════════════════════════════════════╝
I (15431) MATH_PROGRAM: 
🔺 สามเหลี่ยม
I (15431) MATH_PROGRAM: ╔════════════════════════════════════╗
I (15431) MATH_PROGRAM: ║ 📏 ฐาน: 10.00 ซม.
I (15431) MATH_PROGRAM: ║ 📏 สูง: 8.00 ซม.
I (15431) MATH_PROGRAM: ║ 📐 พื้นที่: 40.00 ตร.ซม.
I (15431) MATH_PROGRAM: ╚════════════════════════════════════╝
I (16431) MATH_PROGRAM: 
🍦 ทรงกรวย
I (16431) MATH_PROGRAM: ╔══════════════════════════════════════╗
I (16431) MATH_PROGRAM: ║           ทรงกรวย                 ║
I (16431) MATH_PROGRAM: ╠══════════════════════════════════════╣
I (16431) MATH_PROGRAM: ║ 📏 รัศมี: 7.00 ซม.
I (16431) MATH_PROGRAM: ║ 📏 ความสูง: 12.00 ซม.
I (16431) MATH_PROGRAM: ║ 📐 พื้นที่ฐาน: π×7² = 153.94 ตร.ซม.
I (16431) MATH_PROGRAM: ║ 🔺 ปริมาตร: ⅓×153.94×12.00 = 615.75 ลบ.ซม.
I (16431) MATH_PROGRAM: ║ 💧 เท่ากับ: 0.616 ลิตร
I (16431) MATH_PROGRAM: ╚══════════════════════════════════════╝
I (17431) MATH_PROGRAM: 
🌾 การแปลงหน่วยพื้นที่
I (17431) MATH_PROGRAM: ╔════════════════════════════════════╗
I (17431) MATH_PROGRAM: ║ 📏 ยาว: 100.00 ม.
I (17431) MATH_PROGRAM: ║ 📏 กว้าง: 50.00 ม.
I (17431) MATH_PROGRAM: ║ 📐 พื้นที่: 5000.00 ตร.ม.
I (17431) MATH_PROGRAM: ║ 🌾 เท่ากับ: 3.1250 ไร่
I (17431) MATH_PROGRAM: ╚════════════════════════════════════╝
I (18431) MATH_PROGRAM: 
✅ เสร็จสิ้นการคำนวณทั้งหมด!
I (18431) main_task: Returned from app_main()
```
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/daffb8a1-861c-470e-9843-0f33822fb1dd" />
