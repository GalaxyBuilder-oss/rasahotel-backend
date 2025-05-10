# Security Policy

## Supported Versions

Kami secara aktif memelihara versi utama berikut dari proyek ini:

| Versi | Didukung |
|-------|----------|
| 1.x   | ✅       |

Versi sebelum `1.0.0` tidak lagi menerima patch keamanan.

---

## 📢 Melaporkan Kerentanan

Jika Anda menemukan kerentanan dalam proyek ini, **harap JANGAN langsung membuka isu GitHub**. Demi keamanan pengguna lain:

1. Kirim email ke **galaxybuilder.oss@gmail.com** (ganti dengan email kamu).
2. Gunakan subjek: `[SECURITY] RasaHotel Vulnerability`.
3. Sertakan detail eksploitasi, bukti konsep, dan langkah reproduksi.

Kami berkomitmen untuk:
- Merespon dalam 72 jam
- Merilis patch dalam 7 hari kerja (jika valid)

---

## 🔒 Kebijakan Keamanan

### Autentikasi dan Otorisasi
- Sistem ini menggunakan **JWT** untuk autentikasi berbasis token.
- Endpoint diatur menggunakan `@PreAuthorize`, `@Secured`, atau konfigurasi `SecurityFilterChain`.

### Dependensi
- Kami menggunakan dependensi yang diperbarui dan memantau kerentanan via dependabot.
- Dependensi utama:
  - `spring-boot-starter-security`
  - `jjwt`
  - `midtrans-java-library`

### Enkripsi dan Penyimpanan
- Password dienkripsi menggunakan `BCryptPasswordEncoder`.
- Token disimpan secara aman pada client-side (misalnya, melalui cookie HttpOnly atau localStorage dengan pengamanan tambahan jika di web frontend).

### Logging dan Audit
- Akses endpoint sensitif dicatat menggunakan `spring-boot-starter-actuator`.

---

## 📆 Siklus Patch

Patch keamanan akan dirilis sebagai `patch release` (`1.x.x`) secepatnya setelah:
- Verifikasi kerentanan
- Pengujian regresi

---

## 🤝 Kontribusi Aman

Saat mengajukan PR:
- Hindari mengirim credential (API Key, token, dll.)
- Jangan ubah konfigurasi keamanan tanpa pembahasan di issue

---

## 🛡️ Tools yang Digunakan

- OWASP Dependency Check (via plugin atau GitHub Action)
- Spring Security Test
- SpotBugs + FindSecBugs

---

Terima kasih telah membantu menjaga keamanan proyek kami! 🚀
