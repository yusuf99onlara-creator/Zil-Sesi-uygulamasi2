🛎️ SSEML Okul Zili Uygulaması
Windows tabanlı, profilli ve takvim destekli okul zili / teneffüs müziği otomasyon uygulaması.

Ders zilleri
Teneffüs müzikleri
İstiklal Marşı
Acil alarm
Günlük/takvim bazlı profil seçimi
Otomatik öğle okulu seçimi (kurallarla)
hepsi tek uygulamada yönetilir.

📂 Klasör Yapısı
Uygulama çalıştığı klasörde aşağıdaki yapıyı kullanır:

text

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
Ses Klasörleri
ZilSesleri → Normal zil sesleri (.mp3, .wav)
AlarmSesleri → Acil alarm sesleri (.mp3, .wav)
Marslar → İstiklal Marşı vb. marşlar (.mp3, .wav)
TeneffusMuzikleri → Teneffüs sırasında çalacak müzikler
(Teneffüs kodu .mp3/.wav dışında da deneyebilir ama tavsiye mp3/wav)
Ses dosyalarını bu klasörlere kopyalayınca uygulama otomatik algılar.

💾 Ayar Dosyaları
Ayarlar.txt
Aktif profil, seçili zil/alarm/marş sesleri, tema (karanlık mod), genel ses seviyesi…
Profiller.txt
Tüm zil profilleri ve saat/ders/açıklama bilgileri
Takvim.txt
Belirli tarihlere ait özel gün/özel profil/zil devre dışı bilgileri
TakvimKurallari.txt
“Her Pazartesi öğle okulu” gibi tekrarlayan gün kuralları
TeneffusMuzik.txt
Teneffüs müzik profilleri (gün, saat aralığı, ses seviyesi, müzik listesi)
Bu dosyalar metin tabanlıdır; gerektiğinde elle de düzenlenebilir (dikkatli olmak şartıyla).

💻 Sistem Gereksinimleri
Windows 7 / 8 / 10 / 11
.NET Framework (WinForms desteği olan sürüm – projene göre)
Windows Media Player (WMP) yüklü olmalı (WMPLib kullanıyor)
Okulda genelde tam ekran çalışan bir PC yeterli
🚀 Kurulum
Uygulama dosyalarını bir klasöre çıkar.
Gerekli ses klasörleri yoksa uygulama ilk açılışta otomatik oluşturur:
ZilSesleri, AlarmSesleri, Marslar, TeneffusMuzikleri
İstediğin .mp3/.wav dosyalarını ilgili klasörlere kopyala.
SSEML_OkulZili.exe’yi çalıştır.
🖥️ Ana Ekran Özeti
Ana form (Form1):

Üst kısım: Saat, tarih, geri sayım, sıradaki ders/zil bilgisi
Sol taraf: Profil kartları (NormalGun, OgleOkulu vb.)
Orta: Günün programı (zaman, ders, açıklama)
Sağ: Ses ayarları (zil/alarm/marş seçimi, ses seviyesi)
Alt: Ayar, takvim, teneffüs müzik, test butonları
Profil Kartları
Her profil bir “okul günü tipi”: Normal gün, öğle okulu vb.
Profil kartına tıklayınca o profil aktif olur.
Varsayılan profiller:
NormalGun
OgleOkulu
(İstersen kendin yenilerini ekleyebilirsin.)
🔊 Ses Ayarları
Sağ panelde:

Zil Sesi (ComboBox)
ZilSesleri klasöründeki dosyalardan seçilir.
Alarm Sesi
AlarmSesleri klasöründen.
Marş Sesi
Marslar klasöründen.
Test butonları
Zil/Alarm/Marş için ayrı ayrı test edip durdurabilirsin.
Ses Seviyesi (TrackBar)
Tüm zil/Marş/Alarm/önizleme için genel WMP volume (teneffüs müziği kendi seviyesini ayrıca profilden alır).
📅 Takvim Sistemi
1. Tekil Tarih Ayarları
Takvim butonu → TakvimForm

Solda MonthCalendar ile tarih seçersin.
Profil seç (veya “(Otomatik - Gün bazlı)” bırak).
Açıklama yaz (zorunlu alan).
“🔇 Ziller Çalmasın (Tatil)” tikiyle o gün tüm zilleri devre dışı bırakabilirsin.
➕ EKLE ile o tarihi Takvim listesine kaydedersin.
Sağ listede tüm özel günler görünür, seçim yapıp 🗑️ SİL ile kaldırabilirsin.
Bu kayıtlar Takvim.txt içinde tutulur.

2. Otomatik Kurallar (Her Pazartesi Öğle Okulu vb.)
TakvimForm’un altındaki “Otomatik Kurallar (Tekrarlayan)” alanı:

Gün seç: Pazartesi / Salı / … / Pazar
Profil seç: NormalGun, OgleOkulu vb.
✓ ile kural ekle:
Örnek:
“Pazartesi” + OgleOkulu
→ Her pazartesi otomatik öğle okulu profili
Aynı güne tekrar kural eklerken eski kuralı güncelleyip güncellemeyeceğin sorulur.
Sağdaki “Aktif Kurallar” listesinde hepsi görünür.
Kural seçip ✕ veya çift tıklama ile silebilirsin.
Bu kurallar TakvimKurallari.txt içinde saklanır.

3. Günlük Profil Seçim Mantığı
Uygulama açıldığında (veya gün değiştiğinde) aktif profil seçimi:

Önce Takvim.txt
Bugüne özel kayıt varsa → o profil kullanılır.
Sonra TakvimKurallari.txt
Gün indexine uyan kural varsa → o profil kullanılır.
Hiçbiri yoksa eski mantık:
Cumartesi/Pazar → varsa HaftaSonu yoksa NormalGun
Pazartesi/Perşembe → OgleOkulu
Diğer günler → NormalGun
🎵 Teneffüs Müzik Sistemi
Teneffüs Müzik butonu → TeneffusMuzikForm

Her teneffüs profili için:

Profil adı
Gün (0=Pazar, 1=Pazartesi, … 6=Cumartesi)
Saat aralığı (örn. 09:55–10:10)
Ses seviyesi (%5–%100)
Hangi müzik dosyaları (TeneffusMuzikleri klasöründen seçim)
Çalışma Mantığı
teneffusKontrolTimer her 500 ms’de:
Bugünün gününe ve şu anki saate göre uygun aktif profil var mı bakar.
Varsayılan olarak:
BaslangicSaat <= ŞimdikiSaat < BitisSaat ise profil aktif sayılır.
Bir teneffüs profili aktif olduğunda:
Seçili müzikler sırayla çalınır.
Son şarkı bitince listede başa döner.
Bitiş saatine gelince müzik durdurulur.
Zil/Alarm/Marş/Test çalınca:
Devam eden teneffüs müziği duraklatılır, konumu kaydedilir.
Zil/Alarm/Marş/Test bitince:
Zil/Alarm/Marş çalmıyorsa ve saat aralığı hâlâ uygunsa teneffüs müziği kaldığı yerden devam eder.
🛎️ Zil Sistemi
Tüm zil saatleri, aktif profil için profiller sözlüğünde (ZamanItem listeleri) tutulur.
tmrZilCheck her saniye:
Aktif profilin bugünkü saatine göre:
Şu anki saatle eşleşen ZamanItem varsa zil çalınır.
Çakışmalar:
marsCaliniyor == true ise zil çalmaz.
Zil devre dışı işaretliyse (chkZilDevreDisi) saatleri işaretleyip çalmaz.
Aynı dakika içinde aynı zil ikinci kez çalmaz (sonCalinanZaman kontrolü).
🚨 Alarm ve Marş
Acil Alarm butonu:
Kullanıcıdan onay alır.
Diğer sesleri durdurur, teneffüs müziğini duraklatır.
Seçili alarm sesini çalar.
Marş butonu:
Onay alır.
Diğer sesleri durdurur, teneffüs müziğini duraklatır.
Seçili marşı çalar.
Her ikisi için de:
Bitince, eğer teneffüs müziği duraklatılmışsa devam ettirilir.
🌙 Karanlık Mod
Sağ üstteki Karanlık Mod checkbox’ı ile:
Tüm arka plan ve yazı renkleri koyu/aydınlık tema arasında geçiş yapar.
Seçim Ayarlar.txt içinde KaranlikMod= satırında saklanır.
🔧 Sorun Giderme
Ses hiç çalmıyor:
Dosyalar doğru klasörde mi? (ZilSesleri/AlarmSesleri/Marslar/TeneffusMuzikleri)
Dosya uzantısı .mp3 veya .wav mı?
Windows Media Player kurulu mu?
Hata “ZamanItem/TakvimGunu/TakvimKural tanımsız”:
Bu sınıfların Form1.cs içinde veya ayrı bir .cs dosyasında (aynı namespace içinde) tanımlı olduğundan emin ol.
Takvim kuralı çalışmıyor:
TakvimKurallari.txt silinip yeniden kural eklenerek oluşturulabilir.
Gün indexleri: 0=Pazartesi, 1=Salı, 2=Çarşamba, 3=Perşembe, 4=Cuma, 5=Cumartesi, 6=Pazar.
💡 Önerilen Kullanım Senaryosu
Zil, Alarm, Marş seslerini ilgili klasörlere koy.
Uygulamayı aç, Ses Ayarları kısmında her birini seç.
Profil yöneticisinden (Ayarlar → ProfileManagerForm) gün içi zil saatlerini okuluna göre düzenle.
Takvim kısmında:
Resmi tatiller (zilleri kapat)
Sınav günleri (özel profil)
Her Pazartesi/Çarşamba → OgleOkulu kuralı ekle.
Teneffüs Müzik kısmında teneffüs müzik profilleri oluştur:
Örneğin: “Pazartesi 3. Teneffüs 09:40–10:00”
Uygulamayı sistemle birlikte başlatıp simge durumuna küçülterek tüm günü otomatik çalışmasını sağla.
