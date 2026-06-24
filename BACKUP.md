# Yedekleme ve Geri Yükleme (Backup & Restore)

Ghost blogunuzu güvenle taşıyabilmek veya veri kaybını önlemek için yedeklenmesi gereken iki temel bileşen vardır:

1. **`ghost_content` Volume:** Tema dosyaları, yüklenen görseller ve yapılandırma dosyalarını içerir.
2. **`ghost_mysql` Volume (veya MySQL Dump):** Tüm blog yazıları, kullanıcı verileri ve ayarları içeren veritabanıdır.

## Basit Manuel Yedekleme Komutları

Sunucunuza SSH ile bağlandıktan sonra yedekleme yapabilirsiniz.

**MySQL Veritabanı Yedeği Alma:**
```bash
docker exec $(docker ps -qf "name=mysql") /usr/bin/mysqldump -u root -p'change_me_even_stronger_password' ghost > ghost_db_backup_$(date +%F).sql
```

**Content Klasörü Yedeği Alma:**
Content volume'unun bulunduğu klasörü (genellikle `/var/lib/docker/volumes/..._ghost_content/_data`) tar arşivi haline getirebilirsiniz:
```bash
tar -czvf ghost_content_backup_$(date +%F).tar.gz /var/lib/docker/volumes/PROJEID_ghost_content/_data/
```

## Coolify Volume Backup Mantığı
Coolify, desteklenen veritabanı türleri ve volume'lar için S3 veya yerel yedekleme seçenekleri sunar. Coolify arayüzünden `Backups` sekmesine giderek günlük veya haftalık otomatik yedekleme görevleri oluşturabilirsiniz. En güvenli yöntem Coolify'ın yerleşik yedekleme özelliğini kullanmaktır.

## Geri Yükleme (Restore) Adımları
1. Yeni sunucuda/kurulumda docker-compose projesini ayağa kaldırın (boş olarak).
2. MySQL yedeğinizi içeri aktarın:
   ```bash
   cat ghost_db_backup_202X-XX-XX.sql | docker exec -i $(docker ps -qf "name=mysql") /usr/bin/mysql -u root -p'PASSWORD' ghost
   ```
3. Content yedeğinizi açıp içeriğini yeni sunucudaki `ghost_content` volume yoluna kopyalayın.
4. Ghost container'ını yeniden başlatın.
