# Zenora Network Mobil Launcher — APK Derleme Rehberi

## Paket İçeriği
- `ZenoraConfig.kt`: Sunucu IP (`185.158.151.45`) ve otomatik bağlantı parametreleri.
- `OfflineAccountManager.kt`: Orijinal hesaba gerek kalmadan çevrimdışı profil oluşturma ve UUID üretimi.
- `ServerDatGenerator.kt`: Minecraft `servers.dat` dosyasına Zenora Network sunucusunu otomatik ekler.
- `ModrinthManager.kt`: Modrinth üzerinden Mod ve Resource Pack arama & indirme motoru.
- `MainActivity.kt` & `activity_main.xml`: Yatay ekran mobil launcher arayüzü.
- `.github/workflows/build-apk.yml`: Bilgisayar yormadan GitHub üzerinde bulutta otomatik APK üretme dosyası.

## Yöntem 1: Android Studio ile Tek Tıkla APK Alma (Bilgisayarda)
1. ZIP'i bir klasöre çıkarın.
2. **Android Studio**'yu açın ve **Open** diyerek bu klasörü seçin.
3. Sağ alttaki Gradle senkronizasyonunun bitmesini bekleyin.
4. Üst menüden **Build > Build Bundle(s) / APK(s) > Build APK(s)** seçeneğine tıklayın.
5. Oluşan `app-debug.apk` dosyasını telefonunuza atıp kurun.

## Yöntem 2: GitHub Actions ile Bulutta APK Alma (Android Studio Kurmadan)
1. GitHub'da yeni bir depo (repository) oluşturun ve bu ZIP içindeki tüm dosyaları yükleyin.
2. GitHub'da **Actions** sekmesine girin ve **Build Zenora Network APK** iş akışını çalıştırın.
3. İşlem bittiğinde **Artifacts** bölümünden `ZenoraNetwork-APK` dosyasını telefonunuza indirin.

## Not: Tam Minecraft Java Motoru Entegrasyonu
Bu proje Zenora Network arayüzünü, profil sistemini, Modrinth mağazasını ve `185.158.151.45` oto-bağlantı altyapısını içerir. Telefonun içinde Java VM + OpenGL (GL4ES) çalıştırmak için açık kaynaklı **MojoLauncher / PojavLauncher** reposunu klonlayıp bu `network.zenora.launcher` sınıflarını içine kopyalamanız yeterlidir.
