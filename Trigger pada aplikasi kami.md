# 🏀 Aplikasi Booking Lapangan Basket

## 👥 Anggota Kelompok
- Akhmad Thoriq Aydin Rafif
- Mifta Husasaadah
- Muhammad Ziyasyafa Ar-Rayyan

---

## ⚙️ Trigger Database

### 1️⃣ Auto Create Payment saat Booking dibuat
- **Nama Trigger:** after_booking_insert  
- **Tabel:** bookings  
- **Event:** AFTER INSERT  

**Deskripsi:**  
Trigger ini otomatis membuat data pembayaran setiap kali booking dibuat dengan status `unpaid`.

---

### 2️⃣ Update Status Booking menjadi Done setelah pembayaran & setelah main
- **Nama Trigger:** trg_payment_after_update  
- **Tabel:** payments  
- **Event:** AFTER UPDATE  

**Deskripsi:**  
Jika pembayaran sudah `paid`, maka status booking akan diubah menjadi `done`.

---

### 3️⃣ Set Tanggal Pembayaran Otomatis
- **Nama Trigger:** trg_payment_before_update  
- **Tabel:** payments  
- **Event:** BEFORE UPDATE  

**Deskripsi:**  
Mengisi `payment_date` secara otomatis saat pembayaran dikonfirmasi.

---

### 4️⃣ Mencegah Double Booking (Lock Slot)
- **Nama Trigger:** trg_prevent_double_slot  
- **Tabel:** bookings  
- **Event:** BEFORE INSERT  

**Deskripsi:**  
Mencegah booking pada slot yang sama (tanggal, jam, dan lapangan yang sama).

---
