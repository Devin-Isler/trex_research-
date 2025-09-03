# Trex Research - .NET Backend Geliştirme

## 1. Modern Yazılım Geliştirme Pratikleri
### Git
Git, dağıtık bir versiyon kontrol sistemidir. Yazılım projelerinde veya dosya yönetiminde yapılan değişiklikleri kaydedip, takip etip ve yöneterek versiyon kontrolünü kolaylaştırır.
### GitHub
Github, Git versiyon kontrol sistemini kullanan projeler için bir bulut tabanlı platformdur. Git projeleri saklamak, paylaşmak ve ekip halinde yönetmek için kullanılan bir internet platformudur.
### Temel Git Komutları
- `git init` → Yeni bir repo başlatır.
- `git clone` → Mevcut bir projeyi klonlayıp yerel bilgisayarına indirir.
- `git add` → Değişiklikleri bir sonraki commit'e ekler.
- `git commit -m "mesaj"` → Değişiklikleri kaydeder. Mesaj ekleyerek değişiklikler açıklanabilir.
- `git push` → Değişiklikleri uzak repoya yollar.
- `git pull` → Uzak repodaki değişiklikleri indirir.
- `git branch` → Yeni bir branch(dal) oluşturur.
- `git merge` → Belirli bir branch'in değişikliklerini aktif branch ile birleştirir
### Merge Conflict
Eğer bir dosyanın aynı kısmını, iki farklı dalda iki farklı şekilde değiştirildiyse, Git bu değişimlerden hangisini birleştirmeye katacağını bilemeyeceği için, temiz bir birleştirme işlemi yapamaz.	Git'in çatışmalı dosyada koyduğu özel işaretlere bakılarak, yapılacak değişiklik manuel olarak seçilir.
### CI/CD
- **CI (Continuous Integration):** Kodların geliştirildikten sonra entegre olmadan sürekli bir kontrol mekanizmasının olmasıdır. 
- **CD (Continuous Delivery/Deployment):** Sürekli doğrulama ve sürekli dağıtım olmasıdır.
.NET projelerinde CI'ın görevi kod her push edildiğinde derlenip test edilmesini sağlamak. CD'nin görevi de başarılı CI sonrası kodu otomatik olarak staging veya production ortamına dağıtmak.

### Yazılım Geliştirme Süreçleri (SDLC)
Adımlar: **Planlama → Analiz → Tasarım → Uygulama → Test → Dağıtım → Bakım**
1. **Planlama (Planning)**  
   Projenin kapsamı, hedefleri, kaynakları ve zaman çizelgesi belirlenir. Riskler değerlendirilir ve proje yol haritası oluşturulur.
2. **Gereksinim Analizi (Requirement Analysis)**  
   Yazılımın ne yapması gerektiği belirlenir. İş gereksinimleri ve kullanıcı ihtiyaçları toplanır.
3. **Sistem Tasarımı (System Design)**  
   Gereksinimlerin teknik olarak nasıl uygulanacağı belirlenir. Veri yapıları, yazılım mimarisi ve kullanıcı arayüzü tasarımları oluşturulur.
4. **Uygulama / Kodlama (Implementation / Coding)**  
   Tasarıma uygun şekilde yazılımın kodlanması. Kod yazılır ve birim testleri yapılır.
5. **Test (Testing)**  
   Yazılımın hatasız çalıştığını ve gereksinimleri karşıladığını doğrulamak için testler yapılır.
6. **Kurulum / Dağıtım (Deployment)**  
   Yazılım kullanıcıya sunulmak üzere üretim ortamına taşınır.
7. **Bakım (Maintenance)**  
   Yazılım kullanım sırasında hatalardan arındırılır, güncellenir ve yeni gereksinimlere göre geliştirilir.
   
Yazılımcılar SDLC’de özellikle **kodlama, test ve bakım aşamalarında aktif rol oynar**. Planlama, gereksinim analizi ve tasarım aşamalarında ise teknik değerlendirme ve danışmanlık yaparlar.

- **Agile:** Yazılım geliştirme ve proje yönetiminde esnek, iteratif ve müşteri odaklı bir yaklaşımdır.
- **Scrum:**  Agile metodolojisinin en popüler çerçevelerinden biridir.
- **Kanban:** İş akışını görselleştiren, sürekli akışı ön planda tutan bir metodolojidir.


## 2. .NET Ekosistemi
### .NET nedir?
.NET, Microsoft tarafından geliştirilmiş bir yazılım geliştirme platformudur. Geliştiricilerin farklı türde uygulamalar (masaüstü, web, mobil, oyun, bulut) oluşturmasını kolaylaştırır. Platform, dil bağımsızlığı sağlar; yani bir uygulama C#, F#, VB.NET gibi farklı farklı dillerle yazılabilir.

.NET, 2000 yılında Microsoft tarafından Windows uygulamaları geliştirmeyi kolaylaştırmak amacıyla duyuruldu. 2002’de ilk sürümü yayımlandı ve 2016’da açık kaynaklı ve platformlar arası çalışabilen .NET Core ile geliştirildi; günümüzde modern .NET sürümleriyle devam ediyor.

.NET farklı dilleri tek platformda birleştirerek uygulama geliştirme sürecini uyumlu,hızlı ve güvenilir hale getirmeyi hedefler. 

.NET farklı işletim sistemleri üzerinden erişilebilmesi(Linux, Windows, macOs), geniş kütüphane desteği, yüksek performans, güvenli ve sürekli olarak gelişen bir platform olduğundan tercih edilmektedir.

### .NET Framework, .NET Core ve .NET 7/8+

| Özellik              | .NET Framework          | .NET Core                 | .NET 7/8+ (Modern .NET) |
|---------------------|------------------------|--------------------------|-------------------------|
| Çıkış Yılı           | 2002                   | 2016                     | 2020+                   |
| Platform             | Sadece Windows         | Windows, Linux, macOS    | Windows, Linux, macOS, Mobil, IoT |
| Açık Kaynak          | Hayır                  | Evet                     | Evet                    |
| Kullanım Alanı       | Masaüstü, eski web     | Modern web, mikro servis | Her tür uygulama        |
| Avantaj              | Olgun, kararlı kütüphane | Hafif, platform bağımsız | Tek platform, performans, modern özellikler |

### .NET --info
dotnet --info komutu, .NET SDK ve çalışma ortamınız hakkında kapsamlı bilgi sunar. Bu komut, özellikle kurulum sorunlarını teşhis etmek, destek talepleri oluşturmak veya sistem uyumluluğunu kontrol etmek için faydalıdır.

```powershell
# .NET SDK ve Runtime Bilgisi
.NET SDK (reflected in global.json):
 Version:   8.0.100
 Commit:    abc123def456

Runtime Environment:
 OS Name:     Windows
 OS Version:  10.0.19045
 OS Platform: Windows
 RID:         win-x64
 Base Path:   C:\Program Files\dotnet\sdk\8.0.100\

Host (useful for support):
 Version: 8.0.0
 Commit:  abc123def456

.NET SDKs installed:
 8.0.100 [C:\Program Files\dotnet\sdk]

.NET runtimes installed:
 Microsoft.NETCore.App 8.0.0 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
 Microsoft.AspNetCore.App 8.0.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
 Microsoft.WindowsDesktop.App 8.0.0 [C:\Program Files\dotnet\shared\Microsoft.WindowsDesktop.App]
```
- **.NET SDK:** Projede belirtilen SDK sürümüdür.
- **Runtime Environment:** İşletim sistemi ve çalışma ortamı bilgilerini içerir.
- **Host:** .NET çalışma zamanının sürüm ve commit bilgilerini gösterir.
- **Yüklü SDK’lar:** Sistemde kurulu olan tüm SDK sürümlerini listeler. Farklı projelerde farklı SDK sürümleri kullanılıyorsa, sürümleri takip etmek için bakılır.
- **Yüklü çalışma zamanları:** Kurulu olan tüm çalışma zamanı sürümlerini ve ilgili paylaşımlı dizinleri belirtir.

### Senkron ve Asenkron Programlama
- **Senkron Programlama:** İşlemler sırasıyla, birinin bitmesini bekleyerek yapılır.  
Senaryo:  
-Bir banka uygulaması var ve müşteri hesabına bakiye sorgulamak istiyor. Program şu adımları takip ediyor:  
	1. Veritabanına bağlan  
  2. Hesap bilgilerini getir  
  3. Sonucu ekrana yazdır  

  Senkron Çalışma Şekli:  
  - Program adım adım ilerler.  
  - Veritabanı sorgusu uzun sürerse, kullanıcı ekranında bekler ve başka bir işlem yapamaz.  
  - Basit ve anlaşılır bi yapı ama uzun süren işlemlerde UI veya uygulama bloke olur.  
 
- **Asenkron Programlama:** İşlemler eşzamanlı veya bekleme olmadan yürütülür.  
Senaryo:  
-Aynı banka uygulaması, ama kullanıcı birden fazla işlem yapmak isteyebilir:
  1. Hesap sorgulama
	2. Para transferi
	3. Bildirim gönderme

  Asenkron Çalışma Şekli:  
  - Hesap sorgulama işlemi başlatılır, ama uygulama başka işleri de yapabilir.  
  - Kullanıcı UI kilitlenmez.  
  - Uzun süren işlemler sırasında uygulama yanıt vermeye devam eder.  
  - Kullanıcı başka işlemler yapabilir (UI freeze olmaz).
### Arrow Function (=>)
C#’ta: => expression-bodied members olarak kullanılır. Daha kısa ve okunabilir metod, property veya lambda fonksiyonu yazmak için kullanılır.
```powershell
int Kare(int x) => x * x;
Console.WriteLine(Kare(5)); // 25
```
## 3. Backend Geliştirme Temelleri
### Backend
Backend, bir web sitesinin veya uygulamanın kullanıcı görmediği, veri yönetimi, sunucu işlemleri ve iş mantığını yöneten kısmıdır; veritabanı sorgulamaları, kullanıcı doğrulama ve sunucu tarafı hesaplamalar burada gerçekleşir. Frontend ise kullanıcıların gördüğü ve etkileşimde bulunduğu kısımdır; tasarım, arayüz ve kullanıcı deneyimi (UI/UX) ile ilgilenir. Kısaca, frontend “görünen yüz” iken, backend “arkadaki motor” gibidir. 

### Web Sunucusu
Web sunucusu, internet üzerinden kullanıcıların tarayıcıları aracılığıyla web sayfalarına erişmesini sağlayan yazılım ve donanım sistemidir; gelen istekleri alır, işler ve uygun web içeriğini (HTML, CSS, JS, görseller) kullanıcıya gönderir.
### API
API (Application Programming Interface), farklı yazılım uygulamalarının birbirleriyle veri ve işlev paylaşmasını sağlayan arayüzdür; yani programların “konuşmasını” sağlar.
Başlıca türleri:
- **REST API:** HTTP protokolü üzerinden çalışır, genellikle JSON kullanır, web uygulamalarında yaygındır.
- **SOAP API:** XML tabanlı, daha katı kuralları olan ve genellikle kurumsal sistemlerde kullanılan bir web servisi standardıdır.
- **GraphQL API:** İstemcinin sadece ihtiyacı olan veriyi almasını sağlar, esnek sorgulama yapar.
- **WebSocket API:** Gerçek zamanlı veri iletişimi için sürekli açık bağlantı kullanır, chat veya canlı bildirimlerde kullanılır.

### HTTP
HTTP (HyperText Transfer Protocol), web tarayıcıları ile sunucular arasındaki veri alışverişini sağlayan protokoldür. Web sayfaları, dosyalar ve API’ler HTTP üzerinden iletilir.

- **GET:** Sunucudan veri almak için kullanılır. Örnek: `GET /users` → Tüm kullanıcıları getirir.
- **POST:** Sunucuya yeni veri göndermek için kullanılır. Örnek: `POST /users` → Yeni kullanıcı oluşturur.
- **PUT:** Sunucudaki mevcut veriyi güncellemek için kullanılır. Örnek: `PUT /users/1` → ID’si 1 olan kullanıcıyı günceller.
- **DELETE:** Sunucudan veri silmek için kullanılır. Örnek: `DELETE /users/1` → ID’si 1 olan kullanıcıyı siler.

### JSON
JSON (JavaScript Object Notation), veri alışverişi için kullanılan hafif, okunabilir ve yazımı kolay bir formattır. Aslında bir veri temsil biçimidir; hem insanlar hem de makineler tarafından kolayca anlaşılabilir. Farklı diller arasında veri aktarmak ve veriyi saklamak için kullanılır. JSON, veriyi hiyerarşik olarak (nesne, dizi, değer) düzenleyip paylaşmayı sağlar.

```powershell
{
  "id": 1,
  "isim": "Devin İşler",
  "yas": 20,
  "email": "devinisler@hotmail.com",
  "okul": "Boğaziçi University",
  "adres": {
    "sehir": "İstanbul",
    "ilce": "Beşiktaş"
  },
  "hobiler": ["film izlemek", "yüzmek", "kitap okumak"]
}
```
- ** Key-Value çifti:** "id" anahtarının değeri 1 integer'ı, "isim" anahtarının değeri "Devin İşler" string'i gibi.
- ** Nesne:** Süslü parantezle({}) gösterilir. "adres" anahtarının değeri "sehir" ve "ilce"yi içeren bi nesne.
- ** Dizi: ** Köşeli parantez ile ([]) gösterilir. Birden fazla veriyi depolar.
  
### REST vs SOAP vs GraphQL

| Özellik | REST | SOAP | GraphQL |
|---------|------|------|---------|
| **Tanım** | Web üzerinde kaynaklara HTTP üzerinden erişim sağlayan mimari stil | XML tabanlı, kurallı ve güvenli web servisi protokolü | İstemcinin ihtiyacı olan veriyi sorgulayabildiği modern API dili |
| **Tam Açılım** | Representational State Transfer | Simple Object Access Protocol | Graph Query Language |
| **Protokol** | HTTP (GET, POST, PUT, DELETE) | HTTP, SMTP, TCP vb. | HTTP (genellikle POST) |
| **Veri Formatı** | JSON, XML, YAML | XML (zorunlu) | JSON (isteğe bağlı) |
| **Mimari** | Kaynak odaklı | Katı, standart kurallara bağlı | İstemci bazlı sorgu, tek endpoint |
| **Durumsuzluk (Stateless)** | Evet | Hayır (genellikle stateful) | Evet |
| **Avantajları** | Basit, hafif, yaygın | Güvenli, işlem garantili | Esnek, ihtiyaca göre veri çekilebilir |
| **Dezavantajları** | Karmaşık ilişkilerde çoklu endpoint gerekebilir | Ağır ve karmaşık | Cache ve güvenlik ayarları daha karmaşık |
| **Kullanım Alanı** | Web ve mobil API’leri | Kurumsal uygulamalar, bankacılık | Modern web ve mobil uygulamalar |






