# Tugas Individu 7

1. #### **Jelaskan apa yang dimaksud dengan *stateless widget dan stateful widget*, dan jelaskan perbedaan dari keduanya.**

*Stateless Widget*  
adalah widget yang tidak dapat berubah selama masa hidupnya. Setelah dibuat, *state* dari widget ini bersifat tetap atau konstan. *State* ini biasanya digunakan untuk elemen yang tidak memerlukan perubahan data secara dinamis, seperti label teks, ikon, dan tombol dengan gaya yang tidak berubah.

*Stateful Widget*  
adalah widget yang memiliki *state* internal yang dapat berubah selama masa hidupnya. Widget ini dapat diperbarui, dan perubahan pada *state* ini akan menyebabkan widget direbuild (dibuat ulang) untuk mencerminkan perubahan tersebut. *State* ini cocok untuk elemen-elemen yang membutuhkan perubahan data atau tampilan secara dinamis, seperti penghitung (counter), kolom input teks, atau elemen yang merespons interaksi pengguna (misalnya, ketika tombol ditekan atau ketika data dari API diperbarui).

Perbedaan antara *Stateless Widget* dan *Stateful Widget* adalah:  
***Stateless Widget***:

* **Tidak memiliki state yang berubah**: *Stateless Widget* bersifat statis dan tidak dapat berubah setelah dibuat.  
* **Digunakan untuk elemen statis**: Cocok untuk widget yang tidak memerlukan perubahan, seperti teks, ikon, atau gambar tetap.  
* **Tidak perlu memperbarui UI**: Karena data atau tampilannya tidak berubah, widget ini tidak perlu diperbarui ulang saat aplikasi berjalan.  
* **Kinerja lebih ringan**: *Stateless Widget* lebih ringan karena tidak mengelola *state*, sehingga lebih efisien dalam penggunaan memori.

***Stateful Widget***:

* **Memiliki state yang dapat berubah**: *Stateful Widget* dapat memiliki *state* internal yang memungkinkan perubahan data selama widget digunakan.  
* **Digunakan untuk elemen dinamis**: Cocok untuk widget yang memerlukan pembaruan, seperti tombol interaktif, form input, atau komponen yang menampilkan data yang berubah.  
* **UI dapat diperbarui dengan setState()**: Perubahan pada *state* dapat dilakukan dengan memanggil `setState()`, yang akan memperbarui tampilan sesuai data terbaru.  
* **Kinerja lebih berat**: *Stateful Widget* sedikit lebih berat karena harus mengelola *state*, tetapi ini penting untuk elemen yang membutuhkan interaksi.


2. #### **Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya.**

* **`Scaffold`**:  
  * Menyediakan struktur dasar halaman dengan `AppBar` dan `body`.  
  * Mengatur tata letak dasar aplikasi, termasuk area untuk konten utama dan AppBar di bagian atas.  
* **`AppBar`**:  
  * Menampilkan header di bagian atas halaman.  
  * Pada contoh ini, `AppBar` digunakan untuk menampilkan judul aplikasi "Shopeeta" dengan warna teks putih dan latar belakang yang sesuai dengan skema warna tema.  
* **`Padding`**:  
  * Menambahkan jarak di sekitar widget.  
  * Pada contoh ini, digunakan di `body` untuk memberikan padding di sekitar seluruh konten halaman.  
* **`Column`**:  
  * Menyusun widget secara vertikal.  
  * Digunakan di dalam `body` untuk menempatkan beberapa widget seperti `Row`, teks sambutan, dan `GridView.count`.  
* **`Row`**:  
  * Menyusun widget secara horizontal.  
  * Pada contoh ini, digunakan untuk menampilkan tiga `InfoCard` secara berdampingan, masing-masing untuk `NPM`, `Name`, dan `Class`.  
* **`InfoCard` (Custom Widget)**:  
  * Kartu informasi yang menampilkan `title` dan `content`.  
  * Digunakan untuk menampilkan informasi pengguna (`NPM`, `Name`, dan `Class`) dalam tampilan yang rapi dan konsisten.  
* **`Card`**:  
  * Memberikan tampilan kartu dengan bayangan di bawahnya untuk menunjukkan bahwa elemen ini berbentuk kartu.  
  * Digunakan dalam `InfoCard` untuk membungkus konten informasi agar terlihat seperti kartu.  
* **`Text`**:  
  * Menampilkan teks pada layar.  
  * Digunakan untuk menampilkan teks judul aplikasi, judul `InfoCard`, konten `InfoCard`, teks sambutan "Welcome to Shopeeta", dan nama item dalam `ItemCard`.  
* **`GridView.count`**:  
  * Membuat layout grid dengan jumlah kolom tetap (dalam hal ini, 3 kolom).  
  * Digunakan untuk menampilkan daftar `ItemCard` secara grid, sehingga tiap item dalam `items` tampil dalam tata letak grid.  
* **`ItemCard` (Custom Widget)**:  
  * Kartu yang menampilkan ikon dan nama item dari daftar `items`.  
  * Memiliki warna latar belakang yang berbeda sesuai dengan jenis item, dan akan menampilkan pesan `SnackBar` saat ditekan.  
* **`Material`**:  
  * Menyediakan latar belakang material pada widget dan mendukung efek visual, seperti elevasi dan ripple.  
  * Digunakan dalam `ItemCard` untuk memberikan warna latar belakang dan sudut melengkung.  
* **`InkWell`**:  
  * Menambahkan efek klik (ripple effect) pada widget.  
  * Digunakan dalam `ItemCard` agar ketika kartu ditekan, ada efek ripple dan aksi tertentu (menampilkan `SnackBar`).  
* **`Icon`**:  
  * Menampilkan ikon pada layar.  
  * Digunakan dalam `ItemCard` untuk menampilkan ikon dari item berdasarkan jenisnya (misalnya, ikon product untuk "Lihat Produk", ikon add untuk "Tambah Produk", dan ikon logout untuk "Logout").  
* **`SnackBar`**:  
  * Menampilkan pesan sementara di bagian bawah layar.  
  * Ditampilkan ketika `ItemCard` ditekan untuk menunjukkan pesan bahwa tombol tersebut telah ditekan.  
* **`SizedBox`**:  
  * Menambahkan jarak atau ukuran kosong di antara widget.  
  * Digunakan untuk memberikan jarak antara elemen-elemen di dalam widget, seperti jarak antara `InfoCard` dan `Text`.

3. #### **Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.**

**Fungsi `setState()`** digunakan dalam *Stateful Widget* untuk memberi tahu Flutter bahwa ada perubahan pada data atau *state* yang memengaruhi tampilan, sehingga UI perlu diperbarui. Ketika `setState()` dipanggil, Flutter akan memicu *rebuild* pada widget tersebut, yang berarti Flutter akan merender ulang UI berdasarkan data atau *state* terbaru. 

Variabel yang Terdampak oleh setState():

* **Variabel yang dideklarasikan di dalam class *state***: Hanya variabel yang berada di dalam *state* dari *Stateful Widget* (biasanya dalam class `State`) yang akan terdampak oleh `setState()`. Variabel ini digunakan untuk menyimpan data atau kondisi yang memengaruhi tampilan.  
* **Properti dinamis dari UI**: Contohnya adalah variabel seperti `counter`, `text`, `color`, atau daftar item dalam list. Setiap variabel yang memengaruhi tampilan UI dan berubah seiring waktu harus ditempatkan di dalam *state* dan diperbarui melalui `setState()`.  
* **Data yang mengontrol logika tampilan**: Selain variabel yang langsung muncul di UI, data yang mengontrol logika UI juga bisa terdampak. Contohnya termasuk variabel *boolean* seperti `isLoading`, `isVisible`, atau `isEnabled`, yang digunakan untuk menampilkan atau menyembunyikan elemen tertentu.

4. #### **Jelaskan perbedaan antara const dengan final.**

Perbedaan Utama antara const dan final adalah:

* **Waktu Penentuan Nilai**:  
  * **`final`**: Nilai `final` diatur satu kali saja dan tetap setelah diinisialisasi. Nilainya dapat ditentukan pada saat runtime (saat aplikasi berjalan), sehingga `final` cocok untuk nilai yang hanya diketahui pada runtime.  
  * **`const`**: Nilai `const` bersifat konstan secara *compile-time*, artinya nilai harus sudah diketahui pada waktu kompilasi. `const` digunakan untuk nilai yang benar-benar tidak akan berubah dan sudah dapat ditentukan sejak awal kompilasi.  
* **Penggunaan di dalam Kelas**:  
  * **`final`**: Dapat digunakan sebagai variabel instan di dalam kelas. Ini memungkinkan setiap objek dari kelas tersebut memiliki nilai `final` yang tetap, tetapi berbeda di antara objek-objeknya.  
  * **`const`**: Tidak dapat digunakan sebagai variabel instan dalam kelas secara langsung, karena `const` adalah konstan pada level global. Namun, `const` dapat digunakan dengan membuat objek `const` (misalnya, `const MyClass()`).  
* **Pembuatan Objek Konstan**:  
  * **`final`**: Saat digunakan untuk objek, `final` menjamin bahwa objek tersebut tidak dapat diubah referensinya setelah diinisialisasi, tetapi properti dalam objek tersebut masih bisa diubah (jika propertinya bukan `final` atau `const`).  
  * **`const`**: Ketika digunakan pada objek, `const` menjadikan seluruh objek konstan, termasuk semua propertinya. Setiap penggunaan `const` untuk objek yang sama akan mengarah ke satu *instance* yang sama untuk menghemat memori (*canonicalized instance*).  
* **Efisiensi Memori**:  
  * **`final`**: Tidak ada efisiensi memori khusus, karena nilai `final` bisa berbeda antar objek.  
  * **`const`**: Objek `const` yang memiliki nilai sama akan di-*canonicalized* atau didaur ulang, artinya Flutter/Dart akan menggunakan satu objek yang sama di memori untuk semua referensi yang identik. Ini meningkatkan efisiensi memori.

5. #### **Jelaskan bagaimana cara kamu mengimplementasikan *checklist-checklist* di atas.**

* **Membuat sebuah program Flutter baru dengan tema *E-Commerce* yang sesuai dengan tugas-tugas sebelumnya.**  
  Pertama, saya membuat folder direktori `eshop-mobile` yang akan menjadi tempat proyek Flutter saya. Kemudian pada command prompt, saya *generate* proyek Flutter baru bernama shopeeta dan masuk ke direktori proyek tersebut.   
  `flutter create shopeeta`  
  `cd shopeeta`  
  Selanjutnya, saya mencoba menjalankan proyek tersebut dengan perintah `flutter run`. Lalu, saya melakukan `git init` pada root folder dan melakukan `add-commit-push` proyek ke repositori `eshop-mobile` di github.  
* **Membuat tiga tombol sederhana dengan ikon dan teks untuk melihat daftar produk (`Lihat Daftar Produk`), menambah produk (`Tambah Produk`), dan logout (`Logout`)**  
  Sebelum membuat *button* untuk *card*, saya membuat *class* baru bernama `ItemHomepage` yang berisi atribut-atribut dari card yang akan dibuat (pada kasus ini berisi *name* dan *icon*). Pada berkas `menu.dart`, saya menambahkan class di bawah ini di luar class `MyHomePage` dan `InfoCard`.  
  ```
  ...
  class ItemHomepage {
      final String name;
      final IconData icon;

      ItemHomepage(this.name, this.icon);
  }
  ...
  ```
  
  Kemudian, saya membuat *list of* `ItemHomepage` yang berisi tombol-tombol yang ingin saya tambahkan pada *class* `MyHomePage`.   
  ```
  class MyHomePage extends StatelessWidget {  
      ...
      final List<ItemHomepage> items = [
          ItemHomepage("Lihat Daftar", Icons.mood),
          ItemHomepage("Tambah Produk", Icons.add),
          ItemHomepage("Logout", Icons.logout),
      ];
      ...
  }
  ```
  
  Selanjutnya, saya membuat *class* `ItemCard` untuk menampilkan tombol-tombol yang sudah saya buat. Untuk saat ini, tombol yang ditekan hanya akan menampilkan *snackbar* yang berisi pesan "Kamu telah menekan tombol \[nama *button*\]".  
  ```
  ...
  class ItemCard extends StatelessWidget {
    // Menampilkan kartu dengan ikon dan nama.

    final ItemHomepage item; 
    
    const ItemCard(this.item, {super.key}); 

    // Fungsi untuk memilih warna latar belakang berdasarkan nama tombol.
    Color getBackgroundColor() {
      switch (item.name) {
        case "Lihat Produk":
          return Colors.blue;
        case "Tambah Produk":
          return Colors.green;
        case "Logout":
          return Colors.red;
        default:
          return Colors.grey; // Warna default jika tidak sesuai dengan opsi di atas.
      }
    }

    @override
    Widget build(BuildContext context) {
      return Material(
        // Menentukan warna latar belakang dari tema aplikasi.
        color: getBackgroundColor(), // Gunakan warna yang dipilih
        
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
  
* **Mengimplementasikan warna-warna yang berbeda untuk setiap tombol (`Lihat Daftar Produk`, `Tambah Produk`, dan `Logout`).**  
  Untuk mengimplementasikan warna yang berbeda pada setiap tombol, saya menambahkan fungsi **`getBackgroundColor()`**. Kemudian, memanggil fungsi tersebut dengan **`color: getBackgroundColor()`** di dalam widget `Material` untuk menerapkan warna yang berbeda pada setiap tombol.  
  class ItemCard extends StatelessWidget {
  ```
    ... 
    // Fungsi untuk memilih warna latar belakang berdasarkan nama tombol.
    Color getBackgroundColor() {
      switch (item.name) {
        case "Lihat Produk":
          return Colors.blue;
        case "Tambah Produk":
          return Colors.green;
        case "Logout":
          return Colors.red;
        default:
          return Colors.grey; // Warna default jika tidak sesuai dengan opsi di atas.
      }
    }

    @override
    Widget build(BuildContext context) {
      return Material(
        color: getBackgroundColor(), // Gunakan warna yang dipilih
        borderRadius: BorderRadius.circular(12),
      ...
      ),
    }
  }
  ```

* **Memunculkan `Snackbar`**  
  Untuk memunculkan Snackbar setelah tombol ditekan, saya menambahkan `InkWell` untuk melakukan aksi ketika tombol ditekan:  
  ```
  class ItemCard extends StatelessWidget {
    ...
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
        ),
  ...
  }
  ```
  
* **Mengintegrasikan InfoCard dan ItemCard untuk Ditampilkan di MyHomePage**  
  Langkah terakhir adalah mengintegrasikan dan menampilkan seluruh *card* yang saya miliki di `HomePage`. Saya mengubah bagian `Widget build()` pada *class* `MyHomePage`.  
  ```
  class MyHomePage extends StatelessWidget {
  ...
      @override
    Widget build(BuildContext context) {
      // Scaffold menyediakan struktur dasar halaman dengan AppBar dan body.
      return Scaffold(
        // AppBar adalah bagian atas halaman yang menampilkan judul.
        appBar: AppBar(
          // Judul aplikasi "Shopeeta" dengan teks putih dan tebal.
          title: const Text(
            'Shopeeta',
            style: TextStyle(
              color: Colors.white,
              fontWeight: FontWeight.bold,
            ),
          ),
          // Warna latar belakang AppBar diambil dari skema warna tema aplikasi.
          backgroundColor: Theme.of(context).colorScheme.primary,
        ),
        // Body halaman dengan padding di sekelilingnya.
        body: Padding(
          padding: const EdgeInsets.all(16.0),
          // Menyusun widget secara vertikal dalam sebuah kolom.
          child: Column(
            crossAxisAlignment: CrossAxisAlignment.center,
            children: [
              // Row untuk menampilkan 3 InfoCard secara horizontal.
              Row(
                mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                children: [
                  InfoCard(title: 'NPM', content: npm),
                  InfoCard(title: 'Name', content: name),
                  InfoCard(title: 'Class', content: className),
                ],
              ),

              // Memberikan jarak vertikal 16 unit.
              const SizedBox(height: 16.0),

              // Menempatkan widget berikutnya di tengah halaman.
              Center(
                child: Column(
                  // Menyusun teks dan grid item secara vertikal.

                  children: [
                    // Menampilkan teks sambutan dengan gaya tebal dan ukuran 18.
                    const Padding(
                      padding: EdgeInsets.only(top: 16.0),
                      child: Text(
                        'Welcome to Shopeeta',
                        style: TextStyle(
                          fontWeight: FontWeight.bold,
                          fontSize: 18.0,
                        ),
                      ),
                    ),

                    // Grid untuk menampilkan ItemCard dalam bentuk grid 3 kolom.
                    GridView.count(
                      primary: true,
                      padding: const EdgeInsets.all(20),
                      crossAxisSpacing: 10,
                      mainAxisSpacing: 10,
                      crossAxisCount: 3,
                      // Agar grid menyesuaikan tinggi kontennya.
                      shrinkWrap: true,

                      // Menampilkan ItemCard untuk setiap item dalam list items.
                      children: items.map((ItemHomepage item) {
                        return ItemCard(item);
                      }).toList(),
                    ),
                  ],
                ),
              ),
            ],
          ),
        ),
      );
    }
  }
  ...
  ```

# Tugas Individu 8

1. #### **Apa kegunaan const di Flutter? Jelaskan apa keuntungan ketika menggunakan const pada kode Flutter. Kapan sebaiknya kita menggunakan const, dan kapan sebaiknya tidak digunakan?**

Pada Flutter, `const` digunakan untuk mendeklarasikan objek yang tidak akan berubah setelah diciptakan, menjadikannya konstan. Objek yang dideklarasikan dengan `const` akan dihitung dan disalin pada saat kompilasi, bukan saat runtime, yang memiliki beberapa manfaat penting.

**Keuntungan menggunakan const di Flutter:**

* Peningkatan Performa  
* Penyederhanaan Kode   
* Efisiensi pada Rebuild

**Kapan sebaiknya menggunakan const:**

1. **Untuk Widget yang Tidak Berubah**: Ketika widget tidak memiliki perubahan pada nilai atau propertinya, seperti `Text`, `Icon`, atau `Container` yang tidak memerlukan pembaruan, menggunakan `const` akan sangat bermanfaat.  
2. **Untuk Nilai Konstan**: Jika memiliki nilai konstan yang tidak akan berubah, seperti warna, teks, atau angka yang digunakan di seluruh aplikasi, maka bisa menggunakan `const`.

**Kapan sebaiknya tidak menggunakan const:**

* **Widget yang Memiliki Nilai Dinamis**: Jika widget atau objek memerlukan pembaruan nilai selama runtime, maka tidak sebaiknya menggunakan `const`. Misalnya, ketika nilai propertinya berubah berdasarkan state atau input pengguna, menggunakan `const` tidak memungkinkan perubahan nilai.  
* **Widget dengan Parameter yang Bergantung pada State**: Jika widget memiliki parameter yang berubah berdasarkan state atau input, maka tidak bisa menggunakan `const` pada widget tersebut.

2. #### **Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini\!**

**Column**  
`Column` digunakan untuk menyusun widget secara vertikal. Setiap widget yang dimasukkan dalam `Column` akan ditempatkan satu di bawah yang lainnya. Kita dapat mengatur *alignment* dan *spacing* di antara widget menggunakan properti seperti `mainAxisAlignment`, `crossAxisAlignment`, dan `mainAxisSize`.

**Keuntungan menggunakan Column:**

* Menyusun widget secara vertikal.  
* Dapat menyesuaikan ukuran elemen dalam arah vertikal.  
* Memiliki opsi pengaturan posisi dan jarak antar widget.

**Contoh implementasi Column:**
```
Column(
  mainAxisAlignment: MainAxisAlignment.center,  // Menyusun widget di tengah secara vertikal
  crossAxisAlignment: CrossAxisAlignment.start,  // Menyusun widget ke kiri secara horizontal
  children: <Widget>[
    Text('Item 1'),
    Text('Item 2'),
    Text('Item 3'),
  ],
)
```

Pada contoh di atas, widget `Text` disusun vertikal di dalam `Column`. Properti `mainAxisAlignment` digunakan untuk menempatkan widget secara vertikal di tengah, dan `crossAxisAlignment` digunakan untuk mengatur posisi widget secara horizontal (dalam hal ini di kiri).

**Row**  
`Row` digunakan untuk menyusun widget secara horizontal. Setiap widget yang dimasukkan dalam `Row` akan ditempatkan satu di samping yang lainnya. Seperti `Column`, Anda juga dapat mengatur alignment dan spacing menggunakan properti seperti `mainAxisAlignment`, `crossAxisAlignment`, dan `mainAxisSize`.

**Keuntungan menggunakan Row:**

* Menyusun widget secara horizontal.  
* Dapat menyesuaikan ukuran elemen dalam arah horizontal.  
* Memiliki opsi pengaturan posisi dan jarak antar widget.

**Contoh implementasi Row:**
```
Row(
  mainAxisAlignment: MainAxisAlignment.spaceAround,  // Menyusun widget dengan jarak rata di antara elemen
  crossAxisAlignment: CrossAxisAlignment.center,  // Menyusun widget di tengah secara vertikal
  children: <Widget>[
    Text('Item A'),
    Text('Item B'),
    Text('Item C'),
  ],
)
```

Pada contoh ini, widget `Text` disusun secara horizontal dalam `Row`. Properti `mainAxisAlignment` digunakan untuk memberikan jarak yang merata di antara widget, dan `crossAxisAlignment` mengatur posisi widget secara vertikal (dalam hal ini di tengah).

3. #### **Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan\!**

Pada berkas productentry\_form.dart, elemen input yang saya gunakan adalah **`TextFormField`** untuk berbagai jenis data yang diminta. Beberapa elemen input Flutter lain yang tidak digunakan pada tugas ini, namun bisa digunakan di form lainnya atau di situasi lain, antara lain:

1. **Checkbox** (`Checkbox`, `CheckboxListTile`): untuk input dalam bentuk pilihan ganda yang dapat dipilih atau tidak. Misalnya, untuk memilih apakah produk tersedia atau tidak, atau jika produk memiliki diskon khusus.  
2. **Radio Button** (`Radio`, `RadioListTile`): untuk memilih salah satu dari beberapa opsi yang tersedia. Misalnya, memilih kategori produk atau status produk (baru/second).  
3. **Switch** (`Switch`, `SwitchListTile`): untuk memilih antara dua opsi, seperti mengaktifkan atau menonaktifkan fitur tertentu terkait produk.  
4. **Dropdown Button** (`DropdownButton`, `DropdownButtonFormField`): untuk memilih nilai dari daftar pilihan yang terbatas, seperti memilih kategori produk atau jenis pengiriman.  
5. **Date Picker** (`showDatePicker`): untuk memilih tanggal, misalnya untuk tanggal kadaluarsa produk atau tanggal mulai promosi.  
6. **Time Picker** (`showTimePicker`) untuk memilih waktu, yang mungkin berguna dalam aplikasi yang melibatkan waktu, seperti jam operasional atau waktu pengiriman.  
7. **File Picker** (`FilePicker` atau `ImagePicker`): untuk memilih file atau gambar dari perangkat, yang bisa berguna jika Anda ingin menambahkan gambar produk atau berkas lain ke dalam form.

4. #### **Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?**

Untuk mengatur tema (theme) dalam aplikasi Flutter dan menjaga konsistensi visual di seluruh aplikasi, saya **mendefinisikan Tema Aplikasi (ThemeData)** dan **menerapkan tema** di widget `MaterialApp` pada berkas `main.dart` seperti berikut.
```
class MyApp extends StatelessWidget {  
  const MyApp({super.key});

  // This widget is the root of your application.  
  @override  
  Widget build(BuildContext context) {  
    return MaterialApp(  
      title: 'Flutter Demo',  
      theme: ThemeData(  
      	colorScheme: ColorScheme.fromSwatch(  
              primarySwatch: Colors.teal,  
        ).copyWith(secondary: Colors.teal\[700\]),  
      ),  
      home: MyHomePage(),  
    );  
  }  
}
``` 
Pada kode tersebut, terdapat **`ColorScheme`** yang digunakan untuk menentukan warna utama, sekunder, latar belakang, dan elemen-elemen lainnya dalam aplikasi. 

Saya juga sudah mengimplementasikan Pada halaman form yang saya buat (`ProductEntryFormPage`), saya sudah mengimplementasikan tema dengan memanfaatkan `Theme.of(context)` untuk menyesuaikan warna tombol (`ElevatedButton`) dengan warna tema aplikasi.
```
...
ElevatedButton(  
  style: ButtonStyle(  
    backgroundColor: MaterialStateProperty.all(Theme.of(context).colorScheme.primary),  
  ),  
  onPressed: () {  
    if (\_formKey.currentState\!.validate()) {  
      // aksi untuk menyimpan data  
    }  
  },  
  child: const Text(  
    "Save",  
    style: TextStyle(color: Colors.white),  
  ),  
)
...
```

5. #### **Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?**

Untuk mempermudah navigasi di aplikasi Flutter, saya menambahkan *drawer menu*. *Drawer menu* adalah sebuah menu yang muncul dari sisi kiri atau kanan layar. *Drawer menu* biasanya berisi navigasi ke halaman-halaman lain pada aplikasi. *Drawer menu* tersebut saya buat pada berkas `left_drawer.dart` pada subdirektori baru bernama `widgets` di subdirektori `lib/`. Selanjutnya, pada berkas `left_drawer.dart` saya menambahkan impor untuk halaman-halaman yang ingin dimasukkan navigasinya ke dalam *drawer menu*, yaitu ke halaman `MyHomePage` dan `ProductEntryFormPage`. Kemudian, saya memasukkan routing untuk halaman-halaman yang diimpor dengan menambahkan potongan kode berikut.  
```
ListTile(
  leading: const Icon(Icons.home_outlined),
  title: const Text('Halaman Utama'),
  // Bagian redirection ke MyHomePage
  onTap: () {
    Navigator.pushReplacement(
        context,
        MaterialPageRoute(
          builder: (context) => MyHomePage(),
        ));
  },
),
ListTile(
  leading: const Icon(Icons.mood),
  title: const Text('Tambah Produk'),
  // Bagian redirection ke ProductEntryFormPage
  onTap: () {
    Navigator.pushReplacement(
    context,
    MaterialPageRoute(
        builder: (context) => ProductEntryFormPage(),
    ));
  },
),
```

Pada kode tersebut, digunakan `Navigator.pushReplacement` untuk menggantikan halaman sebelumnya dengan halaman baru, sehingga halaman lama tidak disimpan di dalam stack navigasi. Dengan demikian, saat pengguna berpindah halaman melalui *drawer*, mereka tidak dapat kembali ke halaman sebelumnya dengan tombol "back".

Berikut adalah proses yang dilakukan:

1. **`ListTile` untuk Halaman Utama** – Ketika pengguna menekan opsi ini, `Navigator.pushReplacement` menggantikan halaman saat ini dengan `MyHomePage()`.  
2. **`ListTile` untuk Halaman Tambah Produk** – Saat opsi ini dipilih, `Navigator.pushReplacement` menggantikan halaman saat ini dengan `ProductEntryFormPage()`

Setelah berhasil membuat *drawer menu*, langkah berikutnya adalah memasukkan *drawer* tersebut ke halaman yang ingin ditambahkan drawer, yaitu ke halaman `menu.dart` dan `productentry_form.dart`.

Pada *widget* `ProductItem` di berkas `product_card.dart`, akan dibuat agar kode yang terletak pada atribut `onTap` dari `InkWell` dapat melakukan navigasi ke *route* lain (tambahkan kode tambahan di bawah kode `ScaffoldMessenger` yang menampilkan *snackbar*).
```
...
onTap: () {
  // Menampilkan pesan SnackBar saat kartu ditekan.
  ScaffoldMessenger.of(context)
    ..hideCurrentSnackBar()
    ..showSnackBar(
      SnackBar(content: Text("Kamu telah menekan tombol ${item.name}!"))
    );
  
  // Navigate ke route yang sesuai (tergantung jenis tombol)
  if (item.name == "Tambah Produk") {
    Navigator.push(context,
      MaterialPageRoute(builder: (context) => const ProductEntryFormPage()));
  }
},
...
```

Pada tombol “Tambah Produk”, saya menggunakan `Navigator.push()` sehingga pengguna dapat menekan tombol Back untuk kembali ke halaman menu. Selain itu, saya menggunakan `Navigator.pop()`agar kode dalam program dapat kembali ke halaman menu. 