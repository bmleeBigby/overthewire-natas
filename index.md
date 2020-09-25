## What is Natas OverTheWire ?

Challenges yang disediakan Natas mengajarkan dasar dasar dari keamanan website dari sisi server.

Setiap level menyimpan password yang dapat digunakan untuk mengakses level selanjutnya. Tujuan kita adalah dengan bagaimanapun caranya mendapatkan password berikutnya dan berpindah ke level yang lebih tinggi dan lebih menantang. Semua password juga disimpan di /etc/natas_webpass/natas(n) dan cuma bisa diakses oleh natas(n-1) dan natas(n+1)

Natas OverTheWire dibuka untuk umum dan dapat di akses melalui link [berikut](https://overthewire.org/wargames/natas/)

### Level 00
[http://natas0.natas.labs.overthewire.org/](http://natas0.natas.labs.overthewire.org/0)
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

