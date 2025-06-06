# Mengatur EmailJS untuk Form Kontak

Untuk mengaktifkan fungsi pengiriman email di form kontak, ikuti langkah-langkah berikut:

## Langkah 1: Mendaftar di EmailJS

1. Kunjungi [EmailJS](https://www.emailjs.com/) dan daftar untuk akun gratis
2. Login ke dashboard EmailJS

## Langkah 2: Membuat Email Service

1. Di dashboard EmailJS, klik "Email Services" -> "Add New Service"
2. Pilih penyedia email Anda (Gmail, Outlook, dll.)
3. Ikuti petunjuk untuk mengautentikasi akun email Anda
4. Beri nama service Anda (misalnya "portfolio_contact") dan simpan
5. Catat **Service ID** yang diberikan

## Langkah 3: Membuat Template Email

1. Di dashboard EmailJS, klik "Email Templates" -> "Create New Template"
2. Beri nama template (misalnya "contact_form")
3. Buat template email dengan variabel berikut:
   ```
   Nama: {{name}}
   Email: {{email}}
   Pesan: {{message}}
   ```
4. Simpan template dan catat **Template ID** yang diberikan

## Langkah 4: Mendapatkan Public Key

1. Di dashboard EmailJS, klik "Account" -> "API Keys"
2. Catat **Public Key** Anda

## Langkah 5: Mengupdate Kode Aplikasi

Buka file `src/components/ContactSection.jsx` dan ganti placeholder berikut dengan nilai yang Anda catat:

```jsx
const serviceId = "YOUR_SERVICE_ID"; // Ganti dengan Service ID Anda
const templateId = "YOUR_TEMPLATE_ID"; // Ganti dengan Template ID Anda
const publicKey = "YOUR_PUBLIC_KEY"; // Ganti dengan Public Key Anda
```

## Catatan Penting

- Akun gratis EmailJS memiliki batas 200 email per bulan
- Pastikan nama field di form (`name`, `email`, `message`) sesuai dengan variabel di template email Anda
- Untuk keamanan lebih baik, pertimbangkan untuk menggunakan variabel lingkungan untuk menyimpan key-key ini

Setelah mengikuti langkah-langkah di atas, form kontak Anda akan mengirim email langsung ke alamat yang Anda konfigurasikan di EmailJS.
