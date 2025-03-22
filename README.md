# Metro Simülasyonu Projesi
Akbank Python ile Yapay Zekaya Giriş Bootcamp

Bu projede, bir metro ağı üzerinde iki farklı algoritma kullanılarak:
- **En az aktarmalı rota** (BFS algoritması ile)
- **En hızlı rota** (A* algoritması ile)
bulunmaktadır. Amacımız, metro ağındaki rota optimizasyonunu algoritmik yaklaşımlarla çözmektir.

## Proje Hakkında
Projenin amacı, bir metro ağında iki farklı yaklaşım kullanarak:
- **BFS algoritması** ile istasyonlar arasındaki en az aktarma sayısına sahip rotayı,
- **A\*** algoritması ile toplam seyahat süresi en düşük olan en hızlı rotayı
hesaplamaktır.

## Kullanılan Teknolojiler ve Kütüphaneler
- **Python**: Ana programlama dili.
- **Collections**:
  - `deque`: BFS algoritması için kuyruk yapısı oluşturur.
  - `defaultdict`: Graf yapısını daha kolay yönetmek için kullanılır.
- **Heapq**: A* algoritmasında öncelik kuyruğu oluşturmak için kullanılır.
- **Dictionary**: İstasyonları ve metro hatlarını saklamak için kullanılır.
- **List**: İstasyonlar arası bağlantıları ve rotaları yönetmek için.
- **Set**: Ziyaret edilen istasyonların hızlı kontrolü için.
- **Tuple**: İstasyon ve süre bilgilerini birlikte depolamak için.

## Algoritmaların Çalışma Mantığı

### BFS Algoritması (En Az Aktarma)
- **Amaç**: İki istasyon arasındaki en az aktarmalı (yani en az düğüm geçişi) rotayı bulmak.
- **Çalışma Prensibi**:
  - Komşu istasyonlar, **Breadth-First Search (BFS)** yöntemiyle, genişlik öncelikli olarak keşfedilir.
  - Ziyaret edilen istasyonlar takip edilerek, kısa yol (en az aktarma) elde edilir.
- **Kullanılan Yapılar**: `deque` ile kuyruk, `set` ile ziyaret edilen istasyonlar.

### A* Algoritması (En Hızlı Rota)
- **Amaç**: Toplam seyahat süresini minimize ederek en hızlı rotayı bulmak.
- **Çalışma Prensibi**:
  - Her adımda toplam süre hesaplanarak, **A\*** algoritması yardımıyla en düşük maliyetli rota önceliklendirilmektedir.
  - `heapq` modülü ile oluşturulan öncelik kuyruğunda, en uygun rota seçilir.
- **Kullanılan Yapılar**: `heapq` ile öncelik kuyruğu, `set` ile ziyaret edilen istasyonlar.

### Bu Algoritmaların Tercih Edilme Nedeni
- Metro ağı, her bir istasyonu bir düğüm ve istasyonlar arasındaki bağlantıları bir kenar olarak modellediğinden, BFS algoritması ile en az aktarma sayısını elde etmek doğrudan probleme uygundur.
- A* algoritması, seyahat süresi gibi maliyet ölçütlerini göz önüne alarak, en hızlı yolu hesaplamak için ideal bir seçimdir.

## Örnek Kullanım
Senaryolar:
1. **AŞTİ’den OSB’ye Gitmek**
   - BFS: "Kızılay -> Ulus -> Demetevler -> OSB"
   - A*: "AŞTİ -> Kızılay -> Ulus -> Demetevler -> OSB"
2. **Batıkent’ten Keçiören’e**
3. **Keçiören’den AŞTİ’ye**

## Geliştirme Fikirleri
- **Görselleştirme**: Metro ağı ve rotaları görsel olarak temsil edecek grafiksel bir kullanıcı arayüzü entegre edilebilir.
- **Gerçek Zamanlı Bilgi**: Metro trafik bilgilerini gerçek zamanlı olarak projeye dahil etmek, A* algoritmasının daha dinamik sonuçlar üretmesini sağlayabilir.
- **Ölçeklenebilirlik**: Daha büyük ve detaylı bir metro ağı ile algoritmaların performansı test edilebilir.
- **Yeni Özellikler**: Farklı metro hatları, ek aktarma noktaları ve yolcu yoğunluğu gibi parametreler eklenerek proje geliştirilebilir.
