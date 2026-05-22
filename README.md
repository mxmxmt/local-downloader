# Local Page Media Downloader

Bu Chrome/Chromium tabanlı tarayıcı eklentisi, aktif sayfada tarayıcınızın zaten erişebildiği medya URL'lerini yerel olarak bulur ve isteğe bağlı olarak indirir. Chrome, Edge ve Brave gibi Manifest V3 destekleyen tarayıcılarda çalışır.

Eklenti DRM, kimlik doğrulama, ödeme duvarı, telif koruması veya korumalı stream mekanizmalarını aşmaya çalışmaz.

## Özellikler

- Normal `img src` ve `img srcset` görselleri
- Lazy-load için sık kullanılan `data-src`, `data-original`, `data-lazy-src` gibi görsel öznitelikleri
- `picture/source` kaynakları
- Video `src`, `source` ve poster görselleri
- Audio `src`, `source`, preload ve link kaynakları
- CSS background-image kaynakları
- Link olarak verilen medya dosyaları
- OpenGraph/Twitter image/video meta etiketleri
- OpenGraph/Twitter audio meta etiketleri
- Göreli ve protokol-göreli URL'leri sayfanın adresine göre çözer
- Tekrarlanan URL'leri tekilleştirir
- Ayarlanabilir minimum dosya boyutu filtresi
- Sadece kullanıcı `Sayfayı Tara` butonuna bastığında çalışır

## Kurulum

1. Bu klasörü ZIP'ten çıkardıysanız çıkarın.
2. Chrome/Edge/Brave içinde `chrome://extensions` sayfasını açın.
3. `Developer mode` / `Geliştirici modu` seçeneğini açın.
4. `Load unpacked` / `Paketlenmemiş öğe yükle` seçin.
5. Bu eklenti klasörünü seçin.

## Kullanım

1. Medya indirmek istediğiniz sayfayı normal şekilde açın.
2. Eklenti ikonuna tıklayın.
3. `Sayfayı Tara` butonuna basın.
4. Gerekirse filtreleri düzenleyin.
5. Ayarlar düğmesinden minimum dosya boyutu filtresini ayarlayın.
6. `Filtrelenenleri İndir` butonuna basın.

Çok sayıda dosya seçildiyse eklenti indirme başlamadan önce onay ister.

## Ayarlar

- `Minimum dosya boyutu`: Örneğin `10` yazarsanız boyutu bilinen 10 KB altı medya listede gösterilmez.
- `Boyutu bilinmeyen medyaları göster`: Kapalıysa tarayıcının boyutunu bildirmediği kaynaklar da gizlenir.

Boyut filtresi ekstra `fetch`, `HEAD` veya ağ isteği yapmaz. Yalnızca sayfanın zaten yüklediği kaynaklar için tarayıcının `performance` kayıtlarında görünen boyut bilgisini ve `data:` URL boyutlarını kullanır. Bu nedenle bazı çapraz kaynaklı veya önbellekten gelen dosyaların boyutu bilinmeyebilir.

## İndirebildikleri

- JPG, PNG, GIF, WebP, SVG, AVIF, BMP ve ICO gibi görsel dosyaları
- MP4, WebM, MOV, M4V, AVI ve MKV gibi doğrudan erişilebilir video dosyaları
- MP3, M4A, AAC, WAV, FLAC, OGG, OPUS ve WEBA gibi doğrudan erişilebilir ses dosyaları
- `data:image/...` ve `data:video/...` kaynakları
- `data:audio/...` kaynakları
- Sayfa HTML'i, meta etiketleri, linkleri, mevcut CSS stilleri ve yüklenmiş kaynak kayıtlarında görünen medya URL'leri

## İndiremedikleri ve sınırlar

- DRM korumalı yayınları indirmez.
- Paywall, giriş, yetki veya telif korumasını aşmaz.
- HLS/DASH playlistleri (`.m3u8`, `.mpd`) normal video dosyası gibi indirmeyi hedeflemez.
- MSE/stream tabanlı oynatıcıların parça parça yüklediği video akışlarını birleştirmez.
- Blob URL'leri sayfaya özel ve geçici olabilir. Listede görünebilirler, ancak eklenti bunları güvenilir indirilebilir dosya olarak kabul etmez.
- Tarayıcının normalde erişemediği veya sayfada URL olarak görünmeyen medyaları bulamaz.
- `chrome://`, Chrome Web Store ve tarayıcı tarafından korunan özel sayfalarda içerik betiği çalıştırılamaz.
- Dosya boyutu her kaynak için bilinmeyebilir; eklenti bunu ekstra ağ isteği yapmadan güvenli biçimde ele alır.

## Gizlilik

- Tüm tarama aktif sekmede ve yerel olarak yapılır.
- Harici sunucuya veri gönderilmez.
- Telemetri, analiz, takip kodu veya uzaktan yüklenen kod yoktur.
- Otomatik arka plan taraması yoktur.
- İndirme yalnızca kullanıcı indirme butonuna bastığında başlar.

## İzinler

- `activeTab`: Kullanıcı eklentiyi açtığında yalnızca aktif sekmeye geçici erişim sağlar.
- `scripting`: Kullanıcı tarama istediğinde aktif sayfada medya URL'lerini toplayan kısa kodu çalıştırmak için kullanılır.
- `downloads`: Kullanıcının seçili medya URL'lerini tarayıcının indirme yöneticisiyle indirmek için kullanılır.

`host_permissions` kullanılmaz; eklenti tüm sitelere kalıcı erişim istemez.

## Chrome Web Store hazırlığı

Bu depoda mağaza hazırlığı için şu dosyalar bulunur:

- `PRIVACY.md`: Gizlilik politikası metni.
- `store-listing/listing.md`: Başlık, açıklama, izin açıklamaları ve dashboard notları.
- `store-assets/`: 1280x800 screenshot ve 440x280 küçük tanıtım görseli.
- `dist/local-page-media-downloader-1.1.0.zip`: Chrome Web Store'a yüklenebilecek paket.

Chrome Web Store Developer Dashboard gizlilik politikası için herkese açık bir URL ister. `PRIVACY.md` dosyasını GitHub Pages, kendi siteniz veya başka bir kalıcı herkese açık URL üzerinden yayınlayıp Dashboard'daki privacy policy alanına ekleyin.

## Yasal not

Bu araç yalnızca yerel ve kullanıcı kontrollü kullanım içindir. İndirdiğiniz içerikler için telif haklarına, lisanslara ve web sitesi kullanım şartlarına uymak sizin sorumluluğunuzdadır.
