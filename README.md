# Marmara Şifa Özel Hastanesi

**Hastane tanıtım ve hasta rehberi web sitesi** · Bursa, Nilüfer

Karanlık temalı, kaydırmayla ilerleyen, WebGL parçacık animasyonlu tek sayfalık kurumsal site. İçerik "Hastane Tanıtım ve Hasta Rehberi" broşüründen alınmıştır.

> **Not:** Bu site, Bilgi Güvenliği Yönetim Sistemi (BGYS) dersi kapsamında hazırlanmış **kurgusal** bir proje çalışmasıdır. Gerçek bir sağlık kuruluşunu temsil etmez; sitedeki telefon numaraları, e-posta adresleri, adres ve kurumsal kimlik bilgileri örnektir.

**Canlı site:** https://sec534.github.io/marmara-sifa/

## Sitede neler var?

| Bölüm | İçerik |
|---|---|
| Açılış | Logodan oluşan parçacık animasyonu, randevu hattının canlı durumu (İstanbul saatiyle açık/kapalı) |
| Rakamlarla | 150 yatak, 20 yoğun bakım yatağı, 6 ameliyathane, 110 hekim, yıllık 280 bin muayene |
| Misyon, vizyon, değerler | Kurumsal ilkeler |
| Altyapı | Deprem izolatörlü yapı, kesintisiz enerji, GES, kartlı geçiş, arşiv ve sunucu odası |
| Acil, yoğun bakım, ameliyathane | 7/24 acil servis ve kritik birimler |
| Tanı birimleri | Radyoloji, laboratuvar, eczane, hasta kabul |
| Kat rehberi | Etkileşimli, 7 katlı bina; kat seçince birimler listelenir |
| Branşlar | 23 poliklinik branşı; gruba göre süzme ve Türkçe karakterlere duyarlı arama |
| Randevu | MHRS, online, telefon ve yüz yüze yollar; dört adımlık süreç; yanınızda bulundurulacaklar |
| Sık sorulan sorular | Randevu, acil, ziyaret, tetkik sonucu, KVKK, şikâyet |
| Hasta hakları ve gizlilik | Hasta hakları, hasta güvenliği, KVKK ve BGYS |
| İletişim | Ziyaret saatleri, adres ve telefonlar, şematik yerleşke planı |

## Teknik yapı

- Saf HTML, CSS ve JavaScript. Derleme adımı ve paket yöneticisi gerekmez.
- Parçacık sahneleri için [three.js](https://threejs.org) r128 (`vendor/`), yazı tipleri (`fonts/`) depoyla birlikte gelir. Ziyaretçinin tarayıcısı hiçbir dış sunucuya istek atmaz.
- Masaüstünde kaydırmayla ilerleyen sahneler; telefon, dar ekran ve "hareketi azalt" ayarında normal akışlı sayfa.
- Telefonda altta sabit **Ara · Randevu · Acil** çubuğu.

```
.
├── index.html          Güncel sürüm (2.1): sayfa, stil ve betik tek dosyada
├── 404.html            Bulunamayan sayfalar için hata sayfası
├── fonts/              Chakra Petch, IBM Plex Mono, IBM Plex Sans (woff2) ve lisansları
├── vendor/             three.js r128 ve lisansı
├── v1/                 İlk sürüm, olduğu gibi saklanıyor
├── CHANGELOG.md
└── README.md
```

## Yerelde çalıştırma

Dosyayı çift tıklayıp açmak yerine küçük bir yerel sunucu kullanın:

```bash
python -m http.server 8000
```

Sonra tarayıcıda `http://localhost:8000` adresini açın.

## GitHub Pages ile yayınlama

1. **Settings → Pages → Build and deployment → Source: Deploy from a branch**
2. Branch: `main`, klasör: `/ (root)`, **Save**
3. Birkaç dakika sonra site `https://<kullanıcı-adı>.github.io/<depo-adı>/` adresinde açılır. Eski sürüm `.../v1/` altındadır.

## Güvenlik ve gizlilik

- `index.html` içinde sıkı bir **Content-Security-Policy** (meta etiketi) vardır: yalnızca kendi dosyaları ve tek satır-içi betiğin SHA-256 özeti çalışır; `connect-src 'none'`, `form-action 'none'`, `object-src 'none'`. Betiği değiştirirseniz özetin de güncellenmesi gerekir (tarayıcı konsolu yeni özeti gösterir).
- Sitede form, çerez, analiz, izleme ya da kullanıcı verisi toplayan bir bileşen yoktur. `localStorage` kullanılmaz.
- `no-referrer` açıktır.
- Kurgusal içerik arama sonuçlarında çıkmasın diye `noindex, nofollow` açıktır. İstemezseniz `index.html` başındaki `robots` meta satırını silin.
- GitHub Pages özel HTTP başlığı eklemeye izin vermez; bu yüzden `frame-ancestors` ve HSTS gibi başlıklar meta etiketiyle verilemez.
- `v1/` klasörü ilk sürümü olduğu gibi saklar; bu sürüm Google Fonts ve cdnjs kullanır.

## Erişilebilirlik

- "İçeriğe geç" bağlantısı, klavye ile tüm kontrollere erişim, görünür odak halkası
- Ekran okuyucu için başlık animasyonunun düz metin karşılığı, düğmelerde `aria-pressed` durumu
- Yeterli renk karşıtlığı; telefon numaralarında bölünmez boşluk
- `prefers-reduced-motion` ayarına saygı; yazdırma stili

## Performans

- Parçacık sayısı cihaza göre seçilir (telefon 14 bin, zayıf masaüstü 26 bin, diğerleri 38 bin). İlk saniyelerde kare hızı düşükse sayı otomatik azaltılır.
- Adrese `?hq` eklenirse otomatik azaltma kapanır.

## Sürümler

| Sürüm | Git etiketi | Konum |
|---|---|---|
| **2.1** (güncel) | `v2.1` | `/` |
| 2.0 | `v2.0` | Git geçmişinde |
| 1.0 | `v1.0` | `/v1/` |

Ayrıntılar için [CHANGELOG.md](CHANGELOG.md).

## Lisanslar

- three.js r128: MIT (`vendor/LICENSE-three.txt`)
- Chakra Petch, IBM Plex Mono, IBM Plex Sans: SIL Open Font License 1.1 (`fonts/LICENSE-*.txt`)
