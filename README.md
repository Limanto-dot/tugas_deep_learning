1. Deskripsi Proyek

Proyek menguji penggunaan ResNet-18 dalam klasifikasi ras kucing dan anjing.

Akan ada 3 test yang dilakukan, yaitu training from scratch, feature extraction, fine-tuning, dan data augmentation

2. Dataset

Dataset yang digunakan adalah Oxford-IIIT Pet melalui `torchvision.datasets.OxfordIIITPet`.

Sebanyak 10 kelas dipilih, terdiri dari lima ras kucing (Abyssinian, Bengal, Birman, Bombay, British Shorthair) dan lima ras anjing (Beagle, Boxer, Chihuahua, Pomeranian, Pug).

Total dataset berjumlah 1.981 gambar, dibagi secara stratified menjadi:

- Training: 1.386 gambar (70%)
- Validation: 297 gambar (15%)
- Test: 298 gambar (15%)

3. Konfigurasi Eksperimen

Model utama adalah ResNet-18, menggunakan input 224 × 224 piksel dan normalisasi ImageNet.

Konfigurasi training meliputi batch size 32, optimizer AdamW, CrossEntropyLoss, random seed 42, serta early stopping dengan patience 4.

Eksperimen yang dijalankan:

- B1: ResNet-18 train from scratch
- B2: Feature extraction menggunakan pretrained ImageNet
- B3: Fine-tuning pada `layer4` dan classifier dengan differential learning rate.
- B4: Perbandingan training dengan dan tanpa data augmentation.

4. Interpreter yang digunakan

Project dikerjakan melalui google colab, dan bisa langung dijalankan dengan hanya menggunakan file .ipynb yang sudah tersedia
