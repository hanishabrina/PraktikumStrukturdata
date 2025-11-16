## Praktikum 1

## Queue
Queue adalah sebuah struktur data yang menerapkan prinsip FIFO (First In, First Out), yang berarti elemen yang pertama kali masuk akan menjadi elemen pertama yang keluar.

### Codingan Queue 
```phyton
queue = []

# Enqueue
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue: ", queue)

# Dequeue
element = queue.pop(0)
print("Dequeue: ", element)

# Peek
frontElement = queue[0]
print("Peek: ", frontElement)

# isEmpty
isEmpty = not bool(queue)
print("isEmpty: ", isEmpty)

# Size
print("Size: ", len(queue))
```

### Penjelasan
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

### Hasil Run 
 ```python
Queue:  ['A', 'B', 'C']
Dequeue:  A
Peek:  B
isEmpty:  False
Size:  2 
```
### Kesimpulan 
Struktur data Queue pada Python dapat dibangun menggunakan tipe data list.
Cara kerjanya mengikuti konsep FIFO (First In, First Out), di mana elemen yang masuk lebih dulu akan dikeluarkan lebih dulu juga.

Beberapa operasi penting pada queue yaitu:

- `append()` → untuk menambahkan elemen baru ke bagian belakang antrian

- `pop(0)` → untuk mengeluarkan elemen yang berada di posisi paling depan

- `queue[0]` → untuk melihat isi elemen terdepan tanpa menghapusnya

Queue banyak dimanfaatkan dalam berbagai situasi seperti simulasi antrian, pengelolaan tugas pada printer, hingga pemrosesan data secara berurutan.


## Stack
Stack (tumpukan) adalah sebuah struktur data yang mengikuti prinsip LIFO (Last In, First Out), di mana elemen yang terakhir dimasukkan adalah yang pertama kali dikeluarkan.

### Codingan Stack
```phyton
stack = []

# Push
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack: ", stack)

# Pop
element = stack.pop()
print("Pop: ", element)

# Peek
topElement = stack[-1]
print("Peek: ", topElement)

# isEmpty
isEmpty = not bool(stack)
print("isEmpty: ", isEmpty)

# Size
print("Size: ", len(stack))
```

### Penjelasan
1. ```stack = [] ```
Baris ini digunakan untuk membuat tempat tumpukan kosong. Ibaratnya kita menyiapkan wadah sebelum menaruh data apa pun nantinya.

2.
```phyton
stack.append('A')
stack.append('B')
stack.append('C')
```

Ketiga baris tersebut berguna untuk menambahkan elemen ke dalam tumpukan.
Pada struktur data stack, penambahan dilakukan di posisi paling atas (prinsip LIFO), jadi elemen terakhir yang ditambahkan akan berada di bagian paling atas tumpukan.

3. ```element = stack.pop()```
pop() tanpa indeks akan menghapus elemen paling atas dari stack.
Ibaratnya, kita mengambil benda paling atas dari sebuah tumpukan.

4. ```topElement = stack[-1]```
Baris ini digunakan untuk melakukan peek, yaitu melihat elemen paling atas tanpa menghapusnya.
Jadi kita hanya mengecek "apa yang ada di bagian paling atas sekarang" tanpa mengubah isi tumpukan.

5. ```isEmpty = not bool(stack)```
Baris ini mengecek apakah stack masih berisi atau sudah kosong.
Jika stack ada isinya → bernilai False.
Jika kosong → bernilai True.

### Hasil Run
```
Stack:  ['A', 'B', 'C']
Pop:  C
Peek:  B
isEmpty:  False
Size:  2
```

### Kesimpulan
Struktur data Stack di Python dapat dibuat menggunakan tipe data list.
Cara kerjanya mengikuti prinsip LIFO (Last In, First Out), yaitu elemen yang terakhir dimasukkan akan menjadi elemen pertama yang dikeluarkan.

Operasi penting dalam stack meliputi:

- `append()` → menambah elemen baru ke bagian atas tumpukan

- `pop()` → menghapus elemen paling atas

- `stack[-1]` → melihat elemen paling atas tanpa menghapusnya

Stack banyak dipakai dalam berbagai situasi seperti undo/redo, manajemen pemanggilan fungsi (call stack), hingga proses yang membutuhkan urutan balik.
