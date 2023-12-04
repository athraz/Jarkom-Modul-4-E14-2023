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

```sh
auto eth0
iface eth0 inet dhcp
up iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 192.213.0.0/19

auto eth1
iface eth1 inet static
	address 192.213.0.13
	netmask 255.255.255.252
auto eth2
iface eth2 inet static
	address 192.213.0.17
	netmask 255.255.255.252
auto eth3
iface eth3 inet static
	address 192.213.0.37
	netmask 255.255.255.252
```
- **Frieren**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.14
	netmask 255.255.255.252
	gateway 192.213.0.13
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.213.0.9
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 192.213.0.65
	netmask 255.255.255.224
```
- **Denken**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.38
	netmask 255.255.255.252
	gateway  192.213.0.37
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
auto eth1
iface eth1 inet static
	address 192.213.2.1
	netmask 255.255.255.0
```
- **Eisen**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.18
	netmask 255.255.255.252
	gateway 192.213.0.17
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.213.0.33
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 192.213.0.49
	netmask 255.255.255.248

auto eth3
iface eth3 inet static
	address 192.213.0.29
	netmask 255.255.255.252

auto eth4
iface eth4 inet static
	address 192.213.0.21
	netmask 255.255.255.252
```
- **Fern**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.2
	netmask 255.255.255.252
	gateway 192.213.0.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.213.24.1
	netmask 255.255.248.0
```
- **Flamme**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.10
	netmask 255.255.255.252
	gateway 192.213.0.9
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.213.0.1
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 192.213.8.1
	netmask 255.255.252.0

auto eth3
iface eth3 inet static
	address 192.213.0.5
	netmask 255.255.255.252
```
- **Himmel**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.6
	netmask 255.255.255.252
	gateway 192.213.0.5
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.213.0.41
	netmask 255.255.255.248

```
- **Lawine**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.26
	netmask 255.255.255.252
	gateway 192.213.0.25
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.213.0.129
	netmask 255.255.255.192
```
- **Heiter**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.131
	netmask 255.255.255.192
	gateway 192.213.0.129
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.213.12.1
	netmask 255.255.252.0
```
- **Linie**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.22
	netmask 255.255.255.252
	gateway 192.213.0.21
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.213.4.1
	netmask 255.255.254.0

auto eth2
iface eth2 inet static
	address 192.213.0.25
	netmask 255.255.255.252
```
- **Lugner**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.30
	netmask 255.255.255.252
	gateway 192.213.0.29
	up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 192.213.16.1
	netmask 255.255.252.0

auto eth2
iface eth2 inet static
	address 192.213.1.1
	netmask 255.255.255.0
```
- **LakeKorridor**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.66
	netmask 255.255.255.224
	gateway 192.213.0.65
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- **LaubHills**
```sh
auto eth0
iface eth0 inet static
	address 192.213.24.2
	netmask 255.255.248.0
	gateway 192.213.24.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- **AppetitRegion**
```sh
auto eth0
iface eth0 inet static
	address 192.213.24.3
	netmask 255.255.248.0
	gateway 192.213.24.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- **RohrRoad**
```sh
auto eth0
iface eth0 inet static
	address 192.213.8.2
	netmask 255.255.252.0
	gateway 192.213.8.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- **SchwerMountains**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.42
	netmask 255.255.255.248
	gateway 192.213.0.41
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- **BredtRegion**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.130
	netmask 255.255.255.192
	gateway 192.213.0.129
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- **RiegelCanyon**
```sh
auto eth0
iface eth0 inet static
	address 192.213.12.2
	netmask 255.255.252.0
	gateway 192.213.12.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- **GranzChannel**
```sh
auto eth0
iface eth0 inet static
	address 192.213.4.2
	netmask 255.255.254.0
	gateway 192.213.4.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```  
- **GrobeForest**
```sh
auto eth0
iface eth0 inet static
	address 192.213.1.2
	netmask 255.255.255.0
	gateway 192.213.1.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
``` 
- **TurkRegion**
```sh
auto eth0
iface eth0 inet static
	address 192.213.16.2
	netmask 255.255.252.0
	gateway 192.213.16.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
``` 
- **RoyalCapital**
```sh
auto eth0
iface eth0 inet static
	address 192.213.2.2
	netmask 255.255.255.0
	gateway 192.213.2.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```  
- **WilleRegion**
```sh
auto eth0
iface eth0 inet static
	address 192.213.2.65
	netmask 255.255.255.0
	gateway 192.213.2.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
``` 
- **Richter**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.50
	netmask 255.255.255.248
	gateway 192.213.0.49
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- **Revolte**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.51
	netmask 255.255.255.248
	gateway 192.213.0.49
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```  
- **Stark**
```sh
auto eth0
iface eth0 inet static
	address 192.213.0.34
	netmask 255.255.255.252
	gateway 192.213.0.33
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
- **Sein** 
```sh
auto eth0
iface eth0 inet static
	address 192.213.12.3
	netmask 255.255.252.0
	gateway 192.213.12.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

### Routing
Berikut konfigurasi pada masing-masing router untuk melakukan routing:

- **Aura**
```sh
route add -net 192.213.0.64 netmask 255.255.255.252 gw 192.213.0.14 
route add -net 192.213.0.8 netmask 255.255.255.252 gw 192.213.0.14 
route add -net 192.213.2.0 netmask 255.255.255.0 gw 192.213.0.38
route add -net 192.213.0.32 netmask 255.255.255.252 gw 192.213.0.18
route add -net 192.213.0.48 netmask 255.255.255.248 gw 192.213.0.18
route add -net 192.213.0.28 netmask 255.255.255.252 gw 192.213.0.18
route add -net 192.213.16.0 netmask 255.255.252.0 gw 192.213.0.18
route add -net 192.213.1.0 netmask 255.255.255.0 gw 192.213.0.18
route add -net 192.213.0.20 netmask 255.255.255.252 gw 192.213.0.18
route add -net 192.213.4.0 netmask 255.255.254.0 gw 192.213.0.18
route add -net 192.213.0.24 netmask 255.255.255.252 gw 192.213.0.18
route add -net 192.213.0.0 netmask 255.255.255.252 gw 192.213.0.14
route add -net 192.213.24.0 netmask 255.255.248.0 gw 192.213.0.14
route add -net 192.213.8.0 netmask 255.255.252.0 gw 192.213.0.14
route add -net 192.213.0.4 netmask 255.255.255.252 gw 192.213.0.14
route add -net 192.213.0.40 netmask 255.255.255.248 gw 192.213.0.14
route add -net 192.213.0.128 netmask 255.255.255.192 gw 192.213.0.18
route add -net 192.213.12.0 netmask 255.255.252.0 gw 192.213.0.18
```
- **Frieren**
```sh
route add -net 192.213.0.0 netmask 255.255.255.252 gw 192.213.0.10
route add -net 192.213.24.0 netmask 255.255.248.0 gw 192.213.0.10
route add -net 192.213.8.0 netmask 255.255.252.0 gw 192.213.0.10
route add -net 192.213.0.4 netmask 255.255.255.252 gw 192.213.0.10
route add -net 192.213.0.40 netmask 255.255.255.248 gw 192.213.0.10
```
- **Flamme**
```sh
route add -net 192.213.24.0 netmask 255.255.248.0 gw 192.213.0.2
route add -net 192.213.0.40 netmask 255.255.255.248 gw 192.213.0.6
```
- **Eisen**
```sh
route add -net 192.213.16.0 netmask 255.255.252.0 gw 192.213.0.30
route add -net 192.213.1.0 netmask 255.255.255.0 gw 192.213.0.30
route add -net 192.213.4.0 netmask 255.255.254.0 gw 192.213.0.22
route add -net 192.213.0.24 netmask 255.255.255.252 gw 192.213.0.22
route add -net 192.213.0.128 netmask 255.255.255.192 gw 192.213.0.22
route add -net 192.213.12.0 netmask 255.255.252.0 gw 192.213.0.22
```
- **Lawine**
```sh
route add -net 192.213.12.0 netmask 255.255.252.0 gw 192.213.0.131
```
- **Linie**
```sh
route add -net 192.213.0.128 netmask 255.255.255.192 gw 192.213.0.26
route add -net 192.213.12.0 netmask 255.255.252.0 gw 192.213.0.26
```

### Testing
Berikut beberapa hasil testing:

- **Client - Client**

![CC](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/74baec1a-8246-45ff-a04a-399b08cda4c8)

- **Client - Server**

![CS](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/54f8b548-6b50-4200-ba2a-a018808be94c)

- **Client - Router**

![CR](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/2727c8ed-8885-42eb-ab22-e65d54121e28)

- **Server - Server**

![SS](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/2f64c7f3-6bb6-42bb-9236-d7598429a4a0)

- **Server - Router**

![SR](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/4e7f39ca-41d4-46cc-a980-2f752359ee54)

- **Router - Router**

![RR](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/2a45466f-6925-4b9e-acf1-c6a4a1df77aa)

- **Ping Google**

![ping google](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/74723887-1571-485b-9313-c113af463d5d)

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

- **Lawine**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/b9c8d17d-0bc4-4603-9f1c-b1363aa3e64c)

- **Heiter**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/fba29ed9-4756-401f-912d-d39c58d22fd8)

- **Lugner**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/b05566ab-8c23-4ce8-af8d-c79e1205290b)

- **Denken**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/b9e86de3-0082-4533-a078-3ef550161681)

### Testing
Berikut beberapa hasil testing:

- **Client - Client**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/a382abf2-3028-4972-ab99-429020fd9654)

- **Client - Server**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/fd8a88a1-ddd8-4a96-ae11-947e45af1706)

- **Client - Router**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/f332b64a-4c75-4db6-8f7d-47f96c425cd4)

- **Server - Server**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/8fdd4c24-a932-4c77-a440-fb5693f4a1b3)

- **Server - Router**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/a5ee2dc8-a41b-40bb-80d4-add3a09df971)

- **Router - Router**

![image](https://github.com/athraz/Jarkom-Modul-4-E14-2023/assets/96050618/2197f513-9dc4-4856-80d1-18971f6e0720)
