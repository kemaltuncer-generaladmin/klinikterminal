# Coolify Deployment Rehberi

Bu projeyi Coolify üzerinde ayağa kaldırmak için aşağıdaki adımları izleyin.

## Adım Adım Deploy

1. **Yeni Kaynak Ekleme:**
   Coolify panelinde `New Resource` butonuna tıklayın.
2. **Uygulama Seçimi:**
   `Application` seçeneğine tıklayın.
3. **Kaynak Türü:**
   `Git Repository` seçeneğini seçin (GitHub App veya Public Repository).
4. **Build Pack:**
   Uygulama türü olarak `Docker Compose` seçin.
5. **Docker Compose Dosya Konumu:**
   Docker Compose Location kısmına `/docker-compose.yml` yazın.

## Environment Variables (Çevresel Değişkenler)
Coolify arayüzünde Environment Variables bölümüne geçin ve aşağıdaki değişkenleri ekleyin:

```env
GHOST_URL=https://DOMAIN_BURAYA
MYSQL_PASSWORD=change_me_strong_password
MYSQL_ROOT_PASSWORD=change_me_even_stronger_password
NODE_ENV=production
```
*(Güvenlik için şifreleri değiştirin)*

## Domain Yönlendirmesi
Uygulama ayarlarında "Domains" kısmına `https://DOMAIN_BURAYA` adresini yazın.
Ghost container'ı içindeki çalışan port `2368`'dir. Coolify, bu porta otomatik olarak proxy ayarlarını yapacaktır.

## Auto Deploy / Webhook Ayarları
Coolify'ı GitHub reposuna bağlarken GitHub App veya manuel Webhook yöntemini seçtiyseniz, "Auto Deploy" özelliğini aktif ettiğinizden emin olun. Bu sayede repoya yapılan her push işlemi projeyi otomatik olarak güncelleyecektir.

## Admin Hesabı Oluşturma
Deploy işlemi başarıyla bittikten sonra, kurulumu tamamlamak ve ilk admin hesabını oluşturmak için tarayıcınızda şu adrese gidin:
`https://DOMAIN_BURAYA/ghost`
