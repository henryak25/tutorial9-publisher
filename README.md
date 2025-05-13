1. How much data your publisher program will send to the message broker in one run?
    - Dalam satu kali eksekusi main(), publisher akan mengirim 5 pesan ke message broker (RabbitMQ), karena terdapat 5 pemanggilan fungsi publish_event. Setiap pesan bertipe UserCreatedEventMessage, yang terdiri dari user_id yaitu sebuah String (misalnya "1") dan username yaitu sebuah String (misalnya "2306214990-Amir").

2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
    - Artinya Baik publisher maupun subscriber terhubung ke server RabbitMQ yang sama, yaitu sama sama di localhost, dengan user guest, dan port 5672. Dengan begitu publisher dapat mengirimkan message ke broker, dan subscriber bisa menerima pesan dari broker yang sama karena keduanya mengakses broker di alamt yang sama.

<br><br>

### RabbitMQ Screenshot
![RabbitMQ](RabbitMQ.png)