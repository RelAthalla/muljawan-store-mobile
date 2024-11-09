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

1. 