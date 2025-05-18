Araç Kiralama Sistemi - Proje Dokümantasyonu
1. Proje Analizi Amaç:
Basit ve kullanıcı dostu bir arayüz ile müşterilere araç kiralama hizmeti sunmak.
Kullanıcı Türleri:
- Kullanıcı (Personel): Sisteme araç ve müşteri ekleyebilir, araç kiralayabilir ve mevcut kiralamaları görüntüleyebilir.
 Temel İşlevler:
- Araç ekleme
- Müşteri ekleme
- Araç kiralama
- Kiralama kayıtlarını görüntüleme
2. Sınıf Tanımları
 Arac Sınıfı
- Özellikler:
  - arac_id: (str) Araç kimliği
  - model: (str) Araç modeli
  - kiralama_durumu: (bool) Kiralanmış mı?
- Metotlar:
  - arac_durumu_guncelle(durum: bool): Kiralama durumunu günceller.
 Musteri Sınıfı
- Özellikler:
  - musteri_id: (str) Müşteri kimliği
  - ad: (str) Ad
  - soyad: (str) Soyad
 Kiralama Sınıfı
- Özellikler:
  - kiralamalar: (liste) Kiralama kayıtlarını tutar.
- Metotlar:
  - kiralama_yap(musteri, arac): Araç kiralama işlemini yapar.
  - kiralama_bilgisi(): Tüm kiralama kayıtlarını listeler.
3. Veri Yapıları
Veri Türü	Kullanılan Yapı	Açıklama
Araçlar	list[Arac]	Tüm araçları tutar.
Müşteriler	list[Musteri]	Tüm müşterileri tutar.
Kiralamalar	list[dict]	Müşteri ve araç eşleşmeleri sözlük olarak saklanır.
4. Arayüz Tasarımı (GUI)
Arayüzdeki Bileşenler:
- Araç Ekleme Alanı: Araç ID ve model giriş kutuları
- Müşteri Ekleme Alanı: Müşteri ID, ad ve soyad giriş kutuları
- Listbox'lar: Mevcut araç ve müşteri listesi
- Kiralama Butonu: Seçili müşteri ve araç ile kiralama işlemi
- Kiralama Bilgileri: Mevcut kiralamaları gösteren metin alanı
Kullanılan Teknoloji:
- tkinter kütüphanesi ile masaüstü GUI
5. Kodlama
Kodlama adımında yukarıda verdiğiniz Python kodu başarıyla sınıf tanımlarını, veri yapılarını ve GUI öğelerini kapsamaktadır.
6. Sistem Testi
Sistemin işlevlerini test etmek için:
- Araç eklenip listede görüntüleniyor mu?
- Müşteri eklenip listede görüntüleniyor mu?
- Müşteri ve araç seçilerek kiralama yapılabiliyor mu?
- Kiralanmış araç tekrar kiralanabiliyor mu? (Olmamalı)
- Kiralama bilgileri doğru şekilde listeleniyor mu?
7. Kullanım Kılavuzu
Adım Adım Kullanım:
1. Araç Ekleme
   - Araç ID ve modeli girin, “Araç Ekle” butonuna tıklayın.
2. Müşteri Ekleme
   - Müşteri ID, ad ve soyad girin, “Müşteri Ekle” butonuna tıklayın.
3. Araç Kiralama
   - Listelerden müşteri ve araç seçin.
   - “Araç Kirala” butonuna basın.
   - Araç müsait değilse uyarı mesajı gösterilir.
4. Kiralama Bilgilerini Görüntüleme
   - “Kiralama Bilgileri” butonuna tıklayarak yapılan kiralamaları görün.
8. Geliştirme Önerileri
İleri seviye için şu geliştirmeler yapılabilir:
- Kiralama iptali özelliği
- Tarih bilgisi (kiralama tarihi, iade tarihi)
- Verilerin dosyaya (JSON/DB) kaydedilmesi
- Gelişmiş arama ve filtreleme

Proje Dokümantasyonu – Proje 2: Hastane Randevu Sistemi
1. Temel Tanım
Bu proje, hastaların uygun doktorlardan randevu almasını ve bu randevuları yönetmesini sağlayan bir sistemdir. Python programlama dili ve tkinter arayüz kütüphanesi kullanılarak geliştirilecektir.
2. Temel Sınıfların Tanımlanması
Hasta Sınıfı: Hasta bilgilerini ve geçmiş randevularını tutar.
- Özellikler: isim (str), tc (str), randevu_gecmisi (list)
Doktor Sınıfı: Doktor bilgilerini ve uygunluk durumunu saklar.
- Özellikler: isim (str), uzmanlik (str), musaitlik (list)
Randevu Sınıfı: Bir hasta ile doktor arasında oluşturulan randevuyu temsil eder.
- Özellikler: tarih (str), doktor (Doktor), hasta (Hasta)
3. Randevu Sistemi Fonksiyonları
randevu_al(hasta, doktor, tarih): Hasta için doktorun uygunluk durumuna göre randevu oluşturur.
randevu_iptal(hasta, randevu): Mevcut bir randevuyu iptal eder ve doktorun müsaitlik listesini günceller.
4. Veri Yapıları
- Liste (list): Hasta ve doktor nesnelerini saklamak için.
- Sözlük (dict): TC ile hasta erişimi sağlamak için.
- JSON: Verilerin dosyada kalıcı olarak saklanması.
- datetime/str: Tarih ve saat bilgileri için.
5. Kullanıcı Arayüzü (GUI)
Araçlar: tkinter, customtkinter
Tema: Mavi tonlar, tıbbi ikonlar (steteskop, iğne)
Ekranlar: Giriş, doktor seçimi, randevu takvimi, randevu iptali
6. Kodlama Aşamaları
1. Sınıfların tanımlanması
2. Fonksiyonların yazılması
3. JSON veri kaydetme/yükleme
4. GUI oluşturulması
5. Kullanıcı girdisi ve işlem mantığı
6. Ana döngünün yönetimi
7. Test Etme
- TC ile hasta girişi
- Aynı saate iki randevu alınamaması
- Randevu alındıktan sonra doktorun uygunluk güncellemesi
- Randevu iptali sonrası zaman diliminin serbest kalması
- JSON veri kaydının test edilmesi
8. Kullanım Kılavuzu
1. Programı başlatın: python main.py
2. TC ile giriş yapın: Yeni hasta otomatik eklenir.
3. Doktor ve tarih seçin, Randevu Al butonuna basın.
4. Randevu geçmişi üzerinden iptal işlemi yapılabilir.


