# Conversion Design Skill 🎯

> **Yapay Zeka Tasarım Klişelerini (AI Slop) Engelleyen, Kurumsal Kimlik ve Doğrudan Satış/Dönüşüm Odaklı Tasarım Becerisi.**

Yapay zeka modellerinin web arayüzü üretirken düştüğü en büyük tuzakları (rastgele mor gradient'lar, yarışan butonlar, sürtünmeli formlar, jenerik fontlar) engelleyen; insan psikolojisini, Gestalt boşluk disiplinini ve kurumsal hiyerarşiyi kod seviyesinde zorunlu kılan **Antigravity** ve **Gemini CLI** becerisidir.

---

## 📖 Nasıl Kullanılır? (Kullanım Rehberi)

Bu skill bir terminal CLI aracı değil; yapay zekanın arayüz üretirken uymak **zorunda olduğu** bir otonom tasarım protokolüdür. İki farklı şekilde kullanılır:

### 1. Doğrudan Komut ve Denetim (Audit Modu)
Elinizdeki mevcut bir sayfayı, formu veya bileşeni bu skille denetletmek ve eksiklerini düzelttirmek için yapay zekaya şu şekilde seslenmeniz yeterlidir:

```text
Bu arayüzü `conversion-design` kurallarına ve 10 kapılı denetim listesine göre incele.
Hataları doğrudan söyle ve kodları satışa/dönüşüme uygun şekilde düzelt.
```

### 2. Sıfırdan Üretim
Sıfırdan bir sayfa veya bileşen kodlatırken:

```text
`conversion-design` disiplinini kullanarak bana bir B2B fiyatlandırma (pricing) tablosu ve kayıt akışı kodla.
```

### 3. Otomatik Refleks (Kendiliğinden Devreye Girme)
Promptunuzda *"landing page yap"*, *"ödeme formunu tasarla"*, *"dashboard tablosu kur"* gibi arayüz talepleri geçtiği anda model bu skilli hafızasına alır ve aşağıdaki katı kuralları otomatik uygular.

---

## 🛡️ Zorunlu Tasarım Standartları

1. **Sıfır Yağlama / Dürüst Refleks:** Yapay zeka tasarımda dönüşümü düşüren bir hata gördüğünde kullanıcıya sahte iltifatlar dizmez; doğrudan hatayı söyler ve düzeltir.
2. **Viewport Başına Tek Primary CTA:** Ekranda iki parlayan renkli buton yarışamaz. Tek birincil aksiyon ve hemen 8px altında risk kırıcı mikro-güvenceler yer alır (*"Kredi kartı gerekmez • 14 gün iade"*).
3. **60-30-10 Renk Disiplini:** Markanın canlı aksiyon rengi (%10) süslemelerde harcanamaz; sadece ve sadece kullanıcıyı eyleme geçiren butonlara ayrılır.
4. **AI Fontu Yasağı & Sektörel Tipografi:** Her sektöre jenerik sans-serif basılamaz:
   - **Fintech / Bankacılık:** *Newsreader* (Serif) + *Plus Jakarta Sans*
   - **B2B SaaS / Veri:** *Space Grotesk* / *Geist* + *tabular-nums*
   - **Lüks / Moda:** *Cormorant Garamond* + *Satoshi*
5. **Form Sürtünme Mühendisliği:** Gereksiz alanlar kaldırılır (Ad ve Soyad tek alandır). Anlık (onBlur) doğrulama ve doğru mobil klavye tipleri zorunludur.
6. **E-Ticaret & Checkout:** Misafir alışverişi (guest checkout) zorunludur; şifre zorunluluğu ve gizli kargo masrafları yasaktır. Mobilde ekran altına yapışan sabit satın alma çubuğu (`sticky bottom bar`) bulunur.
7. **Dashboard Ergonomisi:** Sayısal değerler daima sağa yaslanır (`text-right font-mono tabular-nums`). Normal metrikler nötr tonlarda kalırken, sadece müdahale gerektiren anomaliler renk alır.
8. **10 Kapılı Otonom Denetim (Linter):** Kod teslim edilmeden önce 10 maddelik kalite ve dönüşüm kapısından geçer.

---

## 🚀 Kurulum

### Antigravity & Gemini CLI (Global Kurulum)
`SKILL.md` dosyasını global skill dizininize kopyalayın:

```powershell
# Windows (PowerShell)
Copy-Item .\SKILL.md "$env:USERPROFILE\.gemini\config\skills\conversion-design\SKILL.md"
```

```bash
# Linux / macOS
mkdir -p ~/.gemini/config/skills/conversion-design
cp SKILL.md ~/.gemini/config/skills/conversion-design/
```

### Proje Bazlı (Yerel Kurulum)
Çalıştığınız projenin kök dizininde `skills/conversion-design/SKILL.md` yoluna eklemeniz yeterlidir.

---

## 🧪 Doğrulama Testleri

Repo içinde yer alan canlı test dosyalarını tarayıcınızda açarak standart yapay zeka çıktıları (RED) ile bu skillin çıktıları (GREEN) arasındaki farkı görebilirsiniz:
- **`conversion-test.html`**: B2B SaaS Hero ve sürtünmesiz form doğrulaması.
- **`checkout-test.html`**: Sepet terkini önleyen e-ticaret akordeon checkout doğrulaması.
- **`typography-test.html`**: Sektörel kurumsal font ve kimlik doğrulaması.

---

## 📄 Lisans
Bu proje **MIT Lisansı** ile korunmaktadır. Telif Hakkı © 2026 Enes Kabaoğlu.
