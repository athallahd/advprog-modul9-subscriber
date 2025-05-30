# Module 9 Adpro Subscriber Reflection

Nama: Athallah Damar Jiwanto <br>
NPM: 2306245024 <br>
Kelas: Advprog-B
<hr>

1. What is amqp? <br>
AMQP (Advanced Message Queuing Protocol) adalah sebuah protokol standar terbuka untuk sistem message-oriented middleware yang memungkinkan komunikasi asinkron antara aplikasi atau layanan perangkat lunak. AMQP digunakan untuk mengatur pengiriman pesan (message) antar aplikasi dengan cara yang terstruktur, andal, dan terjamin, khususnya dalam sistem terdistribusi dan arsitektur microservices. Protokol ini memungkinkan sebuah aplikasi pengirim (publisher) mengirim pesan ke broker pesan (message broker), yang kemudian akan meneruskan pesan tersebut ke aplikasi penerima (consumer) sesuai aturan tertentu.

2. What does it mean? `guest:guest@localhost:5672` , what is the first guest, and what 
is the second guest, and what is localhost:5672 is for? <br>
`guest:guest@localhost:5672` adalah format URL koneksi untuk mengakses server RabbitMQ menggunakan protokol AMQP. Kata guest pertama adalah username yang digunakan untuk login ke server RabbitMQ. Kata guest kedua adalah password yang sesuai dengan username tersebut. Bagian localhost menunjukkan alamat server RabbitMQ yang dijalankan di komputer lokal (localhost berarti komputer yang sama dengan client). Angka 5672 adalah port default yang digunakan RabbitMQ untuk menerima koneksi AMQP dari client. Jadi, keseluruhan `guest:guest@localhost:5672` berarti kita menghubungkan client ke server RabbitMQ lokal dengan username guest, password guest, melalui port 5672.

## Simulation Slow Subscriber
![Queue Simulation](image/queue.png)
Grafik pada RabbitMQ menunjukkan adanya total 20 pesan dalam antrian karena simulasi "Slow Subscriber" yang sedang berjalan. Dalam skenario ini, publisher mengirim pesan lebih cepat daripada kemampuan subscriber untuk memprosesnya, sehingga pesan-pesan tersebut menumpuk dalam antrian.

## Running at least three subscribers
![Console](image/console.png)
![Performance](image/rabbitmq.png)
Setelah menjalankan perintah sebanyak 3 kali dengan dibukanya 3 subscribers, terlihat tidak terjadi lonjakan pada queue message pada RabbitMQ yang dimana ini menandakan bahwa tiap message yang dikirim oleh publisher langsung diterima dan diproses oleh ketiga subscribers tersebut tanpa ada backlog atau antrian message yang tertinggal di broker. Hal ini menunjukkan bahwa RabbitMQ berhasil menyalurkan message secara efisien ke ketiga subscriber yang aktif, memungkinkan mereka untuk memproses message secara real-time.