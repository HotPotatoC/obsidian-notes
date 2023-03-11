# Machine Learning

Merupakan cabang dari kecerdasan buatan atau Artifical Intelligence yang berorientasi pada dataset dan algoritma. Machine Learning meniru perilaku dan kognitif manusia dalam menyelesaikan sebuah masalah, mengidentifikasi, mempelajari sesuatu ataupun memprediksi suatu hasil. 

## Category Machine Learning

1. **Supervised Learning** adalah metode machine learning dimana dataset yang digunakan memiliki **label** dan juga dilakukan **pengawasan dari pengembang**. Contoh adalah Classification, ChatGPT (Hybrid supervised and reinforcement), Speech Recognition
2. **Unsupervised Learning** adalah metode machine learning yang memiliki tugas utama yaitu pattern matching atau mencari pola dari sebuah dataset yang **tidak memiliki label**. Contoh: Clustering Analysis dan data dimensionality reduction PCA
3. **Reinforcement Learning** adalah metode machine learning yang menggunakan dataset bersistem rewards / punishment dan menawarkan umpan balik algoritma untuk belajar dari pengalamanya untuk meningkatkan akurasinya dan menghasilkan hasil yang tepat. Contoh: AI dalam game (Chess, Go, Alien Isolation)

# PCA

PCA atau Principal Component Analysis merupakan metode dimensionality reduction yang akan digunakan untuk memproses sebuah data dari dataset besar menjadi dataset kecil, namun masih mencakupi sebagian besar informasi dari dataset besar

## Algoritma PCA

1. Mengubah semua nilai pada tiap variabel menjadi nilai standar (z-score)
2. Mencari matriks kovarians
3. Menhitung eigen values dan eigen vector dari matriks kovarian
4. Mengurutkan eigen value dari nilai terbesar ke terkecil untuk mendapatkan principal component
5. Mencari vektor baru berdasarkan principal component dengan mencari invers dari matriks eigen vektor yang sudah diurutkan
6. Menghitung nilai vektor baru dengan mengkalikan hasil matriks invers dengan dataset yang sebelumnya sudah diubah menjadi nilai standar
7. Melakukan dimensional reduction dengan menghilangkan eigen vector dengan nilai eigen value terkecil