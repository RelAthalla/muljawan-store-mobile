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

# Tugas 9

1. Jelaskan mengapa kita perlu membuat model untuk melakukan pengambilan ataupun pengiriman data JSON? Apakah akan terjadi error jika kita tidak membuat model terlebih dahulu?

    Membuat model untuk melakukan pengambilan atau pengiriman data JSON dalam aplikasi memiliki beberapa keuntungan penting, meskipun tidak selalu menyebabkan error jika tidak dilakukan. Berikut penjelasan mengapa model diperlukan dan apa yang bisa terjadi jika tidak membuat model terlebih dahulu:

    Mengapa Membuat Model?
    1. Struktur Data yang Jelas: Model memberikan struktur yang jelas untuk data yang diambil atau dikirim. Ini membantu dalam memahami dan mengelola data dengan lebih baik.
    2. Validasi Data: Model dapat digunakan untuk memvalidasi data yang diterima atau dikirim, memastikan bahwa data tersebut sesuai dengan format yang diharapkan.
    3. Tipe Data yang Konsisten: Dengan model, tipe data untuk setiap atribut dapat ditentukan dengan jelas, mengurangi kemungkinan kesalahan tipe data.
    4. Kemudahan Penggunaan: Model memudahkan akses dan manipulasi data. Anda dapat menggunakan properti dan metode yang didefinisikan dalam model untuk bekerja dengan data.
    5. Pemeliharaan Kode: Kode yang menggunakan model lebih mudah dipelihara dan diperbarui. Perubahan pada struktur data hanya perlu dilakukan pada model, bukan di seluruh kode.

    Apa yang Terjadi Jika Tidak Membuat Model?
    1. Kesulitan dalam Pengelolaan Data: Tanpa model, pengelolaan data menjadi lebih sulit dan rentan terhadap kesalahan. Anda harus bekerja langsung dengan peta (map) atau daftar (list) yang tidak memiliki struktur yang jelas.
    2. Kesalahan Tipe Data: Tanpa model, lebih mudah terjadi kesalahan tipe data karena tidak ada validasi yang dilakukan secara otomatis.
    3. Kode yang Kurang Rapi: Kode yang bekerja langsung dengan JSON tanpa model cenderung menjadi berantakan dan sulit dibaca.
    4. Pemeliharaan yang Sulit: Mengubah struktur data menjadi lebih sulit karena Anda harus memperbarui setiap bagian kode yang bekerja dengan data tersebut.

2. Jelaskan fungsi dari library http yang sudah kamu implementasikan pada tugas ini

    Library http dalam Flutter digunakan untuk melakukan permintaan HTTP ke server. Ini memungkinkan aplikasi Flutter untuk berkomunikasi dengan API web, mengambil data dari server, atau mengirim data ke server. Berikut adalah beberapa fungsi utama dari library http dan bagaimana penggunaannya dalam tugas ini:

    Fungsi Utama Library http:
    1. Mengirim Permintaan HTTP: Library http menyediakan metode untuk mengirim berbagai jenis permintaan HTTP seperti GET, POST, PUT, DELETE, dll.
    2. Mengambil Data dari Server: Dengan metode GET, Anda dapat mengambil data dari server dan menggunakannya dalam aplikasi.
    3. Mengirim Data ke Server: Dengan metode POST, PUT, atau DELETE, Anda dapat mengirim data ke server untuk disimpan, diperbarui, atau dihapus.
    4. Mengelola Respons: Library ini juga menyediakan cara untuk mengelola respons dari server, termasuk menangani status kode dan parsing data JSON.

3. Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.

    CookieRequest adalah sebuah kelas atau utilitas yang digunakan dalam aplikasi Flutter untuk mengelola permintaan HTTP yang melibatkan penggunaan cookie. Fungsi utamanya meliputi:

    1. Manajemen Cookie: Menyimpan, mengirim, dan mengelola cookie yang diterima dari server. Ini penting untuk menjaga sesi pengguna dan autentikasi.
    2. Autentikasi dan Sesi: Memastikan bahwa setiap permintaan HTTP yang dikirim ke server menyertakan cookie yang diperlukan untuk autentikasi, sehingga pengguna tetap memiliki akses yang sah selama sesi.
    3. Pengaturan Header Permintaan: Menyederhanakan penambahan header khusus, termasuk cookie, ke setiap permintaan HTTP.
    4. Pengelolaan Status Permintaan: Menangani status respons dari server, seperti penanganan kesalahan atau refresh token jika diperlukan.

    Mengapa Instance CookieRequest Perlu Dibagikan ke Semua Komponen di Aplikasi Flutter

    1. Konsistensi:
    Dengan menggunakan satu instance CookieRequest yang dibagikan, semua komponen aplikasi menggunakan konfigurasi yang sama untuk permintaan HTTP. Ini memastikan bahwa cookie dan header lainnya konsisten di seluruh aplikasi.

    2. Manajemen Sesi yang Efisien:
    Satu instance memungkinkan pengelolaan sesi yang central, seperti menyimpan token autentikasi atau informasi pengguna, sehingga memudahkan pengelolaan status pengguna di seluruh aplikasi.

    3. Penghematan Sumber Daya:
    Membagikan satu instance mengurangi kebutuhan untuk membuat multiple instance yang bisa mengonsumsi lebih banyak memori dan sumber daya, serta menghindari potensi konflik atau inkonsistensi data.

    4. Kemudahan Pemeliharaan dan Pengembangan:
    Dengan memiliki satu titik pengelolaan permintaan HTTP, lebih mudah untuk memperbarui atau memperbaiki logika permintaan tanpa harus mengubah banyak bagian kode di berbagai komponen.

    5. Keamanan:
    Centralisasi pengelolaan cookie membantu dalam menerapkan kebijakan keamanan yang konsisten, seperti pengaturan cookie secure atau HttpOnly, yang penting untuk melindungi data pengguna.

4. Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.

    Proses pengiriman data dalam aplikasi Flutter dimulai ketika pengguna memasukkan informasi melalui elemen antarmuka seperti formulir atau widget input lainnya. Data yang diinput kemudian divalidasi secara lokal untuk memastikan kesesuaiannya sebelum diubah menjadi format JSON. Setelah data diformat, aplikasi menggunakan library HTTP untuk mengirim permintaan ke backend melalui metode seperti POST, disertai dengan header yang diperlukan seperti Content-Type: application/json dan token autentikasi jika diperlukan. Backend kemudian menerima dan memproses data tersebut, melakukan validasi lebih lanjut, menyimpan informasi ke database, atau menjalankan logika bisnis lainnya sebelum mengembalikan respons dalam format JSON kepada aplikasi Flutter.

    Setelah menerima respons dari backend, aplikasi Flutter akan mengurai data JSON tersebut menjadi objek Dart yang sesuai dan menangani setiap potensi error yang mungkin terjadi selama proses komunikasi. Data yang telah diuraikan kemudian digunakan untuk memperbarui state aplikasi melalui mekanisme manajemen state seperti setState, Provider, atau Bloc, sehingga antarmuka pengguna dapat di-render ulang dengan informasi terbaru. Misalnya, setelah berhasil mendaftar, aplikasi akan menampilkan pesan konfirmasi kepada pengguna. Dengan demikian, mekanisme ini memastikan bahwa setiap interaksi pengguna dengan aplikasi berlangsung secara efisien dan responsif, mulai dari pengisian input hingga tampilan hasil di antarmuka pengguna.

5. Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.

    Mekanisme autentikasi dalam aplikasi ini dimulai dengan pengguna memasukkan data akun di aplikasi Flutter pada halaman login atau register. Pada halaman login, pengguna memasukkan username dan password, yang kemudian dikirim ke server Django melalui endpoint /auth/login/ menggunakan metode POST. Di server Django, data login ini diverifikasi melalui fungsi authenticate(); jika data valid, server akan menjalankan auth_login() untuk mencatat sesi pengguna dan mengembalikan respons JSON berisi pesan sukses, status True, dan username pengguna. Flutter menerima respons ini dan, jika login berhasil, menavigasi pengguna ke halaman menu utama (MyHomePage) sambil menampilkan pesan sambutan. Jika pengguna tidak memiliki akun, mereka dapat menggunakan halaman register, di mana data username, password, dan konfirmasi password dikirim ke endpoint /auth/register/. Django memvalidasi kecocokan password dan ketersediaan username, jika valid, server membuat akun baru dan mengirim respons sukses ke Flutter. Untuk logout, pengguna memilih opsi logout di Flutter, yang mengirim permintaan ke endpoint /auth/logout/. Django menjalankan auth_logout() untuk menghapus sesi pengguna dan mengembalikan pesan logout yang berhasil, setelah itu Flutter mengarahkan kembali ke halaman login, menyelesaikan proses autentikasi secara lengkap.

6. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step!

    1. Mengimplementasikan fitur register,login, dan logout pada project django. Serta menambahkan pbp_django_auth dan provider dan menambahkan cookie request pada page yang membutuhkan.

    2. Membuat model custom untuk melakukan parsing data pada json

    3. Membuat halaman yang menampilkan semua daftar item yang terdapat pada endpoint JSON di django yang terlah di deploy, yaitu name, price dan description

    4. Membuat halaman detail untuk setiap item yang terdapat pada halaman daftar Item dan Tampilkan seluruh atribut pada model item kamu pada halaman ini.

    5. Melakukan filter pada halaman daftar item dengan hanya menampilkan item yang terasosiasi dengan pengguna yang login.

    6. Menambahkan list product pada left drawer

    7. Menambahkan post json pada form pembuatan product.

    8. Membuat suatu login dan register page yang terintegrasi dengan views di django.