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

# Tugas Individu 9

1. #### **Jelaskan mengapa kita perlu membuat model untuk melakukan pengambilan ataupun pengiriman data JSON? Apakah akan terjadi error jika kita tidak membuat model terlebih dahulu?**

Alasan mengapa kita perlu membuat model untuk pengambilan dan pengiriman data JSON adalah:

**1\. Struktur Data yang Konsisten**

* **Model** memungkinkan kita untuk menjaga **konsistensi data** di seluruh aplikasi. Dengan menggunakan model, kita dapat memastikan bahwa data JSON yang kita terima atau kirim memiliki struktur yang sama dan konsisten.  
* Tanpa model, pengelolaan data JSON menjadi tidak terstruktur dan rawan kesalahan. Setiap perubahan pada format JSON yang diterima harus diperiksa secara manual pada setiap tempat di mana data itu digunakan.

**2\. Mengurangi Kesalahan Parsing**

* Jika kita tidak menggunakan model dan hanya melakukan parsing JSON secara manual (misalnya menggunakan `Map<String, dynamic>`), kita harus menulis banyak kode untuk mengekstrak data dari JSON. Hal ini dapat menyebabkan kesalahan seperti kesalahan tipe data, typo dalam nama key, atau kesalahan logika dalam mengambil data.  
* Dengan model, parsing data menjadi lebih aman dan lebih dapat diandalkan karena kita dapat menggunakan metode yang otomatis mengambil nilai dari JSON ke dalam objek yang telah didefinisikan.

**3\. Enkapsulasi dan Validasi Data**

* Model dapat digunakan untuk mengenkapsulasi dan memvalidasi data. Misalnya, ketika kita membuat instance dari model, kita dapat menerapkan validasi data pada level model. Ini membantu menjaga integritas data sebelum dikirim atau diterima.  
* Jika tidak menggunakan model, validasi data harus dilakukan di berbagai tempat di seluruh aplikasi, yang dapat menyebabkan kode yang lebih sulit dikelola dan lebih banyak potensi kesalahan.

**4\. Mudah dalam Konversi Antar Format**

* Model biasanya berisi metode untuk konversi data seperti `fromJson()` dan `toJson()`. Ini memungkinkan kita dengan mudah mengonversi JSON yang diterima dari server menjadi objek Dart dan sebaliknya, mengonversi objek Dart menjadi JSON untuk dikirim ke server.  
* Tanpa model, proses konversi ini harus ditangani secara manual, yang tidak hanya memakan waktu tetapi juga meningkatkan kemungkinan terjadinya error.

**5\. Mengurangi Duplikasi Kode dan Memperbaiki Maintainability**

* Ketika kita menggunakan model, kita dapat menghindari **pengulangan kode** di seluruh aplikasi, terutama ketika ada banyak tempat yang perlu berinteraksi dengan format data JSON yang sama.  
* Model membuat kode lebih **terstruktur dan terorganisir**, yang membantu memperbaiki **maintainability** aplikasi dalam jangka panjang. Misalnya, jika terjadi perubahan pada struktur JSON dari API, kita hanya perlu memperbarui modelnya, dan tidak perlu mengubah setiap bagian kode yang menggunakan data tersebut.

**6\. Error Handling yang Lebih Baik**

* Saat berinteraksi dengan JSON yang kompleks, sering kali kita akan mendapatkan nilai yang bisa jadi `null` atau memiliki tipe data yang tidak sesuai dengan yang diharapkan. Model dapat menangani hal ini dengan cara yang lebih elegan menggunakan metode `try-catch` atau `default values`, dibandingkan langsung mengakses data tanpa pengecekan.  
* Tanpa model, kesalahan parsing data (seperti `null pointer exception` atau `cast error`) akan lebih sering terjadi dan sulit untuk diidentifikasi, terutama pada JSON yang bersarang (nested JSON).

**Apakah Akan Terjadi Error Jika Tidak Membuat Model Terlebih Dahulu?**

* **Tidak selalu terjadi error** jika tidak membuat model terlebih dahulu. Aplikasi masih bisa berfungsi jika Anda melakukan parsing JSON secara manual. Namun, ada beberapa **potensi risiko dan kesalahan** yang mungkin muncul:  
  1. **Kesalahan Parsing**: Manual parsing data sangat rentan terhadap kesalahan, terutama jika struktur JSON berubah di server.  
  2. **Kurangnya Validasi**: Data yang tidak tervalidasi bisa menyebabkan crash atau perilaku yang tidak terduga ketika data yang diterima tidak sesuai dengan yang diharapkan.  
  3. **Kualitas Kode yang Buruk**: Kode menjadi sulit dibaca, dipelihara, dan diuji karena tidak terorganisir dengan baik. Setiap kali ada perubahan pada format JSON, Anda mungkin harus memeriksa banyak bagian kode yang berbeda.

2. #### **Jelaskan fungsi dari library http yang sudah kamu implementasikan pada tugas in**i

Library `http` digunakan dalam Flutter untuk berkomunikasi dengan server melalui protokol HTTP. Berikut fungsi utamanya:

1. **Mengirim Request ke Server**: Mengirim data menggunakan metode HTTP seperti `POST` atau `GET`, misalnya untuk mengirim data produk baru ke server.  
2. **Menerima Response dari Server**: Menerima respons server dan memberikan feedback ke pengguna, apakah operasi berhasil atau terjadi kesalahan.  
3. **Menghubungkan Frontend dan Backend**: Menghubungkan aplikasi Flutter (frontend) dengan Django (backend), sehingga data yang dimasukkan pengguna bisa disimpan di server.  
4. **Handling Asynchronous Operations**: Mengelola operasi jaringan yang bersifat asinkron menggunakan `Future` dan `await` agar UI tetap responsif.  
5. **Mengolah Data JSON**: Mengirim dan menerima data dalam format JSON dengan mudah menggunakan `jsonEncode()` dan `jsonDecode()`.  
6. **Error Handling**: Menangani kesalahan jaringan atau status HTTP dengan memberikan notifikasi kepada pengguna jika terjadi error.

3. #### **Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.**

`CookieRequest` digunakan untuk menangani request HTTP yang membutuhkan sesi berbasis **cookie**. Fungsinya adalah:

1. **Mengelola Cookie**: Menyimpan dan mengirim cookie yang diterima dari server secara otomatis pada setiap request.  
2. **Melakukan HTTP Request**: Mengirimkan request seperti `GET` atau `POST` sambil menyertakan cookie untuk menjaga autentikasi.  
3. **Menjaga Sesi Pengguna**: Mempertahankan status login pengguna sehingga tidak perlu login ulang setiap kali berpindah halaman.

**Mengapa CookieRequest Dibagikan ke Semua Komponen?**

1. **Konsistensi Sesi**: Semua komponen membutuhkan sesi yang sama untuk akses autentikasi agar pengguna tidak perlu login berulang kali.  
2. **State Management**: Dengan membagikan `CookieRequest` menggunakan **provider** atau **dependency injection**, setiap widget bisa mengakses instance yang sama, menjaga aplikasi tetap terorganisir.  
3. **Keamanan dan Efisiensi**: Menggunakan satu instance memastikan cookie sinkron, meningkatkan keamanan, dan memudahkan komunikasi dengan backend.

`CookieRequest` dibagikan agar sesi pengguna dapat dikelola dengan konsisten di seluruh aplikasi, menjaga pengalaman pengguna tetap lancar dan aman.

4. #### **Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.**

Mekanisme pengiriman data dari input hingga dapat ditampilkan dalam aplikasi Flutter melibatkan beberapa langkah penting, mulai dari pengguna mengisi formulir hingga data tersebut dikirimkan ke backend dan akhirnya ditampilkan kembali di aplikasi. Berikut adalah langkah-langkahnya:

1. **Input dari Pengguna**  
* **Pengguna Mengisi Formulir**: Pengguna mengisi input melalui widget seperti `TextFormField` pada halaman aplikasi Flutter. Data ini kemudian disimpan dalam variabel lokal, misalnya `_product`, `_description`, `_price`, dsb.  
* **Validasi Data**: Sebelum data dikirim ke server, formulir melakukan validasi untuk memastikan data sudah sesuai dengan aturan tertentu (misalnya tidak boleh kosong, panjang minimum, harus berupa angka, dll.).

2. **Pengiriman Data ke Backend (HTTP Request)**  
* **Mengirim Request**: Ketika tombol simpan ditekan, aplikasi akan menggunakan library HTTP (contohnya `http` atau `CookieRequest`) untuk mengirimkan data tersebut ke server.  
  **Metode Request (POST)**: Biasanya menggunakan metode `POST` untuk mengirim data ke backend, contohnya:  
  `final response = await request.postJson(`  
    `"http://localhost:8000/create-flutter/",`  
    `jsonEncode(<String, String>{`  
        `'name': _product,`  
        `'description': _description,`  
        `'price': _price.toString(),`  
    `}),`  
  `);`  
* **Data dalam Format JSON**: Data yang dikirimkan diubah ke dalam format JSON dengan `jsonEncode()`, sehingga dapat dipahami oleh server.

3. **Backend Memproses Data**  
* **Server Menerima dan Memproses Request**: Server (misalnya menggunakan Django) menerima request tersebut, mem-parsing data JSON, dan kemudian menyimpannya ke dalam database.  
* **Memberikan Response**: Setelah data berhasil diproses (misalnya disimpan), server mengirimkan response ke aplikasi Flutter. Response ini bisa berupa status `success`, pesan error, atau bahkan data tambahan (seperti ID produk baru yang disimpan).

4. **Menerima dan Mengolah Response di Flutter**  
* **Menerima Response**: Flutter menunggu response dari server setelah melakukan request. Jika server mengirimkan response `success`, aplikasi dapat menampilkan pesan konfirmasi kepada pengguna, misalnya menggunakan `SnackBar`.  
* **Handling Error**: Jika ada kesalahan pada server atau validasi data gagal, response dari server diolah untuk menampilkan pesan error yang relevan kepada pengguna.

5. **Mengambil dan Menampilkan Data Kembali**  
* **Mengambil Data dengan GET Request**: Untuk menampilkan data yang sudah disimpan, aplikasi Flutter dapat melakukan request `GET` ke server untuk mengambil data dari database.  
* **Mengurai JSON dan Menampilkan Data**: Setelah menerima response yang berisi data dalam format JSON, aplikasi mengurai data tersebut (`jsonDecode()`) dan menyimpannya dalam model data. Data ini kemudian ditampilkan dalam widget Flutter, seperti `ListView` atau `Card`.  
* **Widget UI**: Widget seperti `ListView.builder` digunakan untuk menampilkan data yang diambil, sehingga pengguna dapat melihat data yang mereka input sebelumnya.

5. #### **Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.**

1. **Registrasi (Register)**  
* **Input Data Pengguna**: Pengguna mengisi formulir registrasi pada aplikasi Flutter, seperti nama, email, dan password. Data ini disimpan dalam variabel lokal.  
  **Pengiriman Data ke Server**: Data yang telah diisi pengguna dikirim ke server menggunakan HTTP POST request, dikodekan dalam format JSON.  
  Dart  
  `final response = await request.postJson(`  
    `"http://localhost:8000/api/register/",`  
    `jsonEncode(<String, String>{`  
        `'username': _username,`  
        `'email': _email,`  
        `'password': _password,`  
    `}),`  
  `);`  
* **Pemrosesan oleh Django**: Backend Django menerima request tersebut dan melakukan validasi, misalnya memeriksa apakah email sudah terdaftar atau password memenuhi kriteria. Jika semua validasi lolos, Django menyimpan informasi pengguna ke dalam database.  
* **Mengirim Response**: Django mengirimkan response ke Flutter, yang bisa berupa `success` jika registrasi berhasil atau `error` jika terjadi masalah (misalnya, email sudah digunakan).

2. **Login**  
* **Input Data Login**: Pengguna memasukkan kredensial (username/email dan password) melalui formulir login di aplikasi Flutter.  
  **Mengirim Data ke Server**: Data login tersebut dikirim ke server menggunakan HTTP POST request.  
  `final response = await request.postJson(`  
    `"http://localhost:8000/api/login/",`  
    `jsonEncode(<String, String>{`  
        `'username': _username,`  
        `'password': _password,`  
    `}),`  
  `);`  
* **Pemrosesan Login oleh Django**:  
  * Django memeriksa apakah username/email dan password yang diberikan cocok dengan informasi yang ada di database.  
  * Jika valid, Django mengautentikasi pengguna dan membuat **session**. Django akan mengirimkan **cookie** yang berisi informasi sesi ini dalam response.  
* **Menyimpan Cookie di Flutter**: Library seperti `CookieRequest` di Flutter akan menyimpan cookie sesi ini. Cookie tersebut akan digunakan pada setiap permintaan berikutnya untuk menjaga sesi tetap aktif.

3. **Mengakses Menu Setelah Login**  
* **Verifikasi Sesi**: Setelah login berhasil, aplikasi Flutter bisa menggunakan cookie sesi yang telah disimpan untuk mengakses data atau halaman yang memerlukan autentikasi. Aplikasi akan mengirim request (seperti `GET` atau `POST`) sambil menyertakan cookie sesi yang tersimpan.  
* **Mengambil Data Pengguna atau Menu**: Dengan menggunakan request yang disertai cookie, Flutter bisa mengirim permintaan ke server untuk mendapatkan informasi yang relevan, seperti data pengguna, daftar produk, atau akses ke halaman menu utama.  
* **Menampilkan Menu di Flutter**: Data yang diterima dari Django (seperti data pengguna yang terautentikasi atau menu utama) kemudian diolah dan ditampilkan di aplikasi menggunakan widget UI, misalnya `ListView` untuk menampilkan daftar produk.

4. **Logout**  
   **Mengirim Permintaan Logout**: Ketika pengguna menekan tombol logout di aplikasi Flutter, aplikasi mengirimkan request `POST` ke endpoint logout di Django.  
   `final response = await request.postJson(`  
     `"http://localhost:8000/api/logout/",`  
     `{},`  
   `);`  
* **Pemrosesan oleh Django**:  
  * Django menerima request ini dan menghapus sesi pengguna yang aktif. Cookie yang mengidentifikasi sesi pengguna akan dihapus.  
* **Menghapus Cookie di Flutter**: Setelah Django menghapus sesi, aplikasi Flutter juga menghapus cookie sesi yang disimpan di lokal, sehingga pengguna harus login lagi untuk mendapatkan akses.

6. #### **Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step\! (bukan hanya sekadar mengikuti tutorial).**

* Memastikan *deployment* proyek tugas Django kamu telah berjalan dengan baik.  
  Untuk bagian ini, saya baru saja   
* Mengimplementasikan fitur registrasi akun pada proyek tugas Flutter.  
  Untuk mengimplementasikan fitur registrasi akun pada proyek tugas Flutter, langkah pertama yang saya lakukan adalah menginstal *package* yang telah disediakan oleh tim asisten dosen dengan menjalankan perintah flutter pub add provider dan flutter pub add pbp\_django\_auth  pada terminal direktori *root* dari proyek Flutter. Kemudian saya memodifikasi *root widget* yang ada pada berkas `main.dart` untuk menyediakan `CookieRequest` *library* ke semua *child widgets* dengan menggunakan `Provider`.   
    
  class MyApp extends StatelessWidget {  
    const MyApp({super.key});  
    
    @override  
    Widget build(BuildContext context) {  
      return Provider(  
        create: (\_) {  
          CookieRequest request \= CookieRequest();  
          return request;  
        },  
        child: MaterialApp(  
          title: 'Shopeeta',  
          theme: ThemeData(  
            useMaterial3: true,  
            colorScheme: ColorScheme.fromSwatch(  
              primarySwatch: Colors.teal,  
            ).copyWith(secondary: Colors.teal\[700\]),  
          ),  
          home: const LoginPage(),  
        ),  
      );  
    }  
  }  
    
  Hal tersebut akan membuat objek `Provider` baru yang akan membagikan *instance* `CookieRequest` dengan semua komponen yang ada di aplikasi. Selanjutnya, saya mengimpor `'package:pbp_django_auth/pbp_django_auth.dart';` dan `import 'package:provider/provider.dart';` pada bagian atas berkas `main.dart` tersebut  
  Kemudian, saya membuat buatlah berkas baru pada folder `screens` dengan nama `register.dart`.   
* Membuat halaman login pada proyek tugas Flutter.  
  Saya membuat berkas baru pada folder `screen` bernama `login.dart`. Kemudian pada *file* `main.dart`, di bagian Widget `MaterialApp(...)`, saya mengubah `home: MyHomePage()` menjadi `home: const LoginPage().`  
    
* Mengintegrasikan sistem autentikasi Django dengan proyek tugas Flutter.  
  Untuk mengintegrasikan sistem autentikasi Django dengan proyek tugas Flutter, saya membuat `django-app` bernama `authentication` pada project Django yang telah saya buat sebelumnya. Kemudian, saya menambahakn `authentication` ke `INSTALLED_APPS` pada *main project* `settings.py` aplikasi Django saya. Setelah itu, saya menyalakan *virtual environment* Python dan menambahkan `django-cors-headers` ke `requirements.txt`, lalu menjalankan perintah `pip install django-cors-headers` untuk menginstal *library* yang dibutuhkan. Selanjutnya, saya menambahkan `corsheaders` ke `INSTALLED_APPS` dan  `corsheaders.middleware.CorsMiddleware` ke `MIDDLEWARE` pada *main project* `settings.` Berikutnya, saya menambahkan beberapa variabel berikut ini pada *main project* `settings.py` aplikasi Django.  
  ...  
  CORS\_ALLOW\_ALL\_ORIGINS \= True  
  CORS\_ALLOW\_CREDENTIALS \= True  
  CSRF\_COOKIE\_SECURE \= True  
  SESSION\_COOKIE\_SECURE \= True  
  CSRF\_COOKIE\_SAMESITE \= 'None'  
  SESSION\_COOKIE\_SAMESITE \= 'None'  
  …

  Untuk keperluan integrasi ke Django dari *emulator* Android, saya menambahkan `10.0.2.2` pada `ALLOWED_HOSTS` di berkas `settings.py`.  
  ALLOWED\_HOSTS \= \[..., ..., "10.0.2.2"\]  
  Kemudian, saya membuat sebuah metode view pada `authentication/views.py`.  
  from django.contrib.auth import authenticate, login as auth\_login  
  from django.http import JsonResponse  
  from django.views.decorators.csrf import csrf\_exempt  
    
  @csrf\_exempt  
  def login(request):  
      username \= request.POST\['username'\]  
      password \= request.POST\['password'\]  
      user \= authenticate(username=username, password=password)  
      if user is not None:  
          if user.is\_active:  
              auth\_login(request, user)  
              \# Status login sukses.  
              return JsonResponse({  
                  "username": user.username,  
                  "status": True,  
                  "message": "Login sukses\!"  
                  \# Tambahkan data lainnya jika ingin mengirim data ke Flutter.  
              }, status=200)  
          else:  
              return JsonResponse({  
                  "status": False,  
                  "message": "Login gagal, akun dinonaktifkan."  
              }, status=401)  
    
      else:  
          return JsonResponse({  
              "status": False,  
              "message": "Login gagal, periksa kembali email atau kata sandi."  
          }, status=401)  
  Lalu, saya membuat  *file* `urls.py` pada folder `authentication` dan menambahkan URL *routing* terhadap fungsi yang sudah dibuat dengan *endpoint* `login/`.  
  from django.urls import path  
  from authentication.views import login  
    
  app\_name \= 'authentication'  
    
  urlpatterns \= \[  
      path('login/', login, name='login'),  
  \]  
    
  Selanjutnya, saya memodifikasi modul `authentication` pada proyek Django yang dengan menambahkan metode view berikut pada `authentication/views.py` untuk keperluan registrasi.  
  from django.contrib.auth.models import User  
  import json  
    
  ...  
    
  @csrf\_exempt  
  def register(request):  
      if request.method \== 'POST':  
          data \= json.loads(request.body)  
          username \= data\['username'\]  
          password1 \= data\['password1'\]  
          password2 \= data\['password2'\]  
    
          \# Check if the passwords match  
          if password1 \!= password2:  
              return JsonResponse({  
                  "status": False,  
                  "message": "Passwords do not match."  
              }, status=400)  
            
          \# Check if the username is already taken  
          if User.objects.filter(username=username).exists():  
              return JsonResponse({  
                  "status": False,  
                  "message": "Username already exists."  
              }, status=400)  
            
          \# Create the new user  
          user \= User.objects.create\_user(username=username, password=password1)  
          user.save()  
            
          return JsonResponse({  
              "username": user.username,  
              "status": 'success',  
              "message": "User created successfully\!"  
          }, status=200)  
        
      else:  
          return JsonResponse({  
              "status": False,  
              "message": "Invalid request method."  
          }, status=400)  
    
  Tambahkan *path* baru pada `authentication/urls.py` dengan kode berikut  
    
  from authentication.views import login, register   
  ...  
  path('register/', register, name='register'),  
    
  Langkah terakhir, saya menambahkan `path('auth/', include('authentication.urls')),` pada file `shopeeta/urls.py`.  
* Membuat model kustom sesuai dengan proyek aplikasi Django.  
  Saya membuka *endpoint* `JSON` yang sudah saya buat sebelumnya pada tutorial 2, lalu menyalin data `JSON`. Setelah itu, saya membuka situs web [Quicktype](http://app.quicktype.io/). Pada situs web Quicktype, saya mengubah *setup name* menjadi `ProductEntry`, *source type* menjadi `JSON`, dan *language* menjadi `Dart`. Kemudian, saya menempel data JSON yang telah disalin sebelumnya ke dalam *textbox* yang tersedia pada Quicktype, lalu klik pilihan `Copy Code` pada Quicktype. Setelah mendapatkan kode model melalui Quicktype, saya membuat folder baru `models/` pada subdirektori `lib/` di proyek Flutter saya. Kemudian, saya membuat file baru pada folder tersebut dengan nama `product_entry.dart`, dan tempel kode yang sudah disalin dari Quicktype.  
* Membuat halaman yang berisi daftar semua item yang terdapat pada *endpoint* `JSON` di Django yang telah kamu *deploy*.  
  * Tampilkan *name*, *price*, dan *description* dari masing-masing item pada halaman ini.

  Untuk melakukan perintah *HTTP request*, kita membutuhkan *package* tambahan yakni *package* [http](http://pub.dev/packages/http). Saya menjalankan perintah `flutter pub add http` pada terminal proyek Flutter untuk menambahkan *package* `http`. Pada file `android/app/src/main/AndroidManifest.xml`, saya menambahkan kode berikut untuk memperbolehkan akses Internet pada aplikasi Flutter yang sedang dibuat.

  ...

      \<application\>

      ...

      \</application\>

      \<\!-- Required to fetch data from the Internet. \--\>

      \<uses-permission android:name="android.permission.INTERNET" /\>

  ...


  Setelah itu, saya membuat berkas baru pada direktori `lib/screens` dengan nama `list_productentry.dart`. Pada berkas `list_productentry.dart`, impor *library* yang dibutuhkan. Kemudian, saya mengubah \[APP\_NAME\] menjadi `shopeeta`. 


  import 'package:flutter/material.dart';

  import 'package:shopeeta/models/product\_entry.dart';

  ...


  Isi potongan kode dari berkas `list_productentry.dart`. Adalah sebagai berikut.

  import 'package:flutter/material.dart';

  import 'package:shopeeta/models/product\_entry.dart';

  import 'package:shopeeta/widgets/left\_drawer.dart';

  import 'package:pbp\_django\_auth/pbp\_django\_auth.dart';

  import 'package:provider/provider.dart';


  class ProductEntryPage extends StatefulWidget {

    const ProductEntryPage({super.key});


    @override

    State\<ProductEntryPage\> createState() \=\> \_ProductEntryPageState();

  }


  class \_ProductEntryPageState extends State\<ProductEntryPage\> {

    Future\<List\<ProductEntry\>\> fetchProduct(CookieRequest request) async {

      final response \= await request.get('http://localhost:8000/json/');

      

      // Melakukan decode response menjadi bentuk json

      var data \= response;

      

      // Melakukan konversi data json menjadi object ProductEntry

      List\<ProductEntry\> listProduct \= \[\];

      for (var d in data) {

        if (d \!= null) {

          listProduct.add(ProductEntry.fromJson(d));

        }

      }

      return listProduct;

    }


    @override

    Widget build(BuildContext context) {

      final request \= context.watch\<CookieRequest\>();

      return Scaffold(

        appBar: AppBar(

          title: const Text('Produk Entry List'),

        ),

        drawer: const LeftDrawer(),

        body: FutureBuilder(

          future: fetchProduct(request),

          builder: (context, AsyncSnapshot snapshot) {

            if (snapshot.data \== null) {

              return const Center(child: CircularProgressIndicator());

            } else {

              if (\!snapshot.hasData) {

                return const Column(

                  children: \[

                    Text(

                      'Belum ada data produk pada Shopeeta.',

                      style: TextStyle(fontSize: 20, color: Color(0xff59A5D8)),

                    ),

                    SizedBox(height: 8),

                  \],

                );

              } else {

                return ListView.builder(

                  itemCount: snapshot.data\!.length,

                  itemBuilder: (\_, index) \=\> Container(

                    margin:

                        const EdgeInsets.symmetric(horizontal: 16, vertical: 12),

                    padding: const EdgeInsets.all(20.0),

                    child: Column(

                      mainAxisAlignment: MainAxisAlignment.start,

                      crossAxisAlignment: CrossAxisAlignment.start,

                      children: \[

                        Text(

                          "${snapshot.data\!\[index\].fields.name}",

                          style: const TextStyle(

                            fontSize: 18.0,

                            fontWeight: FontWeight.bold,

                          ),

                        ),

                        const SizedBox(height: 10),

                        Text("${snapshot.data\!\[index\].fields.description}"),

                        const SizedBox(height: 10),

                        Text("${snapshot.data\!\[index\].fields.amount}"),

                        const SizedBox(height: 10),

                        Text("${snapshot.data\!\[index\].fields.price}"),

                        const SizedBox(height: 10),

                        Text("${snapshot.data\!\[index\].fields.time}")

                      \],

                    ),

                  ),

                );

              }

            }

          },

        ),

      );

    }

  }


  Kemudian saya menambahakan halaman `list_productentry.dart` ke `widgets/left_drawer.dart` dengan menambahkan kode berikut.

  // Kode ListTile Menu

  ...

  ListTile(

      leading: const Icon(Icons.add\_reaction\_rounded),

      title: const Text('Daftar Produk),

      onTap: () {

          // Route menu ke halaman produk

          Navigator.push(

              context,

              MaterialPageRoute(builder: (context) \=\> const ProductEntryPage()),

          );

      },

  ),

  ...


  Ubah fungsi tombol `Lihat Produk` pada halaman utama agar mengarahkan ke halaman `ProductPage`. Saya melakukan *redirection* dengan menambahkan `else if` setelah kode `if(...){...}` di bagian akhir `onTap: () { }` yang ada pada file `widgets/product_card.dart`

  `...`

  `else if (item.name == "Lihat Product") {`

      `Navigator.push(context,`

          `MaterialPageRoute(`

              `builder: (context) => const ProductEntryPage()`

          `),`

      `);`

  `}`

  `...`


  Impor *file* yang dibutuhkan saat menambahkan `ProductEntryPage` ke `left_drawer.dart` dan `product_card.dart`

* Melakukan filter pada halaman daftar item dengan hanya menampilkan item yang terasosiasi dengan pengguna yang login.  
  Untuk memfilter pada halaman daftar item, saya membuat autentikasi login dan logout. Langkah-langkah untuk implementasi login sudah ada pada penjelasan sebelumnya. Pengguna yang terdaftar ketika berhasil login akan menampilkan data sesuai yang mereka input dan tidak akan menampilkan data pengguna yang lain.