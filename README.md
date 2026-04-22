#Nama: widia hastuti(TI22250043)
#Nama: Shofia Aziz Muharromi(TI22250037)
#Nama: nurul laili(TI22250033)
#Nama: amelia yulviana putri(TI22250005)

from collections import deque

queue = deque()

while True:
    print("\n=== SISTEM ANTRIAN RESTORAN ===")
    print("1. Tambah Pesanan")
    print("2. Proses Pesanan")
    print("3. Lihat Antrian")
    print("4. Batalkan Pesanan")
    print("5. Keluar")

    pilihan = input("Pilih menu (1-5): ")

    if pilihan == "1":
        nama = input("Masukkan nama pesanan: ")
        queue.append(nama)
        print(f" Pesanan '{nama}' ditambahkan ke antrian")

    elif pilihan == "2":
        if not queue:
            print(" Antrian kosong")
        else:
            pesanan = queue.popleft()
            print(f" Memproses pesanan: {pesanan}")

    elif pilihan == "3":
        if not queue:
            print(" Antrian kosong")
        else:
            print(" Daftar antrian:")
            for i, item in enumerate(queue, start=1):
                print(f"{i}. {item}")

    elif pilihan == "4":
        if not queue:
            print(" Antrian kosong")
        else:
            nama = input("Masukkan nama pesanan yang ingin dibatalkan: ")
            if nama in queue:
                queue.remove(nama)  # hapus pesanan tertentu
                print(f"️ Pesanan '{nama}' dibatalkan")
            else:
                print(" Pesanan tidak ditemukan di antrian")

    elif pilihan == "5":
        print(" Program selesai")
        break

    else:
        print(" Pilihan tidak valid, coba lagi!")
