# OSI modeli va Wiresharkage

#### OSI modelining 7 qatlami <a href="#osi-modelining-7-qatlami" id="osi-modelining-7-qatlami"></a>

OSI modeli tarmoqlarni tushunish uchun qatlamli yondashuvni taklif etadi. Har bir qatlam o'ziga xos vazifani bajaradi va quyidagi qatlam bilan bog'liq bo'ladi.

![](https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F2294590586-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F8RlHrBTuUIKEGbK9wED5%252Fuploads%252FXeH4Jk4zh4MTQafulgQA%252Fimage.png%3Falt%3Dmedia%26token%3Dbfc7a304-b461-46c8-9d1d-2729b62829b4\&width=768\&dpr=4\&quality=100\&sign=fa874c89\&sv=2)

#### OSI qatlamlari batafsil <a href="#osi-qatlamlari-batafsil" id="osi-qatlamlari-batafsil"></a>

**1. Fizik qatlam (Physical Layer)**

Bu qatlam tarmoqning eng quyi qatlami bo'lib, fizik signallarni uzatish bilan shug'ullanadi.

* **Vazifasi:** Ikkilik ma'lumot (bit)larni fizik signallarga aylantirib uzatish
* **Asosiy elementlar:** Kabellar, konektorlar, signallar, modulyatsiya
* **Qurilmalar:** Kabellar, modemlar, hablar, takrorlagichlar, NIC
* **Misollar:** RJ45 konnektorlari, UTP kabellari, optik tolalar, radio to'lqinlar

**2. Ma'lumotlarni uzatish qatlami (Data Link Layer)**

Bu qatlam qurilmalar o'rtasida bevosita aloqani ta'minlaydi.

* **Vazifasi:** Xatolarni aniqlash, kadrlarni boshqarish, fizik manzillash (MAC)
* **Asosiy elementlar:** Kadrlar (frames), MAC manzillar, CRC
* **Qurilmalar:** Switch, ko'prik, tarmoq kartalari
* **Misol:** Ethernet kadri - sarlavha, ma'lumot va tekshirish qismi bilan

**3. Tarmoq qatlami (Network Layer)**

Bu qatlam ma'lumotlarni manbadan belgilangan manzilga yo'naltiradi.

* **Vazifasi:** Marshrutizatsiya, mantiqiy manzillash, tarmoqlararo bog'lanish
* **Asosiy elementlar:** IP-manzillar, marshrutizatsiya jadvallari, paketlar
* **Qurilmalar:** Router (marshrutizator)
* **Misol:** Internet protokoli (IP), marshrutizatsiya protokollari (OSPF, BGP)

**4. Transport qatlami (Transport Layer)**

Bu qatlam ma'lumotlarni segmentlarga ajratadi va ishonchli uzatishni ta'minlaydi.

* **Vazifasi:** Aloqa seanslarini boshqarish, ma'lumotlarni segmentlarga ajratish
* **Asosiy elementlar:** Portlar, ulanishlar, segmentlar
* **Protokollar:** TCP (ishonchli) va UDP (tezkor)
* **Misol:** Web trafikda 80-port orqali HTTP ma'lumotlarini uzatish

**5. Sessiya qatlami (Session Layer)**

Bu qatlam qurilmalar o'rtasidagi muloqotni boshqaradi.

* **Vazifasi:** Dialog boshqaruvi, sinxronlash, seanslarni nazorat qilish
* **Asosiy elementlar:** Seanslar, nuqtalar (checkpoint), qayta tiklash
* **Misol:** NetBIOS orqali kompyuterlar o'rtasidagi aloqa

**6. Taqdimot qatlami (Presentation Layer)**

Bu qatlam ma'lumotlarni formatlash va o'zgartirish bilan shug'ullanadi.

* **Vazifasi:** Ma'lumot formatlash, shifrlash/deshifrlash, siqish
* **Asosiy elementlar:** Ma'lumot formatlari, kodlash tizimlari
* **Misol:** SSL/TLS shifrlash, JPEG siqish, ASCII/Unicode kodlash

**7. Ilova qatlami (Application Layer)**

Bu eng yuqori qatlam bo'lib, foydalanuvchi dasturlari uchun interfeysni ta'minlaydi.

* **Vazifasi:** Tarmoq xizmatlarini ilovalarga taqdim etish
* **Asosiy elementlar:** API, dastur protokollari, foydalanuvchi interfeyslari
* **Misollar:** Veb-brauzer (HTTP), elektron pochta (SMTP/POP3), fayl uzatish (FTP)

### OSI **modelini Wireshark bilan tekshirish** <a href="#osi-modelini-wireshark-bilan-tekshirish" id="osi-modelini-wireshark-bilan-tekshirish"></a>

![](https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F2294590586-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F8RlHrBTuUIKEGbK9wED5%252Fuploads%252FAErxR1X8OshU5jFA8dEJ%252Fimage.png%3Falt%3Dmedia%26token%3Dfa47d6be-9497-4770-9c2d-d73c0d4bd4f6\&width=768\&dpr=4\&quality=100\&sign=5132600b\&sv=2)

#### Wireshark bilan OSI modelini amalda tekshirish <a href="#wireshark-bilan-osi-modelini-amalda-tekshirish" id="wireshark-bilan-osi-modelini-amalda-tekshirish"></a>

**1-qadam: Wireshark dasturini o'rnatish va ishga tushirish**

Wireshark - bu ochiq kodli tarmoq analizatori. U sizga tarmoqda sodir bo'layotgan barcha ma'lumot almashinuvlarini kuzatish imkonini beradi.

**2-qadam: Tarmoq interfeysini tanlash**

Dastur ishga tushganda, avval qaysi tarmoq interfeysini kuzatmoqchi ekanligingizni tanlaysiz:

* Ethernet
* Wi-Fi
* Boshqa mavjud interfeyslar

**3-qadam: Ma'lumotlarni yig'ishni boshlash**

"Start capturing packets" tugmasini bosasiz va ma'lumotlar yig'ila boshlaydi.

**4-qadam: OSI modeli qatlamlari bo'yicha paketlarni ko'rish**

**Fizik qatlam (1-qatlam) tekshirish**

* Wireshark bevosita fizik qatlam signallarini ko'rsatmasa-da, tarmoq interfeyslarini va ulardan olingan paketlarni ko'rish mumkin
* "Statistics > Capture File Properties" orqali interfeys ma'lumotlarini ko'rish mumkin

Ma'lumotlarni uzatish qatlami (2-qatlam) tekshirish:

* "Ethernet II" deb nomlanuvchi qismlar MAC-manzillarni ko'rsatadi (manba va belgilangan qurilma)
* Paketni tanlang va pastki panelda "Frame" va "Ethernet II" qismlarini yoying
* Bu yerda ko'rsatilgan ma'lumotlar:
  * Manba MAC-manzili
  * Belgilangan MAC-manzili
  * Ethernet turi (masalan, IPv4=0x0800, ARP=0x0806)

Tarmoq qatlami (3-qatlam) tekshirish:

* IP paketlarini ko'rish uchun "ip" filtrini qo'llang
* Paketni tanlang va "Internet Protocol" qismini yoying
* Bu yerda ko'rsatilgan ma'lumotlar:
  * Manba IP-manzili
  * Belgilangan IP-manzili
  * TTL (Time To Live) qiymati
  * Protokol (TCP=6, UDP=17, ICMP=1)

Transport qatlami (4-qatlam) tekshirish:

* TCP paketlarini ko'rish uchun "tcp" filtrini qo'llang
* UDP paketlarini ko'rish uchun "udp" filtrini qo'llang
* Paketni tanlang va "Transmission Control Protocol" yoki "User Datagram Protocol" qismini yoying
* Bu yerda ko'rsatilgan ma'lumotlar:
  * Manba porti
  * Belgilangan porti
  * TCP bayroqchalari (SYN, ACK, FIN, va boshqalar)
  * TCP ketma-ketlik raqamlari

Seans qatlami (5-qatlam) tekshirish:

* Masalan, "ssl" yoki "tls" filtrini qo'llang (xavfsiz ulanishlar uchun)
* SSH ulanishlarini ko'rish uchun "ssh" filtrini qo'llang
* Paketni tanlang va tegishli protokol qismini yoying

Taqdimot qatlami (6-qatlam) tekshirish:

* HTTP paketlari uchun "http" filtrini qo'llang
* Fayllarni uzatish protokoli uchun "ftp" filtrini qo'llang
* "Follow HTTP Stream" orqali to'liq HTTP so'rov va javobni ko'rish mumkin

Ilova qatlami (7-qatlam) tekshirish:

* "dns" filtrini qo'llang (Domain Name System)
* "http.request.method == GET" kabi murakkab filtrlarni qo'llash mumkin
* "Statistics > Protocol Hierarchy" orqali barcha ilovalar protokollari statistikasini ko'ring

5-qadam: Foydali filtrlar:

* `http` - faqat HTTP trafik
* `tcp.port == 80` - 80-portga yo'naltirilgan TCP trafik
* `ip.addr == 192.168.1.1` - belgilangan IP-manzil bilan bog'liq trafik
* `!arp && !dns` - ARP va DNS trafikdan boshqa barcha trafik

6-qadam: Natijalarni saqlash va tahlil qilish:

* "File > Save As" orqali natijalarni saqlash mumkin
* "Statistics" menyusi orqali turli statistik ma'lumotlarni ko'ring

Bu amaliy mashg'ulot orqali OSI modelining har bir qatlami qanday ishlashini va ular qanday o'zaro bog'langanligini kuzatishingiz mumkin. Wireshark real vaqtda tarmoq trafikini monitoring qilish va xatoliklarni aniqlash uchun kuchli vosita hisoblanadi.
