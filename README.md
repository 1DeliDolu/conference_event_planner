# Conference Event Planner

Lightweight React + Vite application for estimating conference/event costs.

This project provides a simple UI to select venues, add-ons (projector, microphone, speakers, etc.), and catering options, and calculates subtotals and total cost in real time using Redux Toolkit for state management.

**Tech stack**

- React (JSX)
- Vite (dev server & build)
- Redux Toolkit + React Redux (state management)

## Key features

- Venue selection with quantity controls
- Add-on selection (AV equipment) and per-item costs
- Meal options with guest counts
- Live subtotal and total cost calculation
- State organized into Redux slices (`avSlice.js`, `mealsSlice.js`, `venueSlice.js`)

## Repo layout (important files)

- [src/main.jsx](src/main.jsx) — app bootstrap
- [src/App.jsx](src/App.jsx) — top-level app container
- [src/ConferenceEvent.jsx](src/ConferenceEvent.jsx) — main feature UI
- [src/TotalCost.jsx](src/TotalCost.jsx) — total/summary view
- [src/store.js](src/store.js) — Redux store setup
- [src/avSlice.js](src/avSlice.js), [src/mealsSlice.js](src/mealsSlice.js), [src/venueSlice.js](src/venueSlice.js) — state slices
- [src/assets/](src/assets) — static images and assets

## Prerequisites

- Node.js (16+) or compatible
- npm (or pnpm/yarn, adapt commands)

## Install

1. Install dependencies

```bash
npm install
```

2. Start development server

```bash
npm run dev
```

Open the URL printed by Vite (usually http://localhost:5173).

## Available npm scripts

- `npm run dev` — start Vite dev server
- `npm run build` — build production files to `dist`
- `npm run preview` — build and run local preview server
- `npm run lint` — run ESLint checks
- `npm run deploy` — publish `dist` to GitHub Pages (requires `gh-pages` setup)

These scripts come from the project's `package.json`.

## How it works (brief)

- The UI is composed of React components in `src/` that dispatch actions to Redux slices.
- Each slice manages its part of the app state (venue, AV add-ons, meals).
- The `TotalCost`/summary component reads slice state and computes totals for display.

## Development tips

- Inspect `src/ConferenceEvent.jsx` to understand the selection flows and event handlers.
- Slice files contain the add/remove/update logic — extend them if you add new item types.
- Keep UI state (visibility, local toggles) in component state; persist shared selections in Redux.

## Contributing

- Open an issue for feature requests or bugs.
- Fork the repo, make a branch, and open a pull request with a clear description.

## License

This repository includes a `LICENSE` file — follow the terms specified there.

---

If you'd like, I can also:

- run the dev server and confirm the app loads;
- add a short Usage section with screenshots or example flows;
- set up a simple deployment workflow.

# 🧩 Uygulama Projesi: Konferans Gider Planlayıcı

**Tahmini gereken süre:** 90 dakika

---

## 🧠 Görevi anlayın

Alejandre, iş konferansları için bir mekân yönetir. Ana şirketi **“BudgetEase”** , BudgetEase müşterilerinin konferans etkinliklerini kolayca fiyatlandırabilmesi için bir web sitesi geliştirmeniz üzere sizi işe almak istiyor.

Uygulamanın gereksinimleri; kullanıcıların konferans merkezindeki odaları seçip fiyatlandırabilmesini, mikrofon ve projektör gibi _eklentileri (add-ons)_ seçebilmesini ve belirli sayıda misafir için yemekleri seçebilmesini içerir.

**BudgetEase konferans gider planlayıcısının** özellikleri şunları içerecektir:

- Kullanıcı seçimlerine göre gerçek zamanlı güncellenen dinamik bir kullanıcı arayüzü
- Mekân seçimi, eklentiler ve yemek seçenekleri için bileşenler
- Durum değişikliklerini yönetmek için _Redux Toolkit_ kullanılarak _Redux_ entegrasyonu
- Farklı bölüm durumlarını yönetmek için _Redux slices_
- Seçilen öğeleri ve maliyetlerini açılır bir pencerede tablo ile gösterme
- Kullanıcı seçimlerine göre ara toplamları ve genel toplam maliyeti hesaplama ve gösterme

---

## 🎯 Öğrenme hedefleri

Bu laboratuvarı tamamladıktan sonra şunları yapabileceksiniz:

- **React bileşenleri oluşturma:** Bileşen birleştirme ve iç içe yerleştirme kullanarak fonksiyonel React bileşenleri oluşturma.
- **Hook’larla durum yönetimi:** Özellikle _useState_ ve _useEffect_ hook’larını uygulama. Hook’ları, bileşen düzeyi durumu yönetmek ve öğelerin görünürlüğünü kontrol etmek için kullanacaksınız.
- **Redux entegrasyonu:** Eylemler ( _actions_ ), azaltıcılar ( _reducers_ ) ve store gibi Redux kavramlarını kullanarak bir uygulamaya Redux entegre etme.
- **Dinamik veriyi render etme:** Nesne dizilerinden alınan verileri arayüzde dinamik olarak render etme. Bileşen listeleri üretmek için diziler üzerinde _map()_ ile dolaşacaksınız.
- **Koşullu render ile olay yönetimi:** Düğme seçimi gibi kullanıcı olaylarını yönetme ve karşılık gelen eylemleri tetikleme.

---

## 🧾 Proje görevleri

1. Proje ortamını kurun
2. _ConferenceEvent.jsx_ bileşeninin yapısını inceleyin
3. _Venue_ modülünün kodunu inceleyin
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

- Temel HTML ve CSS
- Orta düzey JavaScript
- React fonksiyon bileşenleri, hook’lar ve durum yönetimi için _Redux toolkit_ ile aşinalık
- GitHub kullanarak kod yönetimi

GitHub’da nasıl çalışılacağıyla ilgili yönlendirmeye ihtiyacınız olursa bu talimatları inceleyin.

---

## ⚠️ Bu laboratuvar ortamıyla ilgili önemli bildirim

_Skills Network Cloud IDE_ (Theia ve Docker tabanlı), kurs ve proje laboratuvarlarında uygulamalı çalışmalar için ortam sağlayan açık kaynaklı bir IDE’dir ( _Integrated Development Environment_ ).

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

- Conference room
  [https://pixabay.com/photos/chairs-empty-office-room-table-2181916/](https://pixabay.com/photos/chairs-empty-office-room-table-2181916/)
- Auditorium:
  [https://pixabay.com/photos/event-venue-auditorium-meeting-1597531/](https://pixabay.com/photos/event-venue-auditorium-meeting-1597531/)
- Presentation room:
  [https://pixabay.com/photos/convention-center-chair-seminar-3908238/](https://pixabay.com/photos/convention-center-chair-seminar-3908238/)
- Meeting room:
  [https://pixabay.com/photos/chairs-empty-office-room-table-2181916/](https://pixabay.com/photos/chairs-empty-office-room-table-2181916/)
- Small meeting room:
  [https://pixabay.com/photos/laptops-meeting-businessmen-593296/](https://pixabay.com/photos/laptops-meeting-businessmen-593296/)
- Projector:
  [https://pixabay.com/photos/business-computer-conference-20031/](https://pixabay.com/photos/business-computer-conference-20031/)
- Speakers:
  [https://pixabay.com/photos/speakers-bluetooth-tech-speaker-4109274/](https://pixabay.com/photos/speakers-bluetooth-tech-speaker-4109274/)
- Microphone:
  [https://pixabay.com/photos/public-speaking-mic-microphone-3926344/](https://pixabay.com/photos/public-speaking-mic-microphone-3926344/)
- Whiteboard:
  [https://pixabay.com/photos/whiteboard-dry-erase-marker-blank-2903269/](https://pixabay.com/photos/whiteboard-dry-erase-marker-blank-2903269/)
- Signs:
  [https://pixabay.com/photos/signpost-waypoint-wood-grain-board-235079/](https://pixabay.com/photos/signpost-waypoint-wood-grain-board-235079/)

## 📁 5. Terminal yolunu değiştirin

Terminal yolunuzu aşağıdaki komutla **conference_event_planner** klasörüne değiştirin.

```bash
cd conference_event_planner
```

## ✅ 6. Klonladığınız kodun doğru çalıştığından emin olun

Uygulamayı çalıştırmak için gerekli paketleri _npm_ ile yükleyin.

```bash
npm install
```

Uygulamayı çalıştırmak için aşağıdaki komutu yürütün. Bu komut, 4173 port numarası üzerinde uygulama sunucusunu başlatır.

```bash
npm run preview
```

## 🌐 7. Uygulamayı görüntüleyin

Şimdi uygulamayı görüntüleyebilirsiniz.

Sol paneldeki _Skills Network_ simgesine tıklayın (1 numaraya bakın). Bu işlem _Skills Network Toolbox_ ’ı açacaktır. Ardından **Launch Application** ’a tıklayın (2 numaraya bakın). **Application Port** alanına **4173** port numarasını girin (3 numaraya bakın) ve **[↗]** simgesine tıklayın.

## 🧭 8. Beklenen çıktı

Çıktı aşağıdaki ekran görüntüsüne benzer olmalıdır. **Get Started** düğmesine tıklamak, kullanıcıyı ürün seçimi sayfasına götürmelidir. Üst bilgi ve ilk bölüm **“Room selection”** görünmelidir.

> _Not:_ Size _backgroundImage_ yerine _backgroundColor_ sağlanmıştır. Renk yerine görsel tercih ediyorsanız, kendi görselinizi ekleyebilirsiniz. Verilen kodla uygulama ürün sayfası aşağıdakine benzer görünmelidir.

## 🔄 9. Değişiklik yaptıysanız push edin

Herhangi bir değişiklik yaparsanız **git add** ve **git commit** çalıştırın. Ardından, commit edilen değişiklikleri uzak GitHub deponuza yüklemek için **git push** komutunu çalıştırın ve kodunuzun en son sürümünü kaydettiğinizden emin olun.

> _Not:_ Kodu GitHub deponuza push ederken kullanıcı adı ve parola girmeniz istenebilir. GitHub’da nasıl çalışılacağıyla ilgili daha fazla yönlendirme gerekiyorsa ilgili talimatları inceleyin.

---

# 🧩 Görev 2: ConferenceEvent.jsx yapısını gözden geçirin

İki çalışan modülünüz vardır:

- Başlamak için bir düğme ve şirket açıklaması içeren açılış sayfası
- Mekândaki oda seçimini ve artırma/azaltma düğmelerini içeren **“venue section”**

**src** dizinindeki **ConferenceEvent.jsx** dosyasını açın. Bu bileşen ürün seçimi sayfası için fonksiyonları ve yerleşimleri içerir.

## 🧱 Yerleşimler

- Bir _navbar_ öğesi
- `<div>` etiketi içinde **main_container** sınıfı
- Koşullu operatör `? :` kullanarak işlevi aç/kapat eden bir **showItems** değişkeni
- `<div>` etiketi içinde **items-information** sınıfı
- Mekân, eklentiler ve yemekler için `<div>` etiketlerinde yerleşimler. Bu yerleşimlerin her birinde iki ortak sınıf adı bulunur: **venue_container** ve **container_main**
- Seçilen öğelerin ayrıntılarını göstermek için `<div>` içinde **total_amount_detail** sınıfı

---

# (Tam README içeriği eklendi)

# 🧩 Uygulama Projesi: Konferans Gider Planlayıcı

**Tahmini gereken süre:** 90 dakika

---

## 🧠 Görevi anlayın

Alejandre, iş konferansları için bir mekân yönetir. Ana şirketi **“BudgetEase”** , BudgetEase müşterilerinin konferans etkinliklerini kolayca fiyatlandırabilmesi için bir web sitesi geliştirmeniz üzere sizi işe almak istiyor.

Uygulamanın gereksinimleri; kullanıcıların konferans merkezindeki odaları seçip fiyatlandırabilmesini, mikrofon ve projektör gibi _eklentileri (add-ons)_ seçebilmesini ve belirli sayıda misafir için yemekleri seçebilmesini içerir.

**BudgetEase konferans gider planlayıcısının** özellikleri şunları içerecektir:

- Kullanıcı seçimlerine göre gerçek zamanlı güncellenen dinamik bir kullanıcı arayüzü
- Mekân seçimi, eklentiler ve yemek seçenekleri için bileşenler
- Durum değişikliklerini yönetmek için _Redux Toolkit_ kullanılarak _Redux_ entegrasyonu
- Farklı bölüm durumlarını yönetmek için _Redux slices_
- Seçilen öğeleri ve maliyetlerini açılır bir pencerele tablo ile gösterme
- Kullanıcı seçimlerine göre ara toplamları ve genel toplam maliyeti hesaplama ve gösterme

---

## 🎯 Öğrenme hedefleri

Bu laboratuvarı tamamladığınızda şunları yapabileceksiniz:

- **React bileşenleri oluşturma:** Bileşen birleştirme ve iç içe yerleştirme kullanarak fonksiyonel React bileşenleri oluşturma.
- **Hook’larla durum yönetimi:** Özellikle _useState_ ve _useEffect_ hook’larını uygulama. Hook’ları, bileşen düzeyi durumu yönetmek ve öğelerin görünürlüğünü kontrol etmek için kullanacaksınız.
- **Redux entegrasyonu:** Eylemler ( _actions_ ), azaltıcılar ( _reducers_ ) ve store gibi Redux kavramlarını kullanarak bir uygulamaya Redux entegre etme.
- **Dinamik veriyi render etme:** Nesne dizilerinden alınan verileri arayüzde dinamik olarak render etme. Bileşen listeleri üretmek için diziler üzerinde _map()_ ile dolaşacaksınız.
- **Koşullu render ile olay yönetimi:** Düğme seçimi gibi kullanıcı olaylarını yönetme ve karşılık gelen eylemleri tetikleme.

---

## 🧾 Proje görevleri

1. Proje ortamını kurun
2. _ConferenceEvent.jsx_ bileşeninin yapısını inceleyin
3. _Venue_ modülünün kodunu inceleyin
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

- Temel HTML ve CSS
- Orta düzey JavaScript
- React fonksiyon bileşenleri, hook’lar ve durum yönetimi için _Redux toolkit_ ile aşinalık
- GitHub kullanarak kod yönetimi

GitHub’da nasıl çalışılacağıyla ilgili yönlendirmeye ihtiyacınız olursa bu talimatları inceleyin.

---

## ⚠️ Bu laboratuvar ortamıyla ilgili önemli bildirim

_Skills Network Cloud IDE_ (Theia ve Docker tabanlı), kurs ve proje laboratuvarlarında uygulamalı çalışmalar için ortam sağlayan açık kaynaklı bir IDE’dir ( _Integrated Development Environment_ ).

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

- Conference room
  [https://pixabay.com/photos/chairs-empty-office-room-table-2181916/](https://pixabay.com/photos/chairs-empty-office-room-table-2181916/)
- Auditorium:
  [https://pixabay.com/photos/event-venue-auditorium-meeting-1597531/](https://pixabay.com/photos/event-venue-auditorium-meeting-1597531/)
- Presentation room:
  [https://pixabay.com/photos/convention-center-chair-seminar-3908238/](https://pixabay.com/photos/convention-center-chair-seminar-3908238/)
- Meeting room:
  [https://pixabay.com/photos/chairs-empty-office-room-table-2181916/](https://pixabay.com/photos/chairs-empty-office-room-table-2181916/)
- Small meeting room:
  [https://pixabay.com/photos/laptops-meeting-businessmen-593296/](https://pixabay.com/photos/laptops-meeting-businessmen-593296/)
- Projector:
  [https://pixabay.com/photos/business-computer-conference-20031/](https://pixabay.com/photos/business-computer-conference-20031/)
- Speakers:
  [https://pixabay.com/photos/speakers-bluetooth-tech-speaker-4109274/](https://pixabay.com/photos/speakers-bluetooth-tech-speaker-4109274/)
- Microphone:
  [https://pixabay.com/photos/public-speaking-mic-microphone-3926344/](https://pixabay.com/photos/public-speaking-mic-microphone-3926344/)
- Whiteboard:
  [https://pixabay.com/photos/whiteboard-dry-erase-marker-blank-2903269/](https://pixabay.com/photos/whiteboard-dry-erase-marker-blank-2903269/)
- Signs:
  [https://pixabay.com/photos/signpost-waypoint-wood-grain-board-235079/](https://pixabay.com/photos/signpost-waypoint-wood-grain-board-235079/)

## 📁 5. Terminal yolunu değiştirin

Terminal yolunuzu aşağıdaki komutla **conference_event_planner** klasörüne değiştirin.

```bash
cd conference_event_planner
```

## ✅ 6. Klonladığınız kodun doğru çalıştığından emin olun

Uygulamayı çalıştırmak için gerekli paketleri _npm_ ile yükleyin.

```bash
npm install
```

Uygulamayı çalıştırmak için aşağıdaki komutu yürütün. Bu komut, 4173 port numarası üzerinde uygulama sunucusunu başlatır.

```bash
npm run preview
```

## 🌐 7. Uygulamayı görüntüleyin

Şimdi uygulamayı görüntüleyebilirsiniz.

Sol paneldeki _Skills Network_ simgesine tıklayın (1 numaraya bakın). Bu işlem _Skills Network Toolbox_ ’ı açacaktır. Ardından **Launch Application** ’a tıklayın (2 numaraya bakın). **Application Port** alanına **4173** port numarasını girin (3 numaraya bakın) ve **[↗]** simgesine tıklayın.

## 🧭 8. Beklenen çıktı

Çıktı aşağıdaki ekran görüntüsüne benzer olmalıdır. **Get Started** düğmesine tıklamak, kullanıcıyı ürün seçimi sayfasına götürmelidir. Üst bilgi ve ilk bölüm **“Room selection”** görünmelidir.

> _Not:_ Size _backgroundImage_ yerine _backgroundColor_ sağlanmıştır. Renk yerine görsel tercih ediyorsanız, kendi görselinizi ekleyebilirsiniz. Verilen kodla uygulama ürün sayfası aşağıdakine benzer görünmelidir.

## 🔄 9. Değişiklik yaptıysanız push edin

Herhangi bir değişiklik yaparsanız **git add** ve **git commit** çalıştırın. Ardından, commit edilen değişiklikleri uzak GitHub deponuza yüklemek için **git push** komutunu çalıştırın ve kodunuzun en son sürümünü kaydettiğinizden emin olun.

> _Not:_ Kodu GitHub deponuza push ederken kullanıcı adı ve parola girmeniz istenebilir. GitHub’da nasıl çalışılacağıyla ilgili daha fazla yönlendirme gerekiyorsa ilgili talimatları inceleyin.

---

# 🧩 Görev 2: ConferenceEvent.jsx yapısını gözden geçirin

İki çalışan modülünüz vardır:

- Başlamak için bir düğme ve şirket açıklaması içeren açılış sayfası
- Mekândaki oda seçimini ve artırma/azaltma düğmelerini içeren **“venue section”**

**src** dizinindeki **ConferenceEvent.jsx** dosyasını açın. Bu bileşen ürün seçimi sayfası için fonksiyonları ve yerleşimleri içerir.

## 🧱 Yerleşimler

- Bir _navbar_ öğesi
- `<div>` etiketi içinde **main_container** sınıfı
- Koşullu operatör `? :` kullanarak işlevi aç/kapat eden bir **showItems** değişkeni
- `<div>` etiketi içinde **items-information** sınıfı
- Mekân, eklentiler ve yemekler için `<div>` etiketlerinde yerleşimler. Bu yerleşimlerin her birinde iki ortak sınıf adı bulunur: **venue_container** ve **container_main**
- Seçilen öğelerin ayrıntılarını göstermek için `<div>` içinde **total_amount_detail** sınıfı

---
