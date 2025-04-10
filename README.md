# JavaScript BOM va DOM haqida ma'lumot

JavaScript veb-dasturlashda juda muhim o'rin tutadi, va bu tilning eng kuchli tomonlaridan biri - HTML sahifalari bilan o'zaro aloqa qilish imkoniyatidir. Bu o'zaro aloqa DOM (Document Object Model) va BOM (Browser Object Model) orqali amalga oshiriladi. Keling, bu ikki tushunchani chuqurroq o'rganib chiqamiz.

#### DOM - Document Object Model (Hujjat Obyekt Modeli) <a href="#dom-document-object-model-hujjat-obyekt-modeli" id="dom-document-object-model-hujjat-obyekt-modeli"></a>

DOM - bu HTML yoki XML hujjatlarning struktura va mazmunini obyektlar ko'rinishida tasvirlash usulidir. DOM HTML sahifani daraxt shaklida tasvirlaydi, bu daraxtning har bir tugun (node) alohida element hisoblanadi. Bu JavaScript dasturchilariga HTML tarkibini dinamik ravishda o'qish, yaratish va o'zgartirish imkoniyatini beradi.

**DOM-ning asosiy vazifalari:**

1.  **HTML elementlarini tanlash va ularga murojaat qilish:**

    Copy

    ```
    javascriptCopy// ID bo'yicha
    let element = document.getElementById("elementId");

    // CSS selektori bo'yicha
    let element = document.querySelector(".class-name");

    // Barcha mos elementlarni tanlash
    let elementlar = document.querySelectorAll("div.container");
    ```
2.  **HTML elementlarini yaratish va o'chirish:**

    Copy

    ```
    javascriptCopy// Yangi element yaratish
    let yangiElement = document.createElement("div");

    // Unga matn qo'shish
    yangiElement.textContent = "Salom, dunyo!";

    // Sahifaga qo'shish
    document.body.appendChild(yangiElement);

    // Elementni o'chirish
    yangiElement.remove();
    ```
3.  **Elementlarning mazmunini o'zgartirish:**

    Copy

    ```
    javascriptCopy// innerHTML orqali HTML struktura bilan ishlash
    element.innerHTML = "<strong>Qalin matn</strong>";

    // textContent orqali faqat matn bilan ishlash
    element.textContent = "Oddiy matn";
    ```
4.  **Stillarni o'zgartirish:**

    Copy

    ```
    javascriptCopyelement.style.color = "red";
    element.style.fontSize = "18px";
    element.classList.add("aktiv");
    ```
5.  **Hodisalarni boshqarish (Event handling):**

    Copy

    ```
    javascriptCopyelement.addEventListener("click", function() {
        alert("Element bosildi!");
    });
    ```

#### BOM - Browser Object Model (Brauzer Obyekt Modeli) <a href="#bom-browser-object-model-brauzer-obyekt-modeli" id="bom-browser-object-model-brauzer-obyekt-modeli"></a>

BOM - bu JavaScript dasturchilariga brauzerning o'zi bilan ishlash imkoniyatini beruvchi obyektlar to'plami. BOM yordamida brauzer oynasini boshqarish, ogohlantirish (alert) oynalarini ko'rsatish, brauzer tarixi bilan ishlash va boshqa ko'plab amallarni bajarish mumkin.

**BOM-ning asosiy komponentlari:**

1.  **Window obyekti** - BOMning eng yuqori darajadagi obyekti:

    Copy

    ```
    javascriptCopy// Ogohlantirish ko'rsatish
    window.alert("Muhim xabar!");

    // Yangi oyna ochish
    let yangiOyna = window.open("https://example.com");

    // Belgilangan vaqtdan so'ng kod bajarish
    window.setTimeout(() => {
        console.log("3 soniyadan keyin bajarildi");
    }, 3000);
    ```
2.  **Location obyekti** - joriy URL manzil bilan ishlash:

    Copy

    ```
    javascriptCopy// Joriy URL ko'rish
    console.log(window.location.href);

    // Boshqa sahifaga o'tish
    window.location.href = "https://google.com";

    // Sahifani qayta yuklash
    window.location.reload();
    ```
3.  **Navigator obyekti** - brauzer va tizim haqidagi ma'lumotlar:

    Copy

    ```
    javascriptCopy// Brauzer haqida ma'lumot
    console.log(navigator.userAgent);

    // Foydalanuvchi tili
    console.log(navigator.language);

    // Online/offline holati
    console.log(navigator.onLine);
    ```
4.  **History obyekti** - brauzer tarix bilan ishlash:

    Copy

    ```
    javascriptCopy// Oldingi sahifaga qaytish
    history.back();

    // Keyingi sahifaga o'tish
    history.forward();

    // Belgilangan sahifaga o'tish
    history.go(-2); // 2 sahifa orqaga
    ```
5.  **Screen obyekti** - foydalanuvchi ekrani ma'lumotlari:

    Copy

    ```
    javascriptCopy// Ekran o'lchamlari
    console.log(screen.width, screen.height);

    // Mavjud maydon o'lchamlari
    console.log(screen.availWidth, screen.availHeight);
    ```
6.  **LocalStorage va SessionStorage** - ma'lumotlarni brauzerda saqlash:

    Copy

    ```
    javascriptCopy// Ma'lumot saqlash
    localStorage.setItem("username", "Ali");

    // Ma'lumotni o'qish
    let foydalanuvchi = localStorage.getItem("username");
    ```

#### DOM va BOM farqlari <a href="#dom-va-bom-farqlari" id="dom-va-bom-farqlari"></a>

![](https://2863235780-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FvnyLauddPbIpj2quXHr1%2Fuploads%2FEr1Oc4u9zC6zKsKU2tkZ%2Fdom.svg?alt=media\&token=987b6fe4-7720-4be3-9729-708ee5a0b172)Copy

```
```

JavaScript DOM va BOM VizualizatsiyasiImage

#### DOM va BOM: amaliy foydalanish <a href="#dom-va-bom-amaliy-foydalanish" id="dom-va-bom-amaliy-foydalanish"></a>

**DOM bilan ishlashga misol**

Tasavvur qiling, veb-sahifada foydalanuvchi kiritgan ma'lumotlarni tekshirib, ro'yxatga qo'shish kerak:

Copy

```
javascriptCopy// HTML elementi:
// <input id="yangiVazifa" placeholder="Yangi vazifa">
// <button id="qoshishTugmasi">Qo'shish</button>
// <ul id="vazifalarRoyxati"></ul>

// Elementlarni tanlash
const kiritishMaydoni = document.getElementById("yangiVazifa");
const qoshishTugmasi = document.getElementById("qoshishTugmasi");
const royxat = document.getElementById("vazifalarRoyxati");

// Tugma bosilganda yangi vazifa qo'shish
qoshishTugmasi.addEventListener("click", function() {
    // Kiritilgan qiymatni olish
    const vazifaMatni = kiritishMaydoni.value.trim();
    
    if (vazifaMatni) {
        // Yangi ro'yxat elementi yaratish
        const yangiElement = document.createElement("li");
        yangiElement.textContent = vazifaMatni;
        
        // Yangi elementga klass qo'shish
        yangiElement.classList.add("vazifa-element");
        
        // Ro'yxatga qo'shish
        royxat.appendChild(yangiElement);
        
        // Kiritish maydonini tozalash
        kiritishMaydoni.value = "";
    }
});
```

**BOM bilan ishlashga misol**

Foydalanuvchining brauzer sozlamalari va holati bilan ishlash:

Copy

```
javascriptCopy// Ekran o'lchamlariga qarab turli stillarni qo'llash
function ekranOlchaminiTekshirish() {
    const kenglik = window.innerWidth;
    
    if (kenglik < 768) {
        document.body.classList.add("mobil");
        document.body.classList.remove("desktop");
    } else {
        document.body.classList.add("desktop");
        document.body.classList.remove("mobil");
    }
}

// Sahifa yuklanganida va ekran o'lchami o'zgarganida tekshirish
window.addEventListener("load", ekranOlchaminiTekshirish);
window.addEventListener("resize", ekranOlchaminiTekshirish);

// Foydalanuvchi online/offline holatini tekshirish
window.addEventListener("online", function() {
    document.getElementById("holatXabari").textContent = "Siz internetga ulandingiz!";
    document.getElementById("holatXabari").style.color = "green";
});

window.addEventListener("offline", function() {
    document.getElementById("holatXabari").textContent = "Internet aloqasi yo'q!";
    document.getElementById("holatXabari").style.color = "red";
});

// Foydalanuvchi ma'lumotlarini saqlash
function foydalanuvchiTiliniSaqlash(til) {
    localStorage.setItem("foydalanuvchiTili", til);
    alert("Til sozlamalari saqlandi!");
}

// Saqlangan ma'lumotlarni olish
function saqlashTiliniOlish() {
    return localStorage.getItem("foydalanuvchiTili") || "uz";
}
```

#### Amaliy foydalanish namunalari <a href="#amaliy-foydalanish-namunalari" id="amaliy-foydalanish-namunalari"></a>

DOM va BOM texnologiyalarini quyidagi hollarda qo'llash mumkin:

1. **Dinamik sahifa yaratish** - foydalanuvchi harakatlariga qarab sahifa mazmunini o'zgartirish
2. **Foydalanuvchi interfeysini yaxshilash** - animatsiyalar, ko'rinadigan/ko'rinmaydigan elementlar
3. **Formalarni validatsiya qilish** - foydalanuvchi kiritgan ma'lumotlarni tekshirish
4. **Lokal ma'lumotlarni saqlash** - foydalanuvchi sozlamalari, avvalgi harakatlarni eslab qolish
5. **Adaptiv dizayn** - turli qurilmalar uchun interfeys moslashtirish
6. **Single Page Application (SPA)** - sahifani qayta yuklamasdan dinamik tarkib yaratish

#### Xulosa <a href="#xulosa" id="xulosa"></a>

JavaScript DOM va BOM texnologiyalari veb-dasturlashda juda muhim o'rin tutadi. DOM HTML sahifalar tarkibini o'qish va o'zgartirish imkonini bersa, BOM brauzer funksiyalari bilan ishlash, foydalanuvchi sozlamalari va ma'lumotlarini boshqarish, qo'shimcha brauzer imkoniyatlaridan foydalanish imkonini beradi.

Yuqorida keltirilgan vizual sxema DOM va BOM tuzilishini yaqqol ko'rsatib beradi: DOM HTML hujjat strukturasi bilan ishlashga qaratilgan bo'lsa, BOM brauzer oynasi va uning funksiyalarini boshqarishga mo'ljallangan. Ikkala texnologiya ham JavaScript yordamida veb-sahifalarni interaktiv, dinamik va foydalanuvchi uchun qulay qilish imkonini beradi.
