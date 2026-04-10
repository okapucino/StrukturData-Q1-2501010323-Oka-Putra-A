# StrukturData-Q1-2501010323-Oka-Putra-A

## Jawaban Quis 1 Struktur Data: Array dan Linked List

**1. Karakteristik Memori dan Akses Data**
Operasi akses elemen pada **Array** dapat dilakukan dalam waktu konstan $O(1)$ karena array menggunakan alokasi **memori yang kontinu** (bersebelahan). Komputer dapat langsung menghitung alamat memori elemen ke-$i$ menggunakan rumus matematika sederhana *(Base Address + (Index * Data Size))*, sehingga langsung menuju ke elemen tersebut tanpa harus melewati elemen lain.
Sedangkan pada **Singly Linked List**, alokasi memorinya bersifat **non-kontinu** (tersebar). Untuk mengakses elemen ke-$i$, program tidak bisa menebak lokasi memorinya, melainkan harus menelusuri (*traverse*) pointer dari node pertama (`head`) satu per satu hingga mencapai node yang dituju. Inilah yang membuatnya membutuhkan waktu linear $O(n)$.

**2. Analisis Efisiensi Operasi Manipulasi**
Linked List lebih diunggulkan dibandingkan Array pada kondisi **penyisipan (insertion) atau penghapusan (deletion) data di awal atau di tengah urutan**, dengan asumsi kita sudah berada di posisi tersebut. 
**Alasan teoritisnya:** Pada Array, menyisipkan atau menghapus elemen di awal/tengah mewajibkan kita untuk menggeser (*shifting*) semua elemen setelahnya agar posisi tetap kontinu, yang memakan waktu $O(n)$. Sedangkan pada Linked List, kita hanya perlu mengubah arah referensi (*pointer*) dari node yang bersangkutan tanpa harus menggeser elemen lain, sehingga kompleksitas waktunya bisa mencapai $O(1)$.

**3. Konsep Doubly Linked List**
*   **Struktur Anatomi Node:** Sebuah node pada Doubly Linked List memiliki 3 bagian, yaitu: **Data** (menyimpan nilai), **Pointer Next** (menunjuk ke node selanjutnya), dan **Pointer Prev** (menunjuk ke node sebelumnya).
*   **Dampak Penggunaan Memori:** Lebih boros memori dibandingkan Singly Linked List karena setiap node harus menyimpan satu pointer tambahan (`prev`).
*   **Fleksibilitas Penelusuran:** Jauh lebih fleksibel. Adanya pointer `prev` memungkinkan penelusuran secara dua arah (*bidirectional*), baik maju dari `head` ke `tail` maupun mundur dari `tail` ke `head`. Ini juga membuat operasi penghapusan node tertentu menjadi lebih mudah karena kita langsung tahu node sebelumnya.

**4. Mekanisme Circular Linked List**
*   **Perbedaan Teoritis:** Pada Linked List biasa, pointer `next` pada node terakhir (tail) akan menunjuk ke `NULL`. Pada Circular Linked List, pointer `next` pada node terakhir tidak menunjuk ke `NULL`, melainkan menunjuk kembali ke node pertama (`head`), sehingga membentuk siklus/lingkaran yang tidak terputus.
*   **Contoh Skenario Penggunaan (Use Case):** Sangat efektif digunakan untuk **Sistem Penjadwalan CPU (Round-Robin Scheduling)** di mana setiap proses mendapat jatah waktu bergantian dan terus berputar kembali ke proses pertama. Contoh lain adalah rotasi giliran pemain dalam *multiplayer board game* bergilir.

**5. Array Dinamis di Python**
Ketika sebuah *Dynamic Array* (Python `list`) kehabisan kapasitas saat melakukan operasi `append`, mekanisme "di balik layar" yang terjadi adalah:
1.  **Alokasi Memori Baru:** Python akan membuat array baru di lokasi memori yang berbeda dengan kapasitas yang lebih besar (biasanya kapasitasnya membesar dengan rasio tertentu, misal 1.125x atau lebih besar dari kapasitas lama).
2.  **Menyalin Data (Copying):** Semua elemen dari array lama disalin satu per satu ke dalam array yang baru.
3.  **Menambahkan Elemen Baru:** Elemen yang di-`append` tadi dimasukkan ke indeks kosong berikutnya di array baru.
4.  **Dealokasi:** Array lama yang sudah penuh dan tidak terpakai akan dihapus dari memori (*garbage collected*), dan array baru kini menjadi representasi dari list tersebut.
