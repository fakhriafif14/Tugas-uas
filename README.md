#TUGAS UAS

1. **Menu dan Harga:**
   ```python
   menu = {
       'Nasi bakar': 15000,
       'Mie rebus telor': 12000,
       'Ayam bakar': 18000,
       'baso aci' : 8000,
       'Es Teh': 5000,
       'Es Jeruk': 6000,
       'Air Mineral': 3000
   }
   ```
   - Sebuah dictionary yang berisi opsi makanan/minuman dan harganya.

2. **Fungsi Tampilkan Menu:**
   ```python
   def tampilkan_menu():
       print("Menu Makanan/Minuman:")
       for item, harga in menu.items():
           print(f"{item}: Rp {harga}")
   ```
   - Fungsi ini digunakan untuk menampilkan menu makanan/minuman beserta harganya.

3. **Fungsi Hitung Total:**
   ```python
   def hitung_total(harga, jumlah):
       return harga * jumlah
   ```
   - Fungsi ini menghitung total harga berdasarkan harga per item dan jumlah yang dipesan.

4. **Fungsi Utama (Main):**
   ```python
   def main():
       pesanan = {}

       while True:
           tampilkan_menu()
           pilihan = input("Masukkan nama makanan/minuman yang ingin dipesan (ketik : 'sudah' untuk menampilkan struk): ")

           if pilihan.lower() == 'sudah':
               break

           if pilihan in menu:
               jumlah = int(input(f"Masukkan jumlah {pilihan}: "))
               harga_total = hitung_total(menu[pilihan], jumlah)
               pesanan[pilihan] = {'jumlah': jumlah, 'harga_total': harga_total}
           else:
               print("Menu tidak ada. Silakan pilih menu yang tersedia.")

       # Tampilkan struk pembelian
       print("\nStruk Pembelian:")
       total_pembelian = 0
       for item, detail in pesanan.items():
           print(f"{item} x{detail['jumlah']}: Rp {detail['harga_total']}")
           total_pembelian += detail['harga_total']

       print(f"\nTotal Pembelian: Rp {total_pembelian}")

   if __name__ == "__main__":
       main()
   ```
   - Fungsi `main` merupakan inti dari program. Pengguna diminta untuk memilih makanan/minuman dan memasukkan jumlahnya. Program akan terus berjalan hingga pengguna memilih untuk selesai (`sudah`).
   - Pesanan disimpan dalam bentuk dictionary (`pesanan`).
   - Setelah pengguna selesai memesan, program akan menampilkan struk pembelian berikut total harga pembelian.

Program ini memberikan pengguna kemampuan untuk memesan makanan/minuman, melihat menu, dan menerima struk pembelian dengan total harga.
