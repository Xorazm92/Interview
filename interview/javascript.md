---
description: interview
---

# JavaScript

#### 1. JavaScript qanday ishlaydi?

**Javob:** JavaScript — veb-sahifalarni jonli qiladigan dasturlash tili. U brauzerda ishlaydi va kodni qator-qator o‘qib, bajaradi. Masalan, tugmani bosganingizda biror narsa yuz bersin desangiz, JavaScript shu ishni qiladi. Uning “mexanizmi” (engine) V8 deb ataladi (Google Chrome’da).\
**Tasavvur:** JavaScriptni “ish yurituvchi” deb tasavvur qiling — brauzerga buyruq beradi.\
**Misol:**

```javascript
alert("Salom!"); // Ekranga xabar chiqaradi
2. LocalStorage, SessionStorage va Cookie o‘rtasidagi farq nima?

Javob:

    LocalStorage: Ma’lumot uzoq vaqt saqlanadi, brauzer yopilsa ham o‘chmaydi.
    SessionStorage: Faqat brauzer oynasi ochiq turganda saqlanadi, yopilsa o‘chadi.
    Cookie: Kichik ma’lumotlar serverga yuboriladi, muddati bo‘lishi mumkin.
    Tasavvur: LocalStorage — “doimiy kundalik”, SessionStorage — “bir kunlik qog‘ozcha”, Cookie — “tashrif qog‘ozi”.
    Misol:

javascript
localStorage.setItem("ism", "Ali"); // Doimiy
sessionStorage.setItem("vaqt", "10:00"); // Vaqtinchalik
document.cookie = "rang=kuk"; // Cookie
3. Callback nima?

Javob: Callback — bir funksiyani boshqa funksiyaga “keyin bajar” deb topshirish. Agar ish uzoq vaqt olsa, JavaScript kutmaydi, keyin callback ishga tushadi.

Tasavvur: “Telefon qo‘ng‘irog‘i” — “ma’lumot kelganda menga qo‘ng‘iroq qil”.

Misol:
javascript
setTimeout(function() { console.log("Salom!"); }, 2000); // 2 soniyadan keyin
4. Prototypal merosxo‘rlik nima?

Javob: JavaScriptda ob’ektlar bir-biridan xususiyatlarni “meros” qilib oladi. Har bir ob’ektning “prototipi” (ota-onasi) bor, undan xususiyatlarni oladi.

Tasavvur: “Ota-bobolar kitobi” — o‘zingda bo‘lmasa, otangdan qidirasan.

Misol:
javascript
let hayvon = { ovqatlanadi: true };
let mushuk = Object.create(hayvon);
console.log(mushuk.ovqatlanadi); // true
5. Prototypal merosxo‘rlik va sinfga asoslangan merosxo‘rlik farqi?

Javob:

    Prototypal: Ob’ektlar to‘g‘ridan-to‘g‘ri meros oladi (JavaScript).
    Sinfga asoslangan: Sinflar (qoliplar) yaratiladi (Java).
    Tasavvur: Prototyp — “ota-bobodan nusxa”, Sinf — “qolipdan yasash”.
    Misol:

javascript
let ota = { salom: "Assalom" };
let bola = Object.create(ota);

class Ota { salom() { return "Assalom"; } }
let bola2 = new Ota();
6. JavaScriptda xotira boshqaruvi qanday?

Javob: JavaScript o‘zgaruvchilar uchun xotirada joy ajratadi, keraksiz narsalarni “axlat yig‘uvchi” (Garbage Collector) o‘chiradi. Xotira: Stack (kichik) va Heap (katta).

Tasavvur: Xotira — “shkaf”, kichik kiyimlar bir chetida, katta sumkalar boshqa chetida.

Misol:
javascript
let a = 5; // Stack
let b = { ism: "Ali" }; // Heap
b = null; // Axlat yig‘uvchi o‘chiradi
7. Event Loop nima?

Javob: Event Loop — JavaScriptning “ish boshqaruvchisi”. Kodni birma-bir bajaradi, uzoq ishni navbatga qo‘yadi.

Tasavvur: “Restoran ofitsianti” — buyurtmalarni navbat bilan olib keladi.

Misol:
javascript
console.log("Boshladim");
setTimeout(() => console.log("Keyin"), 1000);
console.log("Tugadim"); // Boshladim -> Tugadim -> Keyin
8. Let, Const va Var o‘rtasidagi farq nima?

Javob:

    Var: Eski, funksiya yoki global, hoisting bor.
    Let: Yangi, blok ichida, qayta qiymat mumkin.
    Const: Doimiy, blok ichida, qiymati o‘zgarmaydi.
    Tasavvur: Var — “hamma joyda ko‘rinadigan do‘st”, Let — “o‘z xonasida”, Const — “o‘zgarmas qoida”.
    Misol:

javascript
var x = 1;
let y = 2;
const z = 3;
9. Oddiy funksiya va strelka funksiyasi farqi?

Javob:

    Oddiy: O‘z “this”iga ega.
    Strelka: “this”ni tashqaridan oladi, qisqa yoziladi.
    Tasavvur: Oddiy — “o‘z uyida yashovchi”, Strelka — “qoidaga rioya qiluvchi”.
    Misol:

javascript
function salom() { console.log("Salom"); }
const strelka = () => console.log("Salom");
10. ES6 sinfi va ES5 funksiya konstruktorlari farqi?

Javob:

    ES5: Funksiya bilan, metodlar prototipga qo‘shiladi.
    ES6: class bilan, hamma bir joyda.
    Tasavvur: ES5 — “qadoqlash qutisi”, ES6 — “tayyor shablon”.
    Misol:

javascript
function Mashina(rang) { this.rang = rang; }
Mashina.prototype.yur = function() { console.log("Vroom"); };

class Mashina2 {
  constructor(rang) { this.rang = rang; }
  yur() { console.log("Vroom"); }
}
11. JavaScriptda ob’ektlarni nusxalash usullari?

Javob:

    Spread (...): Oddiy nusxa.
    Object.assign: Yuzaki nusxa.
    JSON.parse: Chuqur nusxa, lekin funksiyalarni o‘tkazmaydi.
    Tasavvur: Spread — “tez nusxa”, Assign — “yuzaki”, JSON — “to‘liq”.
    Misol:

javascript
let asl = { ism: "Ali" };
let nusxa1 = { ...asl };
let nusxa2 = Object.assign({}, asl);
let nusxa3 = JSON.parse(JSON.stringify(asl));
12. Ob’ekt va Map farqi?

Javob:

    Ob’ekt: Kalitlar matn yoki symbol, tartibsiz.
    Map: Kalit har qanday (ob’ekt, funksiya), tartibli.
    Tasavvur: Ob’ekt — “oddiy quti”, Map — “tartibli sandiq”.
    Misol:

javascript
let obj = { ism: "Ali" };
let map = new Map();
map.set("ism", "Ali");
13. Symbol nima?

Javob: Symbol — har doim noyob qiymat, ob’ekt kaliti sifatida ishlatiladi.

Tasavvur: “Maxfiy kalit”.

Misol:
javascript
let kalit = Symbol("id");
let obj = { [kalit]: 1 };
console.log(obj[kalit]); // 1
14. Doira va leksik muhit nima?

Javob:

    Doira (Scope): O‘zgaruvchi qayerda ishlaydi.
    Leksik muhit: O‘zgaruvchilar saqlanadigan “xotira joyi”.
    Tasavvur: Doira — “qayerda yashaysan”, Leksik muhit — “nimalaring bor”.
    Misol:

javascript
let x = 1; // Global doira
function salom() { let y = 2; } // Funksiya doirasi
15. “this” kalit so‘zi nima qiladi?

Javob: “this” hozirgi funksiya qaysi ob’ekt bilan ishlayotganini ko‘rsatadi. Qanday chaqirilganiga qarab o‘zgaradi.

Tasavvur: “Hozir men kimmiman?” deb so‘raydigan do‘st.

Misol:
javascript
let odam = {
  ism: "Ali",
  salom: function() { console.log("Salom, " + this.ism); }
};
odam.salom(); // "Salom, Ali"
16. IIFE (Immediately Invoked Function Expression) nima?

Javob: Darhol ishlaydigan funksiya, maxfiylik uchun ishlatiladi.

Tasavvur: “Bir marta ishlatib, unutib qo‘yadigan qog‘oz”.

Misol:
javascript
(function() {
  let sir = "Maxfiy";
  console.log(sir); // "Maxfiy"
})();
17. Promise va Async funksiyasi o‘rtasidagi farq?

Javob:

    Promise: Asinxron ishni boshqarish uchun ob’ekt.
    Async: Promise’ni osonlashtiradi, await bilan ishlaydi.
    Tasavvur: Promise — “va’da”, Async — “va’dani oson bajaruvchi”.
    Misol:

javascript
let vaada = new Promise((resolve) => resolve("Tayyor"));
async function bajar() { console.log(await vaada); }
18. JavaScriptda ob’ektlarni qanday yaratish mumkin?

Javob:

    Oddiy usul: {}.
    Konstruktor: new Object().
    Class: class.
    Tasavvur: “Sumka” — turli usulda yasash mumkin.
    Misol:

javascript
let oddiy = { ism: "Ali" };
let konstruktor = new Object(); konstruktor.ism = "Ali";
class Od { constructor(ism) { this.ism = ism; } }
let sinf = new Od("Ali");
19. Prototip zanjiri nima?

Javob: Ob’ektlarning bir-biridan xususiyatlarni meros qilib olish tartibi.

Tasavvur: “Oilaviy daraxt” — otadan qidiradi.

Misol:
javascript
let hayvon = { ovqatlanadi: true };
let mushuk = Object.create(hayvon);
console.log(mushuk.ovqatlanadi); // true
20. Call, Apply va Bind o‘rtasidagi farq?

Javob:

    Call: Darhol chaqiradi, argumentlar birma-bir.
    Apply: Darhol chaqiradi, argumentlar massivda.
    Bind: Yangi funksiya qaytaradi, “this”ni bog‘laydi.
    Tasavvur: Call — “hoziroq chaqir”, Apply — “massiv bilan”, Bind — “keyin tayyorla”.
    Misol:

javascript
let odam = { ism: "Ali" };
function salom(a) { console.log(a + " " + this.ism); }
salom.call(odam, "Salom"); // "Salom Ali"
salom.apply(odam, ["Assalom"]); // "Assalom Ali"
let yangi = salom.bind(odam, "Hola"); yangi(); // "Hola Ali"
21. Slice va Splice o‘rtasidagi farq?

Javob:

    Slice: Massivdan qism oladi, aslni o‘zgartirmaydi.
    Splice: Massivdan qismni o‘chiradi yoki qo‘shadi, aslni o‘zgartiradi.
    Tasavvur: Slice — “nusxa kesib olish”, Splice — “kesib o‘zgartirish”.
    Misol:

javascript
let arr = [1, 2, 3, 4];
console.log(arr.slice(1, 3)); // [2, 3]
arr.splice(1, 2, 5); // arr = [1, 5, 4]
22. Lambda yoki strelka funksiyalari nima?

Javob: Qisqa yozilgan funksiya, “this”ni tashqaridan oladi.

Tasavvur: “Qisqa xat”.

Misol:
javascript
let qosh = (a, b) => a + b;
console.log(qosh(2, 3)); // 5
23. Birinchi darajali funksiya nima?

Javob: Funksiyalar o‘zgaruvchi kabi ishlatilishi mumkin — beriladi, qaytariladi yoki saqlanadi.

Tasavvur: “Odam” — yuborish, qaytarish mumkin.

Misol:
javascript
let salom = function() { console.log("Salom"); };
salom(); // "Salom"
24. Birinchi tartibli funksiya nima?

Javob: Boshqa funksiyani argument sifatida olmaydi va qaytarmaydi.

Tasavvur: “Oddiy ishchi” — faqat o‘z ishini qiladi.

Misol:
javascript
function qosh(a, b) { return a + b; }
25. Yuqori tartibli funksiya nima?

Javob: Boshqa funksiyani oladi yoki qaytaradi.

Tasavvur: “Usta” — boshqalarni boshqaradi.

Misol:
javascript
function kopaytir(n) {
  return function(x) { return x * n; };
}
let ikkiga = kopaytir(2);
console.log(ikkiga(5)); // 10
26. Unary funksiya nima?

Javob: Bitta argument oladigan funksiya.

Tasavvur: “Yolg‘iz ishchi”.

Misol:
javascript
let kvadrat = (x) => x * x;
console.log(kvadrat(3)); // 9
27. Currying funksiyasi nima?

Javob: Ko‘p argumentli funksiyani bir nechta bitta argumentli funksiyaga aylantirish.

Tasavvur: “Bo‘lib-bo‘lib ishlatish” — piyola ovqatni qoshiq-qoshiq yeyish.

Misol:
javascript
function curry(a) {
  return function(b) { return a + b; };
}
let qosh5 = curry(5);
console.log(qosh5(3)); // 8
28. Sof funksiya (Pure Function) nima?

Javob: Bir xil kirish uchun bir xil chiqish beradi, tashqi holatni o‘zgartirmaydi.

Tasavvur: “Halol kalkulyator” — faqat hisoblaydi.

Misol:
javascript
function qosh(a, b) { return a + b; } // Sof
29. Temporal Dead Zone (Vaqtinchalik o‘lik zona) nima?

Javob: let va const o‘zgaruvchilar e’lon qilinmaguncha ishlatib bo‘lmaydigan vaqt oralig‘i.

Tasavvur: “Yopiq eshik” — qiymat bermaguningizcha kirib bo‘lmaydi.

Misol:
javascript
console.log(a); // Xato
let a = 5;
30. Memoization nima?

Javob: Funksiyaning oldingi natijalarini eslab qolish, qayta hisoblamaslik.

Tasavvur: “Eslatma daftari” — bir marta hisoblasangiz, qarab olasiz.

Misol:
javascript
let cache = {};
function memo(a) {
  if (cache[a]) return cache[a];
  cache[a] = a * 2;
  return cache[a];
}
console.log(memo(5)); // 10
31. Hoisting nima?

Javob: O‘zgaruvchilar va funksiyalar kod boshiga “ko‘tariladi”. var undefined bilan, let va const TDZ bilan.

Tasavvur: “Yuqoriga ko‘tarilgan lift”.

Misol:
javascript
console.log(x); // undefined
var x = 5;

console.log(y); // Xato
let y = 10;
32. ES6 da sinflar nima?

Javob: Ob’ektlar yaratish uchun qulay shablon.

Tasavvur: “Tayyor qolip”.

Misol:
javascript
class Mashina {
  constructor(rang) { this.rang = rang; }
  yur() { console.log("Vroom"); }
}
let m = new Mashina("qizil");
m.yur(); // "Vroom"
33. Yopilmalar (Closures) nima?

Javob: Ichki funksiya tashqi funksiyadagi o‘zgaruvchilarni eslab qoladi.

Tasavvur: “Xotira qutisi”.

Misol:
javascript
function tashqi() {
  let x = 5;
  return function ichki() { console.log(x); };
}
let f = tashqi();
f(); // 5
34. Modullar nima?

Javob: Kodni kichik, qayta ishlatiladigan qismlarga bo‘lish.

Tasavvur: “Lego qismi”.

Misol:
javascript
// modul.js
export function salom() { console.log("Salom"); }
// main.js
import { salom } from './modul.js';
salom(); // "Salom"
35. Promise nima?

Javob: Asinxron ishni boshqarish uchun ob’ekt, 3 holat: pending, fulfilled, rejected.

Tasavvur: “Va’da”.

Misol:
javascript
let p = new Promise((resolve) => setTimeout(() => resolve("Tayyor"), 1000));
p.then((x) => console.log(x)); // "Tayyor"
36. Nega Promise kerak?

Javob: Asinxron kodni tartibli va oson boshqarish uchun, callback hell’dan qutqaradi.

Tasavvur: “Navbatchi”.

Misol:
javascript
fetch("https://api.example.com")
  .then((data) => console.log(data));
37. Promise’ning uch holati nima?

Javob:

    Pending: Kutilmoqda.
    Fulfilled: Bajarildi.
    Rejected: Xato.
    Tasavvur: “Kutyapman, Tayyor, Xato”.
    Misol:

javascript
let p = new Promise((resolve, reject) => {
  if (true) resolve("OK");
  else reject("Xato");
});
38. Nega callback kerak?

Javob: JavaScript hodisalarga asoslangan, “tugasa, buni qil” deb aytadi.

Tasavvur: “Keyin qo‘ng‘iroq qil”.

Misol:
javascript
setTimeout(() => console.log("Tugadi"), 1000);
39. Callback hell nima?

Javob: Ichma-ich ko‘p callback’lar tufayli kod chalkash bo‘lishi.

Tasavvur: “Chigal yo‘l”.

Misol:
javascript
setTimeout(() => {
  console.log("1");
  setTimeout(() => console.log("2"), 1000);
}, 1000);
40. Promise qoidalari nima?

Javob: .then() bo‘lishi kerak, holati bir marta o‘zgaradi.

Tasavvur: “Qat’iy shartnoma”.

Misol:
javascript
let p = new Promise((res) => res("Tayyor"));
p.then((x) => console.log(x)); // "Tayyor"
41. Callback ichida callback nima?

Javob: Bir callback’ni boshqasiga qo‘yish, ketma-ket bajarish uchun.

Tasavvur: “Telefon orqali navbat”.

Misol:
javascript
setTimeout(() => {
  console.log("1-bosqich");
  setTimeout(() => console.log("2-bosqich"), 1000);
}, 1000);
42. Promise chaining nima?

Javob: .then() larni zanjir qilib, ketma-ket bajarish.

Tasavvur: “Domino effekt”.

Misol:
javascript
let p = new Promise((res) => res(1));
p.then((n) => n + 1)
 .then((n) => n * 2)
 .then((n) => console.log(n)); // 4
43. Promise.all nima?

Javob: Bir nechta promise’lar bajarilganda natija qaytaradi.

Tasavvur: “Hamma tayyor bo‘lsin”.

Misol:
javascript
let p1 = Promise.resolve("Bir");
let p2 = Promise.resolve("Ikki");
Promise.all([p1, p2]).then((natija) => console.log(natija)); // ["Bir", "Ikki"]
44. Promise.race nima?

Javob: Birinchisi bajarilgan promise’ni qaytaradi.

Tasavvur: “Poyga”.

Misol:
javascript
let p1 = new Promise((res) => setTimeout(() => res("Tez"), 500));
let p2 = new Promise((res) => setTimeout(() => res("Sekin"), 1000));
Promise.race([p1, p2]).then((natija) => console.log(natija)); // "Tez"
45. Strict mode nima?

Javob: "use strict" bilan qattiq qoidalar yoqiladi, xatolarni oldini oladi.

Tasavvur: “Qattiq ustoz”.

Misol:
javascript
"use strict";
x = 5; // Xato
let x = 5; // To‘g‘ri
46. Undefined nima?

Javob: O‘zgaruvchi e’lon qilingan, lekin qiymati yo‘q.

Tasavvur: “Bo‘sh quti”.

Misol:
javascript
let a;
console.log(a); // undefined
47. Null nima?

Javob: Atayin “hech narsa yo‘q” deb belgilangan.

Tasavvur: “Bo‘sh joy”.

Misol:
javascript
let a = null;
console.log(a); // null
48. Null va Undefined farqi nima?

Javob:

    undefined — avtomatik qiymatsiz holat.
    null — atayin bo‘sh qilingan.
    Tasavvur: Undefined — “unutib qo‘yilgan”, Null — “qasddan tozalangan”.
    Misol:

javascript
let x; // undefined
let y = null; // null
49. Window va Document farqi nima?

Javob:

    Window: Brauzer oynasi (hamma narsani o‘z ichiga oladi).
    Document: Sahifa mazmuni (HTML elementlari).
    Tasavvur: Window — “uy”, Document — “uyning ichidagi mebel”.
    Misol:

javascript
console.log(window); // Brauzer oynasi
console.log(document); // Sahifa mazmuni
50. E’lonsiz va undefined o‘zgaruvchilar farqi?

Javob:

    E’lonsiz: Hech qachon e’lon qilinmagan — xato.
    Undefined: E’lon qilingan, lekin qiymatsiz.
    Tasavvur: E’lonsiz — “noma’lum odam”, Undefined — “ism bilaman, ma’lumot yo‘q”.
    Misol:

javascript
console.log(a); // Xato
let b; console.log(b); // undefined
51. Global o‘zgaruvchilar nima?

Javob: Hamma joyda ishlaydigan o‘zgaruvchilar, var bilan yoki hechsiz e’lon qilinadi.

Tasavvur: “Hamma biladigan yangilik”.

Misol:
javascript
var x = 5;
console.log(window.x); // 5
52. Global o‘zgaruvchilarning muammolari?

Javob: Nomlar chalkashligi, kodni sinash qiyinlashadi.

Tasavvur: “Hamma kiradigan xona” — tartibsizlik.

Misol:
javascript
var x = 5;
function test() { x = 10; }
test();
console.log(x); // 10
53. Native, Host va User ob’ektlari farqi?

Javob:

    Native: JS o‘z ob’ektlari (Array).
    Host: Brauzerdan kelgan (window).
    User: Dasturchi yaratgan.
    Tasavvur: Native — “til qoidalari”, Host — “uy egasi”, User — “o‘z qo‘ling bilan”.
    Misol:

javascript
let arr = []; // Native
console.log(window); // Host
let odam = { ism: "Ali" }; // User
54. JavaScript kodini debug qilish usullari?

Javob:

    Chrome DevTools (F12).
    debugger — kodni to‘xtatadi.
    console.log — qiymatlarni ko‘rish.
    Tasavvur: “Kod detektivi”.
    Misol:

javascript
let x = 5;
console.log(x); // 5
debugger;
x = 10;
55. Promise va Callback’larning afzalliklari va kamchiliklari?

Javob:

    Promise: Callback hell’dan qutqaradi, lekin murakkab.
    Callback: Oddiy, lekin chalkashishi mumkin.
    Tasavvur: Promise — “tartibli navbat”, Callback — “tez, lekin chalkash”.
    Misol:

javascript
setTimeout(() => console.log("Callback"), 1000);
new Promise((res) => setTimeout(() => res("Promise"), 1000)).then(console.log);
56. JavaScript kompilyatsiya qilinadimi yoki interpretatsiya qilinadimi?

Javob: Interpretatsiya qilinadi, lekin JIT bilan qisman kompilyatsiya ham bor.

Tasavvur: “Tarjimon” — oldindan tayyorlaydi.
57. Global execution context nima?

Javob: Kod birinchi ishga tushganda yaratiladigan asosiy muhit.

Tasavvur: “Asosiy sahna”.

Misol:
javascript
console.log("Global");
58. Function execution context nima?

Javob: Har bir funksiya chaqirilganda yaratiladigan muhit.

Tasavvur: “Funksiya xonasi”.

Misol:
javascript
function salom() { let x = 5; console.log(x); }
salom();
59. Pass by value va pass by reference farqi?

Javob:

    Value: Nusxa beriladi, asl o‘zgarmaydi.
    Reference: Manzil beriladi, asl o‘zgaradi.
    Tasavvur: Value — “nusxa hujjat”, Reference — “asl hujjat”.
    Misol:

javascript
let a = 5;
let b = a;
b = 10;
console.log(a); // 5

let obj = { x: 5 };
let obj2 = obj;
obj2.x = 10;
console.log(obj.x); // 10
60. Primitive va non-primitive farqi?

Javob:

    Primitive: Oddiy tiplar (son, matn).
    Non-primitive: Ob’ektlar (massiv, funksiya).
    Tasavvur: Primitive — “oddiy odam”, Non-primitive — “ko‘p narsasi bor”.
    Misol:

javascript
let a = 5; // Primitive
let b = { x: 5 }; // Non-primitive
61. BOM nima?

Javob: Browser Object Model — brauzer bilan ishlash uchun ob’ektlar.

Tasavvur: “Brauzer boshqaruvchisi”.

Misol:
javascript
console.log(window.location);
62. BOM va DOM farqi?

Javob:

    BOM: Brauzer bilan ishlaydi.
    DOM: Sahifa mazmuni bilan.
    Tasavvur: BOM — “uy tashqarisi”, DOM — “uy ichi”.
    Misol:

javascript
window.alert("BOM");
document.body.style.color = "red"; // DOM
63. setTimeout nima uchun?

Javob: Ma’lum vaqtdan keyin kodni bajaradi.

Tasavvur: “Taymer”.

Misol:
javascript
setTimeout(() => console.log("Salom"), 2000); // 2 soniyadan keyin
64. setInterval nima uchun?

Javob: Kodni har ma’lum vaqt oralig‘ida takrorlaydi.

Tasavvur: “Doimiy taymer”.

Misol:
javascript
setInterval(() => console.log("Tik-tak"), 1000); // Har soniyada
65. ECMAScript nima?

Javob: JavaScriptning asosiy standarti.

Tasavvur: “JS qonuni”.

Misol: ES6 — let, const.
66. JSON.stringify nima uchun?

Javob: Ob’ektni matnga aylantiradi.

Tasavvur: “Ob’ektni xat qilish”.

Misol:
javascript
let obj = { ism: "Ali" };
let matn = JSON.stringify(obj);
console.log(matn); // '{"ism":"Ali"}'
67. JSON.parse nima uchun?

Javob: Matnni ob’ektga aylantiradi.

Tasavvur: “Xatni o‘qish”.

Misol:
javascript
let matn = '{"ism":"Ali"}';
let obj = JSON.parse(matn);
console.log(obj.ism); // "Ali"
68. clearTimeout nima uchun?

Javob: setTimeoutni bekor qiladi.

Tasavvur: “Taymerni o‘chirish”.

Misol:
javascript
let t = setTimeout(() => console.log("Salom"), 2000);
clearTimeout(t); // Chiqmaydi
69. clearInterval nima uchun?

Javob: setIntervalni bekor qiladi.

Tasavvur: “Doimiy taymerni o‘chirish”.

Misol:
javascript
let i = setInterval(() => console.log("Tik-tak"), 1000);
setTimeout(() => clearInterval(i), 3000); // 3 soniyadan keyin to‘xtaydi
70. Bo‘sh ob’ektni qanday tekshirish mumkin?

Javob: Object.keys(obj).length === 0 bilan.

Tasavvur: “Bo‘sh sumkani tekshirish”.

Misol:
javascript
let obj = {};
console.log(Object.keys(obj).length === 0); // true
71. Arguments ob’ekti nima?

Javob: Funksiyaga berilgan barcha argumentlar massivi.

Tasavvur: “Funksiyaning sumkasi”.

Misol:
javascript
function test() { console.log(arguments); }
test(1, 2, 3); // [1, 2, 3]
72. Funksiyaga xususiyat qo‘shish mumkinmi?

Javob: Ha, funksiyalar ob’ekt bo‘lgani uchun mumkin.

Tasavvur: “Ko‘p funksiyali quti”.

Misol:
javascript
function salom() { console.log("Salom"); }
salom.x = 5;
console.log(salom.x); // 5
73. Funksiya qancha parametr kutayotganini qanday bilish mumkin?

Javob: function.length bilan.

Tasavvur: “Funksiyaning qo‘llari”.

Misol:
javascript
function qosh(a, b) { return a + b; }
console.log(qosh.length); // 2
74. Polyfill nima?

Javob: Eski brauzerlarda yangi xususiyatlarni qo‘llab-quvvatlash uchun kod.

Tasavvur: “Yamoq”.

Misol:
javascript
if (!Array.prototype.includes) {
  Array.prototype.includes = function(item) { return this.indexOf(item) !== -1; };
}
75. JS label’lari nima?

Javob: Tsikl yoki blokka nom berish, break yoki continue bilan ishlatiladi.

Tasavvur: “Yo‘naltiruvchi belgilar”.

Misol:
javascript
outer: for (let i = 0; i < 3; i++) {
  for (let j = 0; j < 3; j++) {
    if (i === j) break outer;
    console.log(i, j);
  }
}
76. __proto__ va prototype farqi nima?

Javob:

    __proto__: Ob’ektning prototipi.
    prototype: Funksiya konstruktorining xususiyati.
    Tasavvur: __proto__ — “ota”, prototype — “qolip”.
    Misol:

javascript
function Test() {}
let t = new Test();
console.log(t.__proto__ === Test.prototype); // true
77. Rest parametri nima?

Javob: ... bilan cheksiz argumentlarni massiv sifatida qabul qiladi.

Tasavvur: “Hamma narsani yig‘uvchi qop”.

Misol:
javascript
function yig(a, ...b) { console.log(a, b); }
yig(1, 2, 3, 4); // 1, [2, 3, 4]
78. Spread operatori nima?

Javob: ... bilan massiv yoki ob’ektni elementlarga ajratadi.

Tasavvur: “Yoyib qo‘yish”.

Misol:
javascript
let arr = [1, 2, 3];
console.log(...arr); // 1 2 3
let yangi = [...arr, 4]; // [1, 2, 3, 4]
79. Ikkita qiymat bir xilligini qanday tekshirish mumkin?

Javob: Object.is() bilan, === dan farqli o‘laroq NaN ni to‘g‘ri tekshiradi.

Tasavvur: “Adolatli hakam”.

Misol:
javascript
console.log(Object.is(5, 5)); // true
console.log(Object.is(NaN, NaN)); // true
80. Ob’ektni prototip bilan qanday yaratish mumkin?

Javob: Object.create() bilan.

Tasavvur: “Nusxa olish mashinasi”.

Misol:
javascript
let ota = { x: 5 };
let bola = Object.create(ota);
console.log(bola.x); // 5
81. Anonim funksiya nima?

Javob: Nomsiz funksiya, darhol ishlatish uchun.

Tasavvur: “Ismsiz yordamchi”.

Misol:
javascript
let salom = function() { console.log("Salom"); };
salom(); // "Salom"
82. Mahalliy va global o‘zgaruvchilarning ustuvorligi?

Javob: Mahalliy o‘zgaruvchi globaldan ustun.

Tasavvur: “O‘z xonangdagi narsa birinchi”.

Misol:
javascript
let x = 5;
function test() {
  let x = 10;
  console.log(x); // 10
}
test();
83. JavaScript’da accessor’lar nima?

Javob: get va set bilan xususiyatlarni boshqarish.

Tasavvur: “Eshik qo‘riqchisi”.

Misol:
javascript
let odam = {
  _ism: "Ali",
  get ism() { return this._ism; },
  set ism(yangi) { this._ism = yangi; }
};
odam.ism = "Vali";
console.log(odam.ism); // "Vali"
84. Ob’ekt konstruktorida xususiyatni qanday belgilash mumkin?

Javob: Object.defineProperty bilan.

Tasavvur: “Xususiyat muhri”.

Misol:
javascript
let obj = {};
Object.defineProperty(obj, "ism", { value: "Ali", writable: true });
console.log(obj.ism); // "Ali"
85. defineProperty bilan getter va setter qo‘shish mumkinmi?

Javob: Ha, dinamik boshqarish uchun.

Tasavvur: “Aqlli qo‘riqchi”.

Misol:
javascript
let obj = { _x: 0 };
Object.defineProperty(obj, "x", {
  get: function() { return this._x; },
  set: function(yangi) { this._x = yangi; }
});
obj.x = 5;
console.log(obj.x); // 5
86. Primitive ma’lumot turlari nima?

Javob: Oddiy tiplar: string, number, boolean, null, undefined, bigint, symbol.

Tasavvur: “Oddiy narsalar”.

Misol:
javascript
let a = "Salom"; // string
let b = 5; // number
87. Error ob’ekti nima?

Javob: Xatolarni ko‘rsatuvchi ob’ekt, name va message bor.

Tasavvur: “Xato kartasi”.

Misol:
javascript
throw new Error("Nimadir xato!");
88. Error ob’ektidagi xato nomlari?

Javob: SyntaxError, ReferenceError, TypeError, RangeError.

Tasavvur: “Xato nomlari ro‘yxati”.

Misol:
javascript
console.log(a); // ReferenceError
89. Node.js nima?

Javob: Serverda JavaScript ishlatish uchun platforma, V8 engine bilan.

Tasavvur: “Serverdagi JS”.

Misol:
javascript
const http = require("http");
http.createServer((req, res) => { res.end("Salom"); }).listen(3000);
90. Iterator, Generator va Loop farqi?

Javob:

    Iterator: Qo‘lda boshqariladi (next()).
    Generator: Avtomatik iterator (yield).
    Loop: Avtomatik takrorlaydi.
    Tasavvur: Iterator — “qo‘lda yuruvchi”, Generator — “yordamchi”, Loop — “avto”.
    Misol:

javascript
let it = [1, 2].values();
console.log(it.next().value); // 1

function* gen() { yield 1; }
let g = gen();
console.log(g.next().value); // 1
91. Decorator nima?

Javob: Sinf yoki metodni o‘zgartiruvchi funksiya (tajriba bosqichida).

Tasavvur: “Bezak”.

Misol:
javascript
function log(target) { console.log("Ishladi"); }
@log
class Test {}
92. Unary operatori nima?

Javob: + bilan qiymatni songa aylantiradi.

Tasavvur: “Son qiluvchi sehr”.

Misol:
javascript
console.log(+"5"); // 5
console.log(+"salom"); // NaN
93. TypeScript nima?

Javob: JavaScript’ning kengaytmasi, statik tiplar qo‘shadi.

Tasavvur: “Aqlli JS”.

Misol:
typescript
let ism: string = "Ali";
94. JavaScript va TypeScript farqi?

Javob:

    JS: Dinamik, tiplarsiz.
    TS: Statik tiplar, xavfsiz.
    Tasavvur: JS — “erkin yozuvchi”, TS — “qoidalarga rioya qiluvchi”.
    Misol:

typescript
let x: number = 5; // TS
95. TypeScript’ning JavaScript’dan afzalliklari?

Javob: Xatolarni oldindan topadi, kod aniq, katta loyihalarda oson.

Tasavvur: “Xavfsizlik kamarli JS”.

Misol:
typescript
function qosh(a: number, b: number) { return a + b; }
96. Ob’ektning prototipini qanday olish mumkin?

Javob: Object.getPrototypeOf(obj) bilan.

Tasavvur: “Ota-boboni so‘rash”.

Misol:
javascript
let ota = { x: 5 };
let bola = Object.create(ota);
console.log(Object.getPrototypeOf(bola) === ota); // true
97. String bilan getPrototypeOf ishlatilsa nima bo‘ladi?

Javob: ES5’da xato, ES6’da string ob’ektga aylanadi.

Tasavvur: “Noto‘g‘ri mehmon”.

Misol:
javascript
console.log(Object.getPrototypeOf("salom")); // String.prototype
98. Ob’ektning prototipini boshqasiga qanday o‘zgartirish mumkin?

Javob: Object.setPrototypeOf(obj, proto) bilan.

Tasavvur: “Ota almashtirish”.

Misol:
javascript
let ota1 = { x: 5 };
let ota2 = { y: 10 };
let bola = Object.create(ota1);
Object.setPrototypeOf(bola, ota2);
console.log(bola.y); // 10
99. Ob’ekt kengaytiriladimi yoki yo‘qligini qanday tekshirish mumkin?

Javob: Object.isExtensible(obj) bilan.

Tasavvur: “Quti ochiqmi?”.

Misol:
javascript
let obj = {};
console.log(Object.isExtensible(obj)); // true
Object.freeze(obj);
console.log(Object.isExtensible(obj)); // false
100. Ob’ektni kengaytishni qanday oldini olish mumkin?

Javob:

    Object.preventExtensions() — yangi xususiyat taqiqlanadi.
    Object.seal() — qo‘shish/o‘chirish taqiqlanadi.
    Object.freeze() — hamma o‘zgartirish taqiqlanadi.
    Tasavvur: Prevent — “eshikni yopish”, Seal — “qulflash”, Freeze — “muzlatish”.
    Misol:

javascript
let obj = { x: 5 };
Object.preventExtensions(obj);
obj.y = 10; // Qo‘shilmaydi
101. Bir nechta xususiyatni ob’ektga qanday belgilash mumkin?

Javob: Object.defineProperties bilan.

Tasavvur: “Ko‘p muhr bosish”.

Misol:
javascript
let obj = {};
Object.defineProperties(obj, {
  ism: { value: "Ali" },
  yosh: { value: 20 }
});
console.log(obj.ism, obj.yosh); // "Ali" 20
102. Minification nima?

Javob: Kodni kichraytirish uchun bo‘sh joylar va nomlarni qisqartirish.

Tasavvur: “Kodni siqish”.

Misol:
javascript
let salom = function() { console.log("Salom"); };
// Minified: let s=function(){console.log("Salom")};
103. JavaScript’da enum bormi?

Javob: Yo‘q, lekin Object.freeze bilan o‘xshatish mumkin.

Tasavvur: “Doimiy ro‘yxat”.

Misol:
javascript
const Ranglar = Object.freeze({ QIZIL: "qizil", YASHIL: "yashil" });
console.log(Ranglar.QIZIL); // "qizil"
104. V8 JavaScript engine nima?

Javob: Google Chrome’da ishlatiladigan tezkor JS mexanizmi.

Tasavvur: “Kod dvigateli”.
105. Nega JavaScript dinamik til deyiladi?

Javob: O‘zgaruvchilar har qanday tipda bo‘lishi mumkin.

Tasavvur: “Erkin ruh”.

Misol:
javascript
let x = 5;
x = "Salom";
console.log(x); // "Salom"
106. Quyidagi for tsikllarining natijasi nima?

Javob:
javascript
for (var i = 0; i < 4; i++) { setTimeout(() => console.log(i), 1000); } // 4 4 4 4
for (let i = 0; i < 4; i++) { setTimeout(() => console.log(i), 1000); } // 0 1 2 3

var global, let har bir tsikl uchun yangi.

Tasavvur: var — “hamma bir xonada”, let — “har biriga xona”.
107. ES6 xususiyatlari qanday?

Javob: let, const, strelka funksiyalari, template literals, destructuring, Promise, Class, Modules.

Tasavvur: “Yangilangan JS”.

Misol:
javascript
const x = 5;
let salom = () => console.log(`Salom, ${x}`);
salom(); // "Salom, 5"
108. ES6 nima?

Javob: ECMAScript 2015 — JS’ning 6-nashri, yangi xususiyatlar qo‘shdi.

Tasavvur: “JS ning yangi kiyimi”.
109. let va const’ni qayta e’lon qilish mumkinmi?

Javob: Yo‘q, bir doirada takrorlanmaydi.

Tasavvur: “Bir ism — bir odam”.

Misol:
javascript
let x = 5;
let x = 10; // Xato
110. const o‘zgaruvchi qiymatni o‘zgarmas qiladimi?

Javob: Yo‘q, faqat yangi qiymat berish taqiqlanadi, ob’ekt ichini o‘zgartirish mumkin.

Tasavvur: “Quti muhri”.

Misol:
javascript
const obj = { ism: "Ali" };
obj.ism = "Vali"; // Mumkin
console.log(obj.ism); // "Vali"
111. Template literals nima?

Javob: ` bilan matn, ${} bilan o‘zgaruvchi ishlatiladi.

Tasavvur: “Aqlli matn”.

Misol:
javascript
let ism = "Ali";
console.log(`Salom, ${ism}!`); // "Salom, Ali!"
112. Template literals’da ko‘p qatorli matn qanday yoziladi?

Javob: ` ichida enter bilan.

Tasavvur: “Erkin she’r”.

Misol:
javascript
let matn = `Birinchi qator
Ikkinchi qator`;
console.log(matn);
113. Destructuring assignment nima?

Javob: Massiv yoki ob’ekt qiymatlarini alohida o‘zgaruvchilarga ajratish.

Tasavvur: “Sumkani bo‘lib olish”.

Misol:
javascript
let [a, b] = [1, 2];
console.log(a, b); // 1 2
114. Destructuring’da standart qiymatlar nima?

Javob: Qiymat bo‘lmasa, standart qiymat belgilanadi.

Tasavvur: “Zapas narsa”.

Misol:
javascript
let [a, b = 10] = [5];
console.log(a, b); // 5 10
115. Enhanced object literals nima?

Javob: Ob’ektlarni qisqaroq yozish usuli.

Tasavvur: “Qisqa yozuvchi”.

Misol:
javascript
let ism = "Ali";
let obj = { ism, salom() { console.log("Salom"); } };
obj.salom(); // "Salom"
116. JavaScript qanday paradigmada?

Javob: Ko‘p paradigmali: imperativ, ob’ektga yo‘naltirilgan, funksional.

Tasavvur: “Hamma yo‘l ochiq”.

Misol:
javascript
let sum = [1, 2, 3].reduce((a, b) => a + b); // Funksional
117. Error ob’ektining maqsadi nima?

Javob: Xatolarni yaratish va tashlash uchun.

Tasavvur: “Xato signalchisi”.

Misol:
javascript
throw new Error("Xato yuz berdi!");
118. Hamma ob’ektlarda prototip bormi?

Javob: Yo‘q, Object.create(null) bilan prototipsiz ob’ekt yaratiladi.

Tasavvur: “Otasiz bola”.

Misol:
javascript
let obj = Object.create(null);
console.log(Object.getPrototypeOf(obj)); // null
119. JavaScript mixins ishlatadimi?

Javob: Ha, metodlarni qo‘lda nusxalash orqali.

Tasavvur: “Metod aralashtirgich”.

Misol:
javascript
let yugur = { yugur() { console.log("Yuguryapman"); } };
let odam = {};
Object.assign(odam, yugur);
odam.yugur(); // "Yuguryapman"
120. Quyidagi funksiya chaqiruvlarining natijasi nima?

Javob: (Kod keltirilmagan, umumiy misol):
javascript
function test() { return 5; }
console.log(test()); // 5
121. Massivni inkor qilsak nima bo‘ladi?

Javob: ! bilan massiv false ga aylanadi, chunki “truthy”.

Tasavvur: “Massivni yo‘q qilish”.

Misol:
javascript
console.log(![]); // false
122. Ikkita massivni qo‘shsak nima bo‘ladi?

Javob: Matnga aylanib birlashadi.

Tasavvur: “Matn yopishtirgich”.

Misol:
javascript
console.log([1, 2] + [3, 4]); // "1,23,4"
123. Falsy qiymatlarga + qo‘ysak nima bo‘ladi?

Javob: Songa aylanadi: 0 yoki NaN.

Tasavvur: “Son sehrbozi”.

Misol:
javascript
console.log(+null); // 0
console.log(+undefined); // NaN
124. Console ob’ektidagi placeholder’lar nima?

Javob: %o (ob’ekt), %s (matn), %d (son) — formatlash uchun.

Tasavvur: “Matn shablonlari”.

Misol:
javascript
console.log("Ism: %s, Yosh: %d", "Ali", 20); // "Ism: Ali, Yosh: 20"
125. Argumentning son ekanligini qanday tekshirish mumkin?

Javob: isNaN va isFinite bilan.

Tasavvur: “Son detektivi”.

Misol:
javascript
function isNumber(x) { return !isNaN(x) && isFinite(x); }
console.log(isNumber(5)); // true
126. AJAX nima?

Javob: Sahifani qayta yuklamasdan server bilan ma’lumot almashish.

Tasavvur: “Tez pochta”.

Misol:
javascript
let xhr = new XMLHttpRequest();
xhr.open("GET", "https://api.example.com", true);
xhr.send();
127. Asinxron kod bilan ishlashning turli usullari?

Javob: Callback, Promise, Async/Await, kutubxonalar.

Tasavvur: “Vaqt boshqaruvchilari”.

Misol:
javascript
async function fetchData() { let data = await fetch("https://api.example.com"); }
128. Fetch so‘rovini qanday bekor qilish mumkin?

Javob: AbortController bilan.

Tasavvur: “To‘xtat tugmasi”.

Misol:
javascript
let controller = new AbortController();
fetch("https://api.example.com", { signal: controller.signal });
controller.abort();
129. TypeScript fayllarida JS kutubxonalarini qanday ishlatish mumkin?

Javob: declare bilan e’lon qilib.

Tasavvur: “Ruxsatnoma”.

Misol:
typescript
declare var myLib: any;
myLib.doSomething();
130. Observables nima?

Javob: Vaqt o‘tishi bilan qiymatlar oqimini qaytaruvchi ob’ekt.

Tasavvur: “Radio stansiyasi”.

Misol:
javascript
const { Observable } = require("rxjs");
let obs = new Observable((sub) => { sub.next("Salom"); });
obs.subscribe((x) => console.log(x)); // "Salom"
131. Promise va Observable farqi?

Javob:

    Promise: Bir marta qiymat.
    Observable: Ko‘p marta qiymat oqimi.
    Tasavvur: Promise — “bir marta xabar”, Observable — “doimiy chat”.
    Misol:

javascript
let p = Promise.resolve("Bir");
p.then(console.log); // "Bir"
let o = new Observable((sub) => { sub.next("Bir"); sub.next("Ikki"); });
o.subscribe(console.log); // "Bir" "Ikki"
132. Shim va Polyfill farqi?

Javob:

    Shim: Yangi API qo‘shadi.
    Polyfill: Mavjud bo‘lmagan xususiyatni taqlid qiladi.
    Tasavvur: Shim — “umumiy yamoq”, Polyfill — “brauzer yamog‘i”.
    Misol:

javascript
if (!Array.prototype.includes) {
  Array.prototype.includes = function(x) { return this.indexOf(x) !== -1; };
}
133. Babel nima?

Javob: Zamonaviy JS kodini eski brauzerlarga moslashtiruvchi kompilyator.

Tasavvur: “Tarjimon”.
134. Observables’ning umumiy ishlatilishi?

Javob: Web socket’lar, tugma bosish, interval’lar.

Tasavvur: “Doimiy kuzatuvchi”.
135. RxJS nima?

Javob: Observable’lar bilan reaktiv dasturlash uchun kutubxona.

Tasavvur: “Observable boshqaruvchisi”.

Misol:
javascript
const { fromEvent } = require("rxjs");
fromEvent(document, "click").subscribe(() => console.log("Bosildi"));
136. Function constructor va function declaration farqi?

Javob:

    Constructor: new Function, global doira.
    Declaration: Oddiy funksiya, yopilmalarga ega.
    Tasavvur: Constructor — “yolg‘iz ishchi”, Declaration — “do‘stona”.
    Misol:

javascript
let f = new Function("x", "return x + 1");
console.log(f(5)); // 6
function g(x) { return x + 1; }
console.log(g(5)); // 6
137. Function va Class declaration farqi?

Javob: Funksiyalar hoisting bilan ko‘tariladi, sinflar ko‘tarilmaydi.

Tasavvur: Function — “tez tayyor”, Class — “kutmang”.

Misol:
javascript
f(); // Ishlaydi
function f() { console.log("Salom"); }
c(); // Xato
class C { static x() { console.log("Salom"); } }
138. Async funksiya nima?

Javob: Promise qaytaradi, await bilan asinxron kodni soddalashtiradi.

Tasavvur: “Kutish ustasi”.

Misol:
javascript
async function test() {
  let x = await Promise.resolve("Salom");
  console.log(x); // "Salom"
}
test();
139. Instance va non-instance xususiyatlarni qanday belgilash mumkin?

Javob:

    Instance: constructorda, har ob’ektga xos.
    Non-instance: static bilan, sinfga tegishli.
    Tasavvur: Instance — “har bir bolaga o‘yinchog‘i”, Static — “umumiy o‘yinchoq”.
    Misol:

javascript
class Mashina {
  constructor(rang) { this.rang = rang; }
  static turi = "Avto";
}
let m = new Mashina("qizil");
console.log(m.rang); // "qizil"
console.log(Mashina.turi); // "Avto"
140. Debouncing nima?

Javob: Tez-tez takrorlanadigan harakatni kechiktirib, oxirgi marta bajarish.

Tasavvur: “Sabrli yordamchi”.

Misol:
javascript
function debounce(func, delay) {
  let timer;
  return function() {
    clearTimeout(timer);
    timer = setTimeout(func, delay);
  };
}
let log = debounce(() => console.log("Salom"), 1000);
log(); log(); // Faqat oxirgi "Salom"
141. Throttling nima?

Javob: Harakatni ma’lum vaqt oralig‘ida cheklash.

Tasavvur: “Vaqt sozlagichi”.

Misol:
javascript
function throttle(func, delay) {
  let last = 0;
  return function() {
    let now = Date.now();
    if (now - last >= delay) {
      func();
      last = now;
    }
  };
}
let log = throttle(() => console.log("Tik"), 1000);
setInterval(log, 200); // Har 1 soniyada "Tik"
142. Coding mashq — GitHub’dagi javascript-questions?

Javob: Lydia Hallie’ning GitHub’dagi JS savollari to‘plami.

Tasavvur: “JS sinov maydoni”.

Misol: https://github.com/lydiahallie/javascript-questions
```
