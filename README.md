# Klinik Terminal - Ghost CMS Deploy Reposu

Bu proje bir Ghost kaynak kodu projesi **değildir**; Coolify deploy reposudur.

## Projenin Amacı
Bu repo, Klinik Terminal kişisel blog sitesini Coolify üzerinden Docker Compose ile ayağa kaldırmak için kullanılan altyapı/deploy yapılandırmasını içerir.

## Kurulum Özeti
1. Coolify üzerinde "Git Repository" kaynağı olarak bu repo eklenir.
2. Build Pack olarak "Docker Compose" seçilir.
3. Çevresel değişkenler (.env) Coolify arayüzünden tanımlanır.
4. Deploy işlemi başlatılır.

## Domain Bağlama Mantığı
Coolify üzerinden uygulamanın Domain ayarlarına `https://DOMAIN_BURAYA` girilir. Coolify, Traefik veya Caddy aracılığıyla Ghost'un expose edilen 2368 portuna yönlendirmeyi otomatik yapar.

İlk kurulum tamamlandığında, admin paneline şu adresten ulaşabilirsiniz:
**https://DOMAIN_BURAYA/ghost**

## Git Push ile Deploy Mantığı
Coolify, bu GitHub reposuna webhook (veya GitHub App) ile bağlıdır. `main` dalına (branch) yapılan her `git push` işlemi, Coolify üzerinde otomatik olarak yeni bir deploy tetikler. Yeni konfigürasyonlar (örneğin docker-compose.yml değişiklikleri) anında sunucuya yansır.

---

## Başlangıç Site Bilgileri Önerisi
* **Site Adı:** Klinik Terminal
* **Açıklama:** Tıp eğitimi, yazılım, yapay zekâ ve MedAsi’yi kurarken aldığım notlar.

## İlk Menü Önerileri
* Ana Sayfa
* Yazılar
* MedAsi Build Log
* Tıp Günlüğü
* Yazılım Notları
* Hakkımda

## İçerik Stratejisi

### Blog Kategorileri
* Tıp Günlüğü
* Yazılım Notları
* MedAsi Build Log
* Dağınık Defter

### İlk Yazı Fikirleri
1. Tıp Öğrencisi Olarak Neden Yazılım Öğreniyorum?
2. MedAsi’yi Kurmaya Beni İten Problem Neydi?
3. SourceBase: Slayttan Çalışma Kartı ve Soru Üretme Fikri
4. Bir Tıpçının Flutter ve Supabase ile İmtihanı
