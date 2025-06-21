# 📊 Reqres API Testing with Apache JMeter

Repo ini berisi pengujian API publik [reqres.in](https://reqres.in/) menggunakan **Apache JMeter**. Tes dilakukan terhadap 4 metode HTTP: `GET`, `POST`, `PATCH`, dan `DELETE`. Setiap request dilengkapi dengan **assertion** untuk:

- Validasi status code HTTP
- Validasi response field JSON

---

## 📁 Struktur Proyek

├── reqresLoadTest.jmx → Test plan JMeter
├── report.jtl → Hasil eksekusi (log) dari test
├── report-html/ → Hasil HTML report dari .jtl
└── README.md → Dokumentasi ini

````

---

## 🔍 Test Cases

| Method   | Endpoint       | Validasi                                                            |
| -------- | -------------- | ------------------------------------------------------------------- |
| `GET`    | `/api/users/2` | ✅ Status `200 OK` + field `data.id == 2`                            |
| `POST`   | `/api/users`   | ✅ Status `201 Created` + field `name`, `job` |
| `PATCH`  | `/api/users/2` | ✅ Status `200 OK` + field `job` sesuai update                       |
| `DELETE` | `/api/users/2` | ✅ Status `204 No Content`                             |

---

## 💻 Prerequisites

Sebelum menjalankan test, pastikan sistem kamu sudah menginstal:

* ✅ Java JDK 8 (required)
* ✅ Apache JMeter (versi terbaru disarankan)

### 🧪 Cek Java

```bash
java -version
```

Harus menghasilkan output mirip:

```
java version "1.8.x"
```

---

## 🛠️ Install Apache JMeter

1. Unduh JMeter dari [https://jmeter.apache.org/download\_jmeter.cgi](https://jmeter.apache.org/download_jmeter.cgi)
2. Ekstrak ke folder manapun (misal: `C:\apache-jmeter-5.6.3\`)
3. Tidak perlu instalasi formal — langsung bisa digunakan

---

## 🚀 Cara Menjalankan Tes

1. Buka terminal dan masuk ke folder `bin` dari JMeter

   ```bash
   cd apache-jmeter-5.6.3/bin
   ```

2. Jalankan test dari file `.jmx`:

   ```bash
   jmeter.bat -n -t path/to/reqresLoadTest.jmx -l path/to/report.jtl
   ```

3. (Opsional) Generate HTML report dari file `.jtl`:

   ```bash
   jmeter.bat -g path/to/report.jtl -o path/to/report-html
   ```

4. Buka `report-html/index.html` di browser untuk melihat hasil grafik dan summary.

---

## 📌 Catatan Tambahan

* File `.jmx` bisa dibuka via GUI JMeter untuk modifikasi visual.
* Report `.jtl` dan HTML bisa digunakan untuk artefak QA atau CI pipeline.
* Tes dirancang untuk stable endpoint dari `https://reqres.in/`.

---

## 👤 Author

* Nur – QA Engineer in Progress 🚀

```
````
