# Belajar Golang Context

1. Context merupakan sebuah data yang membawa value, sinyal cancel, sinyal timeout dan sinyal deadline.
2. Context biasanya dibuat per request (misal setiap ada request masuk ke server web melalui http request)
3. Context digunakan untuk mempermudah kita meneruskan value dan sinyal antar proses.

## Kenapa Context Perlu diPelajar ?
-   Context Di golang biasa digunakan untuk mengirim data request atau sinyal ke proses lain.
-   Dengan menggunakan context, ketika kita ingin membatalkan semua proses, kita cukup mengirim sinyal ke context, maka secara otomatis semua proses akan dibatalkan.
-   Hampir semua bagian di Golang memanfaatkan context, seperti database, http server, http client, dll
-   Bahkan di google sendiri, ketika menggunakan Golang , context wajib digunakan dan selalu dikirim ke setiap function yang dikirim.

## Immutable
-   Context merupakan object yang immutable, artinya setelah Context dibuat, dia tidak bisa diubah lagi.
-   Ketika kita menambahkan value ke dalam context, atau menambahkan pengaturan timeout dan yang lainnya, secara otomatis akan membentuk child context baru, bukan merubah context tersebut.