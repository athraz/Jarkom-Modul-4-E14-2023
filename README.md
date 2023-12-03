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
- **LakeKorridor
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
