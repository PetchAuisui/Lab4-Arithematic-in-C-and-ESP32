# 1.คำนวณพื้นที่สามเหลี่ยม
## Code
```c
#include <stdio.h>
#include <string.h>
#include "esp_log.h"
#include "freertos/FreeRTOS.h"
#include "freertos/task.h"

static const char *TAG = "SHOPPING_MATH";

typedef struct {
    char name[40];          
    int quantity;           
    float price_per_unit;   
    float total_price;      
} product_t;

void calculate_product_total(product_t *product) {
    product->total_price = product->quantity * product->price_per_unit;
}

void display_product(const product_t *product) {
    ESP_LOGI(TAG, "   %s: %d × %.0f = %.0f บาท", 
             product->name, product->quantity, product->price_per_unit, product->total_price);
}

float calculate_total_bill(product_t products[], int count) {
    float total = 0.0;
    for (int i = 0; i < count; i++) {
        calculate_product_total(&products[i]);
        total += products[i].total_price;
    }
    return total;
}

float apply_discount(float total, float discount) {
    return total - discount;
}

float split_payment(float amount, int people) {
    if (people <= 0) {
        ESP_LOGE(TAG, "Error: จำนวนคนต้องมากกว่า 0");
        return 0.0;
    }
    return amount / people;
}

void app_main(void)
{
    ESP_LOGI(TAG, "🛒 เริ่มต้นโปรแกรมซื้อของที่ตลาด 🛒");
    ESP_LOGI(TAG, "=====================================");

    product_t products[] = {
        {"แอปเปิ้ล", 6, 15.0, 0.0},
        {"กล้วย", 12, 8.0, 0.0},
        {"ส้ม", 8, 12.0, 0.0},
        {"ขนมปัง", 2, 20.0, 0.0}
    };
    int product_count = sizeof(products) / sizeof(products[0]);

    float discount_percent = 10.0;    // ส่วนลด 10%
    float discount = 0.0;             // ส่วนลดจริง (คำนวณทีหลัง)
    float vat_rate = 0.07;            // ภาษีมูลค่าเพิ่ม 7%
    float final_total = 0.0;
    int people = 3;

    ESP_LOGI(TAG, "📖 โจทย์:");
    ESP_LOGI(TAG, "   แม่ไปซื้อของที่ตลาด:");
    for (int i = 0; i < product_count; i++) {
        ESP_LOGI(TAG, "   - %s: %d หน่วย หน่วยละ %.0f บาท", 
                 products[i].name, products[i].quantity, products[i].price_per_unit);
    }
    ESP_LOGI(TAG, "   - มีส่วนลด: %.0f%%", discount_percent);
    ESP_LOGI(TAG, "   - ภาษีมูลค่าเพิ่ม (VAT): 7%%");
    ESP_LOGI(TAG, "   - แบ่งจ่าย: %d คน", people);
    ESP_LOGI(TAG, "");

    vTaskDelay(3000 / portTICK_PERIOD_MS);

    ESP_LOGI(TAG, "🧮 ขั้นตอนการคิด:");
    ESP_LOGI(TAG, "   1. คำนวณราคาแต่ละสินค้า (การคูณ):");
    float subtotal = calculate_total_bill(products, product_count);
    for (int i = 0; i < product_count; i++) {
        display_product(&products[i]);
    }
    ESP_LOGI(TAG, "");

    ESP_LOGI(TAG, "   2. รวมราคาทั้งหมด (การบวก): %.0f บาท", subtotal);
    ESP_LOGI(TAG, "");

    discount = subtotal * (discount_percent / 100.0);
    float discounted_total = apply_discount(subtotal, discount);
    ESP_LOGI(TAG, "   3. หักส่วนลด (การลบ): %.0f - %.0f%% (%.2f บาท) = %.2f บาท",
             subtotal, discount_percent, discount, discounted_total);
    ESP_LOGI(TAG, "");

    float vat_amount = 0.0;


    vat_amount = discounted_total * vat_rate;
    final_total = discounted_total + vat_amount;
    ESP_LOGI(TAG, "   4. คำนวณภาษี VAT (7%%): %.2f × 7%% = %.2f บาท", discounted_total, vat_amount);
    ESP_LOGI(TAG, "   5. ยอดรวมหลัง VAT: %.2f + %.2f = %.2f บาท", discounted_total, vat_amount, final_total);
    ESP_LOGI(TAG, "");

    float per_person = split_payment(final_total, people);
    ESP_LOGI(TAG, "   6. แบ่งจ่าย (การหาร): %.2f ÷ %d = %.2f บาท/คน", final_total, people, per_person);
    ESP_LOGI(TAG, "");

    ESP_LOGI(TAG, "🧾 ใบเสร็จรับเงิน:");
    ESP_LOGI(TAG, "   ==========================================");
    ESP_LOGI(TAG, "   🏪 ตลาดสดใหม่ 🏪");
    ESP_LOGI(TAG, "   ==========================================");

    for (int i = 0; i < product_count; i++) {
        display_product(&products[i]);
    }

    ESP_LOGI(TAG, "   ----------------------------------------");
    ESP_LOGI(TAG, "   ยอดรวม:                    %.2f บาท", subtotal);
    ESP_LOGI(TAG, "   ส่วนลด:                   -%.2f บาท", discount);
    ESP_LOGI(TAG, "   ยอดก่อน VAT:               %.2f บาท", discounted_total);
    ESP_LOGI(TAG, "   ภาษี 7%%:                  +%.2f บาท", vat_amount);
    ESP_LOGI(TAG, "   ========================================");
    ESP_LOGI(TAG, "   ยอดสุทธิหลัง VAT:          %.2f บาท", final_total);
    ESP_LOGI(TAG, "   แบ่งจ่าย %d คน:             %.2f บาท/คน", people, per_person);
    ESP_LOGI(TAG, "   ========================================");
    ESP_LOGI(TAG, "   ขอบคุณที่ใช้บริการ 😊");
    ESP_LOGI(TAG, "");

    ESP_LOGI(TAG, "🎉 จบโปรแกรมซื้อของที่ตลาด!");
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

// 🏷️ TAG สำหรับ log
static const char *TAG = "CONE_CALC";

// 🔢 ค่าคงที่
#define PI 3.14159265359

// 🍦 ฟังก์ชันคำนวณปริมาตรทรงกรวย
void calculate_cone(void) {
    double radius = 7.0;    // รัศมี (ซม.)
    double height = 12.0;   // ความสูง (ซม.)

    double base_area = PI * radius * radius; // พื้นที่ฐาน
    double volume = (1.0 / 3.0) * base_area * height; // ปริมาตร

    ESP_LOGI(TAG, "\n🍦 ทรงกรวย");
    ESP_LOGI(TAG, "╔══════════════════════════════════════╗");
    ESP_LOGI(TAG, "║           ทรงกรวยไอศกรีม           ║");
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
    ESP_LOGI(TAG, "🚀 เริ่มต้นโปรแกรมคำนวณปริมาตรทรงกรวย\n");

    vTaskDelay(pdMS_TO_TICKS(1000));  // รอให้ระบบเริ่มต้น

    calculate_cone();  // เรียกใช้ฟังก์ชัน

    ESP_LOGI(TAG, "\n✅ เสร็จสิ้นการคำนวณ!");
}
```
## Result
```c
I (13819) CONE_CALC:
🍦 ทรงกรวย
I (13819) CONE_CALC: ╔══════════════════════════════════════╗
I (13819) CONE_CALC: ║           ทรงกรวย                  ║
I (13819) CONE_CALC: ╠══════════════════════════════════════╣
I (13819) CONE_CALC: ║ 📏 รัศมี: 7.00 ซม.
I (13819) CONE_CALC: ║ 📏 ความสูง: 12.00 ซม.
I (13829) CONE_CALC: ║ 📐 พื้นที่ฐาน: π×7² = 153.94 ตร.ซม.
I (13829) CONE_CALC: ║ 🔺 ปริมาตร: ⅓×153.94×12.00 = 615.75 ลบ.ซม.
I (13829) CONE_CALC: ║ 💧 เท่ากับ: 0.616 ลิตร
I (13829) CONE_CALC: ╚══════════════════════════════════════╝
I (13829) CONE_CALC:
✅ เสร็จสิ้นการคำนวณ!
I (13829) main_task: Returned from app_main()
```
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/9e63a261-4674-4747-82a2-02e28c71304e" />

