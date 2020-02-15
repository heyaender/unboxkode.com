+++
authors = [
    "",
]
title = "Cara Kerja NAT"
date = "2019-03-11"
description = ""
tags = [
    "markdown",
    "css",
    "html",
    "themes",
]
categories = [
    "themes",
    "syntax",
]
series = ["Themes Guide"]
aliases = ["migrate-from-jekyl"]
images = [
    "markdown-syntax.jpg",
]
+++


Dari judulnya udah tau menjelaskan cara kerja dari nat, dan digambar depan juga ada. langsung saja ke bahasan yuk.NAT mempunyai fungsi yaitu sebagai translasi sebuah IP address, sehingga dengan adanya NAT ini IP address private dapat dengan mudah mengakses alamat IP public.

Didalam IP address terdapat sebuah bagian yang mana di dalam IP tersebut terdapat informasi-informasi berupa alamat asal, alamat tujuan, TTL, dll. Bagian ini disebut dengan header.
Berikut adalah proses cara kerja dari NAT:

1. Sebuah komputer client dengan IP 192.168.1.2 akan mengakses atau melakukan request ke alamat www.google.co.id dengan IP 216.239.61.104.
2. Pada header, informasi yang tersimpan antara lain alamat asal > 192.168.1.2.
3. Ketika paket telah sampai pada router (gateway dari client), maka isi dari header akan dirubah menjadi : alamat asal > 192.168.1.1.
4. Sebelum paket keluar (menuju internet), maka header tersebut akan kembali berubah menjadi, alamat asal > 200.100.50.2, demikian seterusnya.

Proses di atas merupakan mekanisme dari SNAT (source NAT), dimana IP asal (komputer client) akan dirubah disesuaikan dengan IP ketika paket telah berpindah. Ketika server google melakukan response / balasan, maka akan terjadi DNAT (destination NAT), dimana IP tujuan akan berubah disesuaikan dengan tujuan paket (komputer client).