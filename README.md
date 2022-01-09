## Tugas Akhir


### Flowchart :
<p align="center"><img src="https://github.com/chanlyseptian/Sentiment-Analysis-using-CNN-and-Word2Vec/blob/master/img/flowchart.png">



### [Part 1] Crawling and Labeling Data

<p align="justify">
Data tweet yang diambil dari tanggal 01 Januari 2021 hingga 10 Oktober 2021. Data dikumpulkan sebanyak-banyaknya agar nanti diseleksi dan diberi label sentimen seimbang. Proses pelabelan dilakukan oleh 2 orang dimana terdapat panduan untuk cara melabeli dataset tersebut.

- Kelas negatif diberi nilai -1 dimana terdapat kata-kata kasar, emosi negatif dan terdapat ujaran kebencian.

- Kelas netral bernilai 0 dimana terdapat kata-kata pertanyaan, informasi berita dan tidak ada kata-kata kasar ataupun 
kata-kata positif.
- Kelas positif diberi nilai 1 dimana terdapat kata-kata positif, emosi positif dan terdapat ujaran pendukung.
<p align="center"><img src="https://github.com/chanlyseptian/Sentiment-Analysis-using-CNN-and-Word2Vec/blob/master/img/label.png" width="500">

</p>



### [Part 2] Exploratory Data Analysis
Dataset yang didapatkan dari hasil crawling masih dalam bentuk yang tidak terstruktur. Preproses yang dilakukan yaitu Cleansing, Case Folding, Normalization, Stop Words Removal, Lemmatazion dan Tokenizing
<p align="center"><img src="https://github.com/chanlyseptian/Sentiment-Analysis-using-CNN-and-Word2Vec/blob/master/img/wordcloud.png"</p>
</p>

### [Part 3] Word2Vec Embeddings

<p align="justify">
Word2Vec yang digunakan telah dilatih dengan 100 miliyar kata dari Google News memakai arsitektur CBOW lalu dihasilkan model dengan vektor 300 dimensi dan memiliki 3 juta kata. Model ini merupakan open-source yang dapat di unduh di laman https://code.google.com/p/Word2Vec/ dengan ukuran 1.6 GB
<p align="center"><img src="https://github.com/chanlyseptian/Sentiment-Analysis-using-CNN-and-Word2Vec/blob/master/img/word2vec.png">

</p>

### [Part 4] CNN

<p align="justify">
<p align="center"><img src="https://github.com/chanlyseptian/Sentiment-Analysis-using-CNN-and-Word2Vec/blob/master/img/CNN.png">

Metode klasifikasi CNN dibangun menggunakan library TensorFlow dan diimplementasikan di Google Collaboratory dengan pengaturan TPU. Arsitektur jaringan pada penelitian ini yaitu 2 convolutional layer,
2 max pooling layer, 2 dropout, global max pooling dan dense layer. 

Convolution layer bertujuan untuk mengekstrak feature dari input kalimat. Proses convolution memanfaatkan 
bantuan filter / kernel untuk mendeteksi representasi teks melalui bentuk vektor kata yang diterima dari model pre-trained Word2Vec embeddings.

Pooling layer bertujuan untuk mengambil sample convolution matrix dan berguna untuk mengurangi 
kompleksitas dimensi dan tetap menyimpan informasi penting dari konvolusi. Pada penelitian ini akan menggunakan 
max-pooling layer untuk mengambil nilai maximum dari pooling. Setelah itu akan menggunakan dropout layer. 

Dropout merupakan teknik regularisasi neural network. Neuron dipilih secara random agar tidak digunakan saat
pelatihan. Proses ini dapat mencegah terjadinya overfitting.

Fully-connected layer atau sering disebut dense layer digunakan untuk melatih model klasifikasi dan memiliki 
output yang jumlahnya sesuai dengan jumlah kelas yang akan diklasifikasikan / diprediksi dimana pada penelitian ini 
ada 3, yaitu negatif, netral dan positif.


</p>

### [Part 5] Confusion Matrix

<p align="justify">
Hasil akurasi tertinggi ada di batch size 256 dengan learning rate 0.01 di epoch ke-17 yaitu dengan akurasi 93%
<p align="center"><img src="https://github.com/chanlyseptian/Sentiment-Analysis-using-CNN-and-Word2Vec/blob/master/img/confusion%20matrix.png">

</p>
