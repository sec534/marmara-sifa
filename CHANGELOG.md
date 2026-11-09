# Değişiklikler

## 2.1
- Altyapı sahnesindeki "Hasta dosyalarınız da güvende" notu parçacıkların üstünde okunmuyordu; cam görünümlü bir panele alındı.
- Üst menüde etkin bağlantı hatası giderildi: menüde bağlantısı olmayan sahneler (değerler, altyapı, tanı, SSS, haklar, final) ait oldukları başlığı işaretliyor.
- Yeni bölüm: **Sık sorulan sorular** (7 soru; yalnızca broşür içeriği).
- Alt bilgi dört sütunlu kurumsal bir yapıya geçti (hastanemiz, hasta rehberi, iletişim); sürüm ve kurgusal içerik notu korundu.
- İletişim bölümüne şematik yerleşke planı eklendi: ana bina, acil servis ve ayrı ambulans girişi, güneş enerjili otopark, toplanma alanı, arşiv binası.
- Telefon ve dar ekranlarda altta sabit Ara · Randevu · Acil çubuğu.
- Erişilebilirlik: "İçeriğe geç" bağlantısı, kat seçici ve tanı düğmelerinde `aria-pressed`, mobil menü açıkken arka planın kaymaması, JavaScript kapalıyken branş listesi için telefon yönlendirmesi.
- Yazdırma stili ve özel 404 sayfası.
- README yeniden yazıldı.

## 2.0
- Logo, açılıştaki çiçeğin yerine geçti: yüklenirken parçacıklardan toplanır, sallanır, fareyle itilir.
- Parçacık sayısı yaklaşık 2,5 kat arttı, noktalara parlak çekirdek eklendi, yıldızlar çoğaldı. Zayıf cihazlarda otomatik kalite düşürme.
- Yazı tipleri ve three.js depoya alındı, CSP eklendi.
- Erişilebilirlik: soluk adım yazılarının kontrastı, buton adları, başlık animasyonunun ekran okuyucu metni, telefon numaralarında bölünmez boşluk.
- Gezinme çubuğu yazısı (menü bağlantıları, Acil servis, Menü) Chakra Petch'e geçti: daha kalın ve okunaklı; menü düğmesi 1180 px altında açılıyor.
- Telefon uyumu: bazı telefonlarda sayfanın yana taşıp küçülmesi giderildi, dar ekranlarda (320 px'e kadar) gezinme çubuğu sığıyor, açılıştaki logoya kısa ekranlarda da yer ayrıldı, eski Safari için `-webkit-backdrop-filter` eklendi.
- Meta etiketleri, simge, kurgusal içerik notu ve sürüm bağlantısı.

## 1.0
- İlk yayın: broşür içeriğiyle kaydırmalı parçacık sahneleri.
