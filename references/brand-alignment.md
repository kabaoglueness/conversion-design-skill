# Kurumsal kimlik ve marka uyum kuralları

Tasarım üretmeden önce kullanıcının kurum kimliği net değilse doğrudan koda geçilmez. Önce aşağıdaki üç soru ile marka çerçevesi belirlenir veya mevcut `BRAND.md` dosyası okunur.

## 1. Marka çerçeveleme soruları (Brand intake)

Eğer projede tanımlı bir `BRAND.md` yoksa ve kullanıcı bir marka kılavuzu vermemişse, model tasarıma başlamadan önce şu üç soruyu sorar:

1. **Sektör ve kurum tonu:** Kurumun duruşu nasıl olmalı? (Örnek: Katı ve kurumsal güven mi, teknik ve analitik mühendislik mi, yoksa samimi ve dinamik mi?)
2. **Kullanıcı kitlesi:** Karar verici kim? (Örnek: Şirket yöneticileri / B2B mi, son tüketici / B2C mi, yazılımcılar mı?)
3. **Renk ve estetik referansı:** Varsa kurumun ana rengi nedir veya örnek aldığınız bir marka var mı? (Örnek: Stripe sadeliği, Linear karanlık teması, Apple ferahlığı vb.)

Alınan cevaplar projede `BRAND.md` dosyasına kaydedilir ve sonraki tüm sayfalarda temel referans olarak kullanılır.

## 2. Çift ajanlı denetim modeli (Auditor agent)

Bu süreçte iki rol bulunur:

### Rol 1: Tasarım mimarı
`BRAND.md` dosyasındaki kurallara ve `conversion-design` ilkelerine göre arayüzü kodlar.

### Rol 2: Marka ve dönüşüm denetçisi (Auditor)
Mimardan bağımsız çalışır. Üretilen kodu alır ve şu iki eksende puanlar:

#### Eksen A: Kurumsal kimlik eşleşmesi
- Kodlanan renkler ve fontlar `BRAND.md` dosyasında belirlenen kurum tonuna uyuyor mu? (Örneğin finans kurumu için çocuksu renkler veya jenerik sans-serif kullanılmış mı?)
- Sayfanın genel görsel ağırlığı hedeflenen müşteri kitlesinin ciddiyetine uygun mu?

#### Eksen B: Dönüşüm kontrolü
- 10 kapılı denetim listesi eksiksiz uygulanmış mı? (Tek CTA, buton altı güvence, formda tek kutu, mobilde sabit satın alma çubuğu vb.)

Denetçi eksik bulursa kodu onaylamaz; mimara eksikleri tek tek bildirip düzelttirir. İki taraf da onay verene kadar tasarım teslim edilmez.
