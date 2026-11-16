---
name: conversion-design
description: Use when designing, reviewing, building, or refactoring web interfaces, landing pages, SaaS apps, e-commerce, forms, or checkout flows to ensure visual hierarchy, corporate brand consistency, cognitive clarity, and ruthless conversion optimization without AI slop.
---

# Conversion Design & Corporate Visual Hierarchy

Tasarım süsleme veya keyfi estetik değildir; bilişsel sürtünmeyi sıfırlayıp ziyaretçiyi en kısa yoldan eyleme (satın alma, kayıt olma, checkout, dashboard kararı) geçirme mühendisliğidir.

---

## 1. TEMEL İLETİŞİM VE ÇALIŞMA KURALI (SIFIR YAĞLAMA)

- **İltifat Yasağı:** Tasarım kararlarında kullanıcıya "harika fikir", "mükemmel vizyon" gibi içi boş övgüler dizilmez.
- **Doğrudan Cerrahi Eleştiri:** Tasarımda veya akışta dönüşümü düşürecek, kurumsallığı zedeleyecek veya bilişsel yük yaratacak bir hata varsa doğrudan, gerekçesiyle söylenir ve düzeltilir.
- **Sonuç Odaklılık:** Konuşma değil; test edilebilir, çalışan ve ölçülebilir kod/arayüz üretilir.

---

## 2. PSİKOLOJİK DÖNÜŞÜM MİMARİSİ (CONVERSION ANATOMY)

Bir sayfa yukarıdan aşağıya rastgele kart dizilimi değildir. İnsan psikolojisine dayalı zorunlu bir ikna omurgası takip edilir:

```
[HERO: 3 Saniyelik Değer Vaadi + Tek Primary CTA + Risk Reversal]
                         ↓
[SOSYAL KANIT: Gerçek Metrikler, Marka Logoları, Güven Çubuğu]
                         ↓
[PROBLEM & ÇÖZÜM: Gerçek Ürün Arayüzü / Etkileşimli Kanıt]
                         ↓
[DEĞER KARŞILAŞTIRMASI: Eski/Acılı Yol vs Sizin Sunduğunuz Kolay Yol]
                         ↓
[EYLEM & FİYATLANDIRMA: Sürtünmesiz Seçim + Net Getiri]
                         ↓
[İTİRAZ GİDERME (SSS): Satın almayı engelleyen son şüpheleri yok etme]
                         ↓
[SON ÇAĞRI (STICKY / FOOTER CTA): Fırsatı kaçırmama kapanışı]
```

### 2.1. Viewport Başına Tek Primary CTA Kuralı
- Her görünüm alanında (ekranda) yalnızca **BİR ADET** birincil aksiyon butonu (Primary CTA) bulunabilir.
- İkinci bir buton gerekiyorsa görsel ağırlığı tamamen düşürülmüş (Ghost / Subtle Outline / Text link) olmak zorundadır.
- İki adet parlayan renkli buton yan yana konulamaz; bu bilişsel felç (choice paralysis) yaratır.

### 2.2. Risk Tersine Çevirme (Risk Reversal Placement)
- Güven unsurları sayfanın dibine saklanmaz.
- Her Primary CTA butonunun tam 6-8px altında mikro-güvence kopyası bulunmalıdır:
  - *Örnek:* "Kredi kartı gerekmez • 14 gün ücretsiz deneme • 2 dakikada kurulum"

### 2.3. Eylem Odaklı Mikro-Kopya (CTA Microcopy)
- "Gönder", "Tıkla", "Devam Et" gibi belirsiz ve pasif kelimeler yasaktır.
- Buton metni kullanıcının elde edeceği somut faydayı belirtmelidir:
  - ❌ Yanlış: "Kayıt Ol"
  - ✅ Doğru: "Ücretsiz Çalışma Alanını Başlat"
  - ❌ Yanlış: "Gönder"
  - ✅ Doğru: "Teklifimi İncele ve İndir"

---

## 3. 60-30-10 KURUMSAL RENK VE TOKEN DİSİPLİNİ

Yapay zekanın rastgele gradient ve neon renk basma eğilimi tamamen engellenir:

| Oran | Kullanım Alanı | Tanım |
|------|----------------|-------|
| **%60 (Baskın Zemin)** | Sayfa arka planı, geniş canvas | Derin nötrler: Slate/Zinc (`bg-background`, `#09090b` veya `#0f172a` koyu; `#f8fafc` veya `#ffffff` açık). Asla çiğ zifiri siyah (`#000000`) kullanılmaz. |
| **%30 (Yapısal Kontrast)** | Kartlar, sidebar, border'lar, tipografi | Zeminle kontrast oluşturan yüzeyler (`bg-card`, `border-border/60`, `text-muted-foreground`). |
| **%10 (Aksiyon / Dönüşüm)** | SADECE Primary CTA, kritik bildirim | Markanın canlı vurgu rengi (Primary / Accent). Bu renk arka planlara, kart kenarlıklarına veya süsleme şekillerine dağıtılarak harcanamaz. Kutsaldır; sadece aksiyonu çeker. |

> [!WARNING]
> Mor-indigo gradient kombinasyonları, neon glowing border'lar ve cam efekti (glassmorphism) aşırılığı yasaktır.

---

## 4. GESTALT BOŞLUK VE GRİD SİSTEMİ (PROXIMITY)

Yapay zeka tüm öğelere eşit `gap-4` dağıtarak hiyerarşiyi öldürür. Katı Gestalt yakınlık kuralı uygulanır:

- **İlişkili Elemanlar (Sıkı - 4px/8px):**
  - Form Label + Input: `gap-1.5` (6px)
  - Başlık + Alt Açıklama: `gap-2` (8px)
  - Avatar + Kullanıcı Adı: `gap-2.5` (10px)
- **Grup Ayrımı (Geniş - 24px/32px):**
  - Bir form satırı ile sonraki grup arası: `space-y-6` veya `gap-6` (İlişkili elemanların en az 3-4 katı mesafe).
- **Bölüm (Section) Mesafeleri:**
  - Bölümler arası dikey nefes alanı: `py-16` (mobil) ve `py-24` ila `py-32` (masaüstü). Sıkışık sayfalar ucuz görünür ve güven vermez.
- **Konteyner Genişliği:**
  - Okuma blokları: `max-w-prose` (45-75 karakter).
  - Arayüz blokları: `max-w-5xl` veya `max-w-7xl` merkezli (`mx-auto px-4 sm:px-6 lg:px-8`).

---

## 5. TİPOGRAFİK RİTİM, MODÜLER ÖLÇEK VE SEKTÖREL MARKA FONT EŞLEŞTİRMESİ

### 5.1. "AI Fontu" (Jenerik Font) Yasağı
Yapay zeka varsayılan olarak her projeye körü körüne standart sistem sans-serif veya jenerik Inter basar. Bu durum kurumsal kimliği öldürür ve "AI prototipi" hissi verir. Bir projenin sektörüne, güven ihtiyacına ve hedef kitlesine göre karakteri olan tipografi seçilmelidir:

| Sektör / Karakter | Başlık Fontu (Display) | Gövde Fontu (Body) | Hissiyat & Güven Faktörü |
|---|---|---|---|
| **Fintech, Bankacılık, Hukuk** | *Newsreader* / *Playfair Display* (Serif) | *Plus Jakarta Sans* / *Inter Tight* | Köklü, prestijli, kurumsal ve tavizsiz güven |
| **B2B SaaS, Veri, Mühendislik** | *Geist* / *Space Grotesk* | *Geist Sans* / *IBM Plex Sans* | Keskin, analitik, modern ve hassas |
| **Lüks, Moda, Özel Tüketim** | *Cormorant Garamond* / *Cinzel* | *Satoshi* / *General Sans* | Rafine, zarif, yüksek marjlı ürün algısı |
| **Developer Tools & Altyapı** | *JetBrains Mono* / *Fira Code* | *Inter* / *Space Grotesk* | Teknik yeterlilik, şeffaflık, mühendis dili |
| **Genel Tüketici & E-Ticaret** | *Cabinet Grotesk* / *Clash Display* | *Switzer* / *Plus Jakarta Sans* | Canlı, dinamik, arkadaş canlısı ve eyleme geçiren |

> [!IMPORTANT]
> Sadece CDN'den font adı çağırmak yetmez; fontun optik ağırlığı (`font-feature-settings: "cv02", "cv03", "cv04", "cv11"` veya `font-weight: 700/800`) ve harf aralığı (`tracking-tight` display başlıklarda, `tracking-normal` gövdede) disiplinle uygulanmalıdır.

### 5.2. Tipografik Modüler Ölçek
- **Ölçek:** Keyfi piksel değerleri yerine modüler oran (Major Third: 1.25) kullanılır:
  - Display / H1: `text-4xl sm:text-5xl lg:text-6xl tracking-tight font-extrabold leading-[1.1]`
  - H2 (Bölüm Başlığı): `text-2xl sm:text-3xl font-bold tracking-tight leading-tight`
  - H3 (Kart Başlığı): `text-lg sm:text-xl font-semibold leading-snug`
  - Gövde (Body): `text-base text-muted-foreground leading-relaxed`
  - Mikro-Kopya (Legal / Badge): `text-xs font-medium uppercase tracking-wider`
- **Satır Uzunluğu Sınırı:** Hiçbir açıklama metni 75 karakterden daha geniş alana yayılamaz (`max-w-2xl` veya `max-w-prose`).

---

## 6. FORM VE SÜRTÜNME ERGONOMİSİ (FRICTION ELIMINATION)

Satış veya dönüşüm formda gerçekleşir; sürtünme dönüşümü öldürür:

1. **Alan Sayısı Katliamı:** Her ekstra input alanı dönüşümü %10-25 düşürür. Ad ve Soyad tek input'tur (`Ad Soyad`). Şirket adı, unvan gibi kritik olmayan sorular sonraya bırakılır.
2. **Anlık Doğrulama (Inline / onBlur):** Kullanıcı formu submit ettikten sonra kırmızı hata yağmuru göremez. Her input'tan çıktığında (blur) doğrulama anında yeşil onay ikonu veya spesifik düzeltme mesajı verir.
3. **Mobil Klavye Uyumu:**
   - E-posta için: `type="email" autocomplete="email"`
   - Telefon / Kod için: `inputmode="numeric" pattern="[0-9]*"`
   - Şifre için: Göz (show/hide) toggle ikonu zorunludur.
4. **Hata Mesajı Standardı:** "Geçersiz değer" değil; "Lütfen geçerli bir kurumsal e-posta girin (örn: ad@sirket.com)" şeklinde yol gösterici olmalıdır.

---

## 7. E-TİCARET & CHECKOUT SÜRTÜNME MÜHENDİSLİĞİ (CHECKOUT CONVERSION)

E-ticarette sepet terk edilme oranını (%70+) düşürmek için şu kurallar tavizsizdir:

1. **Misafir Alışverişi Zorunluluğu (Guest Checkout First):** Satın alma öncesi zorunlu hesap açtırma veya şifre belirletme yasaktır. Kullanıcı alışverişini tamamlar; teşekkür sayfasında "Tek tıkla siparişini takip etmek için şifre belirle" denir.
2. **Tek Sayfa / Akordeon Checkout:** Sayfa yenilenmeleri ve çok adımlı yönlendirmeler bilgi kaybı korkusu yaratır. Kargo ve ödeme tek ekranda netleşmelidir.
3. **Kargo & Gizli Masraf Şeffaflığı:** Kargo veya vergi bedeli son ödeme adımına saklanamaz. Sepet özeti bileşeninde ilk andan itibaren net yazılmalıdır.
4. **Ödeme Güven Çapası (Trust Anchor):** "Siparişi Tamamla" butonunun hemen altına 3D Secure, 256-Bit SSL ve kabul edilen kart ikonları yerleştirilmelidir.
5. **Mobil Sabit Satın Alma Çubuğu (Sticky Bottom Bar):** Mobilde ürün detay sayfasında kullanıcı aşağı kaysa bile fiyat ve "Sepete Ekle" butonu ekranın en altında sabit kalmalıdır (`sticky bottom-0 z-50 p-4 bg-background/95 backdrop-blur border-t`).

---

## 8. DASHBOARD & VERİ YOĞUNLUĞU MİMARİSİ (HIGH-DENSITY UI)

Yapay zeka panellerde her yeri rengarenk grafiklerle doldurarak gürültü yaratır:

1. **Sinyal/Gürültü Oranı (Signal-to-Noise Ratio):**
   - Normal/stabil metrikler nötr tonlarda (`text-zinc-400` / `bg-zinc-800/50`) durur.
   - Sadece eylem gerektiren anomaliler (düşen satış, geciken sipariş, sistem hatası) vurgu rengi alır.
2. **Tablo Ergonomisi:**
   - Sayısal ve para verileri DAİMA sağa yaslanır (`text-right tabular-nums font-mono`).
   - Metinler sola yaslanır (`text-left`).
   - Başlık satırı ekranda sabitlenir (`sticky top-0 bg-background/95 backdrop-blur`).
   - Aksiyonlar her satırda kalabalık butonlar olarak değil, satır hover olduğunda beliren cerrahi ikonlar olarak görünür (`opacity-0 group-hover:opacity-100 transition-opacity`).
3. **Eyleme Geçiren Boş Durumlar (Actionable Empty States):**
   - Boş tabloda veya grafikte sadece "Veri bulunamadı" yazmak yasaktır.
   - Doğrudan ilk veriyi oluşturacak buton yerleştirilir: "Henüz müşteri yok. [İlk Müşteriyi Ekle]"
4. **Arama ve Hızlı Gezinme (Command Palette):**
   - 10 farklı filtre kutusu yerine `Cmd+K` / `Ctrl+K` global arama ve odaklı segment filtreleri (`all`, `active`, `pending`) sunulmalıdır.

---

## 9. BİLEŞEN DURUM BÜTÜNLÜĞÜ (STATE PARITY & AFFORDANCE)

Bir buton veya etkileşimli kart sadece statik bir kutu olamaz. 5 durumu eksiksiz kodlanmalıdır:

```tsx
// Örnek Standart Dönüşüm Butonu (Tailwind)
<button
  disabled={isLoading}
  className="
    relative inline-flex items-center justify-center font-semibold rounded-lg
    px-6 py-3 text-base text-primary-foreground bg-primary
    shadow-sm shadow-primary/20
    hover:bg-primary/90 hover:shadow-md hover:shadow-primary/30
    active:scale-[0.98]
    focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-primary focus-visible:ring-offset-2
    disabled:opacity-60 disabled:cursor-not-allowed disabled:scale-100
    transition-all duration-150 ease-in-out
  "
>
  {isLoading ? (
    <Spinner className="w-5 h-5 mr-2 animate-spin" />
  ) : (
    <>
      <span>{label}</span>
      <ArrowRight className="w-4 h-4 ml-2 transition-transform group-hover:translate-x-1" />
    </>
  )}
</button>
```

---

## 10. GÖRSEL KANIT VE GERÇEK ÜRÜN ARAYÜZÜ

- **Soyut Çizim Yasağı:** Uçuşan anlamsız küpler, jenerik AI kadın/erkek çizimleri veya stok fotoğraflar güven vermez.
- **Gerçek Ürün UI:** Ürünün gerçek paneli, canlı hesaplama widget'ı, kod önizlemesi veya gerçek ekran görüntüsü çerçeveli (`rounded-xl border shadow-2xl`) sunulmalıdır.
- **Mikro Metrikler:** "Binlerce mutlu müşteri" yerine "2.840+ şirket tarafından aktif kullanılıyor" şeklinde spesifik sayılar verilmelidir.

---

## 11. 60 SANİYELİK DÖNÜŞÜM VE TASARIM DENETİMİ (SELF-AUDIT LINTER)

Her sayfa, bileşen veya revizyon teslim edilmeden önce bu 10 kapıdan geçmek ZORUNDADIR:

- [ ] **1. Viewport Çatışması:** Ekranda aynı anda iki farklı baskın renkli CTA yarışıyor mu? (Varsa -> Biri ghost yapılmalı)
- [ ] **2. Risk Kırıcı:** Primary CTA'nın 8px altında mikro güvence (kredi kartsız, iade vb.) var mı? (Yoksa -> Ekle)
- [ ] **3. Satır Taşıması:** Paragraflar `max-w-prose` aşarak ekran boyunca uzuyor mu? (Uzuyorsa -> Sınırla)
- [ ] **4. 60-30-10 Disiplini:** Aksiyon rengi buton dışındaki alakasız süslemelerde harcanmış mı? (Harcanmışsa -> Temizle)
- [ ] **5. Form Sürtünmesi:** 3'ten fazla zorunlu input alanı var mı? (Varsa -> Kademeli adıma böl)
- [ ] **6. Durum Bütünlüğü:** Butonlarda `active:scale-[0.98]` ve `disabled/loading` durumu kodlanmış mı? (Eksikse -> Ekle)
- [ ] **7. E-Ticaret / Checkout:** Zorunlu üyelik şartı koşulmuş mu veya mobilde sticky satın alma çubuğu unutulmuş mu? (Varsa düzelt)
- [ ] **8. Dashboard Veri Sinyali:** Tablolarda sayısal değerler sağa yaslı (`tabular-nums font-mono`) ve anomali renkleri ayrılmış mı? (Yoksa -> Düzelt)
- [ ] **9. Boş Durum Yönlendirmesi:** "Veri yok" diyen ekranda doğrudan aksiyona götüren buton var mı? (Yoksa -> Ekle)
- [ ] **10. İletişim Filtresi:** Cevapta kullanıcıyı gereksiz öven, konudan sapan yağlayıcı tek bir kelime var mı? (Varsa -> Sil)

