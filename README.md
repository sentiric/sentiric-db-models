# 📦 Sentiric DB Models

[![Status](https://img.shields.io/badge/status-active-success.svg)]()

**Sentiric DB Models**, Sentiric platformunun **veritabanı şemalarını** ve gelecekteki **ORM (Object-Relational Mapping) modellerini** barındıran merkezi bir depodur. Bu repo, platformun veri katmanının "planıdır".

**Bu, çalışan bir servis değildir; bir kütüphane/şema tanım deposudur.**

## 🎯 Temel Sorumluluklar

*   **Tek Doğruluk Kaynağı (SSoT):** Platformun tüm PostgreSQL veritabanı şemaları için tek ve merkezi bir doğruluk kaynağı görevi görür.
*   **Veritabanı Başlatma:** `sentiric-infrastructure` tarafından kullanılan, PostgreSQL konteynerini ilk kez başlatırken tüm tabloları, ilişkileri ve başlangıç verilerini oluşturan `.sql` script'lerini içerir.
*   **ORM Modelleri (Gelecek):** Gelecekte, Python servisleri (`SQLModel`) veya Go servisleri (`GORM`, `sqlc`) tarafından kullanılacak olan paylaşılan ORM model tanımlarını barındırabilir.

## 🚀 Kullanım

Bu repo, doğrudan kullanılmaz. `sentiric-infrastructure` reposundaki `docker-compose.yml` dosyası, `postgres-init` klasörünü PostgreSQL konteynerinin `/docker-entrypoint-initdb.d` dizinine bir `volume` olarak bağlar. Docker, bu dizindeki `.sql` dosyalarını veritabanını ilk kez oluştururken otomatik olarak çalıştırır.

Bu yapı, herhangi bir geliştiricinin tek bir komutla (`make up`) platformun gerektirdiği tüm veritabanı yapısını tutarlı bir şekilde oluşturabilmesini sağlar.

## 🤝 Katkıda Bulunma

Veritabanı şemasında yapılan değişiklikler, platformun tümünü etkileyebilecek kritik değişikliklerdir.
1.  Yeni bir tablo veya sütun eklemeden önce, `sentiric-governance` reposunda bir tartışma başlatılmalıdır.
2.  Değişiklikler, önce ilgili `.sql` dosyasına uygulanmalıdır.
3.  Değişiklik, tüm platformun yeniden başlatılmasıyla test edilmelidir (`make down` ve `make up`).

---

---
## 🏛️ Anayasal Konum

Bu servis, [Sentiric Anayasası'nın (v11.0)](https://github.com/sentiric/sentiric-governance/blob/main/docs/blueprint/Architecture-Overview.md) **Zeka & Orkestrasyon Katmanı**'nda yer alan merkezi bir bileşendir.