# RowyClient v2.0

Modern ve güvenli Minecraft AFK bot yönetim sistemi. Web tabanlı arayüz ile botlarınızı kolayca yönetin.

## Özellikler

- **Kullanıcı Sistemi**: JWT tabanlı güvenli giriş ve kayıt sistemi
- **Çoklu Bot Yönetimi**: Kullanıcı başına 10 bot desteği
- **Gerçek Zamanlı İzleme**: WebSocket ile anlık bot durumu takibi
- **Terminal Görünümü**: Bot loglarını canlı olarak izleyin
- **Chat Sistemi**: Minecraft sunucusu ile doğrudan iletişim
- **Envanter Görüntüleme**: Bot envanterini ve istatistiklerini görün
- **Admin Paneli**: Kullanıcı ve bot yönetimi, duyuru sistemi
- **Güvenlik**: XSS, NoSQL injection koruması, rate limiting
- **Otomatik Yeniden Bağlanma**: Bağlantı kesildiğinde otomatik yeniden deneme
- **MongoDB Entegrasyonu**: Tüm veriler güvenli şekilde saklanır

## Kurulum

### Gereksinimler

- Node.js (v14 veya üzeri)
- MongoDB
- npm veya yarn

### Adımlar

1. Projeyi klonlayın:
```bash
git clone https://github.com/kullaniciadi/rowyclient.git
cd rowyclient
```

2. Bağımlılıkları yükleyin:
```bash
npm install
```

3. `.env` dosyası oluşturun:
```env
PORT=3001
MONGODB_URI=mongodb://localhost:27017/rowyclient
JWT_SECRET=gizli_anahtar_buraya
ADMIN_EMAILS=admin@example.com,admin2@example.com
```

4. Sunucuyu başlatın:
```bash
npm start
```
veya Windows için:
```bash
start-simple.bat
```

5. Tarayıcınızda açın:
```
http://localhost:3001
```

## Kullanım

### Kayıt ve Giriş

1. Ana sayfada "Kayıt Ol" sekmesine tıklayın
2. Email, kullanıcı adı ve şifre ile kayıt olun
3. Giriş yapın ve bot paneline erişin

### Bot Ekleme

1. "Yeni Bot Ekle" butonuna tıklayın
2. Bot bilgilerini girin:
   - Kullanıcı Adı (Minecraft)
   - Sunucu IP
   - Port (varsayılan: 25565)
   - Şifre (opsiyonel)
3. "Ekle" butonuna tıklayın

### Bot Yönetimi

- **Başlat**: Botu sunucuya bağlar
- **Durdur**: Bot bağlantısını keser
- **Sil**: Botu kalıcı olarak siler

### Sekmeler

- **Terminal**: Bot loglarını görüntüleyin
- **Chat**: Sunucu ile mesajlaşın
- **Bilgiler**: Bot detaylarını görün
- **Envanter & Durum**: Envanter ve istatistikleri görün

### Admin Paneli

Admin emaili ile giriş yaparsanız:
- Kullanıcı listesini görüntüleyin
- Sistem istatistiklerini takip edin
- Duyuru yayınlayın
- Bot paneline de erişebilirsiniz

## Teknolojiler

- **Backend**: Node.js, Express.js
- **Database**: MongoDB, Mongoose
- **WebSocket**: Socket.io
- **Authentication**: JWT, bcrypt
- **Security**: Helmet, express-rate-limit, xss-clean
- **Bot**: Mineflayer
- **Frontend**: Vanilla JavaScript, CSS3

## Güvenlik Özellikleri

- JWT token tabanlı kimlik doğrulama
- Şifre hashleme (bcrypt)
- XSS saldırı koruması
- NoSQL injection koruması
- Rate limiting (dakikada 100 istek)
- Input sanitization
- .env dosyası koruması

## Proje Yapısı

```
rowyclient/
├── bot-simple.js           # Bot yönetim mantığı
├── server-simple.js        # Express sunucu
├── models/                 # MongoDB modelleri
│   ├── User.js
│   ├── Bot.js
│   └── Announcement.js
├── middleware/             # Güvenlik ve auth
│   ├── auth.js
│   └── security.js
├── public/                 # Frontend dosyaları
│   ├── login.html
│   ├── simple.html
│   └── admin.html
├── .env                    # Ortam değişkenleri
└── package.json
```

## Katkıda Bulunma

1. Fork edin
2. Feature branch oluşturun (`git checkout -b feature/yeniOzellik`)
3. Değişikliklerinizi commit edin (`git commit -m 'Yeni özellik eklendi'`)
4. Branch'inizi push edin (`git push origin feature/yeniOzellik`)
5. Pull Request oluşturun

## Lisans

Bu proje MIT lisansı altında lisanslanmıştır.

## İletişim

Sorularınız için issue açabilirsiniz.

## Ekran Görüntüleri

### Giriş Ekranı
![Giriş Ekranı]([screenshots/login.png](https://media.discordapp.net/attachments/1457103556887838998/1483955125822427198/image.png?ex=69bc7868&is=69bb26e8&hm=964d9ea9f9c6c4757854abfe6b8817ea1cb4d4a3992d3f9e83bcc6ed936cc52a&=&format=webp&quality=lossless&width=719&height=738))

### Bot Paneli
![Bot Paneli]([screenshots/panel.png](https://media.discordapp.net/attachments/1457103556887838998/1483884969985048596/image.png?ex=69bc3712&is=69bae592&hm=ae4ed2abc16fb8b638e57b980c96f839fe13077ab8ec9e2e47fa4d27612b3bdb&=&format=webp&quality=lossless&width=1679&height=730))

### Terminal
![Terminal]([screenshots/terminal.png](https://media.discordapp.net/attachments/1457103556887838998/1483885074729664666/image.png?ex=69bc372b&is=69bae5ab&hm=2511e15abd05080e605dce28291925c3d716ad98a627b23384d07d9576df9509&=&format=webp&quality=lossless&width=1681&height=823))

### Chat
![Chat](https://media.discordapp.net/attachments/1457103556887838998/1483897731599695952/image.png?ex=69bc42f4&is=69baf174&hm=109f0ec7cdf6fc89fe67e45a3585277dd589a915561ea8291c47c801a0d67289&=&format=webp&quality=lossless&width=1405&height=796)

### Admin Paneli
![Admin Paneli]([screenshots/admin.png](https://media.discordapp.net/attachments/1457103556887838998/1483955395683942460/image.png?ex=69bc78a8&is=69bb2728&hm=4f6021ec3733f3eb63892514a459454616b10be19794e24e292fb46d0cdf4649&=&format=webp&quality=lossless&width=1633&height=865))

---

⭐ Projeyi beğendiyseniz yıldız vermeyi unutmayın! 150 Yıldızda altyapıyı paylaşıcağım.
