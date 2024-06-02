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

## Kurulum ve Kullanım

1. **Depoyu İndirin**
   - Depoyu yerel bilgisayarınıza klonlayın veya indirin.
2. **pdf Formatındaki Dosyayı Açın**
   - 'EmrahBas_SQL_Project.pdf' dosyasını açarak veri kümesini inceleyin ve gerçekleştirilen analizleri gözden geçirin. 

