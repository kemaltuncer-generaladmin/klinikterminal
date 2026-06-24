# Bir Tıpçının Flutter ve Supabase ile İmtihanı

**Kategori:** Yazılım Notları / Dağınık Defter

MedAsi'yi hayata geçirirken teknoloji yığını (tech stack) seçimi en kritik kararlardan biriydi. Sonunda frontend için **Flutter**, backend/BaaS olarak ise **Supabase** kullanmaya karar verdim.

## Neden Flutter?
Bir tıp öğrencisi olarak zamanım çok kısıtlı. Hem iOS hem Android hem de Web için ayrı ayrı kod yazmak benim için intihardı. Flutter'ın "tek kod tabanı" (single codebase) mantığı ve zengin UI kütüphanesi beni anında cezbetti. İlk başlarda Widget ağaçları arasında kaybolsam da, state management (durum yönetimi) kavramını anladıkça her şey yerine oturdu.

## Neden Supabase?
Firebase yerine Supabase seçmemin en büyük nedeni açık kaynak olması ve arkasında güçlü bir **PostgreSQL** veritabanı barındırmasıydı. NoSQL'in esnekliği başta cazip gelse de, medikal verilerin ve kullanıcı ilişkilerinin karmaşıklığı ilişkisel bir veritabanını (SQL) zorunlu kılıyordu. Supabase'in sunduğu Row Level Security (RLS) politikaları da güvenlik açısından harika bir çözüm sundu.

Kısacası, bir tıpçının kod dünyasındaki bu yolculuğu bolca hata mesajı (Error: Null check operator used on a null value 😅) ve uykusuz gece içeriyor ama sonuç kesinlikle buna değer!
