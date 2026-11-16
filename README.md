# conversion-design

Web uygulamalarında görsel hiyerarşi kuran, gereksiz form alanlarını kaldıran ve kullanıcıyı doğrudan satın alma veya kayıt işlemine yönlendiren Antigravity ve Gemini CLI kural seti.

Modelin varsayılan olarak ürettiği mor gradient zeminleri, yarışan butonları, tek tip jenerik fontları ve uzun formları engeller.

## Kurallar

- **Tek birincil buton.** Her ekranda yalnızca bir adet ana işlem butonu bulunur. İkinci buton varsa şeffaf veya çerçeveli yapılır. Butonun altına kredi kartı istememe veya iade süresi gibi güvence notu eklenir.
- **Renk dağılımı.** Sayfanın yüzde 60 bölümü nötr arka plana, yüzde 30 bölümü kart ve sınırlara, yüzde 10 bölümü ise sadece işlem butonuna ayrılır. Aksiyon rengi buton harici süslemelerde kullanılmaz.
- **Sektörel yazı tipi.** Bütün projelere tek tip sans-serif font verilmez. Finans için Newsreader veya Playfair Display, veri ve yazılım araçları için Space Grotesk veya Geist, genel tüketici için Cabinet Grotesk veya Plus Jakarta Sans kullanılır. Rakam tablolarında `tabular-nums` zorunludur.
- **Form alanları.** Kayıt ve sipariş formlarında gereksiz bilgi istenmez. İsim ve soyisim tek kutuda toplanır. Kullanıcı kutudan çıktığı an doğrulama yapılır.
- **Sipariş ve sepet.** Kullanıcıdan satın alma öncesi şifre belirlemesi veya üye olması istenmez. Kargo ücreti sepette en baştan gösterilir. Mobil ekranda satın alma butonu ekranın altına sabitlenir.
- **Tablo yerleşimi.** Sayılar ve para birimleri sağa yaslanır. Normal metrikler gri tonlarda tutulur, sadece müdahale gereken hatalar renkli gösterilir.

## Kullanım

Bu dosya bir terminal komutu değildir. Modelin arayüz yazarken takip ettiği kural belgesidir.

### Denetim yaptırma
Yazılmış bir kodu kontrol ettirmek için modele şu komut verilir:

```text
Bu sayfayı conversion-design kurallarına göre incele ve eksikleri düzelt.
```

### Sıfırdan sayfa isteme
Yeni bir arayüz isterken doğrudan kural adını verin:

```text
conversion-design kurallarını kullanarak bir SaaS fiyatlandırma sayfası yaz.
```

## Kurulum

`SKILL.md` dosyasını global ayar klasörünüze kopyalayın:

### Windows (PowerShell)
```powershell
Copy-Item .\SKILL.md "$env:USERPROFILE\.gemini\config\skills\conversion-design\SKILL.md"
```

### Linux ve macOS
```bash
mkdir -p ~/.gemini/config/skills/conversion-design
cp SKILL.md ~/.gemini/config/skills/conversion-design/
```

## Test dosyaları

Repodaki örnek dosyalar standart model çıktısı ile kural uygulanmış çıktı arasındaki farkı gösterir:

- `conversion-test.html`: SaaS açılış sayfası ve tek kutulu kayıt formu.
- `checkout-test.html`: Üyeliksiz sipariş ekranı ve sepet özeti.
- `typography-test.html`: Sektöre göre seçilen fontlar.

## Lisans

MIT License. Telif Hakkı (c) 2026 Enes Kabaoğlu.
