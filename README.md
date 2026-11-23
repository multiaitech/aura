
## Platform Builds

| Platform | Build | Ukuran | Link unduh (di portal anggota) |
|----------|-------|--------|--------------------------------|
| Windows x64 | `windows-x64` | 137.7 MB | https://member.multiaitech.com/apps/downloads/latest/AURA?platform=windows-x64 |
| Windows ARM64 | `windows-arm64` | 136.3 MB | https://member.multiaitech.com/apps/downloads/latest/AURA?platform=windows-arm64 |
| Linux DEB | `linux-deb` | 96.1 MB | https://member.multiaitech.com/apps/downloads/latest/AURA?platform=linux-deb |
| Linux AppImage | `linux-appimage` | 173.6 MB | https://member.multiaitech.com/apps/downloads/latest/AURA?platform=linux-appimage |

**Catatan penting**  
Jika URL di atas menghasilkan 404, pastikan Anda membuka **portal anggota** (https://multiaitech.com/member.html) → **Apps & Downloads** dan pilih file yang sesuai. Build yang tidak dikenal akan selalu mengembalikan 404.

## Instalasi

### Windows (.exe)
1. Unduh file `.exe` dari link di tabel di atas.
2. Jalankan installer dan ikuti wizard yang tersedia.

### Linux (.deb)
1. Unduh file `.deb`.
2. Instal dengan perintah: `sudo dpkg -i <nama-file>.deb`.
3. Jika ada dependensi yang belum terpenuhi, jalankan `sudo apt install -f`.

### Linux (.AppImage)
1. Unduh file `.AppImage`.
2. Beri izin executable: `chmod +x <nama-file>.AppImage`.
3. Jalankan dengan `./<nama-file>.AppImage`.

## Verifikasi SHA-256

Setelah unduhan, periksa hash SHA-256 yang tercantum di portal anggota. Bandingkan dengan hasil `sha256sum <file>` di terminal untuk memastikan integritas file.
