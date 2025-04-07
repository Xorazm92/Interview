# JavaScript-da obyektlarini nusxalash

JavaScriptda nusxalash (copying) jarayoni

JavaScript dasturlash tilida obyektlar bilan ishlash davomida "nusxalash" masalasi katta ahamiyatga ega. Obyektlarni to'g'ri nusxalash dasturingiz ishlashida xatoliklarning oldini olishda muhim rol o'ynaydi.

![](https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F3412342686-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F31VGo1mVm4SttrEscGxg%252Fuploads%252FPlKk6NE6VYXBOi3VY8bh%252Fimage.png%3Falt%3Dmedia%26token%3Dc8043ee2-3607-4da4-a0ab-14ecdc719c87\&width=768\&dpr=4\&quality=100\&sign=e80aba98\&sv=2)

#### Muammo nima? <a href="#muammo-nima" id="muammo-nima"></a>

JavaScript-da obyektlar havola orqali uzatiladi, ya'ni ularga o'zgaruvchilar orqali murojaat qilganda, aslida siz obyektning o'ziga emas, balki uning xotiradagi manzili (reference) ga murojaat qilasiz. Bu esa ko'pincha kutilmagan natijalarga olib kelishi mumkin.

Copy

```
const person1 = { name: "Ali", age: 30 };
const person2 = person1;

person2.name = "Vali";
console.log(person1.name);  // "Vali" chiqadi, chunki ikkala o'zgaruvchi bir xil obyektga ishora qilmoqda
```

#### Nusxalash turlari <a href="#nusxalash-turlari" id="nusxalash-turlari"></a>

JavaScript-da obyektlarni nusxalashning ikki turi mavjud:

**1. Sayoz nusxalash (Shallow copy)**

Sayoz nusxalash faqat obyektning birinchi qavat xususiyatlarini nusxalaydi. Ichma-ich obyektlar esa havolasi orqali ko'chiriladi.

**Usullari:**

**Object.assign() metodi**

Copy

```
const asl = { name: "Ali", location: { city: "Toshkent" } };
const nusxa = Object.assign({}, asl);

nusxa.name = "Vali";  // Bu o'zgarish asliga ta'sir qilmaydi
nusxa.location.city = "Samarqand";  // Bu o'zgarish asliga ta'sir qiladi!

console.log(asl.location.city);  // "Samarqand" - chunki ichki obyekt havolasi orqali ko'chirilgan
```

**Spread operatori**

Copy

```
const asl = { name: "Ali", location: { city: "Toshkent" } };
const nusxa = { ...asl };

nusxa.name = "Vali";  // Bu o'zgarish asliga ta'sir qilmaydi
nusxa.location.city = "Samarqand";  // Bu o'zgarish asliga ta'sir qiladi!
```

**2. Chuqur nusxalash (Deep copy)**

Chuqur nusxalash obyektning barcha darajadagi xususiyatlarini rekursiv ravishda nusxalaydi va yangi obyekt yaratadi.

**Usullari:**

**JSON orqali**

Copy

```
const asl = { name: "Ali", location: { city: "Toshkent" } };
const nusxa = JSON.parse(JSON.stringify(asl));

nusxa.location.city = "Samarqand";  // Bu o'zgarish asliga ta'sir qilmaydi
console.log(asl.location.city);  // "Toshkent" - chunki chuqur nusxa olindi
```

Bu usul oddiy holatlar uchun yaxshi ishlasa-da, quyidagi cheklovlari bor:

* Funksiyalarni nusxalay olmaydi
* `Date` obyektlarini string sifatida saqlaydi
* `undefined` qiymatlarni yo'qotadi
* Siklik obyektlar (circular references) uchun xato beradi

**structuredClone() metodi**

Zamonaviy brauzerlarda mavjud bo'lgan yangi standart usul:

Copy

```
const asl = { name: "Ali", location: { city: "Toshkent" }, birthDate: new Date() };
const nusxa = structuredClone(asl);

nusxa.location.city = "Samarqand";  // Asl obyektga ta'sir qilmaydi
```

Bu usul quyidagi afzalliklarga ega:

* Date obyektlarini to'g'ri nusxalaydi
* ArrayBuffer va TypedArray kabi murakkab obyektlarni qo'llab-quvvatlaydi
* Siklik obyektlar bilan ham ishlaydi

Ammo funksiyalarni va DOM elementlarini nusxalay olmaydi.

**Lodash kutubxonasi**

Copy

```
const asl = { name: "Ali", location: { city: "Toshkent" } };
const nusxa = _.cloneDeep(asl);

nusxa.location.city = "Samarqand";  // Asl obyektga ta'sir qilmaydi
```

**Qo'lda rekursiv nusxalash**

Copy

```
function deepCopy(obj) {
  if (obj === null || typeof obj !== 'object') return obj;
  
  const copy = Array.isArray(obj) ? [] : {};
  
  for (const key in obj) {
    if (Object.prototype.hasOwnProperty.call(obj, key)) {
      copy[key] = deepCopy(obj[key]);
    }
  }
  
  return copy;
}

const asl = { name: "Ali", location: { city: "Toshkent" } };
const nusxa = deepCopy(asl);
```

#### Qaysi usulni qachon qo'llash kerak? <a href="#qaysi-usulni-qachon-qollash-kerak" id="qaysi-usulni-qachon-qollash-kerak"></a>

* **Sayoz nusxalash** - ichki obyektlar bo'lmagan yoki ichki obyektlarni havola orqali ulashish kerak bo'lgan hollarda
* **Chuqur nusxalash** - to'liq mustaqil obyekt kerak bo'lgan va asl obyektni o'zgartirmaslik zarur bo'lgan hollarda

#### Xulosa <a href="#xulosa" id="xulosa"></a>

JavaScript-da obyektlarni nusxalash jarayonini tushunish, dasturlash davomida yuzaga kelishi mumkin bo'lgan ko'plab muammolarning oldini oladi. Har bir loyiha talabiga ko'ra, eng mos nusxalash usulini tanlash muhimdir.

Murakkab obyektlar va kutilmagan xatoliklarni oldini olish uchun `structuredClone()` yoki Lodash kutubxonasining `_.cloneDeep()` metodlaridan foydalanish tavsiya etiladi.
