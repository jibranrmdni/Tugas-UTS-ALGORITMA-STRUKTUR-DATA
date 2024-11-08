# Tugas-UTS-ALGORITMA-STRUKTUR-DATA
# project kasir
### NAMA : Jibran Ramdani
### NIM : 312410419
### KELAS : TI.24.A.3

# Penjelasan mengenai project kasir ini
Mempunyai fitur pada kasir seperti :

a. Menambah barang ke dalam keranjang.

b. Menampilkan daftar barang.

c. Menghitung total harga.

d. Mencetak struk.

# Code Codingan Project Kasir 
```
class Barang:
    def __init__(self, nama_barang, harga_satuan, jumlah):
        self.nama_barang = nama_barang
        self.harga_satuan = harga_satuan
        self.jumlah = jumlah

    def total_harga(self):
        return self.harga_satuan * self.jumlah


class Keranjang:
    def __init__(self):
        self.daftar_barang = []

    def tambah_barang(self, barang):
        self.daftar_barang.append(barang)

    def tampilkan_barang(self):
        print("Daftar Barang dalam Keranjang:")
        for barang in self.daftar_barang:
            print(f"Nama: {barang.nama_barang}, Harga: {barang.harga_satuan}, Jumlah: {barang.jumlah}, Total: {barang.total_harga()}")

    def hitung_total_harga(self):
        total = sum(barang.total_harga() for barang in self.daftar_barang)
        return total

    def cetak_struk(self):
        print("\n===Struk Belanja===")
        self.tampilkan_barang()
        total_harga = self.hitung_total_harga()
        print(f"Total Harga: {total_harga}")
        print("Terimakasih Sudah Belanja di Toko Afif Serba Ada")


# Contoh penggunaan
class Kasir:
    def __init__(self):
        self.keranjang = []
    
    def tambah_barang(self, nama_barang, harga, jumlah):
        # Menambahkan barang ke dalam keranjang
        self.keranjang.append({
            'nama_barang': nama_barang,
            'harga': harga,
            'jumlah': jumlah,
            'total_harga': harga * jumlah
        })
        print(f"{nama_barang} telah ditambahkan ke keranjang.")
    
    def tampilkan_barang(self):
        # Menampilkan daftar barang dalam keranjang
        if not self.keranjang:
            print("Keranjang masih kosong.")
        else:
            print("\nDaftar Barang di Keranjang:")
            for index, item in enumerate(self.keranjang, 1):
                print(f"{index}. {item['nama_barang']} - {item['jumlah']} x {item['harga']} = {item['total_harga']}")
    
    def hitung_total(self):
        # Menghitung total harga dari semua barang di keranjang
        total = sum(item['total_harga'] for item in self.keranjang)
        return total
    
    def cetak_struk(self):
        # Mencetak struk pembelian
        if not self.keranjang:
            print("Keranjang kosong. Tidak ada struk yang dapat dicetak.")
            return
        
        print("\n----- Struk Pembelian -----")
        for item in self.keranjang:
            print(f"{item['nama_barang']} ({item['jumlah']} x {item['harga']}) = {item['total_harga']}")
        
        total_harga = self.hitung_total()
        print("\n-------------------------")
        print(f"Total Harga: {total_harga}")
        print("Terima kasih atas kunjungannya!\n")
    
# Contoh Penggunaan
def main():
    kasir = Kasir()
    
    # Menambahkan barang ke keranjang
    kasir.tambah_barang("Arak bali", 60000, 3)
    kasir.tambah_barang("ice land", 155000, 2)
    kasir.tambah_barang("whisky", 310000, 1)
    
    # Menampilkan daftar barang
    kasir.tampilkan_barang()
    
    # Menghitung total harga
    total = kasir.hitung_total()
    print(f"\nTotal harga semua barang: {total}")
    
    # Mencetak strukA
    kasir.cetak_struk()

if __name__ == "__main__":
    main()
```

# Contoh Hasil Dari Codingan Project
![Screenshot 2024-11-08 090929](https://github.com/user-attachments/assets/0cd9c3c2-c376-46d9-9977-fe0962269bba).

)


# Penjelasan Singkat Mengenai Algoritma Pada Project Kasir 

- Membuat kelas Barang: Kelas Barang menyimpan data tentang barang, termasuk nama, harga satuan, dan jumlah.

- Membuat kelas Keranjang: Kelas Keranjang menyimpan daftar barang yang dibeli dan menyediakan fungsi untuk menambah barang, menampilkan barang, menghitung total harga, dan mencetak struk.

- Menambahkan barang ke keranjang: Program meminta pengguna untuk memasukkan nama barang, harga satuan, dan jumlah, lalu membuat objek Barang baru dengan data tersebut dan menambahkannya ke dalam keranjang.

- Menampilkan daftar barang: Program menampilkan daftar barang yang ada di keranjang, termasuk nama, harga satuan, jumlah, dan total harga per barang.

- Menghitung total harga: Program menghitung total harga semua barang di keranjang.

- Mencetak struk: Program mencetak struk yang berisi daftar barang, total harga, dan ucapan terima kasih.
