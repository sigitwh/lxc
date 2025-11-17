Cara install LXC di Debian.
Semua perinta di sini berada di user root.
Misalnya akan membuat container dengan nama lampp.

lxc-create -n lampp -t download

Pilih OS, versi OS, dan arsitektur dari daftar list.
Misalnya:
OS = ubuntu
Release = jammy
Architecture = arm64

Setelah selesai, jalankan dengan cara
lxc-start -n lampp -d

Untuk masuk ke container sebagai root
lxc-attach -n lampp

Untuk menghapus container
lxc-stop -n lampp
lxc-destroy -n lampp



