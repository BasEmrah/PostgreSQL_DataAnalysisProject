# SQL Project Analysis

This project performs various data analyses using the PostgreSQL database. The details of the datasets involved and the explanations of the analyses conducted are outlined below. The results and visuals obtained from this work have been shared in the GitHub repository.

## Table of Contents
- [Dataset and Tables](#dataset-and-tables)
- [Case 1: Order Analysis](#case-1-order-analysis)
- [Case 2: Customer Analysis](#case-2-customer-analysis)
- [Case 3: Seller Analysis](#case-3-seller-analysis)
- [Case 4: Payment Analysis](#case-4-payment-analysis)
- [Case 5: RFM Analysis](#case-5-rfm-analysis)
- [Visuals and Files](#visuals-and-files)
- [Installation and Usage](#installation-and-usage)

## Dataset and Tables

The dataset used in the project consists of the following tables and columns:

### customers
Contains information about customers.
- **customer_id**: Customer ID
- **customer_unique_id**: Unique ID of the customer
- **customer_zip_code_prefix**: Customer's postal code
- **customer_city**: Customer's city
- **customer_state**: Customer's state

### order_items
Contains details about ordered products.
- **order_id**: Order ID
- **order_item_id**: Order item ID
- **product_id**: Product ID
- **seller_id**: Seller ID
- **shipping_limit_date**: Deadline for shipping
- **price**: Price of the product
- **freight_value**: Shipping fee

### order_payments
Contains information about order payments.
- **order_id**: Order ID
- **payment_sequential**: Payment sequence
- **payment_type**: Payment type (credit card, transfer, etc.)
- **payment_installments**: Number of installments
- **payment_value**: Payment amount

### order_reviews
Contains order reviews and ratings.
- **review_id**: Review ID
- **order_id**: Order ID
- **review_score**: Review score
- **review_comment_title**: Review title
- **review_comment_message**: Review message
- **review_creation_date**: Review creation date
- **review_answer_timestamp**: Review response timestamp

### orders
Contains information about orders.
- **order_id**: Order ID
- **customer_id**: Customer ID
- **order_status**: Order status (delivered, canceled, etc.)
- **order_purchase_timestamp**: Date the order was placed
- **order_approved_at**: Date the order was approved
- **order_delivered_carrier_date**: Date the order was shipped
- **order_delivered_customer_date**: Date the order was delivered to the customer
- **order_estimated_delivery_date**: Estimated delivery date

### products
Contains information about products.
- **product_id**: Product ID
- **product_category_name**: Product category
- **product_name_length**: Length of the product name
- **product_description_length**: Length of the product description
- **product_photos_qty**: Number of product photos
- **product_weight_g**: Product weight (grams)
- **product_length_cm**: Product length (cm)
- **product_height_cm**: Product height (cm)
- **product_width_cm**: Product width (cm)

### sellers
Contains information about sellers.
- **seller_id**: Seller ID
- **seller_zip_code_prefix**: Seller's postal code
- **seller_city**: Seller's city
- **seller_state**: Seller's state

### product_category_name_translation
Contains English translations of product categories.
- **product_category_name**: Product category
- **product_category_name_english**: English name of the product category

## Case 1: Order Analysis

### Question 1: Monthly Order Distribution
- **Query**: The `order_approved_at` date should be used.
- **Result**: Monthly order distribution has been visualized in Excel.

### Question 2: Monthly Order Status Breakdown by Order Count
- **Query**: A query analyzing order counts by monthly order status breakdown has been executed.
- **Result**: Visualized in Excel. Dramatic declines or increases have been identified and interpreted.

### Question 3: Order Counts by Product Category Breakdown
- **Query**: Categories that stand out on special days have been analyzed.
- **Result**: Increases in specific categories have been observed during special occasions like New Year's and Valentine's Day.

### Question 4: Order Counts by Days of the Week and Days of the Month
- **Query**: Order counts have been examined based on days of the week and days of the month.
- **Result**: Visualized in Excel and interpreted.

## Case 2: Customer Analysis

### Question 1: Shopping Intensity by City
- **Query**: Analysis has been made based on the city where the customer made the most orders.
- **Result**: The cities with the most shopping activity have been identified.

## Case 3: Seller Analysis

### Question 1: Fastest Order Delivering Sellers
- **Query**: The top 5 sellers have been identified, and their order counts and product reviews analyzed.
- **Result**: The fastest delivery sellers have been listed and interpreted.

### Question 2: Sellers with the Most Product Categories
- **Query**: Analyzed which sellers sold products from more categories.
- **Result**: Order counts of sellers with a large number of categories have been compared.

## Case 4: Payment Analysis

### Question 1: Regions of Users with High Installment Numbers
- **Query**: Regions of users with a high number of installments have been identified.
- **Result**: Regional distribution has been analyzed.

### Question 2: Successful Order Count and Total Successful Payment Amount by Payment Type
- **Query**: Successful order counts and total payment amounts have been calculated by payment type.
- **Result**: Payment types ranked from most to least used.

### Question 3: Single Payment and Installment Payment Category-Based Analysis
- **Query**: Category-based analysis of orders paid with single payment and installments has been conducted.
- **Result**: The categories where installment payments were most commonly used have been identified.

## Case 5: RFM Analysis

- **RFM Analysis**: Recency, Frequency, and Monetary values have been calculated and analyzed.

## Visuals and Files

- **EmrahBas_SQL_Project.pdf**: PDF file containing detailed explanations of the project.
- **SQL_Project_1.png**: Visual and analysis showing monthly order distribution.
- **SQL_Project_2a.png**: Visual and analysis showing order counts distribution by days of the week (Monday, Tuesday, Wednesday, etc.).
- **SQL_Project_2b.png**: Visual and analysis showing order counts distribution by days of the month (1, 2, 3, ..., 29, 30, 31).
- **README.md**: This documentation file explaining the project overview, dataset, analyses, and repository contents.

## Installation and Usage

1. **Download the Repository**
   - Clone or download the repository to your local computer.
2. **Open the PDF File**
   - Open the 'EmrahBas_SQL_Project.pdf' file to review the dataset and conducted analyses.

---

# SQL Proje Analizi

Bu proje, PostgreSQL veritabanı kullanarak çeşitli veri analizlerini gerçekleştirmektedir. Projede yer alan veri setlerinin detayları ve yapılan analizlerin açıklamaları aşağıda yer almaktadır. Bu çalışmada elde edilen sonuçlar ve görseller GitHub reposunda paylaşılmıştır.

## İçindekiler
- [Veri Seti ve Tablolar](#veri-seti-ve-tablolar)
- [Case 1: Sipariş Analizi](#case-1-sipariş-analizi)
- [Case 2: Müşteri Analizi](#case-2-müşteri-analizi)
- [Case 3: Satıcı Analizi](#case-3-satıcı-analizi)
- [Case 4: Payment Analizi](#case-4-payment-analizi)
- [Case 5: RFM Analizi](#case-5-rfm-analizi)
- [Görseller ve Dosyalar](#görseller-ve-dosyalar)
- [Kurulum ve Kullanım](#kurulum-ve-kullanım)

## Veri Seti ve Tablolar

Projede kullanılan veri seti, aşağıdaki tablo ve sütunlardan oluşmaktadır:

### customers
Müşterilere ait bilgileri içerir.
- **customer_id**: Müşteri ID'si
- **customer_unique_id**: Müşterinin benzersiz ID'si
- **customer_zip_code_prefix**: Müşterinin posta kodu
- **customer_city**: Müşterinin şehri
- **customer_state**: Müşterinin bulunduğu eyalet

### order_items
Sipariş edilen ürünlerin detaylarını içerir.
- **order_id**: Sipariş ID'si
- **order_item_id**: Sipariş öğesi ID'si
- **product_id**: Ürün ID'si
- **seller_id**: Satıcı ID'si
- **shipping_limit_date**: Gönderim için son tarih
- **price**: Ürünün fiyatı
- **freight_value**: Nakliye ücreti

### order_payments
Sipariş ödemelerine ait bilgileri içerir.
- **order_id**: Sipariş ID'si
- **payment_sequential**: Ödeme sırası
- **payment_type**: Ödeme türü (kredi kartı, havale vb.)
- **payment_installments**: Taksit sayısı
- **payment_value**: Ödeme tutarı

### order_reviews
Sipariş incelemeleri ve puanlamalarını içerir.
- **review_id**: İnceleme ID'si
- **order_id**: Sipariş ID'si
- **review_score**: İnceleme puanı
- **review_comment_title**: İnceleme başlığı
- **review_comment_message**: İnceleme mesajı
- **review_creation_date**: İnceleme oluşturulma tarihi
- **review_answer_timestamp**: İncelemeye yanıt verilme zamanı

### orders
Siparişlere ait bilgileri içerir.
- **order_id**: Sipariş ID'si
- **customer_id**: Müşteri ID'si
- **order_status**: Sipariş durumu (teslim edildi, iptal edildi vb.)
- **order_purchase_timestamp**: Siparişin verildiği tarih
- **order_approved_at**: Siparişin onaylandığı tarih
- **order_delivered_carrier_date**: Siparişin kargoya verildiği tarih
- **order_delivered_customer_date**: Siparişin müşteriye teslim edildiği tarih
- **order_estimated_delivery_date**: Tahmini teslim tarihi

### products
Ürünlere ait bilgileri içerir.
- **product_id**: Ürün ID'si
- **product_category_name**: Ürün kategorisi
- **product_name_length**: Ürün adının uzunluğu
- **product_description_length**: Ürün açıklamasının uzunluğu
- **product_photos_qty**: Ürün fotoğraf sayısı
- **product_weight_g**: Ürün ağırlığı (gram)
- **product_length_cm**: Ürün uzunluğu (cm)
- **product_height_cm**: Ürün yüksekliği (cm)
- **product_width_cm**: Ürün genişliği (cm)

### sellers
Satıcılara ait bilgileri içerir.
- **seller_id**: Satıcı ID'si
- **seller_zip_code_prefix**: Satıcının posta kodu
- **seller_city**: Satıcının şehri
- **seller_state**: Satıcının bulunduğu eyalet

### product_category_name_translation
Ürün kategorilerinin İngilizce çevirilerini içerir.
- **product_category_name**: Ürün kategorisi
- **product_category_name_english**: Ürün kategorisinin İngilizcesi

## Case 1: Sipariş Analizi

### Question 1: Aylık Olarak Order Dağılımı
- **Sorgu**: Tarih verisi için `order_approved_at` kullanılmalıdır.
- **Sonuç**: Aylık order dağılımı Excel'de görselleştirilmiştir.

### Question 2: Aylık Olarak Order Status Kırılımında Order Sayıları
- **Sorgu**: Aylık order status kırılımında order sayılarını inceleyen sorgu çalıştırılmıştır.
- **Sonuç**: Excel ile görselleştirilmiştir. Dramatik düşüş veya yükselişler belirlenmiş ve yorumlanmıştır.

### Question 3: Ürün Kategorisi Kırılımında Sipariş Sayıları
- **Sorgu**: Özel günlerde öne çıkan kategoriler analiz edilmiştir.
- **Sonuç**: Yılbaşı, sevgililer günü gibi özel günlerde belirli kategorilerde artış gözlemlenmiştir.

### Question 4: Haftanın ve Ayın Günlerine Göre Order Sayıları
- **Sorgu**: Haftanın günleri ve ay günleri bazında order sayıları incelenmiştir.
- **Sonuç**: Excel'de görselleştirilmiş ve yorumlanmıştır.

## Case 2: Müşteri Analizi

### Question 1: Şehirlere Göre Alışveriş Yoğunluğu
- **Sorgu**: Müşterinin en çok sipariş verdiği şehir baz alınarak analiz yapılmıştır.
- **Sonuç**: En çok alışveriş yapılan şehirler belirlenmiştir.

## Case 3: Satıcı Analizi

### Question 1: En Hızlı Sipariş Teslim Eden Satıcılar
- **Sorgu**: Top 5 satıcı belirlenmiş, bu satıcıların order sayıları ve ürün yorumları analiz edilmiştir.
- **Sonuç**: En hızlı teslimat yapan satıcılar listelenmiş ve yorumlanmıştır.

### Question 2: En Fazla Kategoriye Ait Ürün Satan Satıcılar
- **Sorgu**: Hangi satıcıların daha fazla kategoriye ait ürün sattığı analiz edilmiştir.
- **Sonuç**: Fazla kategoriye sahip satıcıların order sayıları karşılaştırılmıştır.

## Case 4: Payment Analizi

### Question 1: Taksit Sayısı Fazla Olan Kullanıcıların Yaşadığı Bölgeler
- **Sorgu**: Taksit sayısı fazla olan kullanıcıların bölgeleri belirlenmiştir.
- **Sonuç**: Bölgesel dağılım analiz edilmiştir.

### Question 2: Ödeme Tipine Göre Başarılı Order Sayısı ve Toplam Başarılı Ödeme Tutarı
- **Sorgu**: Ödeme tipine göre başarılı order sayıları ve toplam ödeme tutarları hesaplanmıştır.
- **Sonuç**: Ödeme tipleri en çok kullanılan tipten en az olana göre sıralanmıştır.

### Question 3: Tek Çekim ve Taksitli Ödeme Kategori Bazlı Analizi
- **Sorgu**: Tek çekim ve taksitle ödenen siparişlerin kategori bazlı analizi yapılmıştır.
- **Sonuç**: Taksitle ödeme kullanılan en çok kategoriler belirlenmiştir.

## Case 5: RFM Analizi

- **RFM Analizi**: Recency, Frequency ve Monetary değerleri hesaplanarak analiz yapılmıştır.

## Görseller ve Dosyalar

- **EmrahBas_SQL_Project.pdf**: Projenin detaylı açıklamalarını içeren PDF dosyası.
- **SQL_Project_1.png**: Aylık order dağılımını gösteren görsel ve analizi.
- **SQL_Project_2a.png**: Haftanın günlerine göre (Pztesi, Salı, Çarş., ...) order sayılarının dağılımını gösteren görsel ve analizi.
- **SQL_Project_2b.png**: Ayın günlerine göre (1, 2, 3, ... ,29,30,31) order sayılarının dağılımını gösteren görsel ve analizi.
- **README.md**: Projenin genel bakışını, veri kümesini analizleri ve depo içeriğini açıklayan bu dokümantasyon dosyası.

## Kurulum ve Kullanım

1. **Depoyu İndirin**
   - Depoyu yerel bilgisayarınıza klonlayın veya indirin.
2. **"pdf" Formatındaki Dosyayı Açın**
   - 'EmrahBas_SQL_Project.pdf' dosyasını açarak veri kümesini inceleyin ve gerçekleştirilen analizleri gözden geçirin. 
