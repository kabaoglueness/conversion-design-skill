---
name: conversion-design
description: Use when designing, reviewing, building, or refactoring web interfaces, landing pages, SaaS apps, e-commerce, forms, or checkout flows to ensure visual hierarchy, corporate brand consistency, cognitive clarity, and ruthless conversion optimization without AI slop.
---

# Conversion design & field heuristics

Bu kural seti web arayüzlerinde görsel hiyerarşi kurmak, bilişsel sürtünmeyi sıfırlamak, yapay zeka tasarım klişelerini (AI slop) engellemek ve kullanıcıyı doğrudan hedeflenen eyleme yönlendirmek için kullanılır.

Canlı saha deneyimlerinden, kullanıcı düzeltmelerinden ve finansal/analitik terminal arayüz standartlarından çıkarılan kesin kuralları içerir.

---

## 1. Temel iletişim ve çalışma şekli

- Kullanıcıya boş övgüde bulunmayın ("harika fikir", "mükemmel vizyon" yasaktır).
- Tasarımda veya akışta dönüşümü düşüren, bilişsel yük yaratan bir hata varsa doğrudan belirtin ve düzeltin.
- Sonuç odaklı çalışın. Süreci anlatmak yerine doğrudan çalışan kod verin.

### Kurumsal kimlik sorma kuralı (Brand intake)
Projeye başlarken veya arayüz tasarımı yaparken projede tanımlı bir `BRAND.md` yoksa ve kullanıcı bir marka kılavuzu vermemişse, **doğrudan tasarıma geçilmez**. Önce şu 3 soru ile kurum kimliği belirlenir:
1. **Kurum tonu:** Katı kurumsal güven mi, analitik teknik mi, yoksa dinamik/samimi mi?
2. **Hedef kitle:** Şirket yöneticileri (B2B) mi, son kullanıcı (B2C) mi, mühendisler mi?
3. **Renk ve referans:** Varsa kurumun ana rengi nedir veya referans aldığınız bir marka var mı?

Alınan cevaplar `BRAND.md` dosyasına kaydedilir ve tüm renk, tipografi, görsel hiyerarşi bu dosyaya göre şekillendirilir.

---

## 2. Kesin AI Slop ve tasarım sahteciliği yasakları

Aşağıdaki kalıplar yapay zeka modellerinin ezbere ürettiği ve arayüzü amatörleştiren hatalardır, kesinlikle yasaktır:

1. **Kicker etiketleri ve büyük harf gürültüsü:** Başlıkların üstüne eklenen minik büyük harfli etiketler (`text-xs font-semibold uppercase tracking-wider`) yasaktır (Örnek: "SIKÇA SORULANLAR" yazıp altına "Sıkça Sorulan Sorular" başlığı koymak). Başlık ne olduğunu doğrudan anlatmalıdır.
2. **Baloncuklu geometrik sans fontlar:** Kalın ağırlıklarda (`font-bold`, `font-extrabold`) `Poppins` gibi aşırı dairesel oyuncak fontlar kurumsal arayüzü ucuz mobil oyuna çevirir. Kurumsal gövdede saf nötr `Inter` veya `Plus Jakarta Sans`, başlıklarda ise sektöre göre tırnaklı serif (`Cormorant Garamond`, `Newsreader`) veya keskin teknik sans (`Space Grotesk`, `Clash Display`, `Geist`) kullanılır.
3. **Monospace ayaklı fontlar:** B2B kokpitte veya butonlarda `JetBrains Mono` veya slab-serif monospace fontlar kullanılmaz. Rakam tablolarında sadece `font-variant-numeric: tabular-nums` (veya `tabular-nums`) uygulanır.
4. **Hayali Tailwind sınıfları (Hallucinated classes):** Tailwind ölçeğinde olmayan `pl-8.5` gibi hayali sınıflar yazıp arama ikonunu metnin üstüne bindirmek yasaktır. Standart `pl-9` (36px) veya `pl-10` kullanılmalıdır.
5. **Aksiyon sahteciliği (False promise links):** Kullanıcıya "Başvur" veya "Satın Al" deyip genel bir arama motoru ana sayfasına fırlatmak yasaktır. Link ya doğrudan hedefe gitmeli ya da ne yaptığı şeffaf yazılmalıdır.
6. **Ölü veri kutuları (Eylemsiz estetik):** Dashboard'da tıklandığında hiçbir şey yapmayan kartlar yasaktır. "Kritik Stok: 1" yazıyorsa tıklandığında doğrudan o ürünü filtrelemeli ve düzenleme alanını açmalıdır. Her metrik kartı bir aksiyon tetikleyicisidir.
7. **Gereksiz animasyon ve emojiler:** Arayüz metinlerinde emoji kullanmak yasaktır. Rozetlerdeki kontrolsüz yanıp sönmeler (`animate-pulse`) yalnızca kritik anlık canlı veri akışlarında (örn. finansal borsa veya canlı sinyal rozeti) sınırlandırılmalıdır; statik buton ve kartlarda kullanılmaz.
8. **Uzun tire ve yapay jargon:** Cümle ortalarında uzun tire (`—`, em-dash) ve İngilizce LLM çevirisi olan yapay jargonlar kullanılmaz. Düz, net Türkçe cümleler kurulur.

---

## 3. Tipografi DNA'sı ve OpenType karakter hassasiyeti

Sektörel ve analitik derinliği olan arayüzlerde şu tipografi standartları uygulanır:

1. **Display & Teknik Başlık Fontları:** Sayısal veriler, KPI blokları ve ana başlıklarda geometrik/teknik keskinlik taşıyan `Space Grotesk` veya `Clash Display` tercih edilir (`font-display`).
2. **Gövde ve Veri Tabloları:** Yüksek okunabilirlik için `Plus Jakarta Sans` veya `Inter` kullanılır.
3. **OpenType Karakter Ayrımı (`font-feature-settings`):** Sayısal veri ve küçük puntolu teknik tablolarda rakamların ve karakterlerin birbirine karışmaması için gövdeye şu kural uygulanır:
   ```css
   font-feature-settings: "cv02", "cv03", "cv04", "cv11";
   ```
4. **Tipografik Ölçek:**
   - Mikro etiket ve formül dipnotu: `text-[10px]` / `text-[11px]`
   - Tablo başlıkları ve meta veri: `text-xs font-semibold`
   - Bileşen başlıkları: `text-base font-bold`
   - KPI metrik rakamları: `text-3xl font-display font-bold tabular-nums`

---

## 4. Renk dağılımı ve analitik yüzey hiyerarşisi

Finansal terminaller, analitik gösterge panelleri ve karanlık temalarda katı 60-30-10 kuralı ve derinlik seviyeleri uygulanır:

| Katman | Renk / Token | Kullanım Alanı |
|---|---|---|
| **Ana Canvas (%60)** | `#0b0f17` veya `#09090b` | Sayfa zemin rengi, yapışkan header alt tabanı. Katı siyah (`#000000`) kullanılmaz. |
| **Yapısal Paneller (%30)** | `rgba(17, 24, 39, 0.7)` (`backdrop-blur-md`) | Cam kartlar (glass-card), alt taban (`#080c14`). |
| **Kenarlık ve Ayırıcılar** | `rgba(255, 255, 255, 0.08)` | Hover durumunda `0.16` opaklığa çıkar. |
| **Aksiyon & Veri Sinyalleri (%10)** | Zümrüt (`#10b981`), Camgöbeği (`#06b6d4`), Amber (`#f59e0b`) | Birincil butonlar, pozitif/negatif getiri göstergeleri, aktif filtre düğmeleri. Mor-indigo gradient kullanılmaz. |

---

## 5. Çoklu seri zaman grafikleri ve KPI kart ergonomisi

Analitik ve gösterge panellerinde görselleştirme standartları:

1. **4 Sütunlu KPI Izgarası:** Metrik kartları (`grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4`) standart üçlü hiyerarşiyle çizilir:
   - Üst satır: Metrik adı ve teknik niteleyici etiket (`text-xs text-slate-400 font-medium`).
   - Değer alanı: Büyük sayısal veri (`text-3xl font-display font-bold text-white tabular-nums`).
   - Alt satır: Yüzdelik değişim, yön işareti ve açıklama metni.
2. **Grafik Çizgi Ayrımı:**
   - Ana gösterge çizgisi: Canlı zümrüt yeşili (`#10b981`), 2px kalınlık, altında hafif degrade dolgu (`rgba(16, 185, 129, 0.08)`).
   - İkincil seri: Camgöbeği (`#06b6d4`), 1.8px kesikli çizgi (`borderDash: [4, 4]`).
   - Resmi/Referans seri: Nötr gri (`#64748b`).
3. **Zaman Aralığı Seçicileri (Dilimleyici):** 30 Gün, 60 Gün, Tümü gibi butonlar anlık veri dilimleme (`slice(-limit)`) ile grafiği anında günceller. Aktif buton `bg-emerald-500/20 text-emerald-300 border border-emerald-500/40` ile ayrılır.

---

## 6. Boşluk ve grid kuralları (Gestalt yakınlığı)

- Etiket ve giriş kutusu arası 6px (`gap-1.5`) veya 8px (`gap-2`) tutulur.
- Başlık ve altındaki açıklama metni arası 8px (`gap-2`) tutulur.
- Form satırları arasındaki mesafe en az 24px (`gap-6`) yapılır.
- Paragrafların satır genişliği 75 karakteri geçemez (`max-w-prose` veya `max-w-2xl`).
- Bölümler arası dikey boşluk mobilde `py-16`, masaüstünde `py-24` yapılır.

---

## 7. Mobil ve duyarlı ekran mimarisi (Responsive safeguards)

- **Üst bar boğulması engeli:** Mobilde (375px - 414px) logo, arama kutusu ve sayaç tek satıra sıkıştırılamaz. Mobilde 2 satır (`flex flex-col sm:flex-row`) kullanılır; birinci satırda marka ve sayaç, ikinci satırda tam genişlik arama kutusu yer alır.
- **Taşma koruması:** Yatay buton ve sekme gruplarında `whitespace-nowrap shrink-0` kullanılır.
- **Dokunma alanı:** Mobilde tüm buton ve tıklanabilir öğeler en az 44x44px dokunma alanına sahip olmalıdır (Apple HIG).
- **Sayfa geçişi kaydırma sıfırlaması:** Tek sayfa geçişlerinde ekranın altta asılı kalmaması için geçiş anında `window.scrollTo({ top: 0, behavior: 'instant' })` tetiklenir.

---

## 8. Form ve sürtünme ergonomisi

- İsim ve soyisim için iki ayrı kutu açılmaz. Tek bir `Ad Soyad` kutusu kullanılır.
- Kullanıcı formu gönderdikten sonra toplu hata gösterilmez. Kullanıcı kutudan çıktığı an (onBlur) doğrulama yapılır.
- E-posta için `type="email"`, telefon için `inputmode="numeric"`, şifre kutusu için görünürlük butonu eklenir.

---

## 9. E-ticaret ve sepet kuralları

- Satın alma öncesi zorunlu üyelik veya şifre istemek yasaktır. Misafir alışverişi sunulur. Şifre belirleme sipariş sonrasına bırakılır.
- Kargo ve vergi ücretleri ödeme adımına saklanmaz, sepette baştan gösterilir.
- Ödeme butonunun altına SSL ve kart güvenlik ikonları eklenir.
- Mobilde ürün sayfasında gezinirken "Sepete Ekle" butonu ekranın altına sabitlenir (`sticky bottom-0`).

---

## 10. Tablo ve yönetim paneli kuralları

- Sayılar ve para birimleri sağa yaslanır (`text-right tabular-nums`). Metinler sola yaslanır.
- Tablo başlığı kaydırma sırasında üstte sabitlenir (`sticky top-0`).
- İşlem butonları satırın üzerine gelindiğinde görünür yapılır.
- Boş tablolarda sadece "Veri yok" yazılmaz. Yeni veri ekleme veya filtre sıfırlama butonu gösterilir.

---

## 11. Fiyatlandırma psikolojisi ve geri bildirim

- **Öne çıkan paket:** Üç paketten ortadaki paket belirginleştirilir (`scale-105`), birincil renkli buton sadece ona verilir. Yıllık seçimde net kazanç ("2 ay bedava") yazılır.
- **Anlık geri bildirim:** Butona basıldığında 1.5 saniye onay simgesi gösterilir. Başarılı işlemlerde 3 saniye sonra kaybolan sade toast bildirimi açılır.

---

## 12. 16 Kapılı otonom denetim listesi (Linter)

Kod teslim edilmeden önce denetçi ajan şu 16 soruyu kontrol eder:
1. Kod, projede belirlenen `BRAND.md` kurum tonu ve renk kimliği ile yüzde 100 eşleşiyor mu?
2. Başlıkların üstünde gereksiz büyük harfli kicker etiketleri var mı? (Varsa silinmeli)
3. Kalın ağırlıklarda baloncuklu oyuncak sans kullanılmış mı?
4. Sayısal veri veya KPI alanlarında `Space Grotesk` / `Clash Display` keskinliği ve `font-feature-settings: "cv02", "cv03", "cv04", "cv11"` uygulanmış mı?
5. Tailwind ölçeğinde olmayan hayali sınıflar (`pl-8.5` vb.) var mı ve ikonla metin çakışıyor mu?
6. Ekranda birden fazla renkli işlem butonu yarışıyor mu?
7. Ana butonun altında güvence metni var mı?
8. Eylemsiz estetik kartlar (tıklanınca işlem yapmayan ölü istatistikler) var mı?
9. Arayüz metinlerinde emoji veya statik butonlarda parıldayan animasyonlar var mı?
10. Metinlerde uzun tire (`—`) veya yapay çeviri jargonu var mı?
11. Mobilde üst bar öğeleri sıkışıp dışarı taşıyor mu?
12. Butonlar mobilde en az 44x44px dokunma alanına sahip mi?
13. Boş ekranda kullanıcıyı eyleme geçiren buton var mı?
14. Çoklu grafik serilerinde zümrüt/camgöbeği/gri hiyerarşisi korunmuş mu?
15. E-ticarette zorunlu üyelik istenmiş mi?
16. Yanıtta gereksiz iltifat veya dolaylı ifade var mı?
