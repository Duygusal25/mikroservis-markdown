# Mikroservis Mimarisinin Ortaya Çıkışı
Mikroservis mimarisi,yazılım geliştirme süreçlerinde ortaya çıkan bazı temel sournlara çözüm sunmak amacıyla geliştirilmiştir.Bu sorunlar arasında
- Kod Karmaşıklığı
- Dağıtım ve güncelleme zorlukları
- Sınırlı ölçeklenebilirlik
yer almaktadır.

20000'li yılların başında geliştirilen bir çok yazılım ,**monolitik mimari** ile oluşturuluyırdu.
Monolotik mimari, tüm bileşenlerin tek bir bütün halinde, birlikte geliştirildiği ve dağıtıldığı bir yazılım tasarım yaklaşımıdır.


## Monolitik Mimarinin Dezavantajları
Yazılım projeleri büyüdükçe, monolitik mimarinin bazı zorlukları ortaya çıkmıştır:
- Kod karmaşıklığı arttı
- Küçük bir değişiklikte bile tüm uygulamanın yeniden dağıtılması gerekti
- Yeni teknolojilere geçiş zorlaştı
- Uygulamanın ölçeklenmesi zorlaştı

  Yani aslında mikroservisler monolitik mimariye bir alternatif olarak ortaya çıktı.

  

  ## Monolitik Mimari ve Mikroservis Mimarisi Karşılaştırılması

  | **Özellik / Kriter**             | **Monolitik Mimari**                            | **Mikroservis Mimarisi**                                        |
  |----------------------------------|-------------------------------------------------|-----------------------------------------------------------------|
  | **Yapı**                         | Tek parça, bütünleşik uygulama                  | Bağımsız, küçük ve birbirinden ayrılmış servisler               |
  | **Geliştirme**                   | Tüm uygulama tek ekip tarafından geliştirilir   | Her servis farklı ekipler tarafından bağımsız geliştirilir      |
  | **Dağıtım**                      | Tüm uygulama birlikte dağıtılır                 | Her servis bağımsız olarak dağıtılır                            |
  | **Ölçeklenebilirlik**            | Uygulamanın tamamı ölçeklenir                   | İhtiyaç duyulan servisler ayrı ayrı ölçeklenir                  |
  | **Teknoloji Bağımlılığı**        | Tek dil ve teknoloji kullanımı zorunludur       | Farklı servislerde farklı diller ve teknolojiler kullanılabilir |
  | **Hata İzolasyonu**              | Bir modüldeki hata tüm sistemi etkileyebilir    | Hata sadece ilgili servisi etkiler                              |
  | **Bakım ve Güncelleme**          | Güncelleme tüm sistemi etkiler ve karmaşıktır   | Servisler bağımsız güncellenebilir                              |
  | **Test Edilebilirlik**           | Tüm sistem birlikte test edilir                 | Her servis bağımsız test edilebilir                             |
  | **Yaygın Kullanım Alanı**        | Küçük ve orta ölçekli projeler                  | Büyük ve karmaşık, sürekli büyüyen projeler                     |
  | **Dağıtık Sistem Yönetimi**      | Genellikle yok veya minimal                     | Zorunlu; servisler arası iletişim ve orkestrasyon gerektirir    |



 <img width="800" height="400" alt="Image" src="https://github.com/user-attachments/assets/13fe0ae8-16c4-40bb-8b52-6d3195c7094c" />
 

# Mikroservis Mimarisi Nedir

Büyük ve karmaşık bir uygulamayı birbirinden bağımsız, küçük, ölçeklenebilir ve yönetilebilir servisler halinde geliştirme yöntemidir. Servisler birbiriyle API’lar aracılığıyla iletişim kurar. Her mikroservis, belirli bir işlevi yerine getirebilir, bağımsız şekilde geliştirilebilir ve test edilebilir.


## Mikroservisin yaygın kullanım alanları:

1. E-Ticaret Sistemleri  
2. Finans ve Bankacılık uygulamaları  
3. Sosyal Medya ve İletişim Platformları  
4. Bulut Tabanlı Sistemler  

Bir e-ticaret platformu ürün arama, ürün kataloğu, alışveriş sepeti, yönetici arayüzü, ödemeler servislerinden oluşsun. Mikroservis mimarisinde tüm bu modüller küçük, bağımsız ve birbirleriyle bağlantılı yazılım birimleri olarak çalışır.


## Mikroservis Mimarisi Kullanmanın Faydaları:

- Ekipler aynı anda farklı mikroservisler üzerinde çalışabilirler  
- Bir servisteki sorun diğerlerini etkilemez  
- Her servis kendi özel ihtiyacına göre ölçeklenebilir  
- Ekipler her mikroservis için en iyi teknolojiyi seçebilirler
  

  ## Mikroservis Mimarisi Kullanmanın Dezavantajları:

- Servisler arası iletişim karmaşıklığı artar  
- Dağıtık sistemlerden dolayı hata ayıklama zorlaşabilir  
- Servislerin yönetimi ve izlenmesi için ek araçlar gerekir  
- Veri tutarlılığı sağlamak zor olabilir  
- Başlangıçta altyapı ve organizasyon maliyeti yüksek olabilir  



# Mikroservisler Arasında İletişim Nasıl Gerçekleşir

Mikroservisler arasında iletişim hem senkron hem de asenkron olarak gerçekleşebilir. Senkron iletişimde bir servis diğer servise doğrudan istek gönderir ve cevap bekler. Genelde kullanılan teknolojiler Rest API, gRPC.

Asenkron iletişimde ise bir mikroservis, başka bir mikroservise mesaj gönderir ama cevap beklemeden işine devam eder. Genelde kullanılan teknolojiler Mesaj Kuyrukları, Event-driven sistemler.

- Anında cevap gerekiyorsa – Senkron  
- Yüksek gecikme toleransı varsa – Asenkron  
- Bağımlılığı azaltmak isteniyorsa – Asenkron  
- Basit yapı isteniyorsa – Senkron  
- Yoğun trafik altında çalışılacaksa – Asenkron  


# Mikroservis Mimarisinin Temel Bileşenleri:

**API Gateway:** Tüm mikroservislerin önünde duran bir ara katmandır. Kullanıcılar veya istemciler doğrudan mikroservise değil, önce API Gateway'e istek gönderir. Gelen istekleri uygun mikroservise yönlendirir.

**Servis Discovery:** Mikroservislerin adreslerini takip ederek servislerin birbirlerini dinamik olarak bulmalarını ve iletişim kurmalarını sağlar.

**Load Balancer (Yük Dengeleyici):** Gelen istekleri birden fazla servise eşit şekilde dağıtan bir sistem. İstekleri eşit dağıtarak herhangi bir mikroservisin aşırı yüklenmesini önler.

**Database Per Service:** Her mikroservisin kendi veritabanı vardır. Bu da bağımsız yönetim ve ölçeklenmeye olanak tanır.

**Centralized Logging & Monitoring:** Dağıtık mikroservislerin davranışlarını ve hatalarını tek bir yerden takip etmeyi sağlar.

**Caching (Önbellekleme):** Önbellek, sık erişilen verileri mikroservise yakın bir yerde depolar ve tekrarlanan sorguları azaltarak performansı arttırır.

**Servis Yönetimi:** Servislerin nasıl çalıştığını, ne zaman başlatılacağını veya güncelleneceğini yöneten sistemdir.

### Araçlar:

- **Docker - Paketleme Aracı:** Uygulamayı konteyner içine koyar, her yerde aynı şekilde çalışma sağlar.  
- **Kubernetes - Orkestrasyon ve Yönetim:** Dockerla paketlenen servisleri büyük ölçekte otomatik yönetmeyi sağlar.  
- **Helm:** Kubernetes konfigürasyonlarını kolayca yönetmek ve dağıtmak için kullanılır.

  ### Kaynakça:
  [https://www.geeksforgeeks.org/system-design/microservices/]
  
  [https://globalit.com.tr/mikroservis-mimarisi-nedir-ne-icin-kullanilir/]
  
  [https://gokhana.medium.com/microservice-mimarisi-ile-yaz%C4%B1l%C4%B1m-tasar%C4%B1m%C4%B1-1f6e54e09202]













