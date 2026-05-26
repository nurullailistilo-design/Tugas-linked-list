# Tugas-linked-list
Daftar putar musik
# ==========================================
# PROGRAM DAFTAR PUTAR MUSIK (LINKED LIST)
# ==========================================

print("=" * 10, "DAFTAR PUTAR MUSIK", "=" * 10)


class Lagu:
    def __init__(self, judul):
        self.judul = judul
        self.next = None


class Playlist:
    def __init__(self):
        self.head = None

    # Menambah lagu
    def tambah_lagu(self, judul):
        lagu_baru = Lagu(judul)

        if self.head is None:
            self.head = lagu_baru
        else:
            sekarang = self.head
            while sekarang.next is not None:
                sekarang = sekarang.next
            sekarang.next = lagu_baru

    # Menampilkan lagu
    def tampilkan_playlist(self):
        sekarang = self.head

        if sekarang is None:
            print("Playlist kosong")
        else:
            print("\nDaftar Lagu:")
            nomor = 1

            while sekarang is not None:
                print(str(nomor) + ". " + sekarang.judul)
                sekarang = sekarang.next
                nomor += 1


playlist_saya = Playlist()

playlist_saya.tambah_lagu("Hati-Hati di Jalan")
playlist_saya.tambah_lagu("Komang")
playlist_saya.tambah_lagu("Sial")
playlist_saya.tambah_lagu("Rumah ke Rumah")

playlist_saya.tampilkan_playlist()
