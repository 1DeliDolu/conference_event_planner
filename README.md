# 🧩 Uygulama Projesi: Konferans Gider Planlayıcı

**Tahmini gereken süre:** 90 dakika

---

## 🧠 Görevi anlayın

Alejandre, iş konferansları için bir mekân yönetir. Ana şirketi  **“BudgetEase”** , BudgetEase müşterilerinin konferans etkinliklerini kolayca fiyatlandırabilmesi için bir web sitesi geliştirmeniz üzere sizi işe almak istiyor.

Uygulamanın gereksinimleri; kullanıcıların konferans merkezindeki odaları seçip fiyatlandırabilmesini, mikrofon ve projektör gibi *eklentileri (add-ons)* seçebilmesini ve belirli sayıda misafir için yemekleri seçebilmesini içerir.

**BudgetEase konferans gider planlayıcısının** özellikleri şunları içerecektir:

* Kullanıcı seçimlerine göre gerçek zamanlı güncellenen dinamik bir kullanıcı arayüzü
* Mekân seçimi, eklentiler ve yemek seçenekleri için bileşenler
* Durum değişikliklerini yönetmek için *Redux Toolkit* kullanılarak *Redux* entegrasyonu
* Farklı bölüm durumlarını yönetmek için *Redux slices*
* Seçilen öğeleri ve maliyetlerini açılır bir pencerede tablo ile gösterme
* Kullanıcı seçimlerine göre ara toplamları ve genel toplam maliyeti hesaplama ve gösterme

---

## 🎯 Öğrenme hedefleri

Bu laboratuvarı tamamladıktan sonra şunları yapabileceksiniz:

* **React bileşenleri oluşturma:** Bileşen birleştirme ve iç içe yerleştirme kullanarak fonksiyonel React bileşenleri oluşturma.
* **Hook’larla durum yönetimi:** Özellikle *useState* ve *useEffect* hook’larını uygulama. Hook’ları, bileşen düzeyi durumu yönetmek ve öğelerin görünürlüğünü kontrol etmek için kullanacaksınız.
* **Redux entegrasyonu:** Eylemler ( *actions* ), azaltıcılar ( *reducers* ) ve store gibi Redux kavramlarını kullanarak bir uygulamaya Redux entegre etme.
* **Dinamik veriyi render etme:** Nesne dizilerinden alınan verileri arayüzde dinamik olarak render etme. Bileşen listeleri üretmek için diziler üzerinde *map()* ile dolaşacaksınız.
* **Koşullu render ile olay yönetimi:** Düğme seçimi gibi kullanıcı olaylarını yönetme ve karşılık gelen eylemleri tetikleme.

---

## 🧾 Proje görevleri

1. Proje ortamını kurun
2. *ConferenceEvent.jsx* bileşeninin yapısını inceleyin
3. *Venue* modülünün kodunu inceleyin
4. Güncellemeleri ve durum değişikliklerini yönetmek için Redux’u bileşenlerle birleştirin
5. Ara toplamları ve toplam maliyeti hesaplayan mantığı ekleyin
6. Seçilen ürünleri göstermek için dinamik bir tablo oluşturun; öğe adı, birim maliyet, miktar ve o öğe için toplam maliyeti görüntüleyin
7. Konforlu bir kullanıcı deneyimi için web tasarımı oluşturun
8. Web sitenizi herkese açık bir barındırma hizmetine dağıtın

---

## 🧩 Çözümler

Çözüm kodunu bu laboratuvarın sonunda bulacaksınız. Görevlerden herhangi birini tamamlamakta yardıma ihtiyacınız olursa, orada çalışan kodun önerilen bir sürümünü bulabilirsiniz. Ayrıca, kendi çözümünüzü veya laboratuvarın sonundaki kodu kaydettiğinizden emin olun. Bu, nihai proje için kod geliştirirken size yardımcı olacaktır.

---

## ✅ Ön koşullar

* Temel HTML ve CSS
* Orta düzey JavaScript
* React fonksiyon bileşenleri, hook’lar ve durum yönetimi için *Redux toolkit* ile aşinalık
* GitHub kullanarak kod yönetimi

GitHub’da nasıl çalışılacağıyla ilgili yönlendirmeye ihtiyacınız olursa bu talimatları inceleyin.

---

## ⚠️ Bu laboratuvar ortamıyla ilgili önemli bildirim

*Skills Network Cloud IDE* (Theia ve Docker tabanlı), kurs ve proje laboratuvarlarında uygulamalı çalışmalar için ortam sağlayan açık kaynaklı bir IDE’dir ( *Integrated Development Environment* ).

Bu laboratuvar ortamındaki oturumların kalıcı olmadığını lütfen unutmayın. Bu laboratuvara her bağlandığınızda, sizin için yeni bir ortam oluşturulur. Kodunuzu GitHub’a veya başka bir harici kaynağa kaydetmeden ortamdan çıkarsanız verilerinizi kaybedersiniz. Veri kaybını önlemek için bu laboratuvarları tek bir oturumda tamamlamayı planlayın.

---

# 🧰 Görev 1: Ortamı kurma

## 🧷 1. Depoyu fork’layın

React uygulamanız için GitHub deposunu fork’lamanız gerekir. Bu proje için iskelet kodun bulunduğu GitHub deposu şuradadır:

[https://github.com/ibm-developer-skills-network/conference_event_planner.git](https://github.com/ibm-developer-skills-network/conference_event_planner.git)

Yukarıdaki bağlantıyı takip ettikten sonra **fork** düğmesine tıklayın.

Bu depo, bu laboratuvar için React uygulamasının temel yerleşimini içerir.

## 🧬 2. Depoyu klonlayın

Depoyu **git clone `<repository-link>`** komutunu kullanarak klonlayın.

`<repository-link>` ifadesini, fork’ladığınız **conference_event_planner** deposunun bağlantısıyla değiştirin.

```bash
git clone <repository-link>
```

Depoyu klonladıktan sonra, “Project” klasörü altında **conference_event_planner** adlı bir klasör göreceksiniz. Ekran görüntüsü dizin yapısını gösterir.

## 💾 3. Çalışmanızı düzenli olarak push edin

Bu fork’lanmış depoyu, yaptığınız işin kaydını tutmak için en son kodunuzu push etmekte kullanacaksınız. Dosyalarınızı periyodik olarak kaydedin. Git komutlarını çalıştırabilmek için dosyalarınızın kaydedilmiş olması gerekir.

## 🖼️ 4. Görseller

Projede kendi görsellerinizi kullanabilir veya telifsiz görseller sağlayan Pixabay’den önerilen görselleri kullanabilirsiniz.

* Conference room
  [https://pixabay.com/photos/chairs-empty-office-room-table-2181916/](https://pixabay.com/photos/chairs-empty-office-room-table-2181916/)
* Auditorium:
  [https://pixabay.com/photos/event-venue-auditorium-meeting-1597531/](https://pixabay.com/photos/event-venue-auditorium-meeting-1597531/)
* Presentation room:
  [https://pixabay.com/photos/convention-center-chair-seminar-3908238/](https://pixabay.com/photos/convention-center-chair-seminar-3908238/)
* Meeting room:
  [https://pixabay.com/photos/chairs-empty-office-room-table-2181916/](https://pixabay.com/photos/chairs-empty-office-room-table-2181916/)
* Small meeting room:
  [https://pixabay.com/photos/laptops-meeting-businessmen-593296/](https://pixabay.com/photos/laptops-meeting-businessmen-593296/)
* Projector:
  [https://pixabay.com/photos/business-computer-conference-20031/](https://pixabay.com/photos/business-computer-conference-20031/)
* Speakers:
  [https://pixabay.com/photos/speakers-bluetooth-tech-speaker-4109274/](https://pixabay.com/photos/speakers-bluetooth-tech-speaker-4109274/)
* Microphone:
  [https://pixabay.com/photos/public-speaking-mic-microphone-3926344/](https://pixabay.com/photos/public-speaking-mic-microphone-3926344/)
* Whiteboard:
  [https://pixabay.com/photos/whiteboard-dry-erase-marker-blank-2903269/](https://pixabay.com/photos/whiteboard-dry-erase-marker-blank-2903269/)
* Signs:
  [https://pixabay.com/photos/signpost-waypoint-wood-grain-board-235079/](https://pixabay.com/photos/signpost-waypoint-wood-grain-board-235079/)

## 📁 5. Terminal yolunu değiştirin

Terminal yolunuzu aşağıdaki komutla **conference_event_planner** klasörüne değiştirin.

```bash
cd conference_event_planner
```

## ✅ 6. Klonladığınız kodun doğru çalıştığından emin olun

Uygulamayı çalıştırmak için gerekli paketleri *npm* ile yükleyin.

```bash
npm install
```

Uygulamayı çalıştırmak için aşağıdaki komutu yürütün. Bu komut, 4173 port numarası üzerinde uygulama sunucusunu başlatır.

```bash
npm run preview
```

## 🌐 7. Uygulamayı görüntüleyin

Şimdi uygulamayı görüntüleyebilirsiniz.

Sol paneldeki *Skills Network* simgesine tıklayın (1 numaraya bakın). Bu işlem  *Skills Network Toolbox* ’ı açacaktır. Ardından  **Launch Application** ’a tıklayın (2 numaraya bakın). **Application Port** alanına **4173** port numarasını girin (3 numaraya bakın) ve **[↗]** simgesine tıklayın.

## 🧭 8. Beklenen çıktı

Çıktı aşağıdaki ekran görüntüsüne benzer olmalıdır. **Get Started** düğmesine tıklamak, kullanıcıyı ürün seçimi sayfasına götürmelidir. Üst bilgi ve ilk bölüm **“Room selection”** görünmelidir.

> *Not:* Size *backgroundImage* yerine *backgroundColor* sağlanmıştır. Renk yerine görsel tercih ediyorsanız, kendi görselinizi ekleyebilirsiniz. Verilen kodla uygulama ürün sayfası aşağıdakine benzer görünmelidir.

## 🔄 9. Değişiklik yaptıysanız push edin

Herhangi bir değişiklik yaparsanız **git add** ve **git commit** çalıştırın. Ardından, commit edilen değişiklikleri uzak GitHub deponuza yüklemek için **git push** komutunu çalıştırın ve kodunuzun en son sürümünü kaydettiğinizden emin olun.

> *Not:* Kodu GitHub deponuza push ederken kullanıcı adı ve parola girmeniz istenebilir. GitHub’da nasıl çalışılacağıyla ilgili daha fazla yönlendirme gerekiyorsa ilgili talimatları inceleyin.

---

# 🧩 Görev 2: ConferenceEvent.jsx yapısını gözden geçirin

İki çalışan modülünüz vardır:

* Başlamak için bir düğme ve şirket açıklaması içeren açılış sayfası
* Mekândaki oda seçimini ve artırma/azaltma düğmelerini içeren **“venue section”**

**src** dizinindeki **ConferenceEvent.jsx** dosyasını açın. Bu bileşen ürün seçimi sayfası için fonksiyonları ve yerleşimleri içerir.

## 🧱 Yerleşimler

* Bir *navbar* öğesi
* `<div>` etiketi içinde **main_container** sınıfı
* Koşullu operatör `? :` kullanarak işlevi aç/kapat eden bir **showItems** değişkeni
* `<div>` etiketi içinde **items-information** sınıfı
* Mekân, eklentiler ve yemekler için `<div>` etiketlerinde yerleşimler. Bu yerleşimlerin her birinde iki ortak sınıf adı bulunur: **venue_container** ve **container_main**
* Seçilen öğelerin ayrıntılarını göstermek için `<div>` içinde **total_amount_detail** sınıfı

---

# (Tam README içeriği eklendi)
# 🧩 Uygulama Projesi: Konferans Gider Planlayıcı

**Tahmini gereken süre:** 90 dakika

---

## 🧠 Görevi anlayın

Alejandre, iş konferansları için bir mekân yönetir. Ana şirketi  **“BudgetEase”** , BudgetEase müşterilerinin konferans etkinliklerini kolayca fiyatlandırabilmesi için bir web sitesi geliştirmeniz üzere sizi işe almak istiyor.

Uygulamanın gereksinimleri; kullanıcıların konferans merkezindeki odaları seçip fiyatlandırabilmesini, mikrofon ve projektör gibi *eklentileri (add-ons)* seçebilmesini ve belirli sayıda misafir için yemekleri seçebilmesini içerir.

**BudgetEase konferans gider planlayıcısının** özellikleri şunları içerecektir:

* Kullanıcı seçimlerine göre gerçek zamanlı güncellenen dinamik bir kullanıcı arayüzü
* Mekân seçimi, eklentiler ve yemek seçenekleri için bileşenler
* Durum değişikliklerini yönetmek için *Redux Toolkit* kullanılarak *Redux* entegrasyonu
* Farklı bölüm durumlarını yönetmek için *Redux slices*
* Seçilen öğeleri ve maliyetlerini açılır bir pencerele tablo ile gösterme
* Kullanıcı seçimlerine göre ara toplamları ve genel toplam maliyeti hesaplama ve gösterme

---

## 🎯 Öğrenme hedefleri

Bu laboratuvarı tamamladığınızda şunları yapabileceksiniz:

* **React bileşenleri oluşturma:** Bileşen birleştirme ve iç içe yerleştirme kullanarak fonksiyonel React bileşenleri oluşturma.
* **Hook’larla durum yönetimi:** Özellikle *useState* ve *useEffect* hook’larını uygulama. Hook’ları, bileşen düzeyi durumu yönetmek ve öğelerin görünürlüğünü kontrol etmek için kullanacaksınız.
* **Redux entegrasyonu:** Eylemler ( *actions* ), azaltıcılar ( *reducers* ) ve store gibi Redux kavramlarını kullanarak bir uygulamaya Redux entegre etme.
* **Dinamik veriyi render etme:** Nesne dizilerinden alınan verileri arayüzde dinamik olarak render etme. Bileşen listeleri üretmek için diziler üzerinde *map()* ile dolaşacaksınız.
* **Koşullu render ile olay yönetimi:** Düğme seçimi gibi kullanıcı olaylarını yönetme ve karşılık gelen eylemleri tetikleme.

---

## 🧾 Proje görevleri

1. Proje ortamını kurun
2. *ConferenceEvent.jsx* bileşeninin yapısını inceleyin
3. *Venue* modülünün kodunu inceleyin
4. Güncellemeleri ve durum değişikliklerini yönetmek için Redux’u bileşenlerle birleştirin
5. Ara toplamları ve toplam maliyeti hesaplayan mantığı ekleyin
6. Seçilen ürünleri göstermek için dinamik bir tablo oluşturun; öğe adı, birim maliyet, miktar ve o öğe için toplam maliyeti görüntüleyin
7. Konforlu bir kullanıcı deneyimi için web tasarımı oluşturun
8. Web sitenizi herkese açık bir barındırma hizmetine dağıtın

---

## 🧩 Çözümler

Çözüm kodunu bu laboratuvarın sonunda bulacaksınız. Görevlerden herhangi birini tamamlamakta yardıma ihtiyacınız olursa, orada çalışan kodun önerilen bir sürümünü bulabilirsiniz. Ayrıca, kendi çözümünüzü veya laboratuvarın sonundaki kodu kaydettiğinizden emin olun. Bu, nihai proje için kod geliştirirken size yardımcı olacaktır.

---

## ✅ Ön koşullar

* Temel HTML ve CSS
* Orta düzey JavaScript
* React fonksiyon bileşenleri, hook’lar ve durum yönetimi için *Redux toolkit* ile aşinalık
* GitHub kullanarak kod yönetimi

GitHub’da nasıl çalışılacağıyla ilgili yönlendirmeye ihtiyacınız olursa bu talimatları inceleyin.

---

## ⚠️ Bu laboratuvar ortamıyla ilgili önemli bildirim

*Skills Network Cloud IDE* (Theia ve Docker tabanlı), kurs ve proje laboratuvarlarında uygulamalı çalışmalar için ortam sağlayan açık kaynaklı bir IDE’dir ( *Integrated Development Environment* ).

Bu laboratuvar ortamındaki oturumların kalıcı olmadığını lütfen unutmayın. Bu laboratuvara her bağlandığınızda, sizin için yeni bir ortam oluşturulur. Kodunuzu GitHub’a veya başka bir harici kaynağa kaydetmeden ortamdan çıkarsanız verilerinizi kaybedersiniz. Veri kaybını önlemek için bu laboratuvarları tek bir oturumda tamamlamayı planlayın.

---

# 🧩 Görev 1: Ortamı kurma

## 🧷 1. Depoyu fork’layın

React uygulamanız için GitHub deposunu fork’lamanız gerekir. Bu proje için iskelet kodun bulunduğu GitHub deposu şuradadır:

[https://github.com/ibm-developer-skills-network/conference_event_planner.git](https://github.com/ibm-developer-skills-network/conference_event_planner.git)

Yukarıdaki bağlantıyı takip ettikten sonra **fork** düğmesine tıklayın.

Bu depo, bu laboratuvar için React uygulamasının temel yerleşimini içerir.

## 🧬 2. Depoyu klonlayın

Depoyu **git clone `<repository-link>`** komutunu kullanarak klonlayın.

`<repository-link>` ifadesini, fork’ladığınız **conference_event_planner** deposunun bağlantısıyla değiştirin.

```bash
git clone <repository-link>
```

Depoyu klonladıktan sonra, “Project” klasörü altında **conference_event_planner** adlı bir klasör göreceksiniz. Ekran görüntüsü dizin yapısını gösterir.

## 💾 3. Çalışmanızı düzenli olarak push edin

Bu fork’lanmış depoyu, yaptığınız işin kaydını tutmak için en son kodunuzu push etmekte kullanacaksınız. Dosyalarınızı periyodik olarak kaydedin. Git komutlarını çalıştırabilmek için dosyalarınızın kaydedilmiş olması gerekir.

## 🖼️ 4. Görseller

Projede kendi görsellerinizi kullanabilir veya telifsiz görseller sağlayan Pixabay’den önerilen görselleri kullanabilirsiniz.

* Conference room
  [https://pixabay.com/photos/chairs-empty-office-room-table-2181916/](https://pixabay.com/photos/chairs-empty-office-room-table-2181916/)
* Auditorium:
  [https://pixabay.com/photos/event-venue-auditorium-meeting-1597531/](https://pixabay.com/photos/event-venue-auditorium-meeting-1597531/)
* Presentation room:
  [https://pixabay.com/photos/convention-center-chair-seminar-3908238/](https://pixabay.com/photos/convention-center-chair-seminar-3908238/)
* Meeting room:
  [https://pixabay.com/photos/chairs-empty-office-room-table-2181916/](https://pixabay.com/photos/chairs-empty-office-room-table-2181916/)
* Small meeting room:
  [https://pixabay.com/photos/laptops-meeting-businessmen-593296/](https://pixabay.com/photos/laptops-meeting-businessmen-593296/)
* Projector:
  [https://pixabay.com/photos/business-computer-conference-20031/](https://pixabay.com/photos/business-computer-conference-20031/)
* Speakers:
  [https://pixabay.com/photos/speakers-bluetooth-tech-speaker-4109274/](https://pixabay.com/photos/speakers-bluetooth-tech-speaker-4109274/)
* Microphone:
  [https://pixabay.com/photos/public-speaking-mic-microphone-3926344/](https://pixabay.com/photos/public-speaking-mic-microphone-3926344/)
* Whiteboard:
  [https://pixabay.com/photos/whiteboard-dry-erase-marker-blank-2903269/](https://pixabay.com/photos/whiteboard-dry-erase-marker-blank-2903269/)
* Signs:
  [https://pixabay.com/photos/signpost-waypoint-wood-grain-board-235079/](https://pixabay.com/photos/signpost-waypoint-wood-grain-board-235079/)

## 📁 5. Terminal yolunu değiştirin

Terminal yolunuzu aşağıdaki komutla **conference_event_planner** klasörüne değiştirin.

```bash
cd conference_event_planner
```

## ✅ 6. Klonladığınız kodun doğru çalıştığından emin olun

Uygulamayı çalıştırmak için gerekli paketleri *npm* ile yükleyin.

```bash
npm install
```

Uygulamayı çalıştırmak için aşağıdaki komutu yürütün. Bu komut, 4173 port numarası üzerinde uygulama sunucusunu başlatır.

```bash
npm run preview
```

## 🌐 7. Uygulamayı görüntüleyin

Şimdi uygulamayı görüntüleyebilirsiniz.

Sol paneldeki *Skills Network* simgesine tıklayın (1 numaraya bakın). Bu işlem  *Skills Network Toolbox* ’ı açacaktır. Ardından  **Launch Application** ’a tıklayın (2 numaraya bakın). **Application Port** alanına **4173** port numarasını girin (3 numaraya bakın) ve **[↗]** simgesine tıklayın.

## 🧭 8. Beklenen çıktı

Çıktı aşağıdaki ekran görüntüsüne benzer olmalıdır. **Get Started** düğmesine tıklamak, kullanıcıyı ürün seçimi sayfasına götürmelidir. Üst bilgi ve ilk bölüm **“Room selection”** görünmelidir.

> *Not:* Size *backgroundImage* yerine *backgroundColor* sağlanmıştır. Renk yerine görsel tercih ediyorsanız, kendi görselinizi ekleyebilirsiniz. Verilen kodla uygulama ürün sayfası aşağıdakine benzer görünmelidir.

## 🔄 9. Değişiklik yaptıysanız push edin

Herhangi bir değişiklik yaparsanız **git add** ve **git commit** çalıştırın. Ardından, commit edilen değişiklikleri uzak GitHub deponuza yüklemek için **git push** komutunu çalıştırın ve kodunuzun en son sürümünü kaydettiğinizden emin olun.

> *Not:* Kodu GitHub deponuza push ederken kullanıcı adı ve parola girmeniz istenebilir. GitHub’da nasıl çalışılacağıyla ilgili daha fazla yönlendirme gerekiyorsa ilgili talimatları inceleyin.

---

# 🧩 Görev 2: ConferenceEvent.jsx yapısını gözden geçirin

İki çalışan modülünüz vardır:

* Başlamak için bir düğme ve şirket açıklaması içeren açılış sayfası
* Mekândaki oda seçimini ve artırma/azaltma düğmelerini içeren **“venue section”**

**src** dizinindeki **ConferenceEvent.jsx** dosyasını açın. Bu bileşen ürün seçimi sayfası için fonksiyonları ve yerleşimleri içerir.

## 🧱 Yerleşimler

* Bir *navbar* öğesi
* `<div>` etiketi içinde **main_container** sınıfı
* Koşullu operatör `? :` kullanarak işlevi aç/kapat eden bir **showItems** değişkeni
* `<div>` etiketi içinde **items-information** sınıfı
* Mekân, eklentiler ve yemekler için `<div>` etiketlerinde yerleşimler. Bu yerleşimlerin her birinde iki ortak sınıf adı bulunur: **venue_container** ve **container_main**
* Seçilen öğelerin ayrıntılarını göstermek için `<div>` içinde **total_amount_detail** sınıfı

---
