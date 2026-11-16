---
name: conversion-design
description: Use when designing, reviewing, building, or refactoring web interfaces, landing pages, SaaS apps, e-commerce, forms, or checkout flows to ensure visual hierarchy, corporate brand consistency, cognitive clarity, and ruthless conversion optimization without AI slop.
---

# Conversion design & field heuristics

Bu kural seti web arayüzlerinde görsel hiyerarşi kurmak, bilişsel sürtünmeyi sıfırlamak, yapay zeka tasarım klişelerini (AI slop) engellemek ve kullanıcıyı doğrudan hedeflenen eyleme yönlendirmek için kullanılır.

Canlı saha deneyimlerinden ve kullanıcı düzeltmelerinden çıkarılan kesin kuralları içerir.

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
2. **Baloncuklu geometrik sans fontlar:** Kalın ağırlıklarda (`font-bold`, `font-extrabold`) `Plus Jakarta Sans` veya `Poppins` gibi dairesel harfli fontlar kurumsal arayüzü ucuz mobil oyuna çevirir. Kurumsal gövdede saf nötr `Inter` veya `SF Pro`, başlıklarda ise sektöre göre tırnaklı serif (`Cormorant Garamond`, `Newsreader`) veya teknik sans (`Geist`, `Space Grotesk`) kullanılır.
3. **Monospace ayaklı fontlar:** B2B kokpitte veya butonlarda `JetBrains Mono` veya slab-serif monospace fontlar kullanılmaz. Rakam tablolarında sadece `font-variant-numeric: tabular-nums` (veya `tabular-nums`) uygulanır.
4. **Hayali Tailwind sınıfları (Hallucinated classes):** Tailwind ölçeğinde olmayan `pl-8.5` gibi hayali sınıflar yazıp arama ikonunu metnin üstüne bindirmek yasaktır. Standart `pl-9` (36px) veya `pl-10` kullanılmalıdır.
5. **Aksiyon sahteciliği (False promise links):** Kullanıcıya "Başvur" veya "Satın Al" deyip genel bir arama motoru ana sayfasına fırlatmak yasaktır. Link ya doğrudan hedefe gitmeli ya da ne yaptığı şeffaf yazılmalıdır.
6. **Ölü veri kutuları (Eylemsiz estetik):** Dashboard'da tıklandığında hiçbir şey yapmayan kartlar yasaktır. "Kritik Stok: 1" yazıyorsa tıklandığında doğrudan o ürünü filtrelemeli ve düzenleme alanını açmalıdır. Her metrik kartı bir aksiyon tetikleyicisidir.
7. **Gereksiz animasyon ve emojiler:** Arayüz metinlerinde emoji kullanmak ve durum rozetlerinde sürekli yanıp sönen yeşil noktalar (`animate-pulse`) koymak yasaktır. Durumlar dingindir.
8. **Uzun tire ve yapay jargon:** Cümle ortalarında uzun tire (`—`, em-dash) ve İngilizce LLM çevirisi olan yapay jargonlar kullanılmaz. Düz, net Türkçe cümleler kurulur.

---

## 3. Sayfa akışı ve buton yerleşimi

Her sayfa şu sırayı takip eder:
1. Değer vaadi, tek ana buton ve altında güvence notu.
2. Sayısal veri veya şirket logoları içeren kanıt alanı.
3. Gerçek ürün paneli veya arayüz gösterimi.
4. Çözülen sorun ile eski yöntemin karşılaştırması.
5. Fiyat ve paket seçimi.
6. Sıkça sorulan sorular.
7. Sayfa sonu kapanış butonu.

### Buton kuralları
- **Tek birincil aksiyon:** Her ekranda yalnızca bir adet birincil işlem butonu bulunur. İkinci buton varsa şeffaf veya çerçeveli yapılır. İki renkli buton yan yana konulmaz.
- **Risk tersine çevirme:** Birincil butonun altına güvence notu eklenir. Örnek: "Kredi kartı gerekmez, 14 gün ücretsiz deneme".
- **Eylem odaklı mikro-kopya:** Buton metninde "Gönder" veya "Tıkla" gibi pasif ifadeler kullanılmaz. Kullanıcının alacağı fayda yazılır. Örnek: "Ücretsiz çalışma alanını başlat".

---

## 4. 60-30-10 Renk dağılımı

- **Yüzde 60:** Zemin rengi. Koyu temada slate veya zinc tonları (`#09090b` veya `#0f172a`), açık temada nötr beyaz veya gri kullanılır. Katı siyah (`#000000`) kullanılmaz.
- **Yüzde 30:** Kartlar, kenarlıklar ve metinler.
- **Yüzde 10:** Sadece birincil buton ve kritik uyarılar. Bu renk buton harici süslemelerde veya arka planlarda harcanmaz.
- Mor gradient ve parlayan kenarlıklar kullanılmaz.

---

## 5. Boşluk ve grid kuralları (Gestalt yakınlığı)

- Etiket ve giriş kutusu arası 6px (`gap-1.5`) veya 8px (`gap-2`) tutulur.
- Başlık ve altındaki açıklama metni arası 8px (`gap-2`) tutulur.
- Form satırları arasındaki mesafe en az 24px (`gap-6`) yapılır.
- Paragrafların satır genişliği 75 karakteri geçemez (`max-w-prose` veya `max-w-2xl`).
- Bölümler arası dikey boşluk mobilde `py-16`, masaüstünde `py-24` yapılır.

---

## 6. Mobil ve duyarlı ekran mimarisi (Responsive safeguards)

- **Üst bar boğulması engeli:** Mobilde (375px - 414px) logo, arama kutusu ve sayaç tek satıra sıkıştırılamaz. Mobilde 2 satır (`flex flex-col sm:flex-row`) kullanılır; birinci satırda marka ve sayaç, ikinci satırda tam genişlik arama kutusu yer alır.
- **Taşma koruması:** Yatay buton ve sekme gruplarında `whitespace-nowrap shrink-0` kullanılır.
- **Dokunma alanı:** Mobilde tüm buton ve tıklanabilir öğeler en az 44x44px dokunma alanına sahip olmalıdır (Apple HIG).
- **Sayfa geçişi kaydırma sıfırlaması:** Tek sayfa geçişlerinde ekranın altta asılı kalmaması için geçiş anında `window.scrollTo({ top: 0, behavior: 'instant' })` tetiklenir.

---

## 7. Form ve sürtünme ergonomisi

- İsim ve soyisim için iki ayrı kutu açılmaz. Tek bir `Ad Soyad` kutusu kullanılır.
- Kullanıcı formu gönderdikten sonra toplu hata gösterilmez. Kullanıcı kutudan çıktığı an (onBlur) doğrulama yapılır.
- E-posta için `type="email"`, telefon için `inputmode="numeric"`, şifre kutusu için görünürlük butonu eklenir.

---

## 8. E-ticaret ve sepet kuralları

- Satın alma öncesi zorunlu üyelik veya şifre istemek yasaktır. Misafir alışverişi sunulur. Şifre belirleme sipariş sonrasına bırakılır.
- Kargo ve vergi ücretleri ödeme adımına saklanmaz, sepette baştan gösterilir.
- Ödeme butonunun altına SSL ve kart güvenlik ikonları eklenir.
- Mobilde ürün sayfasında gezinirken "Sepete Ekle" butonu ekranın altına sabitlenir (`sticky bottom-0`).

---

## 9. Tablo ve yönetim paneli kuralları

- Sayılar ve para birimleri sağa yaslanır (`text-right tabular-nums`). Metinler sola yaslanır.
- Tablo başlığı kaydırma sırasında üstte sabitlenir (`sticky top-0`).
- İşlem butonları satırın üzerine gelindiğinde görünür yapılır.
- Boş tablolarda sadece "Veri yok" yazılmaz. Yeni veri ekleme veya filtre sıfırlama butonu gösterilir.

---

## 10. Fiyatlandırma psikolojisi ve geri bildirim

- **Öne çıkan paket:** Üç paketten ortadaki paket belirginleştirilir (`scale-105`), birincil renkli buton sadece ona verilir. Yıllık seçimde net kazanç ("2 ay bedava") yazılır.
- **Anlık geri bildirim:** Butona basıldığında 1.5 saniye onay simgesi gösterilir. Başarılı işlemlerde 3 saniye sonra kaybolan sade toast bildirimi açılır.

---

## 11. 14 Kapılı otonom denetim listesi (Linter)

Kod teslim edilmeden önce denetçi ajan şu 14 soruyu kontrol eder:
1. Kod, projede belirlenen `BRAND.md` kurum tonu ve renk kimliği ile yüzde 100 eşleşiyor mu?
2. Başlıkların üstünde gereksiz büyük harfli kicker etiketleri var mı? (Varsa silinmeli)
3. Kalın ağırlıklarda baloncuklu sans (`Plus Jakarta Sans`, `Poppins`) kullanılmış mı?
4. Tailwind ölçeğinde olmayan hayali sınıflar (`pl-8.5` vb.) var mı ve ikonla metin çakışıyor mu?
5. Ekranda birden fazla renkli işlem butonu yarışıyor mu?
6. Ana butonun altında güvence metni var mı?
7. Eylemsiz estetik kartlar (tıklanınca işlem yapmayan ölü istatistikler) var mı?
8. Emojiler veya yanıp sönen `animate-pulse` yeşil/kırmızı noktalar var mı?
9. Metinlerde uzun tire (`—`) veya yapay çeviri jargonu var mı?
10. Mobilde üst bar öğeleri sıkışıp dışarı taşıyor mu?
11. Butonlar mobilde en az 44x44px dokunma alanına sahip mi?
12. Boş ekranda kullanıcıyı eyleme geçiren buton var mı?
13. E-ticarette zorunlu üyelik istenmiş mi?
14. Yanıtta gereksiz iltifat veya dolaylı ifade var mı?
