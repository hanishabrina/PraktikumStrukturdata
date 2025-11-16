## Praktikum 1

### Queue
Queue adalah sebuah struktur data yang menerapkan prinsip FIFO (First In, First Out), yang berarti elemen yang pertama kali masuk akan menjadi elemen pertama yang keluar.

1. ``` queue = [] ``` 
Baris ini dipakai untuk membuat tempat antrian kosong. Jadi kita menyiapkan wadah dulu sebelum memasukkan data apa pun.

2.
```phyton 
queue.append('A')
queue.append('B')
queue.append('C')
```          
Ketiga baris ini fungsinya menambahkan data ke dalam antrian.
Setiap append() memasukkan elemen baru ke bagian belakang, sama seperti orang yang datang ke loket lalu berdiri di barisan paling belakang.

4. ```element = queue.pop(0) ```
Kalau baris ini dijalankan, elemen paling depan akan diambil sekaligus dihapus dari antrian.
pop(0) artinya mengeluarkan data pada posisi paling awal.
Ibaratnya orang pertama di barisan dipanggil dulu.

5. ```frontElement = queue[0] ```
Bagian ini digunakan untuk melihat siapa yang berada di posisi paling depan sekarang, tanpa menghapusnya.
Jadi cuma mengintip “siapa berikutnya”.bukan itu

6. ```print("Peek: ", frontElement)```
Ini hanya menampilkan hasil intipan tadi, yaitu elemen paling depan.

7. ```isEmpty = not bool(queue)```
Pada baris ini, kita mengecek apakah antrian masih ada isinya atau sudah kosong.
Kalau antrian berisi → bool(queue) akan bernilai True.
not membalik nilainya, jadi akan menjadi False.
Kalau antrian kosong → hasilnya True.

8. ```print("Size: ", len(queue))```
Baris terakhir ini menghitung jumlah elemen yang tersisa di antrian dengan len(queue) lalu menampilkannya.

## Hasil Run 
 ```python
Queue:  ['A', 'B', 'C']
Dequeue:  A
Peek:  B
isEmpty:  False
Size:  2 
```
## Kesimpulan 
Struktur data Queue pada Python dapat dibangun menggunakan tipe data list.
Cara kerjanya mengikuti konsep FIFO (First In, First Out), di mana elemen yang masuk lebih dulu akan dikeluarkan lebih dulu juga.

Beberapa operasi penting pada queue yaitu:

- `append()` → untuk menambahkan elemen baru ke bagian belakang antrian

- `pop(0)` → untuk mengeluarkan elemen yang berada di posisi paling depan

- `queue[0]` → untuk melihat isi elemen terdepan tanpa menghapusnya

Queue banyak dimanfaatkan dalam berbagai situasi seperti simulasi antrian, pengelolaan tugas pada printer, hingga pemrosesan data secara berurutan.

