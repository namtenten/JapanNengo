# JapanNengo / 年号
- [x] Convert Western Calendar to Japan Calendar.　西暦を和暦に変換
- [x] Convert Japan Calendar to Western Calendar.　和暦を西暦に変換

E.g: 西暦を和暦に変換

- 1989/01/02 ⇒ 昭和64年01月02日
- 2019/04/30 ⇒ 平成31年04月30日
- 2019/05/01 ⇒ 令和1年05月01日

E.g: 和暦を西暦に変換

- 昭和64年01月02日 ⇒ 1989/01/02
- 平成31年04月30日 ⇒ 2019/04/30
- 令和1年05月01日 ⇒ 2019/05/01

# Installation
## Composer
```shell
composer require namtenten/japan-nengo
```

# Usage
Test file:
```
# ./test/index.php
```

Example code (when using composer):

```php
<?php

require 'vendor/autoload.php';
use NamTenTen\JapanNengo;

$nengo = new JapanNengo();

$date = 19890102; // integer: YYYYMMDD
$nengo_date = $nengo->toNengoDate($date);
echo $date . " ⇒ " . $nengo_date . "\n";

$date = "2019/04/30"; // string: YYYY/MM/DD
$nengo_year = $nengo->toNengoYear($date);
$nengo_date = $nengo->toNengoDate($date);
echo $date . " ⇒ " . $nengo_year . "\n";
echo $date . " ⇒ " . $nengo_date . "\n";

$date = "20190501"; // string: YYYYMMDD
$nengo_year = $nengo->toNengoYear($date);
$nengo_date = $nengo->toNengoDate($date);
echo $date . " ⇒ " . $nengo_year . "\n";
echo $date . " ⇒ " . $nengo_date . "\n";

$date = "20191107";
$nengo_array = $nengo->toNengoArray($date);
$nengo_date = $nengo->toNengoDate($date);
echo $date . " ⇒ " . $nengo_date . "\n";
var_dump($nengo_array);
echo "\n";

$date = 20201231;
$nengo_array = $nengo->toNengoArray($date);
$nengo_date = $nengo->toNengoDate($date);
echo $date . " ⇒ " . $nengo_date . "\n";
var_dump($nengo_array);
echo "\n";

echo "==========================================\n";
echo "和暦を西暦に変換\n";
echo "==========================================\n";

$wareki = "昭和64年01月02日";
$seireki = $nengo->toDate($wareki);
echo "{$wareki} ⇒ {$seireki}\n";
echo "\n";

$wareki = "平成元年01月08日";
$seireki = $nengo->toDate($wareki);
echo "{$wareki} ⇒ {$seireki}\n";
echo "\n";

$wareki = "平成31年04月30日";
$seireki = $nengo->toDate($wareki);
echo "{$wareki} ⇒ {$seireki}\n";
echo "\n";

$wareki = "令和元年05月01日";
$seireki = $nengo->toDate($wareki);
echo "{$wareki} ⇒ {$seireki}\n";
echo "\n";

$wareki = "令和元年11月07日";
$seireki = $nengo->toDate($wareki);
echo "{$wareki} ⇒ {$seireki}\n";
echo "\n";

$wareki = "令和1年11月07日";
$seireki = $nengo->toDate($wareki);
echo "{$wareki} ⇒ {$seireki}\n";
echo "\n";

$seireki = $nengo->toYear($wareki);
echo "{$wareki} ⇒ {$seireki}\n";

$wareki = "令和2年11月07日";
$seireki = $nengo->toDate($wareki);
echo "{$wareki} ⇒ {$seireki}\n";
echo "\n";

$wareki = "令和2年11月07日";
$seireki = $nengo->toDateArray($wareki);
echo "{$wareki}\n";
var_dump($seireki);
echo "\n";
echo "\n";

echo "==========================================\n";
echo "作者情報\n";
echo "==========================================\n";

$donate_url = $nengo->donateUrl();
echo "Donate Url: " . $donate_url . "\n\n";

$author = $nengo->author();
var_dump($author);
echo "\n";
```
