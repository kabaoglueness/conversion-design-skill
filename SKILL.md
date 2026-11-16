---
name: conversion-design
description: Use when designing, reviewing, building, or refactoring web interfaces, landing pages, SaaS apps, e-commerce, forms, or checkout flows to ensure visual hierarchy, corporate brand consistency, cognitive clarity, and ruthless conversion optimization without AI slop.
---

# Conversion design

Bu kural seti web arayüzlerinde görsel hiyerarşi kurmak, form sürtünmesini azaltmak ve kullanıcıyı doğrudan hedeflenen eyleme yönlendirmek için kullanılır.

## 1. Çalışma şekli ve kurumsal kimlik belirleme

- Kullanıcıya boş övgüde bulunmayın.
- Tasarımda veya akışta dönüşümü düşüren bir hata varsa doğrudan belirtin ve düzeltin.
- Sonuç odaklı çalışın. Süreci anlatmak yerine doğrudan çalışan kod verin.

### Kurumsal kimlik sorma kuralı (Brand intake)
Projeye başlarken veya arayüz tasarımı yaparken projede tanımlı bir `BRAND.md` yoksa ve kullanıcı bir marka kılavuzu vermemişse, **doğrudan tasarıma geçilmez**. Önce şu 3 soru ile kurum kimliği belirlenir:
1. **Kurum tonu:** Katı kurumsal güven mi, analitik teknik mi, yoksa dinamik/samimi mi?
2. **Hedef kitle:** Şirket yöneticileri (B2B) mi, son kullanıcı (B2C) mi, mühendisler mi?
3. **Renk ve referans:** Varsa kurumun ana rengi nedir veya referans aldığınız bir marka var mı?

Alınan cevaplar `BRAND.md` dosyasına kaydedilir ve tüm renk, tipografi, görsel hiyerarşi bu dosyaya göre şekillendirilir.

### Çift ajanlı denetim modeli (Architect & Auditor)
Arayüz üretiminde iki rol işler:
1. **Tasarım mimarı:** `BRAND.md` ve dönüşüm kurallarına göre sayfayı kodlar.
2. **Marka ve dönüşüm denetçisi:** Kodlanan sayfanın kullanıcının `BRAND.md` dosyasındaki kurum kimliğiyle ve 10 kapılı denetim listesiyle ne kadar eşleştiğini bağımsız olarak kontrol eder. Eşleşmeyen veya dönüşümü bozan yerleri mimara düzelttirir. İki taraf onaylamadan kod teslim edilmez.

## 2. Sayfa akışı ve buton yerleşimi

Her sayfa şu sırayı takip eder:
1. Değer vaadi, tek ana buton ve altında güvence notu.
2. Sayısal veri veya şirket logoları içeren kanıt alanı.
3. Gerçek ürün paneli veya arayüz gösterimi.
4. Çözülen sorun ile eski yöntemin karşılaştırması.
5. Fiyat ve paket seçimi.
6. Sıkça sorulan sorular.
7. Sayfa sonu kapanış butonu.

### Buton kuralları
- Her ekranda yalnızca bir adet birincil işlem butonu bulunur. İkinci bir buton varsa şeffaf veya çerçeveli yapılır. İki renkli buton yan yana konulmaz.
- Birincil butonun altına güvence notu eklenir. Örnek: "Kredi kartı gerekmez, 14 gün ücretsiz deneme".
- Buton metninde "Gönder" veya "Tıkla" gibi pasif ifadeler kullanılmaz. Kullanıcının alacağı fayda yazılır. Örnek: "Ücretsiz çalışma alanını başlat".

## 3. Renk dağılımı

- Yüzde 60: Zemin rengi. Koyu temada slate veya zinc tonları (`#09090b` veya `#0f172a`), açık temada nötr beyaz veya gri kullanılır. Katı siyah (`#000000`) kullanılmaz.
- Yüzde 30: Kartlar, kenarlıklar ve metinler.
- Yüzde 10: Sadece birincil buton ve kritik uyarılar. Bu renk buton harici süslemelerde veya arka planlarda harcanmaz.
- Mor gradient ve parlayan kenarlıklar kullanılmaz.

## 4. Boşluk ve grid kuralları

- Etiket ve giriş kutusu arası 6px (`gap-1.5`) veya 8px (`gap-2`) tutulur.
- Başlık ve altındaki açıklama metni arası 8px (`gap-2`) tutulur.
- Form satırları arasındaki mesafe en az 24px (`gap-6`) yapılır.
- Paragrafların satır genişliği 75 karakteri geçemez (`max-w-prose` veya `max-w-2xl`).
- Bölümler arası dikey boşluk mobilde `py-16`, masaüstünde `py-24` yapılır.

## 5. Yazı tipi seçimi

Bütün projelere standart sans-serif font verilmez. Sektörün ihtiyacına göre font seçilir:

- Finans, bankacılık ve hukuk: Başlıkta Newsreader veya Playfair Display, gövdede Plus Jakarta Sans.
- B2B yazılım ve veri araçları: Başlıkta Space Grotesk veya Geist, gövdede IBM Plex Sans.
- Lüks tüketim ve moda: Başlıkta Cormorant Garamond, gövdede Satoshi.
- Geliştirici araçları: Başlıkta JetBrains Mono, gövdede Space Grotesk.
- Genel tüketici ve e-ticaret: Başlıkta Cabinet Grotesk, gövdede Switzer.

Sayısal tablolarda rakam genişliklerini sabitlemek için `tabular-nums` ve `font-mono` kullanılır.

## 6. Form kuralları

- İsim ve soyisim için iki ayrı kutu açılmaz. Tek bir `Ad Soyad` kutusu kullanılır.
- Kullanıcı formu gönderdikten sonra toplu hata gösterilmez. Kullanıcı kutudan çıktığı an (onBlur) doğrulama yapılır.
- E-posta için `type="email"`, telefon için `inputmode="numeric"`, şifre kutusu için görünürlük butonu eklenir.

## 7. E-ticaret ve sepet kuralları

- Satın alma öncesi zorunlu üyelik veya şifre istemek yasaktır. Misafir alışverişi sunulur. Şifre belirleme sipariş sonrasına bırakılır.
- Kargo ve vergi ücretleri ödeme adımına saklanmaz, sepette baştan gösterilir.
- Ödeme butonunun altına SSL ve kart güvenlik ikonları eklenir.
- Mobilde ürün sayfasında gezinirken "Sepete Ekle" butonu ekranın altına sabitlenir (`sticky bottom-0`).

## 8. Tablo ve yönetim paneli kuralları

- Sayılar ve para birimleri sağa yaslanır (`text-right tabular-nums`).
- Metinler sola yaslanır.
- Tablo başlığı kaydırma sırasında üstte sabitlenir (`sticky top-0`).
- İşlem butonları satırın üzerine gelindiğinde görünür yapılır.
- Boş tablolarda sadece "Veri yok" yazılmaz. Veri ekleme butonu gösterilir.

## 9. Buton durumları

Butonlarda şu beş durum kodlanır:
1. Normal durum.
2. Hover durumu.
3. Basılma durumu (`active:scale-[0.98]`).
4. Yüklenme durumu (içinde dönen simge ve `disabled`).
5. Klavye odaklanma halkası (`focus-visible:ring-2`).

## 10. Kontrol listesi (Kurumsal kimlik ve dönüşüm denetimi)

Kod teslim edilmeden önce denetçi ajan şu soruları kontrol eder:
1. Kod, projede belirlenen `BRAND.md` kurum tonu ve renk kimliği ile yüzde 100 eşleşiyor mu?
2. Ekranda birden fazla renkli işlem butonu var mı?
3. Ana butonun altında güvence metni var mı?
4. Paragraf satırları 75 karakterden uzun mu?
5. Buton rengi başka yerlerde süsleme için harcanmış mı?
6. Formda 3'ten fazla zorunlu kutu var mı?
7. Butonda basılma (`active:scale-[0.98]`) ve yüklenme durumu var mı?
8. E-ticarette zorunlu üyelik istenmiş mi?
9. Tabloda sayılar sağa yaslanmış mı?
10. Boş ekranda işlem butonu var mı?
11. Yanıtta gereksiz iltifat veya dolaylı ifade var mı?
