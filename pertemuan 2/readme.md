## Praktikum 2

### LinkedList
Linked List adalah struktur data yang terdiri dari node-node yang saling terhubung. Setiap node menyimpan data dan pointer yang menunjuk ke node berikutnya. Tidak seperti array, data pada linked list tidak disimpan berurutan di memori, sehingga penambahan dan penghapusan elemen lebih fleksibel.

### Node
setiap node memiliki dua atribut, yaitu:
`data` -> nilai yang disimpan di node
`next` -> penunjuk ke node berikutnya

## Code Phyton
```python
class Node:
    def __init__(self, data=None, pointer=None) :
        self.data = data 
        self.next = pointer 

class LinkedList:
    def __init__(self):
       self.head = None

    def insert_at_first(self, data):
        node = Node(data, self.head)
        self.head = node

    def insert_at_last(self, data):
        if self.head is None:
           self.head = Node(data)
        else:
            node_sekarang = self.head
            while node_sekarang.next:
                node_sekarang = node_sekarang.next

            node = Node(data)
            node_sekarang.next = node

    def insert_at(self, index, data):
        if index < 0 or index > self.length() -1:
            print("index tidak valid")
        elif index == 0:
            self.insert_at_first(data)
        else:
            urutan = 0
            node_sekarang = self.head

            while urutan < index - 1:
                urutan += 1
                node_sekarang = node_sekarang.next

            node = Node(data, node_sekarang.next)
            node_sekarang.next = node

    def remove_first(self):
        if self.head is None:
            print("tidak ada data yang bisa di hapus")
        else: 
            self.head = self.head.next

    def remove_last(self):
        if self.head is None:
           print("tidak ada data yang bisa di hapus")
        elif self.head.next is None:
            self.head = None
        else:
            node_sebelumnya = None
            node_sekarang = self.head

            while node_sekarang.next:
                node_sebelumnya = node_sekarang
                node_sekarang = node_sekarang.next

            node_sebelumnya.next = None

    def remove_at(self, index):
        if index < 0 or index >= self.length(): 
            print("index invalid")
        elif index == 0:
            self.remove_first()
        else:
            urutan = 0
            node_sekarang = self.head

            while urutan < index - 1:
                node_sekarang = node_sekarang.next
                urutan += 1

            node_sekarang.next = node_sekarang.next.next

    def print(self):
        if self.head is None:
            print("data kosong")
        else:
            text_print = ""
            node_sekarang = self.head

            while node_sekarang:
                text_print += str(node_sekarang.data) + " -> "
                node_sekarang = node_sekarang.next

            print(text_print)

    def length(self):
        urutan = 0
        data_sekarang = self.head

        while data_sekarang:
            data_sekarang = data_sekarang.next
            urutan += 1

        return urutan
    
LL = LinkedList()

#insert
LL.insert_at_first("jeruk")
LL.insert_at_first("mangga")
LL.insert_at_first("manggis")
LL.insert_at_last("apel")
LL.insert_at(2, "anggur")

# remove
LL.remove_first()
LL.remove_last()
LL.remove_at(1)
LL.remove_at(1)

# print
LL.print()
print(LL.length())
```
## Penjelasan Per Fungsi
### `insert_at_first(data)`  
Menambahkan `data` di paling depan list. Node baru dibuat yang menunjuk ke head lama, lalu node baru menjadi head.

### `insert_at_last(data)`  
Menambahkan `data` di paling akhir list. Jika list kosong, langsung jadi head. Jika tidak, telusuri hingga node terakhir lalu tambahkan node baru.

### `insert_at(index, data)`  
Menambahkan `data` di posisi `index`. Validasi index; jika `index = 0` gunakan `insert_at_first`. Lainnya: telusuri hingga posisi sebelum index, sisipkan node baru.

### `remove_first()`  
Menghapus node pertama dengan mengarahkan head ke node berikutnya.

### `remove_last()`  
Menghapus node terakhir. Jika hanya satu node → head jadi `None`. Jika lebih, cari node sebelum terakhir dan set pointer-nya ke `None`.

### `remove_at(index)`  
Menghapus node di posisi `index`. Validasi index; jika `index = 0` gunakan `remove_first`. Lainnya: telusuri hingga sebelum index, skip node yang ingin dihapus.

### `print()`  
Menampilkan seluruh elemen list dalam format "`data1 -> data2 -> … -> `".

### `length()`  
Menghitung jumlah node dengan traversal dari head hingga akhir.

## Penjelasan Bagian Index
1. Cek apakah index valid

Program memastikan index tidak negatif dan tidak melebihi jumlah data.

Tujuannya:
Supaya program tidak error karena posisi yang diminta tidak ada.

2. Kalau index = 0

Artinya kita ingin menambah atau menghapus data pertama.

Maka program langsung memakai fungsi khusus:

``insert_at_first()`` untuk menambah di awal

``remove_first()`` untuk menghapus data pertama

Karena node pertama adalah posisi khusus di linked list.

3. Kalau index > 0

Program perlu berjalan dari awal (head) ke node berikutnya satu per satu sampai menemukan:

node sebelum posisi index

Contoh:Kalau mau masukin atau hapus di index 2, maka kita harus berhenti di index 1 (sebelumnya)

Ini dilakukan dengan loop sederhana.

4. Mengubah pointer

Setelah ketemu node sebelum index:

Untuk insert: Node baru disisipkan dengan menghubungkan pointer ke node berikutnya.

Untuk remove: Pointer dilewati ke node setelahnya, sehingga node pada index terlepas/hilang.

## Hasil Run Codingan  
Setelah menjalankan kode di atas, output yang dihasilkan adalah:
```
mangga -> 
1
```
Artinya hanya tersisa satu elemen, yaitu `mangga`.
