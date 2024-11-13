# Sentiment-Analisis-by-Fawwaz
### Analisis Kode yang dibuat dan Perbedaan Model dengan yang ada di folder zip yang dibagikan

**Alasan perubahan**
> Folder ZIP mungkin tidak bisa dijalankan di Google Colab karena beberapa alasan yang berhubungan dengan keterbatasan Colab. Pertama, jika proyek membutuhkan server runtime khusus seperti gRPC, Colab sering kesulitan menjalankannya karena pengaturan jaringannya tidak mendukung koneksi server yang selalu aktif. Selain itu, jika proyek bergantung pada versi tertentu dari library seperti `tensorflow`, `torch`, atau `transformers`, mungkin ada ketidakcocokan dengan versi standar yang ada di Colab. Proyek yang menggunakan framework tambahan seperti `Caikit` juga bisa menemui masalah, karena framework ini sering membutuhkan konfigurasi yang lebih kompleks yang tidak tersedia di Colab. Jika struktur proyek berisi banyak file konfigurasi atau model yang rumit, Colab dapat kesulitan menavigasi atau menemukan semua file yang diperlukan, terutama karena akses file dibatasi pada direktori tertentu seperti `/content/`. Secara keseluruhan, Colab lebih cocok untuk proyek sederhana, sementara proyek yang membutuhkan server runtime, banyak file konfigurasi, atau setup lingkungan yang khusus lebih cocok dijalankan di komputer lokal atau server khusus.


**1. Kode yang Dibuat**

Kode ini adalah implementasi sederhana untuk melakukan analisis sentimen pada teks bahasa Inggris langsung di Google Colab.

> - **Inisialisasi Model**: Kode ini menggunakan `transformers` dari Hugging Face, yang menyediakan pipeline analisis sentimen dengan model `distilbert-base-uncased-finetuned-sst-2-english`. Model ini dirancang untuk mengenali sentimen positif dan negatif dalam kalimat bahasa Inggris. Karena berbasis arsitektur DistilBERT—versi yang lebih ringan dari BERT—model ini cukup cepat dan akurat untuk tugas analisis sentimen.

> - **Fungsi `analyze_sentiment`**: Fungsi ini menerima teks yang dimasukkan pengguna, kemudian memprosesnya menggunakan model untuk menghasilkan label sentimen positif atau negatif beserta tingkat kepercayaannya. Fungsi ini juga menangani kemungkinan error, sehingga jika terjadi masalah saat analisis, pesan error akan muncul dan nilai default akan dikembalikan.

> - **Antarmuka Interaktif**: Menggunakan `ipywidgets`, kode ini menyediakan antarmuka yang terdiri dari kotak teks untuk input kalimat, tombol “Analisis Sentimen” untuk menjalankan analisis, dan label hasil yang menampilkan sentimen dan tingkat kepercayaan. Terdapat juga pesan peringatan yang memberi tahu pengguna bahwa model ini hanya akurat untuk teks bahasa Inggris.


**2. Perbedaan dengan Model dalam File ZIP**

Jika kita membandingkan dengan model yang mungkin ada dalam file ZIP, ada beberapa perbedaan utama:

> - **Dukungan Bahasa**: Model `distilbert-base-uncased-finetuned-sst-2-english` ini hanya dilatih pada dataset bahasa Inggris, sehingga hasilnya paling akurat untuk teks bahasa Inggris. Jika model dalam file ZIP mendukung bahasa Indonesia atau beberapa bahasa lain, model tersebut akan lebih fleksibel dan mampu menganalisis sentimen dalam berbagai bahasa.

> - **Implementasi dan Backend**: Kode ini menggunakan pipeline sederhana berbasis PyTorch, sehingga mudah dijalankan langsung di Colab. Model dalam file ZIP mungkin menggunakan setup yang lebih kompleks, misalnya berbasis gRPC atau server runtime tertentu, yang lebih cocok untuk integrasi dalam aplikasi atau lingkungan produksi. Pendekatan tersebut biasanya lebih fleksibel untuk berbagai kebutuhan dan beban kerja yang lebih berat.

> - **Framework yang Digunakan**: Kode ini menjalankan model langsung melalui pipeline `transformers`, yang sangat mudah diintegrasikan dalam Google Colab. Sebaliknya, model dalam file ZIP mungkin menggunakan framework tambahan, seperti `Caikit`, yang memungkinkan model dijalankan dalam pengaturan server atau API dengan lebih banyak kontrol dan fleksibilitas.

Secara keseluruhan, kode ini adalah implementasi ringan dan mudah digunakan untuk eksperimen atau tugas sederhana di Colab, sementara model dalam file ZIP kemungkinan besar lebih kompleks dan dirancang untuk penggunaan yang lebih serius atau produksi.
