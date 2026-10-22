# QUICKY web sitesi — yayınlama rehberi

Bu klasör, QUICKY'nin küçük tanıtım ve destek sitesidir. GitHub Pages ile **ücretsiz** yayımlanır. Derleme aracı, program kurulumu ya da komut satırı gerekmez; her şey tarayıcıdan yapılır.

> **Önemli:** Bu klasörü uygulama kodunun bulunduğu depoya değil, **ayrı, yeni bir depoya** yükleyin. Ücretsiz GitHub hesabında Pages sitesinin deposu herkese açık olmak zorundadır; uygulama kodu gizli kalmalı.

## Klasörde neler var?

| Dosya | Ne işe yarar |
|---|---|
| `index.html` | Tanıtım sayfası (App Store'daki "Pazarlama URL'si") |
| `destek.html` | Destek sayfası: e-posta ve sık sorulan sorular (App Store'daki "Destek URL'si") |
| `gizlilik.html` | Gizlilik Politikası (App Store'daki "Gizlilik Politikası URL'si") |
| `kvkk.html` | KVKK Aydınlatma Metni |
| `kosullar.html` | Kullanım Koşulları |
| `404.html` | Olmayan bir adrese gidilirse gösterilen sayfa |
| `style.css` | Tüm sayfaların görünümü (renkler en üstte) |
| `logo.svg`, `favicon.svg`, `favicon.png`, `apple-touch-icon.png` | Logo ve tarayıcı sekmesi simgeleri |
| `fonts/` | Lexend yazı tipi ve lisansı (OFL.txt) |
| `robots.txt` | Arama motorlarına "şimdilik dizine ekleme" der (aşağıya bakın) |
| `.nojekyll` | Boş dosya. GitHub'ın siteyi değiştirmeden olduğu gibi yayımlamasını sağlar. **Silmeyin.** |
| `README.md` | Bu rehber |

> `.nojekyll` adı noktayla başladığı için Windows'ta gizli dosya gibi görünebilir. Dosya Gezgini'nde **Görünüm > Göster > Gizli öğeler** seçeneğini açarsanız görünür.

---

## Yayımlamadan önce yapılacaklar

1. **Yasal metinler taslaktır.** Avukat incelemesi bitmeden mağazaya gönderilmemeli.
2. Sarı kesik çizgili kutular (`[VERİ SORUMLUSU AD SOYAD / UNVAN]` gibi) **doldurulması gereken yer tutuculardır.** Avukatla birlikte doldurun.
3. Avukat onayından sonra her yasal sayfanın en üstündeki turuncu şeridi kaldırın. Her dosyada şu tek satırı silmeniz yeterli:
   ```html
   <div class="taslak-uyari" role="note">Bu metin taslaktır ve hukuki inceleme sürecindedir.</div>
   ```
   (Hızlı yol: `style.css` içindeki `.taslak-uyari {` kuralına `display: none;` eklemek şeridi tüm sayfalarda gizler.)
4. **robots.txt:** Şu an `Disallow: /` yazıyor, yani Google gibi arama motorlarından siteyi dizine eklememeleri istenir. Site yine de adresini bilen herkese açıktır; App Store incelemesi de sayfaları açabilir. Yasal metinler kesinleşince `robots.txt` dosyasının içeriğini şununla değiştirin:
   ```
   User-agent: *
   Allow: /
   ```

---

## Adım 1 — GitHub hesabı açın (varsa giriş yapın)

1. Tarayıcıda **https://github.com** adresine gidin.
2. Sağ üstteki **Sign up** (Kaydol) düğmesine tıklayın. Hesabınız varsa **Sign in** (Giriş) ile girin.
3. E-posta adresinizi, bir şifre ve bir **kullanıcı adı** girin. Kullanıcı adı sitenizin adresinde görünecek (ör. kullanıcı adı `quickyapp` ise adres `quickyapp.github.io` olur). Kısa ve düzgün bir ad seçin.
4. E-postanıza gelen doğrulama kodunu girin. Ücretli plan sorulursa **Free** (ücretsiz) seçin.

## Adım 2 — Yeni, herkese açık bir depo oluşturun

"Depo" (repository), dosyalarınızın GitHub'daki klasörüdür.

1. Sağ üstteki **+** simgesine, sonra **New repository** seçeneğine tıklayın.
2. **Repository name** (depo adı) kutusuna bir ad yazın. İki seçenek var:

   | Depo adı | Site adresi | Ne zaman seçilir |
   |---|---|---|
   | `quicky` (önerilen) | `https://KULLANICIADI.github.io/quicky/` | Hesabınızda başka siteler de olabilecekse |
   | `KULLANICIADI.github.io` (kullanıcı adınızın birebir aynısı) | `https://KULLANICIADI.github.io/` | Hesabı yalnız QUICKY için açtıysanız; adres daha kısa olur |

   Örnek: kullanıcı adı `quickyapp` ise, depo adı `quicky` → `https://quickyapp.github.io/quicky/`; depo adı `quickyapp.github.io` → `https://quickyapp.github.io/`.
3. Görünürlük olarak **Public** (herkese açık) seçin. Ücretsiz hesapta Pages yalnızca herkese açık depolarda çalışır.
4. **Add README** seçeneğini açık bırakabilirsiniz (depo boş kalmasın diye; bizim README dosyamız bunun üzerine yazılacak).
5. **Create repository** düğmesine tıklayın.

## Adım 3 — Dosyaları tarayıcıdan yükleyin

1. Yeni deponun sayfasında, dosya listesinin üstündeki **Add file** düğmesine, sonra **Upload files** seçeneğine tıklayın.
2. Bilgisayarınızda bu `site` klasörünü açın. **Klasörün kendisini değil, içindeki her şeyi** seçin (Ctrl+A) ve tarayıcıdaki "Drag files here" alanına sürükleyip bırakın. `fonts` klasörü de içindekilerle birlikte yüklenir.
   - `.nojekyll` dosyasının da seçildiğinden emin olun (görünmüyorsa yukarıdaki "gizli öğeler" notuna bakın).
   - `index.html` deponun **en üst düzeyinde** olmalı, bir alt klasörün içinde değil.
3. Sayfanın altındaki "Commit changes" kutusuna kısa bir not yazın (ör. `İlk yükleme`).
4. **Commit directly to the main branch** seçili olsun ve **Commit changes** düğmesine tıklayın.

GitHub tarayıcıdan bir seferde en fazla 100 dosya ve dosya başına 25 MB kabul eder; bu site bunun çok altındadır.

## Adım 4 — GitHub Pages'i açın

1. Deponun üst menüsünden **Settings** (Ayarlar) sekmesine tıklayın.
2. Soldaki menüde **Pages** seçeneğine tıklayın ("Code and automation" bölümünde).
3. **Build and deployment** başlığı altında, **Source** için **Deploy from a branch** seçin.
4. **Branch** için **main**, yanındaki klasör için **/ (root)** seçin.
5. **Save** (Kaydet) düğmesine tıklayın.
6. Birkaç dakika bekleyin, sonra sayfayı yenileyin. Üstte **"Your site is live at https://…"** yazısı çıkınca site yayındadır. Bağlantıya tıklayıp kontrol edin.

İlerlemeyi deponun **Actions** sekmesinden de izleyebilirsiniz (yeşil tik = tamamlandı).

## Adım 5 — Siteyi güncellemek

- **Tek bir dosyayı değiştirmek için:** Depoda dosyaya tıklayın, sağ üstteki kalem simgesine (**Edit this file**) tıklayın, değişikliği yapın, **Commit changes** ile kaydedin.
- **Dosyayı yenisiyle değiştirmek için:** Adım 3'teki gibi **Add file > Upload files** ile aynı adlı dosyayı yükleyin; eskisinin yerine geçer.
- **Dosya silmek için:** Dosyayı açın, sağ üstteki **…** menüsünden **Delete file** seçin, **Commit changes**.
- Her kayıttan sonra sitenin güncellenmesi birkaç dakika sürebilir. Değişikliği görmüyorsanız tarayıcıda sayfayı zorla yenileyin (Ctrl+F5; iPhone'da Safari'yi kapatıp açın).

## Adım 6 — App Store Connect'e girilecek adresler

Aşağıda `https://KULLANICIADI.github.io/quicky/` örnek adrestir; kendi adresinizi yazın. Adreslerin sonundaki `.html` uzantısını **silmeyin**.

| App Store Connect alanı | Adres |
|---|---|
| **Gizlilik Politikası URL'si** (Privacy Policy URL, zorunlu) | `https://KULLANICIADI.github.io/quicky/gizlilik.html` |
| **Destek URL'si** (Support URL, zorunlu) | `https://KULLANICIADI.github.io/quicky/destek.html` |
| **Pazarlama URL'si** (Marketing URL, isteğe bağlı) | `https://KULLANICIADI.github.io/quicky/` |
| Uygulama açıklamasındaki "Kullanım Koşulları" | `https://KULLANICIADI.github.io/quicky/kosullar.html` |

Bu adresleri yasal metinlerdeki `[GİZLİLİK POLİTİKASI URL'Sİ]` ve `[KVKK AYDINLATMA METNİ URL'Sİ]` yer tutucularına da yazın. Adresleri girmeden önce telefonunuzdan açıp çalıştığını kontrol edin.

## Adım 7 — İleride kendi alan adınız (isteğe bağlı)

`quicky.com.tr` gibi bir alan adı alırsanız siteyi o adresle de yayımlayabilirsiniz. GitHub Pages bunu ücretsiz destekler; yalnız alan adının yıllık ücretini alan adı firmasına ödersiniz.

1. Alan adını bir firmadan satın alın.
2. Depoda **Settings > Pages > Custom domain** kutusuna alan adını yazıp **Save** deyin.
3. Alan adı firmasının panelinde, GitHub'ın belgesinde yazan DNS kayıtlarını ekleyin (bkz. kaynak 5).
4. Kayıtlar etkinleşince **Enforce HTTPS** kutusunu işaretleyin.
5. App Store Connect'teki adresleri yeni alan adıyla güncelleyin. (Eski `github.io` adresleri yeni adrese yönlendirilir.)

---

## GitHub Pages kuralları (22 Ekim 2026'da belgelerden kontrol edildi)

- **Herkese açık depo şartı:** Depo sahibi GitHub Free kullanıyorsa deponun herkese açık olması gerekir. Site, depo gizli olsa bile (ücretli planlarda) internette herkese açıktır. (Kaynak 2)
- **Ticari kullanım:** GitHub Pages, "çevrimiçi işletmenizi, e-ticaret sitenizi" yürütmek için ücretsiz barındırma olarak ya da esas olarak ticari işlemlere aracılık eden siteler için kullanılamaz; şifre veya kredi kartı gibi hassas işlemler için de kullanılmamalıdır. Bu site yalnızca bilgi, destek ve yasal metin sayfalarıdır; satış, ödeme veya giriş formu içermez. Satışlar Apple üzerinden uygulama içinde yapılır. Bu yorum bizimdir; GitHub'ın kendisi onaylamış değildir. (Kaynak 1)
- **Sınırlar:** Yayımlanan site en fazla 1 GB; depo için önerilen sınır 1 GB; aylık **yumuşak** bant genişliği sınırı 100 GB; saatte 10 derleme (yumuşak sınır); bir yayımlama 10 dakikadan uzun sürerse zaman aşımına uğrar. Bu site yaklaşık 150 KB'dır. (Kaynak 1)
- **Ziyaretçi kaydı:** GitHub, Pages sitelerini ziyaret edenlerin IP adresini güvenlik amacıyla kaydeder. (Kaynak 3) Bu yüzden yazı tipi Google'dan çekilmiyor, sitenin içinde duruyor; böylece ziyaretçinin IP adresi ayrıca Google'a gitmez.

### Kaynaklar

1. GitHub Docs, GitHub Pages limits: https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits
2. GitHub Docs, Creating a GitHub Pages site: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
3. GitHub Docs, About GitHub Pages: https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages
4. GitHub Docs, Configuring a publishing source for your GitHub Pages site: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
5. GitHub Docs, Managing a custom domain for your GitHub Pages site: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
6. GitHub Docs, Adding a file to a repository (tarayıcıdan yükleme sınırları): https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository
7. Lexend yazı tipi lisansı (SIL Open Font License 1.1): `fonts/OFL.txt`, https://github.com/googlefonts/lexend
