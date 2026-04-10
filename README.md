# StrukturData-Q1-2501010323-Oka-Putra-A

Jawaban Quis 1 Struktur Data: Array dan Linked List

1. Karakteristik Memori dan Akses Data
Operasi akses elemen pada Array dapat dilakukan dalam waktu konstan O(1) karena array menggunakan alokasi memori yang kontinu (bersebelahan). Komputer dapat langsung menghitung alamat memori elemen tujuan menggunakan indeks sehingga tidak perlu melewati elemen lain. 
Sedangkan pada Singly Linked List, alokasi memorinya bersifat non-kontinu (tersebar). Untuk mengakses elemen, program harus menelusuri pointer dari node pertama (head) satu per satu hingga mencapai node tujuan, sehingga membutuhkan waktu linear O(n).

2. Analisis Efisiensi Operasi Manipulasi
Linked List lebih diunggulkan dibandingkan Array pada kondisi penyisipan (insertion) dan penghapusan (deletion) data di awal atau di tengah urutan. 
Alasan teoritisnya: Pada Array, menyisipkan atau menghapus elemen di awal/tengah mewajibkan kita menggeser elemen-elemen lainnya agar memori tetap kontinu, yang memakan waktu O(n). Sedangkan pada Linked List, kita hanya perlu mengubah arah pointer dari node yang bersangkutan tanpa menggeser elemen lain, sehingga kompleksitas waktunya O(1).

3. Konsep Doubly Linked List
Struktur anatomi node pada Doubly Linked List memiliki 3 bagian: Data (menyimpan nilai), Pointer Next (menunjuk ke node selanjutnya), dan Pointer Prev (menunjuk ke node sebelumnya).
Dampak penggunaan memori: Lebih boros memori dibandingkan Singly Linked List karena setiap node harus menyimpan satu pointer tambahan.
Fleksibilitas penelusuran: Jauh lebih fleksibel karena penelusuran bisa dilakukan secara dua arah, baik maju maupun mundur.

4. Mekanisme Circular Linked List
Perbedaan teoritis: Pada Linked List biasa, pointer next pada node terakhir (tail) menunjuk ke NULL. Pada Circular Linked List, pointer next pada node terakhir tidak menunjuk ke NULL, melainkan menunjuk kembali ke node pertama (head), sehingga membentuk siklus melingkar.
Contoh use case: Sistem penjadwalan proses pada CPU (Round-Robin Scheduling) di mana setiap proses mendapat jatah waktu bergantian dan terus berputar kembali ke proses pertama.

5. Array Dinamis di Python
Ketika Dynamic Array (seperti list pada Python) kehabisan kapasitas saat melakukan operasi append, mekanisme yang terjadi di balik layar adalah:
- Python mengalokasikan memori baru (array baru) dengan kapasitas yang lebih besar.
- Semua elemen data dari array lama disalin satu per satu ke dalam array yang baru.
- Elemen data baru yang di-append kemudian dimasukkan ke array baru.
- Memori array lama dihapus/dikosongkan, dan array baru kini digunakan sebagai representasi list tersebut.
