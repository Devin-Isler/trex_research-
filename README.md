# Trex Research - .NET Backend Geliştirme

## 1. Modern Yazılım Geliştirme Pratikleri
### Git
Git, dağıtık bir versiyon kontrol sistemidir. Yazılım projelerinde veya dosya yönetiminde yapılan değişiklikleri kaydedip, takip etip ve yöneterek versiyon kontrolünü kolaylaştırır.
### GitHub
Github, Git versiyon kontrol sistemini kullanan projeler için bir bulut tabanlı platformdur. Git projeleri saklamak, paylaşmak ve ekip halinde yönetmek için kullanılan bir internet platformudur. Kodların paylaşıldığı bir sosyal medya platformu gibidir.
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

---

## 2. .NET Ekosistemi
### .NET nedir?
.NET, Microsoft'un geliştirdiği güçlü bir yazılım platformu olup, geliştiricilerin web'den mobile, masaüstünden bulut uygulamalarına kadar geniş bir yelpazede proje üretmesine imkan tanır.

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

---

## 3. Backend Geliştirme Temelleri
### Backend
Backend'i bir iceberg'in su altında kalan kısmı gibi düşünebilirsiniz - görünmez ama asıl işi o yapar. Veri yönetimi, güvenlik kontrolleri ve tüm hesaplamalar burada gerçekleşir. Frontend ise kullanıcıların gördüğü ve etkileşimde bulunduğu kısımdır; tasarım, arayüz ve kullanıcı deneyimi (UI/UX) ile ilgilenir. Kısaca, frontend “görünen yüz” iken, backend “arkadaki motor” gibidir. 

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
  "hobiler": ["film izlemek", "yüzmek", "satranç"]
}
```
- **Key-Value çifti:** "id" anahtarının değeri 1 integer'ı, "isim" anahtarının değeri "Devin İşler" string'i gibi.
- **Nesne:** Süslü parantezle({}) gösterilir. "adres" anahtarının değeri "sehir" ve "ilce"yi içeren bi nesne.
- **Dizi:** Köşeli parantez ile ([]) gösterilir. Birden fazla veriyi depolar.
  
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

---

## 4. ASP.NET
ASP.NET, Microsoft tarafından geliştirilmiş, açık kaynak ve Windows ortamında çalışan bir web uygulama framework’üdür. Web Forms, MVC ve Web API gibi yapılar sunar ve hızlı geliştirme ile güçlü entegrasyon imkânı sağlar. ASP.NET Core ise modern, platformlar arası çalışabilen (.NET Core üzerinde) bir framework olup Windows, Linux ve macOS’u destekler. Modüler yapısı sayesinde sadece gerekli paketleri kullanır, performansı yüksektir ve bulut ile mikroservis mimarileri için uygundur. Özetle, ASP.NET eski ve Windows odaklı iken, ASP.NET Core modern, hafif, hızlı ve platformlar arası uyumlu bir çözüm sunar.
### MVC
Açılımı **Model View Controller** olan **MVC**, işleri oldukça kolaylaştıran bir mimaridir. Burada model kelimesi, veritabanından verilerin çekilmesine yardımcı olur. Bu sayede verileri bir yerden kontrol etme olanağı bulunur. View kelimesi ise, görünüm katmanıdır. Yani Html, JavaScript ve CSS gibi bazı kodların tutulduğu bölümdür. Son kelimesi olan Controller ise, model ve view arasında kalan katmandır ve iş akışını yönetir. MVC farklı amaçlara hizmet eden bileşenlerini birbirinden ayırarak, kodu daha rahat bir şekilde geliştirebilir ve test haline getirebilirsin.
### Middleware
Middleware, bir web uygulamasında gelen HTTP isteğinin uygulamaya ulaşmadan önce ve yanıt oluşturulurken uygulamadan çıkmadan önce ara katmanlarda işlenmesini sağlayan bir yazılım parçasıdır. Her middleware, isteği inceleyip değiştirebilir, ek işlemler yapabilir veya isteğin devam edip etmeyeceğine karar verebilir.  
Middleware sırası işlem mantığına göre dikkatlice belirlenir: örneğin hata yakalama en üstte olmalı ki tüm zincirdeki hataları yakalayabilsin, authentication yetkilendirmeden önce gelmeli ki kullanıcı doğrulaması yapılabilsin, statik dosya middleware’i genellikle en başta olmalı ki basit dosya istekleri hızla işlenebilsin. Sıralama yanlış olursa middleware’lerin işlevleri doğru çalışmayabilir veya gereksiz yere performans kaybı oluşabilir.
```powershell
using Microsoft.AspNetCore.Authentication.JwtBearer;

var builder = WebApplication.CreateBuilder(args);

// Services konfigürasyonu
builder.Services.AddControllers();
builder.Services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
    .AddJwtBearer();
builder.Services.AddAuthorization();

var app = builder.Build();

// ⚠️ ÖNEMLİ: Middleware sırası çok kritik!

// 1. Exception Handling - En üstte olmalı (tüm hataları yakalar)
if (app.Environment.IsDevelopment())
{
    app.UseDeveloperExceptionPage();
}
else
{
    app.UseExceptionHandler("/Error");
    app.UseHsts(); // HTTP Strict Transport Security
}

// 2. HTTPS Redirection - Güvenlik için erken olmalı
app.UseHttpsRedirection();

// 3. Static Files - Basit dosya isteklerini erken yakalasın
app.UseStaticFiles();

// 4. Routing - URL eşleştirme
app.UseRouting();

// 5. CORS - Cross-origin istekler için (eğer gerekiyorsa)
// app.UseCors();

// 6. Authentication - Kullanıcı kimliği doğrulama
app.UseAuthentication();

// 7. Authorization - Yetkilendirme (Authentication'dan SONRA)
app.UseAuthorization();

// 8. Custom Middleware (eğer varsa)
app.UseMiddleware<RequestLoggingMiddleware>();

// 9. Endpoints - Son olarak controller'lara yönlendirme
app.MapControllers();

app.Run();
```
### Dependency Injection
Dependency Injection, bir sınıfın ihtiyaç duyduğu bağımlılıkların (services, repository, logger vb.) sınıfın içinde kendisi tarafından oluşturulması yerine dışarıdan verilmesi prensibidir. Sınıflar sıkı sıkıya birbirine bağlı olmadıklarından test edilebilirliği yüksektir. Farklı implemantasyonlar kolaylıkla uygulanabilir.  
```powershell
// Servis
public interface IMessage { void Send(string msg); }
public class Email : IMessage { public void Send(string msg) => Console.WriteLine(msg); }

// Kullanıcı sınıf
public class Notification
{
    private IMessage _message;
    public Notification(IMessage message) { _message = message; }
    public void Notify(string msg) => _message.Send(msg);
}

// Kullanım
var notification = new Notification(new Email());
notification.Notify("Merhaba!");
```
Notification sınıfı mesaj gönderme işini kendi yaratmadığı bir IMessage nesnesi üzerinden yapıyor. Bu, DI ile bağımlılığı dışarıdan sağlamak demek.
### Katmanlı Mimari
Katmanlı Mimari (Layered Architecture) yazılımda en temel ve yaygın kullanılan mimarilerden biridir. Mantığı, uygulamanın sorumluluklarını farklı katmanlara ayırarak kodun daha düzenli, sürdürülebilir ve test edilebilir olmasını sağlamaktır.
Katmanlar:
- **Presentation Layer (Sunum Katmanı):** Kullanıcı ile etkileşimi sağlar. Web sayfası, API controller veya mobil uygulama arayüzü bu katmanda yer alır. İş mantığı içermez; yalnızca veriyi gösterir ve kullanıcıdan gelen veriyi toplar.
- **Business Layer (İş Mantığı Katmanı):** Uygulamanın iş kurallarını uygular. Verilerin doğrulanması, hesaplamalar, iş süreçleri burada yapılır. Sunum ve veri erişim katmanlarından bağımsızdır.
- **Data Access - Persistince Layer (Veri Erişim Katmanı):** Veritabanı veya başka veri kaynaklarına erişimi sağlar. CRUD (Create, Read, Update, Delete) işlemleri bu katmanda yapılır. Business katmanı bu katmana doğrudan bağımlı olur, fakat sunum katmanı dolaylı olarak erişir.  
![Layered Architecture pattern](https://www.oreilly.com/content/wp-content/uploads/sites/2/2020/01/sapr_0104-0cf58347b8f994c7605d68eca5ef8ba4.png)

### Clean Architecture
Bu yaklaşımda, uygulamanın çekirdek iş mantığı dış bağımlılıklardan izole edilir ve katmanlar arasında tek yönlü bağımlılık kuralı uygulanır: iç katmanlar dış katmanlardan bağımsızdır.
- **Domain (Core) Katmanı:** İş kurallarının ve temel mantığın bulunduğu katmandır. Entity ve Value Object gibi yapılar burada yer alır. Başka katmanlara bağımlılığı yoktur, en bağımsız katmandır.
- **Application Katmanı:** Domain katmanını kullanarak iş süreçlerini (use case’leri) yönetir. Service, Use Case, Interface gibi yapılar içerir. Domain’e bağımlıdır, ama Infrastructure veya API’ye bağımlı değildir.
- **Infrastructure Katmanı:** Veri tabanı, dosya sistemi, e-posta, üçüncü taraf servisler gibi dış bağımlılıkları yönetir. Application veya Domain katmanına alt seviyeden hizmet sağlar. Örneğin Repository implementasyonları burada bulunur.
- **API (Presentation) Katmanı:** Kullanıcıya veya dış sistemlere açılan uç noktaları sağlar (Web API, UI, vb.). Application katmanındaki use case’leri çağırır. Infrastructure veya Domain’e doğrudan bağımlı değil, sadece Application üzerinden iletişim kurar.

---

## 5. Veritabanı ve ORM
### SQL
SQL(Structured Query Language) veritabanlarıyla iletişim kurmak için kullanılan standart bir dildir. SQL, ilişkisel veritabanlarında (Relational Databases) veri ekleme, silme, güncelleme, sorgulama ve yönetme işlemlerini yapmanızı sağlar.
- Veri Sorgulama (SELECT)
	- Veritabanındaki verileri filtreleyip, sıralayıp, gruplandırarak çekmenizi sağlar.
	- Örnek: `SELECT * FROM ogrenciler WHERE yas > 18;`
- Veri Ekleme (INSERT)
	 - Yeni kayıtları tabloya ekler.
	 - Örnek: `INSERT INTO ogrenciler (isim, yas) VALUES ('Ali', 20);`
- Veri Güncelleme (UPDATE)
	 - Mevcut kayıtları değiştirir.
	 - Örnek: `UPDATE ogrenciler SET yas = 21 WHERE isim = 'Ali';`
- Veri Silme (DELETE)
	 - Kayıtları tablodan siler.
	 - Örnek: `DELETE FROM ogrenciler WHERE yas < 18;`

 ### İlişkisel vs İlişkisel Olmayan Veri Tabaları

| Özellik | İlişkisel Veritabanı (RDBMS) | İlişkisel Olmayan Veritabanı (NoSQL) |
|---------|-----------------------------|------------------------------------|
| Veri Yapısı | Tablo (satır ve sütun) şeklinde, ilişkiler vardır | JSON, belge, anahtar-değer, grafik veya sütun tabanlı yapılar |
| Şema (Schema) | Önceden tanımlanmış, sabit şema | Esnek şema, veriler farklı formatlarda olabilir |
| Veri Bütünlüğü | ACID (Atomicity, Consistency, Isolation, Durability) kurallarına uyulur | BASE (Basically Available, Soft state, Eventually consistent) yaklaşımı |
| Ölçeklenebilirlik | Dikey ölçeklenir (daha güçlü sunucu ile) | Yatay ölçeklenebilir (birden fazla sunucu ekleyerek) |
| Sorgulama | SQL dili ile sorgulanır | Çoğu kendi sorgu dili veya API kullanır |
| Kullanım Alanı | Bankacılık, muhasebe, insan kaynakları gibi veri bütünlüğünün önemli olduğu uygulamalar | Büyük veri, sosyal medya, gerçek zamanlı analiz, IoT gibi yüksek hacimli ve esnek veri gereken uygulamalar |
| Örnek Sistemler | MySQL, PostgreSQL, Oracle, SQL Server | MongoDB, Cassandra, Redis, CouchDB |

### ORM
ORM(Object-Relational Mapping), nesne yönelimli programlama (OOP) ile ilişkisel veritabanları (RDBMS) arasındaki köprüdür. Veritabanı tablolarını C# sınıfları ile temsil ederek, SQL sorguları yazmadan veri işlemlerini gerçekleştirmeyi sağlar. Kodun okunabilirliğini arttırır.
**Entity Framework Core** Microsoft tarafından geliştirilmiş bir ORM framework’üdür ve .NET uygulamaları için tasarlanmıştır. Veritabanı ile C# sınıfları arasında doğrudan ilişki kurar.
**DbContext** Entity Framework Core’da veritabanı ile uygulama arasındaki ana köprüdür. Veritabanı oturumu gibi düşünülebilir. İçinde tabloların temsil edildiği DbSet’ler vardır ve bu sayede veritabanına veri eklenebilir, silinebilir veya güncellenebilir.

### LINQ
LINQ (Language Integrated Query), C# içine gömülü bir sorgulama dilidir ve koleksiyonlar, diziler veya veritabanları üzerinde SQL benzeri sorgular yapmayı sağlar.

| LINQ İfadesi | Açıklama | Örnek | SQL Karşılığı |
|--------------|----------|-------|---------------|
| `Where` | Verileri filtreler | `students.Where(s => s.Age >= 18)` | `SELECT * FROM Students WHERE Age >= 18;` |
| `Select` | Belirli kolonları seçer | `students.Select(s => s.Name)` | `SELECT Name FROM Students;` |
| `OrderBy` / `OrderByDescending` | Verileri artan/azalan sırada sıralar | `students.OrderBy(s => s.Name)` | `SELECT * FROM Students ORDER BY Name ASC;` |
| `First` / `FirstOrDefault` | Şarta uyan ilk elemanı alır | `students.FirstOrDefault(s => s.Age > 20)` | `SELECT TOP 1 * FROM Students WHERE Age > 20;` |
| `Single` / `SingleOrDefault` | Tek bir elemanı alır (tek veya hiç) | `students.SingleOrDefault(s => s.Id == 1)` | `SELECT * FROM Students WHERE Id = 1;` |
| `Any` / `All` | Koşulun varlığını veya tümünü kontrol eder | `students.Any(s => s.Age >= 18)` | `SELECT CASE WHEN EXISTS(SELECT * FROM Students WHERE Age >= 18) THEN 1 ELSE 0 END;` |
| `Count` / `Sum` / `Max` / `Min` / `Average` | Sayısal işlemler yapar | `students.Count()` | `SELECT COUNT(*) FROM Students;` |


### Code-First vs DataBase-First

Entity Framework Core’da iki temel yaklaşım vardır: Code-First ve Database-First.

| Özellik | Code-First | Database-First |
|---------|------------|----------------|
| Tanım | C# sınıflarından veritabanı oluşturulur | Var olan veritabanından C# sınıfları ve DbContext oluşturulur |
| Başlangıç Noktası | Kod (Model sınıfları) | Veritabanı |
| Avantaj | Kod üzerinden tam kontrol, migration desteği | Mevcut veritabanı ile hızlı entegrasyon |
| Dezavantaj | Var olan veritabanı ile entegrasyon zor | Kod değişiklikleri veritabanına otomatik yansımaz |

---

## 6. Güvenlik ve Performans
### Authentication
Kullanıcının kim olduğunu doğrulama işlemidir. Kullanıcı adı - şifre, biyometrik doğrulama, OBP gibi.
- **OpenID:** Kullanıcının kimliğini doğrulamak için standart bir protokol.    	
	- **Örnek:** Google hesabımla giriş yapmak.  

### Authorization
Kullanıcının hangi kaynaklara veya işlemlere erişebileceğini belirleme işlemidir. Admin mi user mı, hangi belgeleri okuyabilir, yazabilir gibi.  
- **OAuth:** Kullanıcının parolasını paylaşmadan, üçüncü taraf uygulamalara belirli kaynaklara erişim izni vermesini sağlar.    
	- **Örnek:** Bir kullanıcı, “Uygulama X’in Gmail mesajlarıma erişmesini istiyorum” dediğinde OAuth kullanılır.  
- **OAuth 2.0:** OAuth'un en güncel ve yaygın sürümü.  

**OpenIddict:** ASP.NET Core projelerinde OAuth 2.0 ve OpenID Connect’i kolayca uygulamaya sokmak için kullanılan bir kütüphane.

### JWT
JWT(JSON Web Token) kullanıcının kimliğini kanıtlayan dijital bir kimlik kartı gibi. Güvenli ve taşınabilir. JWT, kullanıcının doğrulanması, web servis güvenliği, bilgi güvenliği gibi birçok konuda kullanılabilir. Kişiye login sonrasında sunucudan gönderilen token ile erişim izni olan isteklere kolay ve güvenli bir şekilde erişmesini sağlar. 3 temel yapıdan oluşur:
- **Header:** Token tipini (JWT) ve kullanılan imzalama algoritmasını belirtir. `{"alg": "HS256", "typ": "JWT" }`
- **Payload:** Kullanıcı bilgileri ve token ile taşınacak veriler burada yer alır. `{"sub": "1234567890", "name": "Devin", "role": "admin"}`
- **Signature:** Header ve Payload, gizli bir anahtar ile imzalanır. Bu sayede tokenın değişmediği ve güvenli olduğu doğrulanabilir. `xxxxx.yyyyy.zzzzz`
- 
### Performans Artırımı
- **AsNoTracking:** Entity Framework Core’da veriyi sadece okumak için çekiyorsanız AsNoTracking() kullanmak, EF’in değişiklik takibi yapmasını engeller. Bu sayede bellekte ve CPU’da daha az yük olur, sorgular çok daha hızlı çalışır.
- **Caching:** Sık kullanılan verileri veritabanından sürekli çekmek yerine, bellek veya dağıtık cache’e almak performansı artırır.
-**IAsyncEnumerable** 	Büyük veri setlerini asenkron ve streaming şeklinde çekmek için kullanılır. Tüm veriyi belleğe yüklemek yerine, veriler parça parça çekilir, bu bellek kullanımını azaltır ve performansı artırır.

### OWASP
- **1. Broken Access Control (Erişim Kontrolü Hataları):** Erişim kontrolü hataları, kullanıcıların yalnızca yetkili oldukları verilere ve işlemlere erişmesini sağlayan mekanizmaların yetersiz olmasından kaynaklanır. Bu durum, kullanıcıların başkalarının verilerine erişmesine veya kritik işlemleri gerçekleştirmesine olanak tanır. 
- **2. Cryptographic Failures (Kriptografik Hatalar):** Şifreleme yöntemlerinin zayıflıklarından kaynaklanır. 
- **3. Injection (Enjeksiyon):** Enjeksiyon saldırıları, kötü niyetli verilerin uygulama tarafından beklenmeyen şekilde işlenmesine neden olur. **SQL enjeksiyonu**, saldırganların veritabanı sorgularını manipüle ederek veri sızdırmasına veya değiştirmesine olanak tanır.
- **4. Insecure Design (Güvensiz Tasarım):** Güvensiz tasarım, uygulamanın mimarisinde veya işleyişinde güvenlik açıklarına yol açabilecek hatalı kararlar alınması durumudur. 
- **5. Security Misconfiguration (Güvenlik Yanlış Yapılandırması):** Yanlış yapılandırılmış güvenlik ayarları, sistemlerin ve uygulamaların yanlış yapılandırılmasından kaynaklanan güvenlik açıklarını ifade eder.
- **6. Vulnerable and Outdated Components (Zayıf ve Güncel Olmayan Bileşenler):** Eski bilgisayar programları bilinen güvenlik açıklarına sahip olduğundan sadırganların açık hedefi haline gelir.
- **7. Identification and Authentication Failures (Kimlik Doğrulama ve Tanımlama Hataları):** Kimlik doğrulama ve tanımlama hataları, kullanıcıların kimliklerinin doğru bir şekilde doğrulanamaması veya yetkilendirilmemesi durumudur. Broken Authentication gibi kimlik doğrulama ve oturum yönetimindeki hatalar sebep olur.
- **8. Software and Data Integrity Failures (Yazılım ve Veri Bütünlüğü Hataları):** Bu kategori, yazılım güncellemeleri, kritik veriler ve sürekli entegrasyon/sürekli teslimat (CI/CD) süreçlerinde bütünlük kontrollerinin eksik olmasından kaynaklanan riskleri kapsar. 
- **9. Security Logging and Monitoring Failures (Güvenlik Günlüğü ve İzleme Hataları):** Güvenlik günlüğü ve izleme hataları, güvenlik olaylarının yeterince kaydedilmemesi veya izlenmemesi durumudur. Bu, saldırıların tespit edilmesini ve yanıt verilmesini zorlaştırır. 
- **10. Server-Side Request Forgery (SSRF):** Server-Side Request Forgery (SSRF), bir saldırganın, sunucunun dış kaynaklara istek göndermesini sağlayarak, iç ağlara veya sistemlere erişim elde etmesine olanak tanır.  

ASP.NET Core uygulamalarında web güvenliği risklerine karşı alınabilecek önlemler şunlardır:
- **Model Validation (Model Doğrulama):** Kullanıcıdan gelen verilerin beklenen formatta olup olmadığını kontrol eder. Boş veya hatalı veri girişleri otomatik engellenir.
- **Input Sanitization (Girdi Temizleme):** Kullanıcıdan gelen HTML/JS içeriğinin zararlı kod içermesini önler.
- **Anti-Forgery Token (CSRF Koruması):** Formlara otomatik CSRF token ekleyerek CSRF saldırılarını engeller.
- **Exception Handling & Logging:** Kullanıcılara ham hata mesajı gösterilmemeli. UseExceptionHandler("/Home/Error") ile özel hata sayfası kullanılmalı.


---

## 7. Logging ve Hata Yönetimi
### Loglama
Loglama, bir yazılım uygulamasında veya sistemde çalışma sırasında gerçekleşen olayların, hataların, uyarıların ve genel bilgilerin kaydedilmesi işlemidir. Diğer bir deyişle loglama, programın "günlük tutmasıdır".  
Log seviyesi, uygulamanın hangi önemdeki bilgileri log dosyasına yazacağını belirten bir derecelendirmedir. 
- TRACE → En ayrıntılı seviye, uygulamanın adım adım neler yaptığını gösterir. (Genelde geliştirme aşamasında kullanılır.)
- DEBUG → Hata ayıklama için ayrıntılı bilgiler içerir.
- INFO → Uygulamanın normal işleyişi hakkında genel bilgiler (başlatıldı, durduruldu, kullanıcı giriş yaptı vb.).
- WARN → Beklenmedik ama uygulamayı durdurmayan durumlar (örn. cache miss, deprecated metod kullanımı).
- ERROR → Uygulamanın düzgün çalışmasını engelleyen hatalar.
- FATAL (veya CRITICAL) → Uygulamanın tamamen çökmesine sebep olan kritik hatalar.

### ASP.NET Core'da Loglama
ASP.NET Core’da logging, uygulamanın çalışma süresince oluşan olayların, hataların ve bilgilendirici mesajların kaydedilmesini sağlayan yerleşik bir altyapıdır. Bu altyapı, esnek ve genişletilebilir bir şekilde tasarlanmıştır. Log seviyelerini destekler. Yerleşik logging API vardır.

- ASP.NET Core’da **global exception handling** (küresel hata yakalama), uygulama boyunca yakalanmayan tüm hataları merkezi bir noktada yakalayıp loglamak ve kullanıcıya kontrollü bir yanıt dönmek için kullanılır.

- **UseExceptionHandler** ASP.NET Core’un hazır middleware’idir. Uygulama genelinde yakalanmayan hataları merkezi bir noktada yakalamak için kullanılır. Uygulamada bir hata oluşursa, akış kesilip bu hata hata pipeline'ına gönderilir, gerekli önlemler ve düzenlemeler burdan  yapılabilir.

- **Iloger** ASP.NET Core’un yerleşik loglama mekanizmasıdır. Uygulamada gerçekleşen olayları log seviyesini belirleyerek kayıt altına alır.  
İkisi beraber çalışarak hatayı yakalayıp kayıt altına alır.

- ASP.NET Core’da hata yönetimi, uygulamadaki tüm hataları tek bir yerde yakalayarak hem loglamak hem de kullanıcıya güvenli bir mesaj göstermek için yapılır. Bunun için UseExceptionHandler() kullanılır; bu middleware, hata oluştuğunda isteği belirlenen bir endpoint’e yönlendirir. Bu endpoint içinde ILogger ile hatanın detayları kaydedilir ve kullanıcıya teknik detay içermeyen bir hata mesajı döner. Böylece uygulama çökmez ve hatalar izlenebilir, ve düzeltilmeye çalışılır.


 ---

##  8. Yazılım Geliştirme Prensipleri

### SOLID prensibi
- ***S*ingle Responsibility Principle (SRP) - Tek Sorumluluk Prensibi:** Bir sınıfın yalnızca bir tek sorumluluğu olmalıdır.
  ```powershell
  class InvoicePrinter {
    void printInvoice(Invoice invoice) { ... }
  }

  class InvoiceSaver {
  	void saveInvoice(Invoice invoice) { ... }
  }
  ```
  Burada Invoice sınıfı yalnızca fatura ile ilgilenir, yazdırma ve kaydetme işleri ayrı sınıflarda.
- ***O*pen/Closed Principle (OCP) - Açık/Kapalı Prensibi:** Yazılım varlıklarının (sınıflar, modüller, fonksiyonlar vb.) genişletmeye açık, ancak değişime kapalı olması gerektiğini belirtir.
   ```powershell
   interface Shape {
    double area();
  }

  class Circle implements Shape {
    double radius;
    public double area() { return Math.PI * radius * radius; }
  }

  class Rectangle implements Shape {
    double width, height;
    public double area() { return width * height; }
  }
  ```

- ***L*iskov Substitution Principle (LSP) - Liskov Yerine Geçme Prensibi:** Türetilmiş sınıfların, temel sınıfların yerine kullanılabilmesi gerektiğini belirtir.
   ```powershell
  class Bird { void fly() { ... } }
  class Duck extends Bird { void fly() { ... } }
  ```
   Bird bekleyen yerde Duck kullanılabilir. Ama Ostrich gibi uçamayan bir kuş için bu tasarım hatalı olur.
   Yeni şekil eklemek için mevcut kodu değiştirmeye gerek yok, sadece Shape implement eden yeni sınıf eklenir.
- ***I*nterface Segregation Principle (ISP) - Arayüz Ayırma Prensibi:** Sınıflar, kullanmadıkları metotları içeren büyük arayüzlere bağlı kalmamalı.
   ```powershell
  interface Printer { void print(); }
  interface Scanner { void scan(); }

  class MultiFunctionPrinter implements Printer, Scanner { ... }
  ```
   Yazıcı sadece yazdırma işlevi kullanıyorsa Scanner’a bağlı kalmaz.
- ***D*ependency Inversion Principle (DIP) - Bağımlılıkların Tersine Çevrilmesi Prensibi:** Üst seviye modüllerin, alt seviye modüllere bağımlı olmaması gerektiğini belirtir. Bunun yerine, her iki tür modül de soyutlamalara bağımlı olmalıdır.
   ```powershell
  interface Database { void save(String data); }

  class MySQLDatabase implements Database {
     public void save(String data) { ... }
  }

  class UserService {
    private Database db;
    UserService(Database db) { this.db = db; }
    void saveUser(String name) { db.save(name); }
  }
  ```
   UserService, doğrudan MySQLDatabase’e bağlı değil; Database interface’i üzerinden çalışıyor.
### Design Patterns
- **Singleton Pattern:** Bu tasarım örüntüsündeki amaç, bir class’tan sadece bir instance yaratılmasını sağlar. Yani herhangi bir class’tan bir instance yaratılmak istendiğinde, eğer daha önce yaratılmış bir instance yoksa yeni yaratılır. Daha önce yaratılmış ise var olan instance kullanılır.
- **Factory Pattern:** Factory Design Pattern, nesne yaratma işlemi için bir arayüz tasarlanmasını gerektirir ve alt sınıfların nesne üretmesine olanak sağlar. Ayrıca, hangi sınıf nesnesinin oluşacağını da alt sınıflar kendileri belirler. Böylece nesne yaratma işlemini soyutlaştırır.
### Clean Code
Temiz kod (Clean Code), okunabilir, anlaşılabilir, sürdürülebilir ve hataya açık olmayan kod yazma yaklaşımıdır. Gereksiz karmaşıklardan yoksun, sade, tekrar etmeyen bir yapıda olmalıdır. Değişken isimlerinin anlamlı olması gerekir. Başkasının veya gelecekte kendimiz koda baktığımızda "Bu ne ya?" dememek için kodumuzu temiz yazmamız gerekir.

- Anlamlı isimler kullanmak
  ```powershell
  // Kötü
  int d; // neyi temsil ediyor?  

  // İyi
  int daysSinceCreation;
  ```
- Karışık taskleri farklı fonksiyonlara bölmek
  ```powershell
  // Kötü
  void process() {
  // veri çek
  // filtrele
  // yazdır
  }
 
  // İyi
  void fetchData() { ... } // veri çek
  void filterData() { ... } // filtrele
  void printData() { ... } // yazdır
  ```
- Tek fonksiyon tek sorumluluk
  ```powershell
  class Invoice {
    void calculateTotal() { ... }   // Hesaplama
    void printInvoice() { ... }     // Yazdırma
    void saveInvoice() { ... }      // Kaydetme
   }
  ```
- Yorumları ne eksik ne fazla tutmak
  
- Magic Number ve String’lerden Kaçının
  ```powershell
  // Kötü
  if(status == 3) { ... }

  // İyi
  final int STATUS_APPROVED = 3;
  if(status == STATUS_APPROVED) { ... }
  ```
### Yazılım Mimari Desenleri

 Mimari | Kısa Açıklama | Avantajları | Dezavantajları | Kullanım Senaryosu |
|--------|---------------|------------|----------------|------------------|
| **Layered (Katmanlı)** | İş mantığı, veri erişimi ve sunum katmanlarına ayrılır | Basit ve anlaşılır | Büyük projelerde bağımlılıklar karmaşık olabilir | Küçük/orta ölçekli uygulamalar |
| **Clean Architecture** | Bağımlılıklar içten dışa doğru yönlendirilir | Test edilebilir, sürdürülebilir | Karmaşık | Orta/uzun vadeli projeler |
| **Microservices** | Uygulama küçük bağımsız servisler olarak bölünür | Ölçeklenebilir, bağımsız dağıtım | Dağıtık sistem karmaşıklığı | Büyük, ölçeklenebilir uygulamalar |
| **Event-Driven** | Servisler olaylar üzerinden iletişim kurar | Gevşek bağlı, esnek | Debug zor | Gerçek zamanlı sistemler |
| **Hexagonal (Ports & Adapters)** | İş mantığı merkezde, giriş/çıkış adaptörlerle bağlanır | İş mantığı bağımsız, test kolaylığı | Öğrenme eğrisi | Test ve değişime önem verilen projeler |
---
