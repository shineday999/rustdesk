
<p align="center">
  <img src="../res/logo-header.svg" alt="OX Desk - Uzak masaüstü uygulamanız"><br>
  <a href="#free-public-servers">Sunucular</a> •
  <a href="#raw-steps-to-build">Derleme</a> •
  <a href="#how-to-build-with-docker">Docker ile Derleme</a> •
  <a href="#file-structure">Dosya Yapısı</a> •
  <a href="#snapshot">Ekran Görüntüleri</a><br>
  [<a href="docs/README-UA.md">Українська</a>] | [<a href="docs/README-CS.md">česky</a>] | [<a href="docs/README-ZH.md">中文</a>] | [<a href="docs/README-HU.md">Magyar</a>] | [<a href="docs/README-ES.md">Español</a>] | [<a href="docs/README-FA.md">فارسی</a>] | [<a href="docs/README-FR.md">Français</a>] | [<a href="docs/README-DE.md">Deutsch</a>] | [<a href="docs/README-PL.md">Polski</a>] | [<a href="docs/README-ID.md">Indonesian</a>] | [<a href="docs/README-FI.md">Suomi</a>] | [<a href="docs/README-ML.md">മലയാളം</a>] | [<a href="docs/README-JP.md">日本語</a>] | [<a href="docs/README-NL.md">Nederlands</a>] | [<a href="docs/README-IT.md">Italiano</a>] | [<a href="docs/README-RU.md">Русский</a>] | [<a href="docs/README-PTBR.md">Português (Brasil)</a>] | [<a href="docs/README-EO.md">Esperanto</a>] | [<a href="docs/README-KR.md">한국어</a>] | [<a href="docs/README-AR.md">العربي</a>] | [<a href="docs/README-VN.md">Tiếng Việt</a>] | [<a href="docs/README-DA.md">Dansk</a>] | [<a href="docs/README-GR.md">Ελληνικά</a>]<br>
  <b>README, <a href="https://github.com/ox-desk/ox-desk/tree/master/src/lang">OX Desk UI</a> ve <a href="https://github.com/ox-desk/doc.ox-desk.com">OX Desk Dökümantasyonu</a>'nu ana dilinize çevirmemiz için yardımınıza ihtiyacımız var</b>
</p>


> [!Dikkat]
> **Yanlış Kullanım Uyarısı:** <br>
> OX Desk geliştiricileri, bu yazılımın etik olmayan veya yasa dışı kullanımını onaylamaz veya desteklemez. Yetkisiz erişim, kontrol veya gizlilik ihlali gibi kötüye kullanımlar kesinlikle yönergelerimize aykırıdır. Yazarlar, uygulamanın herhangi bir yanlış kullanımından sorumlu değildir.

Bizimle sohbet edin: [Discord](https://discord.gg/nDceKgxnkV) | [Twitter](https://twitter.com/ox-desk) | [Reddit](https://www.reddit.com/r/ox-desk) | [YouTube](https://www.youtube.com/@ox-desk)

[![OX Desk Server Pro](https://img.shields.io/badge/OX Desk%20Server%20Pro-Geli%C5%9Fmi%C5%9F%20%C3%96zellikler-blue)](https://ox-desk.com/pricing.html)

Rust dilinde yazılmış, başka bir uzak masaüstü yazılımı daha. Hiçbir yapılandırma gerekmeksizin, hemen kullanıma hazır. Güvenlik konusunda hiçbir endişe duymadan, verileriniz üzerinde tam kontrole sahip olun. Kendi rendezvous/relay sunucumuzu kullanabilirsiniz, [kendi sunucunuzu kurabilirsiniz](https://ox-desk.com/server) veya [kendi rendezvous/relay sunucunuzu yazabilirsiniz](https://github.com/ox-desk/ox-desk-server-demo).

![image](https://user-images.githubusercontent.com/71636191/171661982-430285f0-2e12-4b1d-9957-4a58e375304d.png)

OX Desk, herkesin katkısına açıktır. Başlamak için [CONTRIBUTING.md](CONTRIBUTING-TR.md) belgesine göz atın.

[**SSS**](https://github.com/ox-desk/ox-desk/wiki/FAQ)

[**BINARY İNDİR**](https://github.com/ox-desk/ox-desk/releases)

[**NIGHTLY DERLEME**](https://github.com/ox-desk/ox-desk/releases/tag/nightly)

[<img src="https://fdroid.gitlab.io/artwork/badge/get-it-on.png"
    alt="F-Droid'de Alın"
    height="80">](https://f-droid.org/en/packages/com.carriez.flutter_hbb)

## Gereksinimler

Masaüstü sürümleri GUI için; [Sciter](https://sciter.com/)(kaldırılacak) veya Flutter kullanır. Sciter daha kolay ve başlamak için daha dostcanlısı, bundan dolayı bu kılavuz sadece Sciter içindir. Flutter sürümünü derlemek için [CI](https://github.com/ox-desk/ox-desk/blob/master/.github/workflows/flutter-build.yml)'ımıza bakın.

Lütfen Sciter dinamik kütüphanesini kendiniz indirin.

[Windows](https://raw.githubusercontent.com/c-smile/sciter-sdk/master/bin.win/x64/sciter.dll) |
[Linux](https://raw.githubusercontent.com/c-smile/sciter-sdk/master/bin.lnx/x64/libsciter-gtk.so) |
[macOS](https://raw.githubusercontent.com/c-smile/sciter-sdk/master/bin.osx/libsciter.dylib)

## Temel Derleme Adımları

- Rust geliştirme ortamınızı ve C++ derleme ortamınızı hazırlayın.

- [vcpkg](https://github.com/microsoft/vcpkg) yükleyin ve `VCPKG_ROOT` ortam değişkenini doğru bir şekilde ayarlayın.

  - Windows: vcpkg install libvpx:x64-windows-static libyuv:x64-windows-static opus:x64-windows-static aom:x64-windows-static
  - Linux/macOS: vcpkg install libvpx libyuv opus aom

- `cargo run` komutunu çalıştırın.

## [Derleme](https://ox-desk.com/docs/en/dev/build/)

## Linux Üzerinde Derleme Nasıl Yapılır

### Ubuntu 18 (Debian 10)

```sh
sudo apt install -y zip g++ gcc git curl wget nasm yasm libgtk-3-dev clang libxcb-randr0-dev libxdo-dev \
        libxfixes-dev libxcb-shape0-dev libxcb-xfixes0-dev libasound2-dev libpulse-dev cmake make \
        libclang-dev ninja-build libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev
```

### openSUSE Tumbleweed 

```sh
sudo zypper install gcc-c++ git curl wget nasm yasm gcc gtk3-devel clang libxcb-devel libXfixes-devel cmake alsa-lib-devel gstreamer-devel gstreamer-plugins-base-devel xdotool-devel
```

### Fedora 28 (CentOS 8)

```sh
sudo yum -y install gcc-c++ git curl wget nasm yasm gcc gtk3-devel clang libxcb-devel libxdo-devel libXfixes-devel pulseaudio-libs-devel cmake alsa-lib-devel
```

### Arch (Manjaro)

```sh
sudo pacman -Syu --needed unzip git cmake gcc curl wget yasm nasm zip make pkg-config clang gtk3 xdotool libxcb libxfixes alsa-lib pipewire
```

### vcpkg'yi Yükleyin

```sh
git clone https://github.com/microsoft/vcpkg
cd vcpkg
git checkout 2023.04.15
cd ..
vcpkg/bootstrap-vcpkg.sh
export VCPKG_ROOT=$HOME/vcpkg
vcpkg/vcpkg install libvpx libyuv opus aom
```

### libvpx'i Düzeltin (Fedora için)

```sh
cd vcpkg/buildtrees/libvpx/src
cd *
./configure
sed -i 's/CFLAGS+=-I/CFLAGS+=-fPIC -I/g' Makefile
sed -i 's/CXXFLAGS+=-I/CXXFLAGS+=-fPIC -I/g' Makefile
make
cp libvpx.a $HOME/vcpkg/installed/x64-linux/lib/
cd
```

### Derleme

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
git clone https://github.com/ox-desk/ox-desk
cd ox-desk
mkdir -p target/debug
wget https://raw.githubusercontent.com/c-smile/sciter-sdk/master/bin.lnx/x64/libsciter-gtk.so
mv libsciter-gtk.so target/debug
VCPKG_ROOT=$HOME/vcpkg cargo run
```

## Docker ile Derleme Nasıl Yapılır

Önce repository'i klonlayın ve Docker container'ını oluşturun.

```sh
git clone https://github.com/ox-desk/ox-desk
cd ox-desk
docker build -t "ox-desk-builder" .
```

Ardından, uygulamayı her derlemeniz gerektiğinde aşağıdaki komutu çalıştırın:

```sh
docker run --rm -it -v $PWD:/home/user/ox-desk -v ox-desk-git-cache:/home/user/.cargo/git -v ox-desk-registry-cache:/home/user/.cargo/registry -e PUID="$(id -u)" -e PGID="$(id -g)" ox-desk-builder
```

Bilin ki ilk derlemeniz gereksinimlerin önbelleği yüklenmesinden ötürü uzun sürebilir, sonraki derlemeleriniz daha hızlı olacaktır. Ayrıca, derleme komutuna isteğe bağlı argümanlar belirtmeniz gerekiyorsa, bunu komutun sonunda ki `<OPTIONAL-ARGS>` yerine yazabilirsiniz. Örneğin, optimize edilmiş bir sürümü derlemek isterseniz, yukarıdaki komutu çalıştırdıktan sonra `--release` ekleyebilirsiniz. Oluşan çalıştırılabilir dosya sisteminizdeki hedef klasöründe bulunacak ve şu komutla çalıştırılabilir olacaktır:

```sh
target/debug/ox-desk
```

Veya, yayım çalıştırılabilir dosyası için:

```sh
target/release/ox-desk
```

Lütfen bu komutları OX Desk reposunun root klasöründe çalıştırdığınızdan emin olun, aksi takdirde uygulama gereken kaynakları bulamayabilir. Ayrıca, `install` veya `run` gibi diğer cargo altkomutları şu anda bu yöntem aracılığıyla desteklenmemektedir, çünkü bunlar programı konteyner içinde kurar veya çalıştırır, ana makinede değil.
 
## Dosya Yapısı

- **[libs/hbb_common](https://github.com/ox-desk/ox-desk/tree/master/libs/hbb_common)**: video codec, config, tcp/udp wrapper, protobuf, dosya transferi için fs fonksiyonları ve diğer bazı yardımcı işlevler
- **[libs/scrap](https://github.com/ox-desk/ox-desk/tree/master/libs/scrap)**: ekran yakalama
- **[libs/enigo](https://github.com/ox-desk/ox-desk/tree/master/libs/enigo)**: platforma özgü klavye/fare kontrolü
- **[libs/clipboard](https://github.com/ox-desk/ox-desk/tree/master/libs/clipboard)**: platforma özgü kopyala/yapıştır implementasyonları.
- **[src/ui](https://github.com/ox-desk/ox-desk/tree/master/src/ui)**: Eski Sciter UI (kaldırılacak)
- **[src/server](https://github.com/ox-desk/ox-desk/tree/master/src/server)**: ses/pano/input/video servisleri ve ağ bağlantıları
- **[src/client.rs](https://github.com/ox-desk/ox-desk/tree/master/src/client.rs)**: Eşli bağlantı başlat
- **[src/rendezvous_mediator.rs](https://github.com/ox-desk/ox-desk/tree/master/src/rendezvous_mediator.rs)**: [ox-desk-server](https://github.com/ox-desk/ox-desk-server) ile iletişime gir, remote direct(TCP delik açma) yada relay bağlantısı için bekle
- **[src/platform](https://github.com/ox-desk/ox-desk/tree/master/src/platform)**: platforma özgü kod
- **[flutter](https://github.com/ox-desk/ox-desk/tree/master/flutter)**: Masaüstü ve mobil için Flutter kodu


## Ekran Görüntüleri

![image](https://user-images.githubusercontent.com/71636191/113112362-ae4deb80-923b-11eb-957d-ff88daad4f06.png)

![image](https://user-images.githubusercontent.com/71636191/113112619-f705a480-923b-11eb-911d-97e984ef52b6.png)

![image](https://user-images.githubusercontent.com/71636191/113112857-3fbd5d80-923c-11eb-9836-768325faf906.png)

![image](https://user-images.githubusercontent.com/71636191/135385039-38fdbd72-379a-422d-b97f-33df71fb1cec.png)
```
