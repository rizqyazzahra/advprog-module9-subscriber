# Tutorial Module 9 Advanced Programming

Nama: Rizqya Az Zahra Putri

NPM: 2306244936

Kelas: B

## Reflection
a. What is amqp?

AMQP (Advanced Message Queuing Protocol) adalah protokol standar untuk pertukaran pesan antar sistem secara terdistribusi. Digunakan untuk komunikasi asynchronous antara aplikasi, terutama dalam arsitektur microservices.

b. What does it mean? guest:guest@localhost:5672 , what is the first guest, and what is the second guest, and what is localhost:5672 is for?

`guest:guest@localhost:5672` adalah connection string untuk koneksi ke server AMQP, misalnya RabbitMQ, menggunakan kredensial yang diberikan.
- `guest` pertama: Username yang digunakan untuk mengakses server AMQP
- `guest` kedua: Password pengguna
- `localhost:5672`: Alamat dan port di mana server AMQP berjalan. `localhost` berarti server tersebut berjalan di mesin yang sama dengan aplikasi yang mencoba terhubung dan `5672` adalah port default yang digunakan oleh server AMQP untuk menerima koneksi

## Simulating Slow Subscriber
![Slow Subscriber](images/slow_subs.png)
Total queue meningkat karena publisher terus mengirimkan pesan lebih cepat daripada subscriber dapat memprosesnya. Setiap `cargo run` pada publisher menambah 5 pesan sekaligus ke queue, tetapi subscriber hanya menangani 1 pesan per detik, sehingga pesan-pesan tersebut menumpuk dalam antrean.