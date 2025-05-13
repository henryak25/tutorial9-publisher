1. How much data your publisher program will send to the message broker in one run?
    - Dalam satu kali eksekusi main(), publisher akan mengirim 5 pesan ke message broker (RabbitMQ), karena terdapat 5 pemanggilan fungsi publish_event. Setiap pesan bertipe UserCreatedEventMessage, yang terdiri dari user_id yaitu sebuah String (misalnya "1") dan username yaitu sebuah String (misalnya "2306214990-Amir").

2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
    - Artinya Baik publisher maupun subscriber terhubung ke server RabbitMQ yang sama, yaitu sama sama di localhost, dengan user guest, dan port 5672. Dengan begitu publisher dapat mengirimkan message ke broker, dan subscriber bisa menerima pesan dari broker yang sama karena keduanya mengakses broker di alamt yang sama.

<br><br>

### RabbitMQ Screenshot
![RabbitMQ](RabbitMQ.png)

<br><br>
<br><br>

### Sending and Processing Event
![sendingpublisher](sendingpublisher.png)
![sendingsubscriber](sendingsubscriber.png)

<br><br>
<br><br>

### Monitoring chart based on publisher
![monitoringchart](monitoringchart.png)
Explanation: Garis kuning merepresentasikan jumlah message yang dikirim (publish rate) oleh publisher ke message broker. Garis ungu menunjukkan jumlah message yang berhasil diambil (consume rate) oleh subscriber dari queue. Ketika program publisher dijalankan, maka langsung mengirimkan lima event sekaligus ke RabbitMQ. Sementara itu, subscriber membutuhkan waktu untuk menerima dan memproses message" tersebut. Maka, setelah event message dikirim, baru muncul kenaikan pada garis ungu yang menunjukkan proses konsumsi sedang berlangsung.