# Dijital Pazarlama Müdürü 25 (DPM25)
## Oyun Tasarım Dokümanı (OTD)
**Versiyon:** 1.0  
**Son Güncelleme:** 20 Kasım 2025  
**Geliştirici:** Dijital Pazarlama Müdürü Ekibi  
**Tür:** Yönetim Simülasyonu / İş Stratejisi  
**Platform:** Web (Tarayıcı tabanlı)  
**İlham Kaynağı:** Football Manager 2025, SimCity, Game Dev Tycoon

---

## İçindekiler
1. [Oyun Vizyonu ve Ana Konsept](#1-oyun-vizyonu-ve-ana-konsept)
2. [Oynanış Genel Bakış](#2-oynanış-genel-bakış)
3. [Temel Oyun Sistemleri](#3-temel-oyun-sistemleri)
4. [Oyuncu İlerlemesi](#4-oyuncu-ilerlemesi)
5. [Oyun Modülleri](#5-oyun-modülleri)
6. [Kullanıcı Arayüzü](#6-kullanıcı-arayüzü)
7. [Sanat Yönetimi](#7-sanat-yönetimi)
8. [Teknik Mimari](#8-teknik-mimari)
9. [Para Kazanma Stratejisi](#9-para-kazanma-stratejisi)
10. [Gelecek Yol Haritası](#10-gelecek-yol-haritası)

---

## 1. Oyun Vizyonu ve Ana Konsept

### 1.1 Yüksek Konsept
*"Football Manager ile Mad Men'in buluşması"*

Dijital Pazarlama Müdürü 25, oyuncuların bir dijital ajansın Pazarlama Müdürü rolüne büründüğü derin bir yönetim simülasyonudur. Oyuncular, yaratıcılık ile analitik arasında denge kurmalı, kampanyaları yönetmeli, ekipler oluşturmalı, yönetim kurulunun beklentilerini karşılamalı ve birden fazla sezon boyunca dinamik dijital pazarlama dünyasında yol almalıdır.

### 1.2 Ana İlkeler
1. **Stratejik Karar Verme**: Her seçim önemlidir
2. **Veriye Dayalı Yönetim**: FM25 tarzı derinlik ve metrikler
3. **Sezon İlerlemesi**: 30 saatlik sezonlarla uzun vadeli hedefler
4. **Yönetim Kurulu İlişkileri**: Güven tabanlı kariyer sistemi
5. **Otantik Simülasyon**: Gerçek dünya pazarlama senaryoları

### 1.3 Hedef Kitle
- **Birincil**: Dijital pazarlamacılar, iş simülasyonu hayranları (25-45 yaş)
- **İkincil**: Football Manager oyuncuları, strateji oyunu tutkunları
- **Deneyim Seviyesi**: Gündelik oyunculardan hardcore yönetim simülasyonu oyuncularına

### 1.4 Eşsiz Satış Noktaları (ESN)
- ✅ Pazarlama bağlamında FM25'ten ilham alan yönetim derinliği
- ✅ Anlamlı ilerleme ile 30 saatlik sezon sistemi
- ✅ Dinamik yönetim kurulu güveni ve görev yönetimi
- ✅ Kapsamlı analitik ve veri görselleştirme
- ✅ Gerçek dünya pazarlama platformları (Google, Meta, TikTok, LinkedIn)
- ✅ Güzel glassmorphic UI tasarımı

---

## 2. Oynanış Genel Bakış

### 2.1 Oyun Döngüsü

#### Mikro Döngü (Günlük/Oturum)
1. **Bildirimleri Kontrol Et**: Yeni görevler, yönetim kurulu mesajları
2. **Performansı Gözden Geçir**: Dashboard metrikleri, trendler
3. **Karar Ver**: Kampanyalar başlat, içerik oluştur, ekibi yönet
4. **Zamanı İlerlet**: Gün/hafta ilerlet
5. **Sonuçları Değerlendir**: Sonuçları kontrol et, stratejiyi ayarla

#### Makro Döngü (Sezon)
1. **Sezon Başlangıcı**: Sözleşme imzalandı, hedefler belirlendi
2. **Strateji Oluştur**: Arketip seç, bütçe tahsis et
3. **Kampanya Yürüt**: Reklamlar, SEO, sosyal medya başlat
4. **Zorlukları Yönet**: Yönetim kurulu görevlerini tamamla, güveni koru
5. **Sezon İncelemesi**: Performans derecelendirmesi (S/A/B/C/D)
6. **Ödüller ve İlerleme**: Bonuslar, XP, yeni sezon

### 2.2 Ana Oynanış Deneyimi

**Sensin:** Bir dijital ajansın Pazarlama Müdürü  
**Hedefin:** Başarılı kampanyalar oluştur, yönetim kurulunu memnun et, sezonları tamamla  
**Kazanırsın:** Yüksek performans notları alarak, yönetim kurulu güvenini koruyarak  
**Kaybedersin:** Bütçe tükenerek, yönetim kurulu güveni sıfır olarak  

### 2.3 Zafer ve Yenilgi Koşulları

#### Zafer Koşulları
- Sezonu S Notu ile Tamamla (Olağanüstü)
- Tam sezon boyunca 80+ Yönetim Kurulu Güveni koru
- Seviye 10 müdür statüsüne ulaş
- 10 sezonu başarıyla tamamla

#### Yenilgi Koşulları
- Şirket bütçesi $0'a ulaşır
- Yönetim kurulu güveni %0'a düşer
- Sözleşme yönetim kurulu tarafından feshedilir

---

## 3. Temel Oyun Sistemleri

### 3.1 Sezon Sistemi 🏆

**Genel Bakış:** FM25'ten ilham alan gerçek zamanlı takipli sezonsal ilerleme

**Mekanikler:**
- **Süre**: 30 saat oynanış = 1 sezon
- **Takip**: Gerçek zamanlı oyun zamanlayıcısı (her saniye güncellenir)
- **İlerleme**: Başlıkta görsel ilerleme çubuğu
- **Sınırsız Sezonlar**: Oyuncular süresiz devam edebilir

**Sezon Akışı:**
```
Sezon Başlangıcı → Günlük Operasyonlar (30 saat) → Sezon Sonu İncelemesi → Ödüller → Yeni Sezon
```

**Sezon Sonu Değerlendirmesi:**
- **Performans Notu**: Puana göre S, A, B, C, D
- **Puanlama Formülü**:
  ```
  Puan = (Tamamlanan Görevler × 10) 
        + (Toplam Gelir / 1000)  
        + (Yönetim Kurulu Güveni × 2) 
        - (Başarısız Görevler × 15)
  ```
- **Not Eşikleri**:
  - S: 800+ puan (Olağanüstü)
  - A: 600-799 (Mükemmel)
  - B: 400-599 (İyi)
  - C: 200-399 (Orta)
  - D: 0-199 (Zayıf)

**Sezon Ödülleri:**
- $50,000 bonus bütçe
- +2,000 XP
- Sezon ilerlemesi
- Sözleşme yenileme (Yönetim Kurulu Güveni ≥ %60 ise)

**İzlenen İstatistikler:**
- Tamamlanan/Başarısız Görevler
- Başlatılan Kampanyalar
- Toplam Gelir
- Tepe/En Düşük Yönetim Kurulu Güveni
- Son Bütçe

### 3.2 Yönetim Kurulu Güven Sistemi 📊

**Genel Bakış:** Yönetim kurulu güven mekanizması (0-100%)

**Güven Seviyeleri:**
- **80-100**: Güvenli (Yeşil) - Tam güven
- **60-79**: İyi (Mavi) - Tatmin edici
- **40-59**: Endişe (Sarı) - Baskı altında
- **0-39**: Kritik (Kırmızı) - İş risk altında

**Güven Etkisi:**
- **Artar**: Görevleri tamamlamak, yüksek gelir, başarılı kampanyalar
- **Azalır**: Görevlerde başarısızlık, düşük performans, son tarihi kaçırma

**Sonuçlar:**
- **Yüksek Güven (70+)**: Sözleşme uzatmaları, bonuslar, özerklik
- **Düşük Güven (<40)**: Yönetim kurulu toplantıları, uyarılar, fesih riski

**Görüntüleme:**
- Dashboard: Büyük görsel gösterge
- Başlık: Kompakt güven çubuğu
- Aksiyonlarda gerçek zamanlı güncellemeler

### 3.3 Görev Yönetim Sistemi ✅

**Genel Bakış:** FM25 tarzı yönetim kurulu direktifleri ve hedefleri

**Görev Tipleri:**

1. **Kampanya Başlatma**
   - Gereksinim: 1+ yeni kampanya oluştur ve başlat
   - Son Tarih: 7 gün
   - Ödüller: +8 Güven, +150 XP
   - Ceza: -12 Güven

2. **Gelir Hedefi**
   - Gereksinim: $X gelir üret (zorluk tabanlı)
   - Son Tarih: 7 gün
   - Ödüller: +10 Güven, +200 XP
   - Ceza: -15 Güven

3. **SEO İyileştirmesi**
   - Gereksinim: Teknik sağlık ≥ %70
   - Son Tarih: 5 gün
   - Ödüller: +6 Güven, +100 XP
   - Ceza: -8 Güven

4. **Sosyal Medya Aktivitesi**
   - Gereksinim: 3+ sosyal gönderi yayınla
   - Son Tarih: 5 gün
   - Ödüller: +5 Güven, +80 XP
   - Ceza: -7 Güven

5. **Anahtar Kelime Araştırması**
   - Gereksinim: 5+ yeni anahtar kelime takip et
   - Son Tarih: 3 gün
   - Ödüller: +4 Güven, +60 XP
   - Ceza: -6 Güven

**Görev Yaşam Döngüsü:**
```
Atama → Aktif → [Tamamlandı/Başarısız/Gecikmiş] → Geçmiş
```

**Otomatik Tamamlama:**
- Gereksinimler karşılandığında görevler otomatik tamamlanır
- Manuel tamamlama seçeneği mevcut
- Otomatik başarısızlık ile son tarih takibi

**Görev Oluşturma:**
- Günlük ilerleme başına %30 şans
- Zorluk oyuncu seviyesi ile ölçeklenir
- Görev havuzundan rastgele seçim

### 3.4 Zaman Yönetimi ⏰

**Zaman İlerlemesi:**
- **Manuel İlerleme**: "Devam Et" butonu (1 gün ilerletir)
- **Gerçek Zamanlı Sezon**: Oyun süresi sürekli takip edilir
- **Otomatik İlerleme Yok**: Oyuncu hızı kontrol eder

**Zaman Etkileri:**
- Günlük maliyetler: Günlük $100 işletme giderleri
- Kampanya performans güncellemeleri
- Takipçi artışı
- SEO sıralaması değişiklikleri
- Görev son tarihi takibi

### 3.5 Finansal Sistem 💰

**Bütçe Yönetimi:**
- **Başlangıç Bütçesi**: $50,000 (sözleşmeye göre özelleştirilebilir)
- **Gelir Kaynakları**:
  - Kampanya geliri (değişken)
  - Müşteri hizmet bedelleri (aylık)
  - Reklam performansı (günlük)
- **Giderler**:
  - Personel maaşları
  - Reklam harcaması
  - İşletme maliyetleri (günlük $100)
  - Araç abonelikleri

**Bütçe Simülasyonu:**
```javascript
Günlük Bütçe = Önceki Bütçe - Günlük Maliyetler + Günlük Gelir
Gelir = Temel Gelir × (1 + Rastgele Dalgalanma ± %20)
```

**İflas:**
- Bütçe ≤ $0 ise Oyun Biter
- $5,000'in altında uyarı

### 3.6 Deneyim ve Seviye Atlama 📈

**XP Kaynakları:**
- Görev tamamlama: 60-200 XP
- Günlük gelir: Gelir / 100
- Sezon tamamlama: 2,000 XP

**Seviye İlerlemesi:**
- **XP Eşiği**: 1,000 XP (Seviye 1)
- **Ölçekleme**: Seviye başına Eşik × 1.2
- **Faydalar**: 
  - Zorluk artışı
  - Yeni sözleşme teklifleri
  - Kilidi açılan özellikler

**Seviye Sınırı:**
- Seviye 10 = Zafer koşulu
- Sınırsız ilerleme mümkün

---

## 4. Oyuncu İlerlemesi

### 4.1 Müdür Profili

**Müdür Özellikleri:**
- **Strateji** (10-20): Kampanya planlama etkinliği
- **Yaratıcılık** (10-20): İçerik kalitesi ve yenilik
- **Teknik** (10-20): SEO ve teknik optimizasyon
- **Liderlik** (10-20): Ekip yönetimi ve motivasyon

**İtibar Sistemi:**
- Başarılı sezonlar ile inşa edilir
- Sözleşme tekliflerini etkiler
- Endüstri tanınırlığı

### 4.2 Kariyer Yolu

**Oryantasyon Aşaması:**
1. Müdür Oluşturma: İsim, avatar, başlangıç özellikleri
2. Sözleşme Teklifleri: Başlangıç şirketi seç
3. Eğitim/İlk Adımlar

**Sezon-sezon:**
- Sezon 1-3: Öğrenme aşaması
- Sezon 4-6: Yerleşik müdür
- Sezon 7-9: Endüstri uzmanı
- Sezon 10+: Efsane statüsü

### 4.3 Sözleşme Sistemi

**Sözleşme Teklifleri:**
- Seviye atlama ile oluşturulur
- Farklı şirketler (bütçe, endüstri değişir)
- Maaş seviye ile artar

**Şirketler:**
- TechFlow Solutions (SaaS) - $80K bütçe
- PixelPulse Studios (Yaratıcı) - $60K bütçe
- DataForge Analytics (Veri) - $90K bütçe
- GreenWave Marketing (Ekolojik) - $70K bütçe

---

## 5. Oyun Modülleri

### 5.1 Dashboard (Ana Sayfa)

**Amaç:** Üst düzey genel bakış için merkezi merkez

**Elemanlar:**
- **Performans İstatistikleri**: Gelir, Kullanıcılar, Gösterimler, TO
- **Performans Trendi**: 6 aylık trend grafiği
- **Yönetim Kurulu Güveni**: Durum ile güven ölçer
- **Yönetim Kurulu Beslemesi**: Son mesajlar ve güncellemeler

**Görüntülenen Veri:**
- Toplam Gelir (trend ile)
- Aktif Kullanıcılar (trend ile)
- Gösterimler
- Ortalama TO (Tıklama Oranı)
- Yönetim kurulu güveni %

### 5.2 Yönetim Kurulu Vizyonu

**Amaç:** Stratejik planlama ve yönetim kurulu beklentileri

**Özellikler:**
- Şirket misyon beyanı
- Aylık hedefler
- Yönetim kurulu beklentileri
- Stratejik öncelikler

**İşlevsellik:**
- Çeyreklik hedefler belirle
- Yönetim kurulu duyarlılığını görüntüle
- Geçmiş performansı incele

### 5.3 Görev Yöneticisi ✅

**Amaç:** FM25 tarzı görev ve hedef takibi

**Düzen:**
- **Aktif Görevler**: Son tarihli mevcut hedefler
- **Görev Geçmişi**: Tamamlanan/Başarısız görevler
- **İstatistik Dashboard**: Tamamlanan görevler, başarısız olanlar, yönetim kurulu güveni

**Görev Kartı Bilgisi:**
- Başlık ve açıklama
- Gereksinim detayları
- Son tarih geri sayımı (gün/saat)
- Güven ödülü/cezası
- Durum göstergesi (Aktif/Tamamlandı/Başarısız)

**Aksiyonlar:**
- Manuel tamamlama butonu
- Gereksinim karşılandığında otomatik tamamlama
- Duruma göre filtreleme

### 5.4 Reklam Yöneticisi 🎯

**Amaç:** Ücretli reklam kampanyası yönetimi

**Kampanya Oluşturma (Çok Adımlı Sihirbaz):**

**Adım 1: Temel Bilgiler**
- Kampanya adı
- Hedef (Trafik/Dönüşümler/Farkındalık)

**Adım 2: Platform ve Bütçe**
- Platform seçimi (Google/Meta/TikTok)
- Günlük bütçe tahsisi

**Adım 3: Kreatif ve Hedefleme**
- Reklam formatı (Görsel/Video/Carousel)
- Hedefleme stratejisi (Geniş/İlgi/Yeniden Hedefleme)

**Kampanya Dashboard:**
- **Kampanya Listesi**: Tüm aktif kampanyalar
- **Performans Metrikleri**:
  - Gösterimler
  - Tıklamalar
  - Dönüşümler
  - TO (Tıklama Oranı)
  - TBM (Tıklama Başına Maliyet)
  - ROAS (Reklam Harcamasından Dönüş)

**Kampanya Detayları:**
- Bireysel kampanya analitikleri
- Zaman içinde performans
- Bütçe kullanımı

**İçgörüler:**
- Platform karışımı analizi
- Cihaz kullanımı dağılımı
- Optimizasyon önerileri

### 5.5 SEO Merkezi 🔍

**Amaç:** Organik arama optimizasyonu ve teknik SEO

**Site Sağlık Dashboard:**

**Sağlık Metrikleri (her biri 0-100):**
1. **Teknik Sağlık**
   - Sunucu yanıt süresi
   - Mobil optimizasyon
   - Temel Web Hayati Değerleri
   - Sorunları Düzelt butonu (düzeltme başına +5)

2. **İçerik Skoru**
   - İçerik kalitesi
   - Anahtar kelime optimizasyonu
   - İç bağlantı

3. **Backlink Profili**
   - Alan otoritesi
   - Link kalitesi
   - Link çeşitliliği

**Anahtar Kelime Yönetimi:**
- **Anahtar Kelime Araştırma Aracı**:
  - Konuya göre ara
  - Hacim metrikleri
  - Zorluk puanları (1-100)
  - Eklemek için "Takip Et" butonu

- **Takip Dashboard**:
  - Anahtar kelime sıralaması (1-100, düşük = daha iyi)
  - Hacim tahminleri
  - Zorluk seviyeleri
  - Sıralama değişim göstergeleri (↑↓ oklar)

**Teknik Sorunlar Paneli:**
- Eksik meta açıklamaları
- Yavaş sayfa hızı
- Kırık linkler (404'ler)
- Yinelenen başlık etiketleri
- Öncelik seviyeleri (YÜKSEK/ORTA/DÜŞÜK)

**SEO Simülasyonu:**
- Sıralamalar günlük değişir (±2 pozisyon)
- Teknik düzeltmeler sağlığı iyileştirir
- Anahtar kelime takibi performansı etkiler

### 5.6 Sosyal Stüdyo 📱

**Amaç:** Sosyal medya içerik oluşturma ve yönetimi

**Gönderi Oluşturma:**
- Platform seçimi (Instagram/LinkedIn/Twitter)
- Başlık yazma (metin alanı)
- Görsel/video yükleme yer tutucusu
- Viral potansiyel ölçer (0-100%)
- Şimdi yayınla veya planla

**İçerik Akışı:**
- Instagram tarzı gönderi kartları
- Platform göstergesi
- Etkileşim metrikleri (beğeniler, yorumlar)
- Görsel küçük resimler

**Takipçi Takibi:**
- **Instagram**: Başlangıç 100 takipçi
- **LinkedIn**: Başlangıç 50 takipçi
- **Twitter**: Başlangıç 20 takipçi
- Yayınlama aktivitesine dayalı büyüme simülasyonu

**Marka Duyarlılığı:**
- Genel pozitif yüzde
- Duyarlılık dağılımı (Pozitif/Nötr/Negatif)
- Dairesel gösterge görselleştirmesi
- Etkileşim oranlarına dayalı

**Takipçi Büyümesi:**
- Yeni gönderi başına +1-10 takipçi
- Platforma özel büyüme oranları
- Etkileşim viralliği yönlendirir

### 5.7 Ekip Yönetimi 👥

**Amaç:** Personel yönetimi ve kadro

**Ekip Kadrosu:**
- **Personel Üyeleri**:
  - İsim ve rol
  - Değerlendirme (FM tarzı 0-20)
  - Yıllık maaş
  - Avatar yer tutucusu

**Mevcut Ekip (Örnek):**
- Sarah Jenkins - Kıdemli Metin Yazarı (16/20) - $65K/yıl
- Mike Ross - PPC Uzmanı (14/20) - $58K/yıl
- Jessica Lee - Grafik Tasarımcı (18/20) - $72K/yıl

**Metrikler:**
- Toplam maaş bordrosu
- Ekip morali
- Beceri kapsamı

### 5.8 Personel Geliştirme 📚

**Amaç:** Eğitim ve beceri geliştirme

**Eğitim Programları:**
- **Beceri tabanlı kurslar**:
  - Analitik Ustalığı
  - Yaratıcı Düşünme
  - İleri SEO
  - PPC Optimizasyonu
  - Sosyal Medya Stratejisi

**Geliştirme Yolları:**
- Bireysel personel geliştirme
- Ekip atölyeleri
- Endüstri sertifikaları

**İyileştirme Mekanikleri:**
- Eğitim süresi: 1-4 hafta
- Maliyet: $500-$2,000
- Değerlendirme iyileştirmeleri: +1-3 puan

### 5.9 İşe Alım 🔎

**Amaç:** Yeni yetenek işe al

**İşe Alma Süreci:**
1. Mevcut adayları görüntüle
2. Değerlendirmeleri ve maaşları kontrol et
3. Teklif yap
4. Ekibe katıl

**Aday Havuzu:**
- Dinamik oluşturma
- Çeşitli beceri değerlendirmeleri
- Farklı uzmanlıklar
- Maaş beklentileri

### 5.10 İzci Ağı 🌐

**Amaç:** Pazar araştırması ve rakip analizi

**Özellikler:**
- Endüstri trendleri
- Rakip kampanyaları
- Pazar fırsatları
- Yetenek keşfi

**İstihbarat Toplama:**
- Haftalık pazar raporları
- Trend tahminleri
- Fırsat uyarıları

### 5.11 Dinamikler 😊

**Amaç:** Ekip morali ve ilişkileri

**Moral Sistemleri:**
- Bireysel mutluluk
- Ekip kimyası
- Müdür itibarı

**Olaylar:**
- Ekip çatışmaları
- Doğum günü kutlamaları
- Başarı kilometre taşları

### 5.12 Veri Merkezi 📊

**Amaç:** Derin analitik ve raporlama

**Rapor Kategorileri:**
- **Genel Bakış**: Üst düzey KPI'lar
- **Kampanyalar**: Kampanya performansı
- **Kitle**: Demografi ve davranış
- **Finansal**: Gelir ve giderler

**Görselleştirmeler:**
- Gelir vs Harcama (Çizgi grafiği)
- Kanal Dağılımı (Pasta grafiği)
- Cihaz Dönüşümü (Sütun grafiği)

**Ana Metrikler:**
- Müşteri Edinme Maliyeti (MEM)
- Yaşam Boyu Değer (YBD)
- Reklam Harcamasından Dönüş (ROAS)
- Kayıp Oranı

**Analist İçgörüleri:**
- AI tarafından oluşturulan öneriler
- Veriye dayalı öneriler
- Performans tahminleri

### 5.13 Finanslar 💵

**Amaç:** Bütçe ve işlem takibi

**Finansal Genel Bakış:**
- Mevcut bütçe (büyük görüntüleme)
- Bu ay gelir
- Bu ay giderler
- Net kar/zarar

**İşlem Geçmişi:**
- Son işlemler listesi
- Gelir vs gider kategorileştirme
- Tarih ve tutar takibi

**İşlem Tipleri:**
- Reklam geliri (gelir)
- Personel maaşları (gider)
- Reklam harcaması (gider)
- Müşteri hizmet bedelleri (gelir)

### 5.14 Strateji Merkezi 🎯

**Amaç:** Pazarlama felsefesi ve yaklaşımını tanımla

**Strateji Arketipleri:**

1. **Agresif Büyüme** (Zap ikonu)
   - Yüksek reklam harcaması
   - Hızlı kullanıcı edinme
   - Riskli kampanyalar
   - En iyisi: Startup'lar

2. **Marka Oluşturma** (Kalkan ikonu)
   - İtibar odaklı
   - Uzun vadeli değer
   - Yüksek içerik kalitesi
   - En iyisi: Yerleşik firmalar

3. **Dengeli Yaklaşım** (Aktivite ikonu)
   - Performans ve marka karışımı
   - Orta risk
   - İstikrarlı büyüme

**Stratejik Ayarlar:**
- Bütçe tahsisi (Reklamlar vs İçerik)
- Hedef kitle etiketleri
- Kampanya odak alanları

### 5.15 Fırsatlar

**Amaç:** Özel projeler ve sözleşmeler

**Fırsat Tipleri:**
- Tek seferlik projeler
- Uzun vadeli ortaklıklar
- Endüstri etkinlikleri
- Ödüller ve tanınma

### 5.16 Gelen Kutusu 📧

**Amaç:** Mesajlar ve iletişimler

**Mesaj Tipleri:**
- Yönetim kurulu direktifleri
- İK duyuruları
- Sistem bildirimleri
- Görev atamaları
- Endüstri haberleri

**Mesaj Yönetimi:**
- Okundu/Okunmadı durumu
- Öncelik işaretleme (ACİL/NORMAL)
- Tarih takibi

### 5.17 Haber Akışı 📰

**Amaç:** Endüstri haberleri ve olayları

**İçerik:**
- Pazar güncellemeleri
- Rakip aktiviteleri
- Platform değişiklikleri
- Endüstri trendleri

### 5.18 Ayarlar ⚙️

**Amaç:** Oyun yapılandırması

**Seçenekler:**
- Ses ayarları
- Zorluk ayarlaması
- Kaydet/Yükle oyun
- İlerlemeyi sıfırla

---

## 6. Kullanıcı Arayüzü

### 6.1 Tasarım Felsefesi

**Glassmorphism Estetiği:**
- Buzlu cam paneller
- İnce gölge ve bulanıklık efektleri
- Modern gradyanlar
- Temiz tipografi (Inter font ailesi)
- FM25'ten ilham alan renk paleti

**Ana İlkeler:**
1. **Netlik**: Bilgi hiyerarşisi açık
2. **Tutarlılık**: Modüller arası tekrarlayan desenler
3. **Geri Bildirim**: Tüm aksiyonlara görsel yanıtlar
4. **Erişilebilirlik**: Yüksek kontrast, okunabilir fontlar

### 6.2 Düzen Yapısı

**Ana Düzen:**
```
┌──────────┬─────────────────────────┐
│          │   Başlık                │
│ Kenar    │   (Sezon, Tarih, Stats) │
│  Çubuğu  ├─────────────────────────┤
│  (Nav)   │                         │
│          │   Modül İçeriği         │
│          │   (Dashboard/Modül)     │
│          │                         │
└──────────┴─────────────────────────┘
```

**Kenar Çubuğu Navigasyonu (260px sabit):**
- Logo/Markalama
- Yönetim bölümü
- Strateji bölümü
- Ayarlar

**Başlık (Dinamik):**
- Satır 1: Tarih, Sezon, Seviye, Zorluk, Aylık Hedef
- Satır 2: Sezon İlerleme Çubuğu

**İçerik Alanı (Esnek):**
- Tam modül render
- Kaydırılabilir içerik
- Duyarlı grid'ler

### 6.3 Renk Paleti

**Birincil Renkler:**
- `--color-accent`: #3b82f6 (Mavi) - Birincil aksiyonlar
- `--color-success`: #10b981 (Yeşil) - Pozitif göstergeler
- `--color-warning`: #f59e0b (Amber) - Dikkat/uyarı
- `--color-danger`: #ef4444 (Kırmızı) - Negatif/kritik

**Nötr Renkler:**
- `--color-bg-primary`: #ffffff (Beyaz) - Ana arka plan
- `--color-bg-secondary`: #f8f9fa (Açık gri) - İkincil arka plan
- `--color-bg-tertiary`: #f3f4f6 (Açık gri) - Üçüncül arka plan
- `--color-text-primary`: #1f2937 (Koyu gri) - Birincil metin
- `--color-text-secondary`: #6b7280 (Gri) - İkincil metin

**Gradyanlar:**
- Accent gradyan: `linear-gradient(135deg, #3b82f6, #60a5fa)`
- Success gradyan: `linear-gradient(135deg, #10b981, #34d399)`

### 6.4 Tipografi

**Font Yığını:**
- Birincil: 'Inter', -apple-system, BlinkMacSystemFont, system-ui
- Yedek: sans-serif

**Font Boyutları:**
- Hero (h1): 2.5rem / 40px
- Başlık (h2): 1.5rem / 24px
- Alt Başlık (h3): 1.25rem / 20px
- Gövde: 1rem / 16px
- Küçük: 0.875rem / 14px
- Minik: 0.75rem / 12px

**Font Kalınlıkları:**
- Normal: 400
- Orta: 500
- Yarı Kalın: 600
- Kalın: 700
- Ekstra Kalın: 900

### 6.5 Bileşenler

**Cam Kart:**
```css
background: rgba(255, 255, 255, 0.5);
backdrop-filter: blur(10px);
border-radius: 12px;
box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
border: 1px solid rgba(255, 255, 255, 0.3);
```

**Buton Stilleri:**
- Birincil: Accent rengi, beyaz metin, gölge
- İkincil: Şeffaf, kenarlık, accent metin
- Başarı: Yeşil arka plan
- Tehlike: Kırmızı arka plan

**İlerleme Çubukları:**
- Yükseklik: 8-12px
- Yuvarlak köşeler
- Gradyan dolgular
- Yumuşak geçişler

### 6.6 Modal Sistemi

**Modal Tipleri:**

1. **Görev Bildirimi:**
   - Tam ekran kaplama
   - Ortalanmış kart (500px)
   - Yönetim kurulu direktif teması
   - Animasyonlu giriş

2. **Sezon Sonu:**
   - Tam ekran devralma
   - Büyük görünüm alanı (900px)
   - Performans inceleme tasarımı
   - Nota dayalı renk teması

3. **Oyun Bitti/Zafer:**
   - Kutlama/Üzüntü ekranları
   - Aksiyon seçenekleri (Yeniden Başlat/Devam Et)

**Modal Yığını:**
- Z-index hiyerarşisi (100, 200, 300)
- Arka plan bulanıklığı
- Dışına tıklayarak kapat (bazı)

---

## 7. Sanat Yönetimi

### 7.1 Görsel Stil

**İlham:**
- Football Manager 2025 (veri yoğunluğu, profesyonel)
- macOS Big Sur (glassmorphism)
- Linear.app (modern, temiz)
- Notion (içerik hiyerarşisi)

**Özellikler:**
- **Modern**: Çağdaş web tasarımı
- **Profesyonel**: İşe uygun
- **Veri Zengin**: Gerektiğinde bilgi yoğun
- **Nefes Alma Alanı**: Cömert beyaz alan
- **Derinlik**: Bulanıklık ve gölge ile katmanlama

### 7.2 Ikonografi

**Ikon Kütüphanesi:** Lucide React
- Tutarlı 20px varsayılan boyut
- İnme tabanlı, taslak stili
- Navigasyon, aksiyonlar, göstergeler için kullanılır

**Ana İkonlar:**
- Kupa: Sezonlar
- Hedef: Hedefler/Görevler
- TrendingUp: Performans
- Takvim: Tarih
- Dolar İşareti: Para
- Kullanıcılar: Ekip
- Sütun Grafiği: Analitikler

### 7.3 Animasyon ve Hareket

**İlkeler:**
- **İnce**: Dikkat dağıtmayan
- **Amaçlı**: Dikkati yönlendirir
- **Yumuşak**: 60fps hedef
- **Hızlı**: 200-300ms geçişler

**Animasyonlar:**
- Belir: Modaller ve kaplamalar
- Yukarı kaydır: Kartlar ve bildirimler
- İlerleme çubukları: Genişlik geçişleri
- Hover durumları: Ölçek/öteleme dönüşümü

---

## 8. Teknik Mimari

### 8.1 Teknoloji Yığını

**Frontend:**
- **Framework**: React 18
- **Durum Yönetimi**: Zustand (kalıcılık ile)
- **Stillendirme**: Vanilla CSS (CSS değişkenleri)
- **İkonlar**: Lucide React
- **3D Grafikler**: React Three Fiber (@react-three/fiber)

**Yapım Araçları:**
- **Paketleyici**: Vite
- **Dil**: JavaScript (ESNext)

**Depolama:**
- **Kalıcılık**: LocalStorage (Zustand persist aracılığıyla)
- **Kayıt Anahtarı**: `dmm-save-v1`

### 8.2 Durum Mimarisi

**Global Durum (Zustand):**
```javascript
{
  // Oyun Aşaması
  gamePhase: 'ONBOARDING' | 'CONTRACT' | 'GAMEPLAY',
  
  // Müdür
  manager: { name, avatar, attributes, reputation },
  
  // Şirket
  company: { name, industry, budget },
  
  // Oyun Durumu
  date: Date,
  level: Number,
  xp: Number,
  xpThreshold: Number,
  difficulty: Number,
  
  // İçerik
  campaigns: Array,
  posts: Array,
  keywords: Array,
  tasks: Array,
  
  // Metrikler
  siteHealth: { technical, content, backlinks },
  followers: { instagram, linkedin, twitter },
  history: Array,
  
  // Yönetim Kurulu
  boardTrust: Number (0-100),
  monthlyGoal: Number,
  contractOffers: Array,
  
  // Sezon
  currentSeason: Number,
  seasonPlayTime: Number (ms),
  seasonDuration: Number (ms),
  seasonStats: Object,
  seasonHistory: Array,
  
  // UI Durumu
  showSeasonEnd: Boolean,
  pendingNotifications: Array,
  gameOver: Boolean,
  victory: Boolean
}
```

**Aksiyonlar:**
- setGamePhase, setManagerName, setCompany
- addCampaign, addPost, addKeyword, addTask
- completeTask, failTask
- advanceTime, updatePlayTime
- completeSeasonAndStartNew
- fixSiteIssue
- addXP, generateMonthlyGoal

### 8.3 Dosya Yapısı

```
src/
├── App.jsx                 # Ana uygulama ve yönlendirme
├── main.jsx               # Giriş noktası
├── index.css              # Global stiller
├── store/
│   └── gameStore.js       # Zustand durum yönetimi
├── utils/
│   └── simulationEngine.js # Oyun mantığı
├── components/
│   ├── Layout/
│   │   ├── Sidebar.jsx
│   │   └── Header.jsx
│   ├── Onboarding/
│   │   ├── ManagerCreation.jsx
│   │   └── ContractOffer.jsx
│   ├── Modals/
│   │   ├── TaskNotification.jsx
│   │   ├── SeasonEndModal.jsx
│   │   ├── GameOverModal.jsx
│   │   └── VictoryModal.jsx
│   ├── Modules/
│   │   ├── Dashboard.jsx
│   │   ├── BoardVision.jsx
│   │   ├── TaskManager.jsx
│   │   ├── AdsManager.jsx
│   │   ├── SeoCenter.jsx
│   │   ├── SocialStudio.jsx
│   │   ├── Team.jsx
│   │   ├── StaffDevelopment.jsx
│   │   ├── Recruitment.jsx
│   │   ├── ScoutingNetwork.jsx
│   │   ├── Dynamics.jsx
│   │   ├── DataHub.jsx
│   │   ├── Finances.jsx
│   │   ├── StrategyHub.jsx
│   │   ├── Opportunities.jsx
│   │   ├── Inbox.jsx
│   │   ├── NewsFeed.jsx
│   │   └── Settings.jsx
│   └── 3D/
│       └── InteractiveParticles.jsx
```

### 8.4 Simülasyon Motoru

**Günlük Hesaplama:**
```javascript
calculateDailyResults(state) {
  Temel Gelir = Bütçe × 0.02
  Dalgalanma = ±%20 rastgele
  Son Gelir = Temel × (1 + Dalgalanma)
  
  return { revenue }
}
```

**Zaman İlerlemesi:**
```javascript
advanceTime(days) {
  1. Günlük sonuçları hesapla
  2. Kampanyaları güncelle (gösterimler, tıklamalar, dönüşümler)
  3. Gönderileri güncelle (beğeniler, yorumlar yaşlanması)
  4. Anahtar kelimeleri güncelle (sıralama ±2)
  5. Takipçileri büyüt (yeni gönderi başına +1-10)
  6. Görev son tarihlerini kontrol et (geç kalırsa otomatik başarısız)
  7. Gelir görevlerini kontrol et (karşılanırsa otomatik tamamla)
  8. Yeni görevler oluştur (%30 şans)
  9. Bütçeyi güncelle (maliyetler + gelir)
  10. Ay değişikliğini kontrol et (zorluğu artır)
  11. XP ekle ve seviye atlama kontrol et
  12. Oyun bitti/zafer kontrol et
}
```

**Oyun Süresi Takibi:**
```javascript
// Her 1000ms'de (1 saniye) güncelle
setInterval(() => {
  updatePlayTime(1000);
  if (seasonPlayTime >= 30 saat) {
    showSeasonEnd = true;
  }
}, 1000);
```

### 8.5 Veri Kalıcılığı

**LocalStorage:**
- Durum değişikliklerinde otomatik kayıt
- Anahtar: `dmm-save-v1`
- JSON serileştirme
- Yüklemede hidrasyon

**Kaydedilen Veri:**
- Tüm oyun durumu (tam depo)
- Sezon geçmişi
- Görev geçmişi
- Müdür profili

---

## 9. Para Kazanma Stratejisi

### 9.1 Ücretsiz Oynanabilir Model

**Ana Oyun:** Tamamen ücretsiz

**İsteğe Bağlı Premium:**
1. **Sezon Geçişi** (sezon başına $4.99):
   - Özel avatarlar
   - Özel şirket markalaması
   - Gelişmiş analitik dashboard
   - Bekleme sürelerini atla

2. **Kariyer Modu** (tek seferlik $9.99):
   - Çoklu şirket kariyeri
   - Geçmiş sezon oynatma
   - Gelişmiş raporlama

3. **Kozmetik DLC**:
   - UI temaları ($1.99)
   - Ikon paketleri ($0.99)
   - Kutlama animasyonları

### 9.2 Reklamız Deneyim

**Seçenek:** $2.99/ay banner reklamları kaldırır (uygulanırsa)

---

## 10. Gelecek Yol Haritası

### Faz 1: Parlatma ve Dengeleme (Q1 2026)
- [ ] Eğitim sistemi
- [ ] Mobil duyarlı tasarım
- [ ] Performans optimizasyonu
- [ ] Hata düzeltmeleri ve dengeleme

### Faz 2: İçerik Genişletme (Q2 2026)
- [ ] Daha fazla görev tipi (10+ toplam)
- [ ] Ek şirketler (15+ toplam)
- [ ] Genişletilmiş ekip kadrosu (20+ pozisyon)
- [ ] Daha fazla strateji arketipi

### Faz 3: Çok Oyunculu (Q3 2026)
- [ ] Lider tablosu
- [ ] Sezon sıralamaları
- [ ] Rekabetçi mod
- [ ] Ajans vs Ajans savaşları

### Faz 4: Derin Simülasyon (Q4 2026)
- [ ] Gerçek dünya API entegrasyonları
- [ ] Gelişmiş AI rakipler
- [ ] Dinamik pazar olayları
- [ ] Endüstri trendleri simülasyonu
- [ ] Müşteri memnuniyeti sistemi

### Faz 5: Platform Genişletme (2027)
- [ ] Mobil uygulamalar (iOS/Android)
- [ ] Steam yayını
- [ ] Konsol portları (Switch/Xbox/PS)

---

## Ek

### A. Sözlük

**Terimler:**
- **Yönetim Kurulu Güveni**: Yönetimden güven metriği (0-100%)
- **Sezon**: 30 saatlik oynanış dönemi
- **Not**: Performans değerlendirmesi (S/A/B/C/D)
- **Görev**: Yönetim kurulu tarafından atanan hedef
- **Kampanya**: Ücretli reklam girişimi
- **ROAS**: Reklam Harcamasından Dönüş
- **TO**: Tıklama Oranı
- **MEM**: Müşteri Edinme Maliyeti

### B. Kontroller

**Fare:**
- Tıklama: Seç/Etkileşim
- Kaydır: Listelerde gezin
- Hover: Araç ipuçları/Önizlemeler

**Klavye:**
- ESC: Modalleri kapat
- Space: Devam Et/Zamanı ilerlet
- Tab: Navigasyon

### C. Başarımlar (Gelecek)

- İlk Sezon Tamamlandı
- Mükemmel Sezon (S Notu)
- Bütçe Milyarderi ($1M+)
- Güven Ustası (30 gün boyunca %100)
- Görev Tamamlayıcısı (100 görev)
- Sosyal Etkileyici (100K takipçi)
- SEO Uzmanı (Tüm sağlık %100)
- Kampanya Ustası (50 kampanya)
- Kariyer Efsanesi (10 sezon)
- Viral Hit (10K+ etkileşimli gönderi)

### D. Katkıda Bulunanlar

**İlham:**
- Sports Interactive (Football Manager serisi)
- Kairosoft (Game Dev Story)
- Ndemic Creations (Plague Inc.)

**Geliştirme Ekibi:**
- Tasarım ve Programlama: [Adınız]
- UI/UX Tasarım: Glassmorphism.com ilhamı
- İkonlar: Lucide React
- 3D Grafikler: React Three Fiber

---

**Doküman Versiyonu:** 1.0  
**Son Güncelleme:** 20 Kasım 2025  
**Durum:** Yaşayan Doküman - Güncellemelere tabi

---

*Bu Oyun Tasarım Dokümanı, Dijital Pazarlama Müdürü 25 için plan görevi görmektedir. Geliştirme ilerledikçe ve oyuncu geri bildirimleri dahil edildikçe gelişecek yaşayan bir dokümandır.*
