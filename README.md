Cara install LXC di Debian.
Semua perinta di sini berada di user root.
Misalnya akan membuat container dengan nama lampp.

lxc-create -n lampp -t download

Pilih OS, versi OS, dan arsitektur dari daftar list.
Misalnya:
OS = ubuntu
Release = jammy
Architecture = arm64

kemudian set apparmor
nano /var/lib/lxc/lampp/config

ubah bagian ini menjadi
lxc.apparmor.profile = unconfined

Setelah selesai, jalankan dengan cara
lxc-start -n lampp -d

Untuk masuk ke container sebagai root
lxc-attach -n lampp

Untuk menghapus container
lxc-stop -n lampp
lxc-destroy -n lampp

Melihat daftar container
lxc-ls

Untuk melihat IP address
ip a
misalnya hasilnya 10.0.3.101

Untuk fowarding port 80 dari host ke container port 80, di jalankan di host
iptables -t nat -A PREROUTING -p tcp --dport 80 -j DNAT --to-destination 10.0.3.101:80
iptables -t nat -A POSTROUTING -j MASQUERADE





