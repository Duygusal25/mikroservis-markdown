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

  # Monolitik Mimari ve Mikroservis Mimarisi Karşılaştırılması

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


![Mikroservis ve Monolitik Mimari](C:/Users/hp/Desktop/gorsel_1.png)










