# SourceBase: Slayttan Çalışma Kartı ve Soru Üretme Fikri

**Kategori:** MedAsi Build Log / Yazılım Notları

MedAsi'nin kalbinde yer alan en önemli modüllerden biri **SourceBase**. 

## SourceBase Nedir?
Tıp eğitiminin ana materyali genellikle PDF slaytlarıdır. SourceBase, kullanıcının yüklediği bu slaytları analiz eden, metinleri çıkaran ve yapay zeka desteğiyle bu metinlerden yapılandırılmış "Çalışma Kartları" (Flashcards) ve "Çoktan Seçmeli Sorular" üreten bir sistemdir.

## Teknik Zorluklar
Bu sistemi tasarlarken karşılaştığımız bazı teknik zorluklar oldu:
1. **PDF Parse İşlemleri:** Medikal terimlerin ve karmaşık slayt düzenlerinin doğru okunması.
2. **Yapay Zeka (LLM) Entegrasyonu:** Modelin halüsinasyon (yanlış bilgi üretme) yapmasını engellemek. Tıp gibi kritik bir alanda %100 doğruluğa yakın sonuçlar almamız gerekiyordu.
3. **Kullanıcı Deneyimi:** Üretilen kartların kolayca düzenlenebilir ve gözden geçirilebilir olması.

Bir sonraki adım, SourceBase mimarisini daha ölçeklenebilir hale getirmek ve OCR destekli görsel analizi eklemek olacak.
