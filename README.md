graph TD
    A[Kamar Hotel: Sensor Suhu, PIR, Pintu] -->|Membaca Data| B(Edge Node: ESP8266)
    B -->|Publish MQTT via Wi-Fi| C{Mosquitto Broker<br>Ubuntu: 192.168.1.23}
    C -->|Subscribe Topik| D[Apache Spark<br>Big Data Processing]
    D -->|Simpan Data Bersih| E[(InfluxDB<br>Time-Series Database)]
    E -->|Query Data| F[Grafana<br>Dashboard Visualisasi]
    G[Dosen / User] -->|Akses Web: 30080| H[Nginx Web Server<br>Portal Utama]
    H -.->|Klik Tombol Shortcut| F
