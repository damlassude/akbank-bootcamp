
# Sürücüsüz Metro Simülasyonu (Rota Optimizasyonu)

Bu proje, bir metro ağı üzerinde verilen başlangıç ve hedef istasyonları arasında en hızlı ve en az aktarmalı rotayı bulmalarını sağlar.


## Kullanılan Teknolojiler ve Kütüphaneler

**Python 3.x:** Proje Python dilinde yazılmıştır.

**collections (defaultdict, deque):** `deque` veri yapısı BFS algoritması için kuyruk olarak kullanılmıştır. `defaultdict` ise hatlar için istasyonların listesini depolamak amacıyla kullanılmıştır.

**heapq:** A* algoritmasında öncelik kuyruğu oluşturmak için kullanılmıştır.

**typing:** Kodun daha anlaşılır olmasını sağlamak için veri tiplerini belirtmek amacıyla kullanılmıştır.
  
## Algoritmaların Çalışma Mantığı

### BFS (Breadth-First Search) Algoritması

- BFS, en kısa yolun bulunduğu algoritmalardan biridir ve burada en az aktarmalı rotayı bulmak için kullanılmaktadır.

- Algoritma, her bir istasyonu sırasıyla keşfederek hedefe ulaşmaya çalışır. Kuyruk yapısı kullanarak, her adımda bir istasyonun komşularını keşfeder ve hedef istasyon bulunana kadar bu işlemi devam ettirir.

### A* Algoritması
- Bu proje için A* algoritması, en hızlı rotayı bulmak amacıyla kullanılmıştır.

- A* algoritması, en kısa yolu bulmak için kullanılan etkili bir arama algoritmasıdır. Bu algoritma, her adımda geçilen yolu ve hedefe olan tahmini mesafeyi dikkate alır.

### Neden Bu Algoritmalar Kullanıldı?
- BFS, en az aktarmalı rotaları bulmak için mükemmeldir çünkü her adımda komşu istasyonları keşfeder ve hedefe ulaşır ulaşmaz en kısa yolu bulur.

- A* algoritması, özellikle rotalar arasındaki mesafeyi hesaplarken en düşük maliyeti (en hızlı süreyi) dikkate alır, bu yüzden zaman açısından daha verimlidir.
## Algoritmaların Çalışma Mantığı

### BFS (Breadth-First Search) Algoritması

- BFS, en kısa yolun bulunduğu algoritmalardan biridir ve burada en az aktarmalı rotayı bulmak için kullanılmaktadır.

- Algoritma, her bir istasyonu sırasıyla keşfederek hedefe ulaşmaya çalışır. Kuyruk yapısı kullanarak, her adımda bir istasyonun komşularını keşfeder ve hedef istasyon bulunana kadar bu işlemi devam ettirir.

### A* Algoritması
- Bu proje için A* algoritması, en hızlı rotayı bulmak amacıyla kullanılmıştır.

- A* algoritması, en kısa yolu bulmak için kullanılan etkili bir arama algoritmasıdır. Bu algoritma, her adımda geçilen yolu ve hedefe olan tahmini mesafeyi dikkate alır.

### Neden Bu Algoritmalar Kullanıldı?
- BFS, en az aktarmalı rotaları bulmak için mükemmeldir çünkü her adımda komşu istasyonları keşfeder ve hedefe ulaşır ulaşmaz en kısa yolu bulur.

- A* algoritması, özellikle rotalar arasındaki mesafeyi hesaplarken en düşük maliyeti (en hızlı süreyi) dikkate alır, bu yüzden zaman açısından daha verimlidir.
## Örnek Kullanım

### Test Senaryoları
#### 1.AŞTİ'den OSB'ye
- En az aktarmalı rota ve en hızlı rota, doğru şekilde hesaplanarak çıktılar sağlanmıştır.

#### 2.Batıkent'ten Keçiören'e
- Benzer şekilde, Batıkent'ten Keçiören'e olan en kısa ve en hızlı rotalar bulunmuştur.

#### 3.Keçiören'den AŞTİ'ye
- Keçiören'den AŞTİ'ye yapılan seyahat için de en az aktarmalı ve en hızlı rota bilgileri elde edilmiştir.

```javascript
# Örnek test çıktıları
# Senaryo 1: AŞTİ'den OSB'ye
    print("\n1. AŞTİ'den OSB'ye:")
    rota = metro.en_az_aktarma_bul("M1", "K4")
    if rota:
        print("En az aktarmalı rota:", " -> ".join(i.ad for i in rota))
    
    sonuc = metro.en_hizli_rota_bul("M1", "K4")
    if sonuc:
        rota, sure = sonuc
        print(f"En hızlı rota ({sure} dakika):", " -> ".join(i.ad for i in rota))
}
```

  
## Projeyi Geliştirme Fikirleri

### Dinamik Güncellemeler
- Metro hatlarında meydana gelen güncellemeler (örneğin, yeni istasyon eklemeleri veya kapalı hatlar) sistemde dinamik olarak yansıtılabilir.

### Kullanıcı Arayüzü 
- Konsol yerine görsel bir kullanıcı arayüzü ile rotalar kullanıcıya daha anlaşılır bir şekilde sunulabilir.

### Mobil Uygulama Entegrasyonu
- Bu sistemi bir mobil uygulama ile entegre ederek, kullanıcıların seyahat bilgilerini her zaman yanlarında taşıması sağlanabilir.