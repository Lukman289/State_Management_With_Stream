# Nama  : Lukman Eka Septiawan
# Kelas : TI-3C

## Praktikum 1: Dart Streams
### Langkah 1: Buat Project Baru
    Buatlah sebuah project flutter baru dengan nama stream_nama (beri nama panggilan Anda) di folder week-13/src/ repository GitHub Anda.

![image for practicum 1 step 1](images/practicum/p1-1.png)

### Langkah 2: Buka file main.dart
    Ketiklah kode seperti berikut ini

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Stream Lukman',
      theme: ThemeData(
        primaryColor: Colors.deepPurple
      ),
      home: const StreamHomePage(),
    );
  }
}

class StreamHomePage extends StatefulWidget {
  const StreamHomePage({super.key});

  @override
  State<StreamHomePage> createState() => _StreamHomePageState();
}

class _StreamHomePageState extends State<StreamHomePage> {
  @override
  Widget build(BuildContext context) {
    return Container();
  }
}

```

> 1. Task
> - Tambahkan nama panggilan Anda pada title app sebagai identitas hasil pekerjaan Anda.
> - Gantilah warna tema aplikasi sesuai kesukaan Anda.
> - Lakukan commit hasil jawaban Soal 1 dengan pesan "W13: Jawaban Soal 1"

```dart
class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Stream Lukman',
      theme: ThemeData(
        primaryColor: Colors.blueAccent,
      ),
      home: const StreamHomePage(),
    );
  }
}
```

### Langkah 3: Buat file baru stream.dart
    Buat file baru di folder lib project Anda. Lalu isi dengan kode berikut.

```dart

```

### Langkah 4: Tambah variabel colors
    Tambahkan variabel di dalam class ColorStream seperti berikut.
    
```dart

```
> 2. Task
> - Tambahkan 5 warna lainnya sesuai keinginan Anda pada variabel colors tersebut.
> - Lakukan commit hasil jawaban Soal 2 dengan pesan "W13: Jawaban Soal 2"

### Langkah 5: Tambah method getColors()
    Di dalam class ColorStream ketik method seperti kode berikut. Perhatikan tanda bintang di akhir keyword async* (ini digunakan untuk melakukan Stream data)

```dart

```

### Langkah 6: Tambah perintah yield*
    Tambahkan kode berikut ini.

```dart
yield* Stream.periodic(
  const Duration(seconds: 1), (int t) {
    int index = t % colors.length;
    return colors[index];
});
```

> 3. Task
> - Jelaskan fungsi keyword yield* pada kode tersebut!
> - Apa maksud isi perintah kode tersebut?
> - Lakukan commit hasil jawaban Soal 3 dengan pesan "W13: Jawaban Soal 3"

## Langkah 7: Buka main.dart
    Ketik kode impor file ini pada file main.dart

```dart
import 'stream.dart';
```

## Langkah 8: Tambah variabel
    Ketik dua properti ini di dalam class _StreamHomePageState

```dart

```

## Langkah 9: Tambah method changeColor()
    Tetap di file main, Ketik kode seperti berikut

```dart

```

## Langkah 10: Lakukan override initState()
    Ketika kode seperti berikut

```dart

```

## Langkah 11: Ubah isi Scaffold()
    Sesuaikan kode seperti berikut.

```dart

```

## Langkah 12: Run Project
    Lakukan running pada aplikasi Flutter Anda, maka akan terlihat berubah warna background setiap detik.

![image for practicum 1 step 12]()

> 4. Task
> - Capture hasil praktikum Anda berupa GIF dan lampirkan di README.
> - Lakukan commit hasil jawaban Soal 4 dengan pesan "W13: Jawaban Soal 4"

## Langkah 13: Ganti isi method changeColor()
    Anda boleh comment atau hapus kode sebelumnya, lalu ketika kode seperti berikut.

```dart

```

> 5. Task
> - Jelaskan perbedaan menggunakan listen dan await for (langkah 9) !
> - Lakukan commit hasil jawaban Soal 5 dengan pesan "W13: Jawaban Soal 5"

> **Catatan** : Stream di Flutter memiliki fitur yang powerfull untuk menangani data secara async. Stream dapat dimanfaatkan pada skenario dunia nyata seperti real-time messaging, unggah dan unduh file, tracking lokasi user, bekerja dengan data sensor IoT, dan lain sebagainya.

## Praktikum 2: Stream controllers dan sinks
`StreamControllers` akan membuat jembatan antara `Stream` dan `Sink`. `Stream` berisi data secara sekuensial yang dapat diterima oleh subscriber manapun, sedangkan `Sink` digunakan untuk mengisi (injeksi) data.

Secara sederhana, StreamControllers merupakan stream management. Ia akan otomatis membuat stream dan sink serta beberapa method untuk melakukan kontrol terhadap event dan fitur-fitur yang ada di dalamnya.

Anda dapat membayangkan stream sebagai pipa air yang mengalir searah, dari salah satu ujung Anda dapat mengisi data dan dari ujung lain data itu keluar.
 
Di Flutter, Anda dapat menggunakan `StreamController` untuk mengontrol aliran data `stream`. Sebuah `StreamController` memiliki sebuah properti bernama sink yang berguna untuk insert data. Sedangkan properti `stream` berguna untuk menerima atau keluarnya data dari `StreamController` tersebut.

### Langkah 1: Buka file stream.dart
    Lakukan impor dengan mengetik kode ini.

```dart

```

### Langkah 2: Tambah class NumberStream
    Tetap di file stream.dart tambah class baru seperti berikut.

```dart

```

### Langkah 3: Tambah StreamController
    Di dalam class NumberStream buatlah variabel seperti berikut.

```dart

```

### Langkah 4: Tambah method addNumberToSink
    Tetap di class NumberStream buatlah method ini

```dart

```

### Langkah 5: Tambah method close()

```dart

```

### Langkah 6: Buka main.dart
    Ketik kode import seperti berikut

```dart

```

### Langkah 7: Tambah variabel
    Di dalam class _StreamHomePageState ketik variabel berikut

```dart

```

### Langkah 8: Edit initState()

```dart

```

### Langkah 9: Edit dispose()

```dart

```

### Langkah 10: Tambah method addRandomNumber()

```dart
void addRandomNumber() {
  Random random = Random();
  int myNum = random.nextInt(10);
  numberStream.addNumberToSink(myNum);
}
```

### Langkah 11: Edit method build()

```dart

```

### Langkah 12: Run Prokect
    Lakukan running pada aplikasi Flutter Anda, maka akan terlihat seperti gambar berikut.

![image for practicum 2 step 12]()

> 6. Task
> - Jelaskan maksud kode langkah 8 dan 10 tersebut!
> - Capture hasil praktikum Anda berupa GIF dan lampirkan di README.
> - Lalu lakukan commit dengan pesan "W13: Jawaban Soal 6".

## Langkah 13: Buka stream.dart
    Tambahkan method berikut ini.

```dart

```

## Langkah 14: Buka main.dart
    Tambahkan method onError di dalam class StreamHomePageState pada method listen di fungsi initState() seperti berikut ini.

```dart

```

## Langkah 15: Edit method addRandomNumber()
    Lakukan comment pada dua baris kode berikut, lalu ketik kode seperti berikut ini.

```dart

```

> 7. Task
> - Jelaskan maksud kode langkah 13 sampai 15 tersebut!
> - Kembalikan kode seperti semula pada Langkah 15, comment addError() agar Anda dapat melanjutkan ke praktikum 3 berikutnya.
> - Lalu lakukan commit dengan pesan "W13: Jawaban Soal 7".

## Praktikum 3: Injeksi data ke streams
Skenario yang umum dilakukan adalah melakukan manipulasi atau transformasi data stream sebelum sampai pada UI end user. Hal ini sangatlah berguna ketika Anda membutuhkan untuk filter data berdasarkan kondisi tertentu, melakukan validasi data, memodifikasinya, atau melakukan proses lain yang memicu beberapa output baru. Contohnya melakukan konversi angka ke string, membuat sebuah perhitungan, atau menghilangkan data yang berulang terus tampil.

Pada praktikum 3 ini, Anda akan menggunakan `StreamTransformers` ke dalam `stream` untuk melakukan `map` dan filter data.

### Langkah 1: Buka main.dart
    Tambahkan variabel baru di dalam class _StreamHomePageState

```dart

```

### Langkah 2: Tambahkan kode ini di initState

```dart

```

### Langkah 3: Tetap di initState
    Lakukan edit seperti kode berikut.

```dart

```

### Langkah 4: Run Project
    Terakhir, run atau tekan F5 untuk melihat hasilnya jika memang belum running. Bisa juga lakukan hot restart jika aplikasi sudah running. Maka hasilnya akan seperti gambar berikut ini. Anda akan melihat tampilan angka dari 0 hingga 90.

![Image for Practicum 3 step 4]()

> 8. Task
> - Jelaskan maksud kode langkah 1-3 tersebut!
> - Capture hasil praktikum Anda berupa GIF dan lampirkan di README.
> - Lalu lakukan commit dengan pesan "W13: Jawaban Soal 8".

## Praktikum 4: Subscribe ke stream events
Dari praktikum sebelumnya, Anda telah menggunakan method `listen` mendapatkan nilai dari `stream`. Ini akan menghasilkan sebuah `Subscription`. `Subscription` berisi method yang dapat digunakan untuk melakukan `listen` pada suatu event dari `stream` secara terstruktur.

Pada praktikum 4 ini, kita akan gunakan `Subscription` untuk menangani event dan error dengan teknik praktik baik (best practice), dan menutup `Subscription` tersebut.

### Langkah 1: Tambah variabel
    Tambahkan variabel berikut di class _StreamHomePageState

```dart

```

### Langkah 2: Edit initState()
    Edit kode seperti berikut ini.

```dart

```

### Langkah 3: Tetap di initState()
    Tambahkan kode berikut ini.

```dart

```

### Langkah 4: Tambah properti onDone()
    Tambahkan dibawahnya kode ini setelah onError

```dart

```

### Langkah 5: Tambah method baru
    Ketik method ini di dalam class _StreamHomePageState

```dart

```

### Langkah 6: Pindah ke method dispose()
    Jika method dispose() belum ada, Anda dapat mengetiknya dan dibuat override. Ketik kode ini didalamnya.

```dart

```

### Langkah 7: Pindah ke method build()
    Tambahkan button kedua dengan isi kode seperti berikut ini.

```dart

```

### Langkah 8: Edit method addRandomNumber()
    Edit kode seperti berikut ini.

```dart

```

### Langkah 9: Run Project
    Anda akan melihat dua button seperti gambar berikut.

![Image for Practicum 4 step 9]()

### Langkah 10: Tekan button ‘Stop Subscription'
    Anda akan melihat pesan di Debug Console seperti berikut.

![Image for Practicum 4 step 10]()

> 9. Task
> - Jelaskan maksud kode langkah 2, 6 dan 8 tersebut!
> - Capture hasil praktikum Anda berupa GIF dan lampirkan di README.
> - Lalu lakukan commit dengan pesan "W13: Jawaban Soal 9".

## Praktikum 5: Multiple stream subscriptions
Secara default, stream hanya bisa digunakan untuk satu subscription. Jika Anda mencoba untuk melakukan subscription yang sama lebih dari satu, maka akan terjadi error. Untuk menangani hal itu, tersedia broadcast stream yang dapat digunakan untuk multiple subscriptions. Pada praktikum ini, Anda akan mencoba untuk melakukan multiple stream subscriptions.

### Langkah 1: Buka file main.dart
    Ketik variabel berikut di class _StreamHomePageState

```dart

```

### Langkah 2: Edit initState()
    Ketik kode seperti berikut.

```dart

```

### Langkah 3: Run Project
    Lakukan run maka akan tampil error seperti gambar berikut.

![Image for Practicum 5 step 3]()

> 10. Task
> - Jelaskan mengapa error itu bisa terjadi ?.

### Langkah 4: Set broadcast stream
    Ketik kode seperti berikut di method initState()

```dart

```

### Langkah 5: Edit method build()
Tambahkan text seperti berikut

```dart

```

### Langkah 6: Run Project
Tekan button '**New Random Number**' beberapa kali, maka akan tampil teks angka terus bertambah sebanyak dua kali.

![Image for Practicum 5 step 6]()

> 11. Task
> - Jelaskan mengapa hal itu bisa terjadi ?
> - Capture hasil praktikum Anda berupa GIF dan lampirkan di README.
> - Lalu lakukan commit dengan pesan "W13: Jawaban Soal 10,11".

## Praktikum 6: StreamBuilder
`StreamBuilder` adalah sebuah widget untuk melakukan listen terhadap 
event dari stream. Ketika sebuah event terkirim, maka akan 
dibangun ulang semua turunannya. Seperti halnya widget `FutureBuilder` 
pada pertemuan pekan lalu, `StreamBuilder` berguna untuk membangun UI secara reaktif yang diperbarui 
setiap data baru tersedia.

### Langkah 1: Buat Project Baru
    Buatlah sebuah project flutter baru dengan nama streambuilder_nama (beri nama panggilan Anda) di folder week-13/src/ repository GitHub Anda.

![Image for Practicum 6 step 1]()

### Langkah 2: Buat file baru stream.dart
    Ketik kode ini

```dart

```
    
### Langkah 3: Tetap di file stream.dart
    Ketik kode seperti berikut.

```dart

```

### Langkah 4: Edit main.dart
    Ketik kode seperti berikut ini.

```dart

```

```dart

```

### Langkah 5: Tambah variabel
    Di dalam `class _StreamHomePageState`, ketika variabel ini.

```dart

```

### Langkah 6: Edit initState()
    Ketik kode seperti berikut.

```dart

```

### Langkah 7: Edit method build()

```dart

```

### Langkah 8: Run Project
    Hasilnya, setiap detik akan tampil angka baru seperti berikut.

![Image for Practicum 6 step 8]()

> 12. Task
> - Jelaskan maksud kode pada langkah 3 dan 7 !
> - Capture hasil praktikum Anda berupa GIF dan lampirkan di README.
> - Lalu lakukan commit dengan pesan "W13: Jawaban Soal 12".

## Praktikum 7: BLoC Pattern
Ketika menggunakan pola BLoC, maka segalanya merupakan stream event. BLoC atau Business Logic Component adalah lapisan antara semua sumber data dan UI yang mengonsumsi data itu. Contohnya seperti sumber data dari HTTP layanan web servis atau JSON dari sebuah basis data.

Sebuah BLoC menerima stream data dari sumbernya, proses itu membutuhkan logika bisnis Anda, dan return stream data ke subscriber-nya. Perhatikan diagram pola kerja BLoC berikut ini.

![Image for Practicum 7]()

Alasan utama menggunakan BLoC adalah memisahkan logika bisnis aplikasi dengan presentasi UI pada widget, terutama akan sangat berguna ketika aplikasi Anda mulai semakin kompleks dan membutuhkan akses state di berbagai tempat. Hal ini akan membuat semakin mudah dalam menggunakan kode Anda, pada beberapa bagian di aplikasi atau bahkan berbeda aplikasi. Selain itu, BLoC secara independen berdiri sendiri dengan UI, sehingga sangat mudah dilakukan isolasi dalam proses testing.

Pada praktikum codelab ini, Anda akan membuat aplikasi sederhana menggunakan BLoC, namun Anda dapat dengan mudah mengembangkannya untuk aplikasi yang lebih besar ruang lingkupnya.

### Langkah 1: Buat Project baru
    Buatlah sebuah project flutter baru dengan nama bloc_random_nama (beri nama panggilan Anda) di folder week-13/src/ repository GitHub Anda. Lalu buat file baru di folder lib dengan nama random_bloc.dart

![Image for Practicum 7 step 1]()

### Langkah 2: Isi kode random_bloc.dart
    Ketik kode impor berikut ini.

```dart

```

### Langkah 3: Buat class RandomNumberBloc()

```dart

```

### Langkah 4: Buat variabel StreamController
    Di dalam class RandomNumberBloc() ketik variabel berikut ini

```dart

```

### Langkah 5: Buat constructor

```dart

```

### Langkah 6: Buat method dispose()

```dart

```

### Langkah 7: Edit main.dart

```dart

```

### Langkah 8: Buat file baru random_screen.dart
    Di dalam folder lib project Anda, buatlah file baru ini.

![Image for Practicum 7 step 8]()

### Langkah 9: Lakukan impor material dan random_bloc.dart
    Ketik kode ini di file baru random_screen.dart

```dart

```

### Langkah 10: Buat StatefulWidget RandomScreen
Buatlah di dalam file random_screen.dart

![Image for Practicum 7 step 10]()

### Langkah 11: Buat variabel
    Ketik kode ini di dalam class _RandomScreenState

```dart

```

### Langkah 12: Buat method dispose()
    Ketik kode ini di dalam class _StreamHomePageState

```dart

```

### Langkah 13: Edit method build()
    Ketik kode ini di dalam class _StreamHomePageState

```dart

```

    Run aplikasi, maka Anda akan melihat angka acak antara angka 0 sampai 9 setiap kali menekan tombol FloactingActionButton.

> 13. Task
> - Jelaskan maksud praktikum ini ! Dimanakah letak konsep pola BLoC-nya ?
> - Capture hasil praktikum Anda berupa GIF dan lampirkan di README.
> - Lalu lakukan commit dengan pesan "W13: Jawaban Soal 13".