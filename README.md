# QueryMaster

**Görsel Veritabanı Tasarım ve Test Aracı**

QueryMaster, özellikle MS SQL ve Oracle gibi büyük ölçekli ilişkisel veritabanı sistemlerinde (RDBMS) karmaşık mimariler kurarken hata yapma riskini en aza indiren yenilikçi bir tasarım, test ve eğitim aracıdır. Geliştiricilerin, mimarların ve öğrencilerin şemaları görselleştirerek tasarlamasını ve sorgu mantıklarını yaşayarak test etmesini sağlar.

## Proje Odak Noktaları ve İşleyiş

Sistem, veritabanı modellemesini kod satırlarından çıkarıp etkileşimli ve güvenli bir görsel arayüze taşır:

*   **Sürükle-Bırak (Drag-and-Drop) Modelleme:** Kullanıcılar tabloları, sütunları ve veri tiplerini interaktif bir tuval üzerinde oluşturur. Birincil anahtar (Primary Key) ve Yabancı Anahtar (Foreign Key) ilişkileri tablolar arasında sadece bağlantı çizgileri çekilerek saniyeler içinde hatasız şekilde kurulur.
*   **Otomatik SQL Üretimi (Code Generation):** Görsel olarak hazırlanan veya revize edilen bu şema, arka planda anlık olarak optimize edilmiş, hedef veritabanına (MS SQL, Oracle vb.) uygun DDL (Data Definition Language) kodlarına dönüştürülür.
*   **Görsel Join Analizi ve Simülasyon:** Karmaşık "Join" (Inner, Left, Right, Full) operasyonlarının çıktıları simüle edilir. Hangi tablodan hangi verinin nasıl kesiştiği ve sonuç kümesinin (result set) nasıl oluştuğu adım adım grafiklerle gösterilerek soyut veritabanı mantığı somutlaştırılır.

## Temel Özellikler

*   **Hatasız Şema Tasarımı:** İlişki kısıtlamalarının (Constraint), kaskad kurallarının (Cascade Delete/Update) ve indekslerin görsel arayüzde ön validasyondan geçerek oluşturulması, böylece olası mimari çöküşlerin engellenmesi.
*   **Eğitim ve Prototipleme Odaklı:** Geliştiricilerin SQL ilişkilerini ezberlemek yerine mantığını görerek kavramasını sağlayan, hızlı prototip üretmeye olanak tanıyan sandbox yapısı.
*   **Çoklu Veritabanı Desteği (Agnostik Yapı):** Tasarlanan tek bir evrensel şemadan, isteğe bağlı olarak MS SQL, Oracle, PostgreSQL veya MySQL formatlarına uygun export alabilme esnekliği.
*   **Akıllı Optimizasyon Tavsiyeleri:** Sürükle-bırak işlemleri sırasında sistemin normalizasyon kurallarını analiz ederek (örneğin: "Bu tabloda çok fazla alan var, bölmek isteyebilirsiniz") tavsiyeler sunması.

## Mimari Yaklaşım ve Teknoloji Yığını

*   **Frontend (Görsel Tuval ve UI):** React.js veya Vue.js. Akıcı bir sürükle-bırak (drag-and-drop) tuval deneyimi ve node tabanlı diyagramlar için React Flow, JointJS veya mxGraph kütüphaneleri.
*   **Backend (SQL Çevirici Motoru):** Node.js veya Python. Kullanıcının görseldeki (JSON) düğüm (node) verilerini alıp spesifik veritabanı sentakslarına çeviren sağlam bir AST (Abstract Syntax Tree) / Parsing servisi.
*   **Durum Yönetimi (State Management):** Redux veya Zustand. Çok tablolu karmaşık diyagramların anlık koordinat ve ilişki durumlarını tarayıcıda performanslı bir şekilde saklamak için.
*   **Simülasyon Veritabanı (İsteğe Bağlı):** SQLite, WebAssembly tabanlı SQL.js (Tarayıcı üzerinde gerçek verilerle Join işlemlerini hızlıca test etmek ve çıktıları tablo olarak anında görebilmek için).

---
