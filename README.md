# Jarkom-Modul-4-E14-2023

| Nama                      | NRP           |Username      |
|---------------------------|---------------|--------------|
|Muhammad Razan Athallah    |5025211008     |athraz        |
|Moh rosy haqqy aminy       |5025211012     |hqlco         |

$~$

## Topologi
Berikut topologi yang digunakan pada praktikum modul 4:

![Screenshot 2023-11-28 235649 (1)](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/bf2f33f1-e1cf-441c-a5f3-413e4041c7a7)

$~$

## Rute
Topologi dibagi menjadi 21 subnet dengan `rute` sebagai berikut:  

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/7e987d1c-ff19-4ca1-8bba-f4ee7483b6a2)

Berikut pembagian rute jika digambarkan pada topologi:

![Prak Jarkom M4 E14 - Frame 1](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/de27e60d-10fe-49be-b9f0-ee3bfe247b9d)

$~$

## VLSM
VLSM (Variable Length Subnet Masking) digunakan untuk mengefisienkan pembagian IP di dalam jaringan. Besar netmask disesuaikan dengan banyaknya komputer/host yang membutuhkan alamat IP. Total IP yang dibutuhkan adalah `4255`, sehingga pada awalnya menggunakan Network ID `192.213.0.0` dengan netmask `/19`.
Untuk memenuhi kebutuhan masing-masing subnet, IP akan dibagi menggunakan tree dibawah.

### Tree
Berikut tree pembagian IP metode VLSM:

![Prak Jarkom M4 E14 - VLSM.jpg](<Prak Jarkom M4 E14 - VLSM.jpg>)

### Pembagian IP
Dari tree diatas, didapatkan pembagian IP untuk masing-masing subnet sebagai berikut:

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/e61f7b71-7412-445f-9e17-aca4ab3b15b2)

### Subnetting
Berikut konfigurasi pada masing-masing router, client, dan server untuk melakukan subnetting:

- **Aura**
- **Frieren**
- **Denken**
- **Eisen**
- **Fern**
- **Flamme**
- **Himmel**
- **Lawine**
- **Heiter**
- **Linie**
- **Lugner**
- **LakeKorridor**
- **LaubHills**
- **AppetitRegion**
- **RohrRoad**
- **SchwerMountains**
- **BredtRegion**
- **RiegelCanyon**
- **GranzChannel**  
- **GrobeForest** 
- **TurkRegion** 
- **RoyalCapital**  
- **WilleRegion** 
- **Richter**
- **Revolte**  
- **Stark**
- **Sein** 

### Routing
Berikut konfigurasi pada masing-masing router untuk melakukan routing:

- **Aura**
- **Frieren**
- **Flamme**
- **Eisen**
- **Lawine**
- **Linie**

### Testing
Berikut beberapa hasil testing:

$~$

## CIDR
Classless Inter Domain Routing, perhitungan pada teknik CIDR juga didasarkan pada jumlah komputer/host yang ada di dalam subnet. Tetapi cara mendapatkan subnet besar tidak sama dengan VLSM. Penerapan teknik CIDR dilakukan dengan beberapa iterasi, tiap iterasi menggabungkan subnet paling bawah di dalam topologi (subnet yang paling jauh dari internet). Pada praktikum ini didapat hasil penggabungan akhir memiliki netmask `/14`, berikutnya akan diberikan detail dari tiap penggabungan.

### Penggabungan


### Tree
Berikut tree pembagian IP metode CIDR:

![Prak Jarkom M4 E14 - CIDR.jpg](<Prak Jarkom M4 E14 - CIDR.jpg>)

### Pembagian IP
Dari tree diatas, didapatkan pembagian IP untuk masing-masing subnet sebagai berikut:

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/1766ea9d-4a0e-4a04-9f91-6eee173b13ab)

### Subnetting
Berikut konfigurasi pada masing-masing router, client, dan server untuk melakukan subnetting:

![Prak Jarkom M4 E14 - Address CIDR](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/35cd93f5-95c7-4631-8d32-3458e6414f76)

Netmask disesuaikan dengan pembagian IP dan gateway disesuaikan dengan gambar diatas.

### Routing
Berikut konfigurasi pada masing-masing router untuk melakukan routing:

- **Aura**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/c597567a-6858-4c30-a448-432622e7c566)
![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/287d0f67-61d6-44d5-a8d2-69c56f7bea9c)

- **Frieren**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/2a68da15-060f-4dd8-93fa-0bbc051618dc)

- **Flamme**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/7e9cd799-c09d-4aaa-b94b-a307eb276b72)

- **Fern**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/bdbe0697-b325-4c90-a9a0-47712ce50703)

- **Himmel**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/3ed14ca8-efe3-4049-977a-872155f7bdbd)

- **Eisen**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/8b8980e7-48f8-4c2b-8aff-ec06de064f95)

- **Linie**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/b9d02881-c9a6-4eeb-968c-8130db461923)

- **Lawime**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/b9c8d17d-0bc4-4603-9f1c-b1363aa3e64c)

- **Heiter**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/fba29ed9-4756-401f-912d-d39c58d22fd8)

- **Lugner**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/b05566ab-8c23-4ce8-af8d-c79e1205290b)

- **Denken**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/b9e86de3-0082-4533-a078-3ef550161681)

### Testing
Berikut beberapa hasil testing:
