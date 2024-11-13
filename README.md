# Muljawan Store

    Farrel Athalla Muljawan
    2306223925
    PBP E

# Tugas 7

1. Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget, dan jelaskan perbedaan dari keduanya.

    StatelessWidget adalah widget yang tidak memiliki state yang dapat berubah. Artinya, setelah widget ini dibuat, ia tidak akan berubah selama siklus hidupnya. StatelessWidget cocok digunakan untuk tampilan yang statis atau tidak memerlukan perubahan data.

    Contoh penggunaan StatelessWidget:
    ```python
    import 'package:flutter/material.dart';

    class MyStatelessWidget extends StatelessWidget {
        @override
        Widget build(BuildContext context) {
            return Scaffold(
            appBar: AppBar(
                title: Text('Stateless Widget'),
            ),
            body: Center(
                child: Text('Hello, I am a Stateless Widget!'),
            ),
            );
        }
    }
    ```

    StatefulWidget adalah widget yang memiliki state yang dapat berubah. Artinya, widget ini dapat berubah selama siklus hidupnya berdasarkan interaksi pengguna atau perubahan data. StatefulWidget cocok digunakan untuk tampilan yang dinamis atau memerlukan perubahan data.

    Contoh penggunaan StatefulWidget:
    ```python
    import 'package:flutter/material.dart';

    class MyStatefulWidget extends StatefulWidget {
        @override
        _MyStatefulWidgetState createState() => _MyStatefulWidgetState();
    }

    class _MyStatefulWidgetState extends State<MyStatefulWidget> {
        int _counter = 0;

        void _incrementCounter() {
            setState(() {
            _counter++;
            });
        }

        @override
        Widget build(BuildContext context) {
            return Scaffold(
            appBar: AppBar(
                title: Text('Stateful Widget'),
            ),
            body: Center(
                child: Column(
                mainAxisAlignment: MainAxisAlignment.center,
                children: <Widget>[
                    Text('You have pushed the button this many times:'),
                    Text(
                    '$_counter',
                    style: Theme.of(context).textTheme.headline4,
                    ),
                ],
                ),
            ),
            floatingActionButton: FloatingActionButton(
                onPressed: _incrementCounter,
                tooltip: 'Increment',
                child: Icon(Icons.add),
            ),
            );
        }
    }
    ```
    Perbedaan Utama

    State Management:

    StatelessWidget: Tidak memiliki state yang dapat berubah. StatefulWidget: Memiliki state yang dapat berubah.

    Penggunaan:

    StatelessWidget: Digunakan untuk tampilan yang statis. StatefulWidget: Digunakan untuk tampilan yang dinamis.

    Lifecycle:

    StatelessWidget: Dibuat sekali dan tidak berubah. StatefulWidget: Dapat berubah selama siklus hidupnya melalui metode setState.

2. Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya.

    - Material App Berfungsi sebagai root aplikasi Flutter dan mengatur tema, nama aplikasi, serta konfigurasi awal. Ini mengatur navigasi dan tampilan keseluruhan aplikasi.
    - Scaffold Menyediakan struktur dasar layar, seperti AppBar, Body, dan Bottom Navigation. Di sini digunakan untuk membangun tampilan utama aplikasi.
    Text Menampilkan teks statis atau dinamis sesuai dengan data yang diberikan.
    - Padding Menambahkan ruang di sekitar widget agar tampilan lebih rapi.
    - Column Mengatur tata letak widget secara vertikal
    - Row Mengatur tata letak secara horizontal
    - Card Menyediakan tampilan berupa kartu dengan elevation GridView.builder Membuat tata letak berbentuk grid secara dinamis berdasarkan data yang ada.
    - SliverGridDelegateWithFixedCrossAxisCount konfigurasi GridView yang menentukan jumlah kolom, spasi antar-kolom, dan antar-baris di grid.
    - ItemCard widget kustom yang menampilkan setiap item dalam grid dengan warna latar belakang tertentu dan ikon yang sesuai.
    - InkWell Memberikan efek ripple saat widget diketuk
    - MediaQuery Mendapatkan informasi ukuran layar, seperti lebar perangkat agar card lebih responsive terhadap layar
    - SnackBar Menampilkan notifikasi sementara di bagian bawah layar saat pengguna mengetuk item tertentu

3. Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.

    Fungsi setState() dalam Flutter digunakan untuk memberitahu framework bahwa ada perubahan pada state dari widget yang memerlukan pembaruan tampilan. Fungsi setState() sangat penting dalam widget yang bersifat stateful karena memungkinkan pembaruan tampilan berdasarkan perubahan data. Variabel yang terdampak adalah semua variabel state yang didefinisikan dalam kelas state dan digunakan dalam metode build(). Dalam code saya, belum terdefinisikan fungsi setState() karena semua widget yang saya gunakan bersifat stateless, seperti nama, npm, kelas, yang hanya diinisialisasikan sekali saja dan bersifat final

4. Jelaskan perbedaan antara const dengan final.

    Dalam Dart, const dan final adalah dua kata kunci yang digunakan untuk mendeklarasikan variabel yang nilainya tidak dapat diubah setelah diinisialisasi. Namun, ada perbedaan penting antara keduanya:

    - final

    Inisialisasi Sekali: Variabel yang dideklarasikan dengan final hanya dapat = - diinisialisasi sekali. Setelah diinisialisasi, nilainya tidak dapat diubah.
    Waktu Inisialisasi: Nilai dari variabel final dapat ditentukan pada saat runtime.
    Penggunaan: Digunakan ketika nilai variabel diketahui pada saat runtime dan tidak akan berubah setelah diinisialisasi.
    const

    - const

    Konstanta Kompilasi: Variabel yang dideklarasikan dengan const adalah konstanta kompilasi. Artinya, nilainya harus diketahui pada saat kompilasi dan tidak dapat diubah.
    Waktu Inisialisasi: Nilai dari variabel const harus ditentukan pada saat kompilasi.
    Penggunaan: Digunakan ketika nilai variabel diketahui pada saat kompilasi dan tidak akan pernah berubah.

5. Jelaskan bagaimana cara kamu mengimplementasikan checklist-checklist di atas.

    1. Membuat main.dart untuk base dari app yang akan dibuat. Terdapat fungsi main() untuk menjalankan widget-widget yang sudah dibuat. Serta menentukan colorScheme dari app.
    ```python
    void main() {
        runApp(const MyApp());
    }

    class MyApp extends StatelessWidget {
        const MyApp({super.key});

        // This widget is the root of your application.
        @override
        Widget build(BuildContext context) {
            return MaterialApp(
            title: 'Muljawan Store',
            theme: ThemeData(
                colorScheme: ColorScheme.fromSwatch(primarySwatch: Colors.deepPurple,).copyWith(secondary: Colors.deepPurple[400]),
                useMaterial3: true,
            ),
            home: MyHomePage(),
            );
        }
    }
    ```

    2. Membuat beberapa variabel final, constructor, dan list warna untuk memberikan warna yang berbeda di tiap button
    ```python
    MyHomePage({super.key});
        final String npm = '2306223925';
        final String name = 'Farrel Athalla Muljawan';
        final String className = 'PBP E';

        final List<ItemHomepage> items = [
            ItemHomepage("Lihat Daftar Produk", Icons.mood),
            ItemHomepage("Tambah Produk", Icons.add),
            ItemHomepage("Logout", Icons.logout),
        ];
    ```

    3. Membuat class ItemHomepage yang memiliki atribut nama dan icon
    ```python
    class ItemHomepage {
        final String name;
        final IconData icon;

        ItemHomepage(this.name, this.icon);
    }
    ```

    4. Membuat class ItemCard untuk menampung class-class ItemHomePage untuk menampung dan styling item name, icon, dan terdapat fungsi onTap() untuk menampilkan snackbar dengan fungsi built-in. Saya juga mengimplementasi fungsi getColor untuk mengganti warna tiap buttonnya.
    ```python
    class ItemCard extends StatelessWidget {
        // Menampilkan kartu dengan ikon dan nama.
        final ItemHomepage item; 
        const ItemCard(this.item, {super.key});
        Color getColor(String itemName) {
            switch (itemName) {
            case "Lihat Daftar Produk":
                return Colors.blue;
            case "Tambah Produk":
                return Colors.green;
            case "Logout":
                return Colors.red;
            default:
                return Colors.grey;
            }
        }
        @override
        Widget build(BuildContext context) {
            return Material(
            // Menentukan warna latar belakang dari tema aplikasi.
            color: getColor(item.name),
            // Membuat sudut kartu melengkung.
            borderRadius: BorderRadius.circular(12),
            
            child: InkWell(
                // Aksi ketika kartu ditekan.
                onTap: () {
                // Menampilkan pesan SnackBar saat kartu ditekan.
                ScaffoldMessenger.of(context)
                    ..hideCurrentSnackBar()
                    ..showSnackBar(
                    SnackBar(content: Text("Kamu telah menekan tombol ${item.name}!"))
                    );
                },
                // Container untuk menyimpan Icon dan Text
                child: Container(
                padding: const EdgeInsets.all(8),
                child: Center(
                    child: Column(
                    // Menyusun ikon dan teks di tengah kartu.
                    mainAxisAlignment: MainAxisAlignment.center,
                    children: [
                        Icon(
                        item.icon,
                        color: Colors.white,
                        size: 30.0,
                        ),
                        const Padding(padding: EdgeInsets.all(3)),
                        Text(
                        item.name,
                        textAlign: TextAlign.center,
                        style: const TextStyle(color: Colors.white),
                        ),
                    ],
                    ),
                ),
                ),
            ),
            );
        } 
    }
    ```

# Tugas 8

1. Apa kegunaan const di Flutter? Jelaskan apa keuntungan ketika menggunakan const pada kode Flutter. Kapan sebaiknya kita menggunakan const, dan kapan sebaiknya tidak digunakan?

    Dalam Flutter, kata kunci const digunakan untuk mendeklarasikan konstanta yang nilainya tetap dan tidak berubah selama runtime. Penggunaan const memiliki beberapa keuntungan dan pertimbangan kapan sebaiknya digunakan atau tidak digunakan.

    - Kegunaan const di Flutter
    const digunakan untuk mendeklarasikan nilai yang diketahui pada saat kompilasi dan tidak akan berubah selama runtime. Widget yang dideklarasikan sebagai const hanya akan dibuat sekali dan dapat digunakan kembali tanpa perlu dibuat ulang, yang dapat meningkatkan performa aplikasi. Menandakan bahwa nilai atau objek tersebut tidak akan berubah, yang dapat membantu dalam menulis kode yang lebih aman dan mudah dipahami.

    - Keuntungan Menggunakan const
    Menggunakan const dapat mengurangi jumlah objek yang perlu dibuat ulang, sehingga mengurangi beban pada garbage collector dan meningkatkan performa aplikasi. Membuat kode lebih aman dengan memastikan bahwa nilai-nilai tertentu tidak akan berubah selama runtime. Membuat kode lebih mudah dipahami dengan menunjukkan secara eksplisit bahwa nilai tersebut adalah konstan.

    - Kapan Sebaiknya Menggunakan const
    Gunakan const untuk nilai yang diketahui pada saat kompilasi dan tidak akan berubah selama runtime. Gunakan const untuk widget yang tidak memiliki state dan tidak berubah selama siklus hidup aplikasi.Gunakan const untuk objek yang digunakan berulang kali untuk menghindari pembuatan objek baru setiap kali digunakan.

2. Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini!

    - Column
    penggunaan: Column digunakan untuk menyusun widget anak secara vertikal (dari atas ke bawah).
    Properti Utama:
    mainAxisAlignment: Mengatur penyelarasan widget anak di sepanjang sumbu utama (vertikal).
    crossAxisAlignment: Mengatur penyelarasan widget anak di sepanjang sumbu silang (horizontal).
    children: Daftar widget anak yang akan disusun secara vertikal.

    contoh implementasi :
    ```python
    import 'package:flutter/material.dart';

    void main() {
    runApp(MyApp());
    }

    class MyApp extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
        return MaterialApp(
        home: Scaffold(
            appBar: AppBar(
            title: Text('Column Example'),
            ),
            body: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            crossAxisAlignment: CrossAxisAlignment.center,
            children: <Widget>[
                Text('Item 1'),
                Text('Item 2'),
                Text('Item 3'),
            ],
            ),
        ),
        );
    }
    }
    ```

    - Row
    Penggunaan: Row digunakan untuk menyusun widget anak secara horizontal (dari kiri ke kanan).
    Properti Utama:
    mainAxisAlignment: Mengatur penyelarasan widget anak di sepanjang sumbu utama (horizontal).
    crossAxisAlignment: Mengatur penyelarasan widget anak di sepanjang sumbu silang (vertikal).
    children: Daftar widget anak yang akan disusun secara horizontal.

    contoh implementasi:
    ```python
    import 'package:flutter/material.dart';

    void main() {
    runApp(MyApp());
    }

    class MyApp extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
        return MaterialApp(
        home: Scaffold(
            appBar: AppBar(
            title: Text('Row Example'),
            ),
            body: Row(
            mainAxisAlignment: MainAxisAlignment.center,
            crossAxisAlignment: CrossAxisAlignment.center,
            children: <Widget>[
                Text('Item 1'),
                Text('Item 2'),
                Text('Item 3'),
            ],
            ),
        ),
        );
    }
    }
    ```

3.  Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan!

    - Pada halaman form yang dibuat ini, elemen input yang digunakan terdiri dari tiga TextFormField, yaitu:

    Name: Menggunakan TextFormField untuk memasukkan teks yang merepresentasikan nama produk. Field ini dilengkapi dengan validasi agar tidak kosong dan memiliki panjang karakter antara 1 hingga 1000.

    Amount: Juga menggunakan TextFormField dengan keyboardType disetel ke TextInputType.number untuk memastikan input adalah angka. Elemen ini divalidasi agar tidak kosong, harus berupa angka positif, dan tidak boleh bernilai negatif.

    Description: Menggunakan TextFormField untuk memasukkan deskripsi produk. Field ini juga divalidasi agar tidak kosong dan panjang karakter minimal 10 hingga maksimal 2000.

    - Dan ada elemen input lain yang tidak digunakan, seperti: Checkbox: Digunakan untuk membuat opsi yang bisa dicentang, biasanya untuk persetujuan atau pengaturan pilihan biner.

    Radio: Digunakan untuk membuat pilihan dalam kelompok di mana hanya satu opsi yang dapat dipilih pada satu waktu.

    Switch: Digunakan untuk mengaktifkan atau menonaktifkan pengaturan dengan tampilan switch yang lebih interaktif.

    DropdownButton: Digunakan untuk membuat pilihan yang dapat dipilih dari daftar yang ditampilkan saat tombol ditekan.

    Slider: Digunakan untuk memilih nilai dari rentang tertentu, biasanya untuk mengatur volume, kecerahan, atau pengaturan tingkat lainnya.

    DatePicker: Digunakan untuk memilih tanggal, biasanya digunakan pada aplikasi yang memerlukan input tanggal seperti pemesanan atau penjadwalan.

4. Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?

    Ya, saya mengimplementasikan tema pada aplikasi yang saya buat. 
    Saya mendefinisikan warna utama dan warna sekunder menggunakan ThemeData dalam theme pada MaterialApp di 
    main.dart. Warna utama dan sekunder diatur melalui ColorScheme. 
    Misalnya, di kode ini, primarySwatch disetel ke Colors.deepPurple, dan warna sekunder (secondary) disetel ke warna ungu yang lebih terang.


5. Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?

    Metode navigasi yang saya gunakan dalam aplikasi ini adalah metode Navigator.push dan Navigator.pop. 
    Metode Navigator.push digunakan untuk menambahkan halaman baru ke dalam stack navigasi. 
    Dengan push, halaman baru ditempatkan di atas halaman sebelumnya, sehingga halaman tersebut akan menjadi halaman aktif yang dilihat oleh pengguna. 
    Halaman sebelumnya tetap ada di dalam stack, sehingga pengguna dapat kembali ke sana jika diperlukan.
    Sebaliknya, metode Navigator.pop digunakan untuk kembali ke halaman sebelumnya dalam stack. 
    Ketika pop dipanggil, Flutter menghapus halaman aktif dari stack dan kembali ke halaman sebelumnya. 
    Hal ini berguna dalam situasi di mana pengguna telah menyelesaikan suatu interaksi pada halaman saat ini dan ingin kembali. Selain itu, saya juga membuat sebuah drawer untuk mempermudah navigasi di dalam app.

        