PteroBridge MUX 3.1.2 Fix2 - EXPERIMENTAL

Perbaikan inti: gateway sebelumnya membungkus socket pemain dengan BufferedInputStream saat membaca 4 byte awal untuk membedakan magic tunnel vs handshake Minecraft. BufferedInputStream dapat membaca lebih banyak byte dari socket ke buffer; setelah itu pump membaca langsung dari socket, sehingga byte handshake Minecraft yang sudah ter-buffer hilang. Versi ini membaca tepat 4 byte awal dari DataInputStream yang langsung membungkus socket tanpa buffering tambahan, lalu meneruskan 4 byte tersebut sebagai prefix dan membaca sisa stream langsung dari socket.

Kompilasi menggunakan stub API hanya untuk resolusi compile-time. Class org/bukkit TIDAK dimasukkan ke JAR. Belum diuji pada server Paper nyata. Gunakan server cadangan dan backup.

Protokol tetap eksperimental dan tidak menjamin kompatibilitas/keamanan produksi.
