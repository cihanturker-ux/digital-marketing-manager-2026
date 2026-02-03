# FM25-Style Task System - Implementation Summary

## Overview
Oyununuza Football Manager 2025 tarzında bir görev sistemi ekledim. Her gün atladığınızda yeni görevler atanıyor ve bu görevleri tamamlamak/başarısız olmak Board Trust (Yönetim Kurulu Güveni) oranını etkiliyor.

## Eklenen Özellikler

### 1. **Board Trust Sistemi**
- 0-100 arası bir güven skoru
- Dashboard'da dinamik olarak gösteriliyor
- Görevlerin başarısı/başarısızlığına göre değişiyor
- Renk kodlu durum göstergeleri:
  - 80+: Secure (Yeşil)
  - 60-79: Good (Mavi)
  - 40-59: Concern (Sarı)
  - 0-39: Critical (Kırmızı)

### 2. **Otomatik Görev Oluşturma**
Her gün atladığınızda %30 ihtimalle yeni görev atanıyor. Görev türleri:

- **Launch New Campaign**: Yeni reklam kampanyası başlatma
  - 7 gün süre
  - +8 Trust (başarı), -12 Trust (başarısızlık)
  
- **Revenue Target**: Belirli gelir hedefine ulaşma
  - 7 gün süre
  - +10 Trust (başarı), -15 Trust (başarısızlık)
  
- **Improve SEO Health**: SEO sağlığını iyileştirme
  - 5 gün süre
  - +6 Trust (başarı), -8 Trust (başarısızlık)
  
- **Social Media Activity**: 3 sosyal medya postu yayınlama
  - 5 gün süre
  - +5 Trust (başarı), -7 Trust (başarısızlık)
  
- **Keyword Research**: 5 yeni keyword ekleme
  - 3 gün süre
  - +4 Trust (başarı), -6 Trust (başarısızlık)

### 3. **Görev Bildirimleri**
- Yeni görev atandığında otomatik popup gösteriliyor
- FM25 tarzında profesyonel tasarım
- Görev detayları, deadline, ödül/ceza bilgileri

### 4. **Task Manager Ekranı**
- Sidebar'da "Tasks" menüsü eklendi
- Aktif görev sayısını gösteren kırmızı badge
- Tüm aktif, tamamlanmış ve başarısız görevleri görüntüleme
- Görevleri manuel olarak tamamlama butonu
- Renk kodlu durum göstergeleri

### 5. **Otomatik Deadline Kontrolü**
- Her gün atladığınızda tüm görevler kontrol ediliyor
- Süresi dolan görevler otomatik olarak "FAILED" oluyor
- Board Trust otomatik olarak azalıyor

## Kullanım

### Görevleri Görüntüleme
1. Sidebar'dan "Tasks" menüsüne tıklayın
2. Aktif görevlerinizi, deadline'larını ve ödüllerini görün

### Görev Tamamlama

#### Otomatik Tamamlama ✨
Görevler ilgili aktiviteyi yaptığınızda **otomatik olarak tamamlanır**:

- **Campaign Task**: Yeni kampanya oluşturduğunuzda (Ads Manager)
- **Social Task**: 3 post yayınladığınızda (Social Studio)
- **Keyword Task**: 5 keyword eklediğinizde (SEO Center)
- **SEO Task**: Technical health 70'e ulaştığında (SEO Center - Fix Issues)
- **Revenue Task**: Hedef gelire ulaştığınızda (otomatik kontrol)

#### Manuel Tamamlama
Alternatif olarak Task Manager'dan "Mark Complete" butonuna da tıklayabilirsiniz.

### Board Trust Takibi
- Dashboard'da "Board Confidence" bölümünde mevcut durumu görün
- Trust çok düşerse oyun sonu riski artar

## Teknik Detaylar

### Yeni Store Özellikleri
```javascript
boardTrust: 70,              // 0-100 board güven skoru
tasks: [],                   // Tüm görevler
pendingNotifications: [],    // Gösterilecek yeni görevler
```

### Yeni Fonksiyonlar
```javascript
completeTask(taskId)         // Görevi tamamla, trust artır
failTask(taskId)             // Görev başarısız, trust azalt
addTask(task)                // Yeni görev ekle
clearPendingNotifications()  // Bildirimleri temizle
```

### Yeni Komponentler
- `/components/Modals/TaskNotification.jsx` - Görev bildirimi popup'ı
- `/components/Modules/TaskManager.jsx` - Görev yönetim ekranı

## Oyun Dinamikleri

### Board Trust Etkileri
- **Yüksek Trust (70+)**: Güvenli pozisyon, board memnun
- **Orta Trust (40-69)**: Dikkatli olun, performans bekleniyor
- **Düşük Trust (0-39)**: Tehlikeli bölge, işiniz risk altında

### Strateji İpuçları
1. Kolay görevlerle başlayın (3 gün deadline'lılar)
2. Trust'ı yüksek tutmak için görevleri zamanında tamamlayın
3. Zor görevler daha fazla trust kazandırır
4. Deadline yaklaşırken task manager'ı sık kontrol edin

## Test Senaryosu
1. Oyunu başlatın
2. Birkaç gün atlayın (Header'daki "Advance" butonu)
3. Yeni görev bildirimi popup'ını görün
4. Sidebar'daki "Tasks" menüsüne gidin
5. Görev gereksinimlerini yerine getirin
6. "Mark Complete" ile tamamlayın
7. Dashboard'da Board Trust'ın arttığını görün

## Gelecek Geliştirmeler (Opsiyonel)
- [ ] Görev önceliklendirme (yıldız sistemi)
- [ ] Görev reddetme seçeneği (trust kaybıyla)
- [ ] Özel board toplantılarında görev değerlendirme
- [ ] Başarım rozetleri (achievements)
- [ ] AI destekli görev önerileri

Bu sistem artık tam fonksiyonel ve oyununuza FM25 tarzında derinlik katıyor!
