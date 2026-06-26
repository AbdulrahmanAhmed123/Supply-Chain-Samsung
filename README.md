# 📊 SAMSUNG Supply Chain & Logistics Dashboard (Power BI)

![SAMSUNG Banner](https://img.shields.io/badge/SAMSUNG-Supply_Chain-034EA2?style=for-the-badge&logo=samsung&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-Data_Analysis-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

المشروع ده عبارة عن **End-to-End BI Project** معمول مخصوص عشان يحلل ويعمل Optimization لعمليات الـ Supply Chain، الـ Procurement، الـ Inventory، والـ Shipments في شركة **SAMSUNG**. 

بدل الـ Star Schema التقليدي، استخدمنا هنا **Galaxy Schema (Fact Constellation)** قوي جداً بيربط **5 جداول حقائق (Fact Tables)** ببعض من خلال **Shared Master Dimensions** عشان نطلع بـ Actionable Insights تخدم الـ Decision Makers.

---

## 🖥️ Dashboard Interface (Home Page)

<img width="1800" height="790" alt="Screenshot 2026-06-26 185332" src="https://github.com/user-attachments/assets/ae7290ec-5894-4d40-aa62-5a7bd7baf4ed" />

---

## 📌 الـ Executive Summary وأهم الـ KPIs

الـ Dashboard بتراقب الـ Business Lifecycle كاملة من أول ما بنشتري من الـ Supplier لحد ما المنتج يوصل للـ End Customer:

* **Gross Revenue:** عملنا إجمالي إيرادات **$186.86M**.
* **Net Revenue:** صافي الإيرادات بعد الخصومات وصل لـ **$176.95M**.
* **Net Profit:** صافي ربح **$48.56M** (يعني **Profit Margin = 27.44%**).
* **Perfect Order Rate:** وصلنا لنسبة **75%** في دقة وجودة الطلبات.
* **Quantities:** إجمالي الـ Order Qty حوالي **129K وحدة**، والـ Delivered Qty وصل لـ **187K وحدة**.

---

## 🛠️ الـ Data Architecture و الـ Galaxy Schema

الموديل مبني بطريقة احترافية عشان يربط الـ 5 Fact Tables دول ببعض:
1. `fact_sales`: عشان تحليل المبيعات والـ Revenue والـ Discounts.
2. `fact_procurement`: لمتابعة أداء الموردين، والـ Actual Lead Times.
3. `fact_inventory`: لمراقبة الـ Stock Levels اليومية جوه المخازن.
4. `fact_shipment`: عشان الـ Carrier Performance وحساب التأخيرات.
5. `fact_production`: لقياس حجم الإنتاج والـ Defect Rates في المصنع.

* **الـ Shared Dimensions:** جدول الـ `dim_product` هو الـ Hub المركزي اللي رابط كل الـ Facts دي ببعض، مع الـ `dim_date` والـ `dim_customer` والـ `dim_supplier`.

---

## 🔍 أهم الـ Insights اللي طلعت بيها من الداتا

### 1️⃣ أداء الموردين (Supplier Performance)
* **الـ Lead Time:** الموردين في **Vietnam & India** هما الأسرع بمتوسط **9 أيام**، متفوقين على كوريا الجنوبية والصين (12 يوم).
* **الـ Quality:** شركتين *Taiwan Semiconductor* و *Sony* جابوا أعلى سكور في الجودة (**98/100**).

### 2️⃣ المخزون والمصنع (Inventory & Production)
* **الـ Overstocking:** المخزون مركز جداً في المنتجات الـ Flagship، على رأسهم الـ **Galaxy S24 Ultra** (حوالي 25K حتة في المخزن).
* **الـ Defect Rate:** نفس المنتج (S24 Ultra) مطلع أعلى نسبة عيوب تصنيعية (**4.3K وحدة معيبة**)، وده جرس إنذار لبتوع الـ Quality Assurance يدخلوا فوراً.

### 3️⃣ الشحن واللوجستيات (Shipment & Carrier Performance)
* **حالة الشحنات:** من بين 218 شحنة، **78.44%** اتسلموا تمام، لكن عندنا **12.84% (28 شحنة)** حصل فيهم Delays.
* **الـ Bottlenecks:** شركة **DHL Express** هي أكتر شركة شحن أخرتنا (24 شحنة متأخرة).
* **الـ Root-Cause:** لما عملنا Root-Cause Analysis، لقينا إن أهم أسباب التأخير هي: مشاكل العناوين (**Address Exceptions**)، والـ **Carrier Capacity**، والـ **Customs Clearance** (التخليص الجمركي والورق).

### 4️⃣ تحليل القنوات والعملاء (Customer Channels)
* **الـ Sales Channels:** الأونلاين (**Online E-Commerce**) مسيطر على الحصة الأكبر بنسبة **43.94%** من الصافي.
* **الـ Platforms:** منصة **Amazon** هي التوب بـ **$37M**، وبتنافسها Flipkart و Best Buy بـ $36M لكل منصة.

---

## 🧠 الـ Advanced DAX والـ Features اللي اطبقت

* **Time Intelligence:** حسابات الـ YoY والـ MoM عشان نقيس الـ Seasonal Spikes (زي ذروة المخزون في ديسمبر).
* **Active vs Inactive Relationships:** استخدمنا دالة `USERELATIONSHIP` عشان ندير التواريخ المختلفة زي الـ `OrderDate` والـ `DeliveryDate`.
* **UI/UX Best Practices:** تطبيق الـ Custom Card Visuals الجديدة، وحطينا معاه الـ Context Icons، وعملنا نظام الـ Tab-Navigation الشيك عشان ننقل بين الصفحات كأنك جوه ويبسايت.

---
💡 *Developed by Abdulrahman Ahmed - Data Analyst*
