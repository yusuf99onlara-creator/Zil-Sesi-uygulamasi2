🛎️ SSEML Okul Zili Uygulaması

Windows tabanlı, profilli ve takvim destekli gelişmiş okul zili otomasyon sistemi.
Ders zili, teneffüs müziği, marş çalma, acil alarm ve takvim kuralları tek bir uygulamadan yönetilir.

⭐ Öne Çıkan Özellikler

📚 Ders Zilleri Yönetimi

🎵 Teneffüs Müzikleri

🇹🇷 İstiklal Marşı / Diğer Marşlar

🚨 Acil Alarm Sistemi

📅 Takvim veya Günlük Kurallarla Profil Seçimi

🤖 Otomatik Öğle Okulu Profili (Kurallarla)

🎨 Karanlık Mod

🔊 Test Butonları ve Gelişmiş Ses Yönetimi

📂 Klasör Yapısı
UygulamaKlasörü/
├─ SSEML_OkulZili.exe
├─ ZilSesleri/
├─ AlarmSesleri/
├─ Marslar/
├─ TeneffusMuzikleri/
├─ Ayarlar.txt
├─ Profiller.txt
├─ Takvim.txt
├─ TakvimKurallari.txt
└─ TeneffusMuzik.txt

🎧 Ses Klasörleri
Klasör	İçerik
ZilSesleri/	Ders zilleri (.mp3 / .wav)
AlarmSesleri/	Acil durum alarmları
Marslar/	İstiklal Marşı veya diğer marşlar
TeneffusMuzikleri/	Teneffüs sırasında çalacak müzik listeleri
💾 Ayar Dosyaları
Dosya	Açıklama
Ayarlar.txt	Tema, aktif profil, sesler, genel ayarlar
Profiller.txt	Zil profilleri ve tüm ders saatleri
Takvim.txt	Belirli tarihler için özel ayarlar
TakvimKurallari.txt	“Her Pazartesi öğle okulu” gibi kurallar
TeneffusMuzik.txt	Teneffüs müzik profilleri (gün, saat, seviye, liste)

Tüm dosyalar düz metin formatındadır ve gerekirse elle düzenlenebilir.

💻 Sistem Gereksinimleri

Windows 7 / 8 / 10 / 11

.NET Framework (WinForms uyumlu)

Windows Media Player (WMPLib için gerekli)

Temel okul bilgisayarında çalışabilir (yüksek performans gerekmez)

🚀 Kurulum

Uygulamayı bir klasöre çıkar.

Gerekli klasörler yoksa uygulama otomatik oluşturur.

Kullanmak istediğin .mp3 / .wav dosyalarını ilgili klasörlere kopyala.

SSEML_OkulZili.exe’yi çalıştır.

🖥️ Ana Ekran (Form1) Özeti

Üst alan: Saat, tarih, geri sayım, sıradaki zil bilgisi

Sol panel: Profil kartları (Normal Gün, Öğle Okulu vb.)

Orta panel: Günün ders/zil programı

Sağ panel: Ses ayarları (Zil / Alarm / Marş seçimi, volume)

Alt panel:

Ayarlar

Takvim

Teneffüs Müzik Yönetimi

Test Butonları

🧩 Profil Sistemi

Her profil bir okul gününün yapısını temsil eder:

NormalGun

OgleOkulu

(İsteğe bağlı yeni profiller eklenebilir)

Profillerdeki tüm zil saatleri Profiller.txt içinde saklanır.

🔊 Ses Ayarları

Zil sesi → ZilSesleri/

Alarm sesi → AlarmSesleri/

Marş sesi → Marslar/

Ek olarak:

🎚️ Ses Seviyesi (TrackBar)

▶️ Test et / ⏹️ Durdur

Teneffüs müziği bağımsız seviye ile çalışır

📅 Takvim Sistemi
1) Tek Gün Ayarları – TakvimForm

Belirli bir güne özel profil atama

Tatil işareti (Ziller çalmasın)

Açıklama alanı

Listeye ekleme / silme

Veriler: Takvim.txt

2) Tekrarlayan Kurallar

Örnek:

“Her Pazartesi → Öğle Okulu”

“Her Cuma → Normal Gün”

Kural ekleme:

Gün seç → Profil seç → Ekle

Veriler: TakvimKurallari.txt

3) Otomatik Profil Seçim Mantığı

1️⃣ Önce Takvim.txt
2️⃣ Sonra TakvimKurallari.txt
3️⃣ Hiçbiri yoksa varsayılan mantık:

Gün	Profil
Cumartesi/Pazar	HaftaSonu (varsa)
Pazartesi / Perşembe	OgleOkulu
Diğer	NormalGun
🎵 Teneffüs Müzik Sistemi

Her profil için:

Gün (0–6)

Başlangıç / bitiş saati

Ses seviyesi

Çalınacak müzik listesi
→ TeneffusMuzik.txt

Çalışma Mantığı

Sistem 500ms'de bir uygun saat aralığını kontrol eder.

Müzikler sırayla çalınır, bittiğinde başa sarar.

Zil / Alarm / Marş çalarsa:

Teneffüs müziği duraklatılır

Bitince kaldığı yerden devam eder

🛎️ Zil Sistemi

Her profil kendi zil saatlerini taşır.

Sistem her saniye kontrol eder.

Aynı zil aynı dakika içinde tekrar çalmaz.

Marş çalıyorsa zil tetiklenmez.

“Ziller devre dışı” seçilmişse çalma engellenir.

🚨 Alarm & Marş

Çalmadan önce kullanıcıdan onay ister.

Çalarken diğer sesler durdurulur.

Bitince teneffüs müziği devam eder.

🌙 Karanlık Mod

Tek tıkla:

Arka plan renkleri

Yazı renkleri

Panel renkleri
tamamen karanlık tema moduna geçer.

Ayar: Ayarlar.txt → KaranlikMod=1

🔧 Sorun Giderme
❌ Ses çalmıyor

Dosyalar doğru klasörde mi?

Uzantı .mp3 / .wav mı?

Windows Media Player kurulu mu?

❌ Takvim kuralı işlemiyor

Gün indexleri doğru mu?
0=Pazartesi … 6=Pazar

TakvimKurallari.txt yeniden oluşturulabilir.

❌ Class hataları

ZamanItem, TakvimGunu, TakvimKural sınıfları aynı namespace içinde olmalı.

💡 Önerilen Kullanım Senaryosu

Tüm ses dosyalarını ilgili klasörlere koy.

Ses Ayarları panelinden zil/alar/marş seç.

Profillerden okuluna göre zil saatlerini düzenle.

Takvimde:

Tatiller

Sınav günleri

Haftalık otomatik kurallar
ekle.

Teneffüs müzik profillerini oluştur.

Uygulamayı açıp simge durumuna küçült → gün boyunca otomatik çalışır.
