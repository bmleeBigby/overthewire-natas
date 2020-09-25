## What is Natas OverTheWire ?

Challenges yang disediakan Natas mengajarkan dasar dasar dari keamanan website dari sisi server.

Setiap level menyimpan password yang dapat digunakan untuk mengakses level selanjutnya. Tujuan kita adalah dengan bagaimanapun caranya mendapatkan password berikutnya dan berpindah ke level yang lebih tinggi dan lebih menantang. Semua password juga disimpan di /etc/natas_webpass/natas(n) dan cuma bisa diakses oleh natas(n-1) dan natas(n+1)

Natas OverTheWire dibuka untuk umum dan dapat di akses melalui link [berikut](https://overthewire.org/wargames/natas/)

### Level 00
[http://natas0.natas.labs.overthewire.org/](http://natas0.natas.labs.overthewire.org/)
natas0:natas0

![Image](img/natas0/soal.PNG)

Diberikan tampilan awal website challenge seperti diatas, kita bisa mendapatkan flag dengan membuka page source

```
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas0", "pass": "natas0" };</script></head>
<body>
<h1>natas0</h1>
<div id="content">
You can find the password for the next level on this page.

<!--The password for natas1 is gtVrDuiDfck831PqWsLEZy5gyDz1clto -->
</div>
</body>
</html>
```

### Level 01
[http://natas1.natas.labs.overthewire.org/](http://natas1.natas.labs.overthewire.org/)
natas1:gtVrDuiDfck831PqWsLEZy5gyDz1clto

![Image](img/natas1/soal.PNG)

Diberikan tampilan awal website challenge mirip seperti challenge 0, kita bisa menggunakan cara yang sama namun klik kanan di block, jadi kita bisa menggunakan CTRL-U untuk membuka source page

```
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas1", "pass": "gtVrDuiDfck831PqWsLEZy5gyDz1clto" };</script></head>
<body oncontextmenu="javascript:alert('right clicking has been blocked!');return false;">
<h1>natas1</h1>
<div id="content">
You can find the password for the
next level on this page, but rightclicking has been blocked!

<!--The password for natas2 is ZluruAthQk7Q2MqmDeTiUij2ZvWy2mBi -->
</div>
</body>
</html>
```

### Level 02
[http://natas2.natas.labs.overthewire.org/](http://natas2.natas.labs.overthewire.org/)
natas2:ZluruAthQk7Q2MqmDeTiUij2ZvWy2mBi

![Image](img/natas2/soal.PNG)

Seperti challenge sebelumnya kita akan melihat source code page nya

```
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas2", "pass": "ZluruAthQk7Q2MqmDeTiUij2ZvWy2mBi" };</script></head>
<body>
<h1>natas2</h1>
<div id="content">
There is nothing on this page
<img src="files/pixel.png">
</div>
</body></html>
```

Kita bisa melihat ada img src tag ke files/pixel.png, mari kita cek ada apa sebenarnya di directory files.

![Image](img/natas2/step1.PNG)

Ternyata kita bisa melihat directory dan files didalamnya, hal ini terjadi karena misconfiguration pada htaccess yang tidak menonaktifkan Indexes.

Membuka users.txt kita akan mendapatkan flag untuk challenge selanjutnya

```
# username:password
alice:BYNdCesZqW
bob:jw2ueICLvT
charlie:G5vCxkVV3m
natas3:sJIJNW6ucpu6HPZ1ZAchaDtwd7oGrD14
eve:zo4mJWyNj2
mallory:9urtcpzBmH
```