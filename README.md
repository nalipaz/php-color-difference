php-color-difference
====================

PHP Color Difference using Delta E CIE 2000  

Example Usage for getting color difference:  

```php
<?php
include('lib/color_difference.class.php');

$rgb1 = [ 255, 0, 0 ];
$rgb2 = [ 100, 0, 0 ];

$color_difference = (new color_difference())->deltaECIE2000($rgb1, $rgb2);

print $color_difference . chr(10);
```

Example usage for getting closest color in a palette:
```php
<?php
$palette = array(
  '00' => array(255, 255, 255),
  '01' => array(0, 0, 0),
  '02' => array(0, 0, 139),
  '03' => array(0, 128, 0),
  '04' => array(255, 0, 0),
  '05' => array(139, 0, 0),
  '06' => array(128, 0, 128),
  '07' => array(255, 165, 0),
  '08' => array(255, 255, 0),
  '09' => array(50, 205, 50),
  '10' => array(0, 128, 128),
  '11' => array(173, 216, 230),
  '12' => array(0, 0, 255),
  '13' => array(255, 105, 180),
  '14' => array(128, 128, 128),
  '15' => array(211, 211, 211),
);

$color_rgb = array(255, 255, 128);
$color_delta_e = new color_difference($color_rgb);
$match_index = $color_delta_e->getClosestMatch($palette);
$color = $palette[$match_index];
```

Installation
============

Depends on PHP 5.4  

```
$ git clone https://github.com/renasboy/php-color-difference
$ cd php-color-difference
$ php example.php
```

Formula from www.brucelindbloom.com<br/>
Inspired by ruby colorscore and python colormath<br/>

