
---
id: 1068
title: GNU/Linux Temel Komutlar
date: 2017-08-27T13:13:28+00:00
author: admin
layout: post
image: /wp-content/uploads/2017/08/DeepinScreenshot_20170827154901.png
categories:
  - Linux
tags:
  - gnu
  - komut
  - komut satırı
  - linux
  - temel komutlar
---
Linux işletim sistemine yeni geçtiyseniz temel gnu/linux komutlarını bulmakta zorlanabilirsiniz. Bu bölümde başlagınçta işinize yarayacak birçok gnu/linux komutunu bulabilirsiniz. Bu yazının devamı niteliğinde bir yazı daha gelebilir.

Önemli tüm diğer temel linux komutlarını vermeden önce bahsetmek istediğim bir komut var. Bu komut "**man**" komutu. man komutu sayesinde kullanımını bilmediğiniz komutların nasıl kullanıldıklarını, ne işe yaradıklarını, yaratıcısını ve benzer komutları öğrenebilirsiniz.

Manual kelimesinin kısatlması olan **man**, gnu/linux üzerinde kullanılan komutların manual sayfalarını görmenizi sağlar.
man `komut` 
şeklinde kullanılır. Örneğin **man touch** ile touch komutu hakkında bilgi edinebilirsiniz.

## Dizinler/Klasörler Arasında Gezme ve İçeriğini Listeleme
**pwd** 
Bulunduğumuz dizini görmemizi sağlar.
**cd** 
Change Directory’nin kısaltımıdır. Dizin değiştirmek için kullanılır. `cd Desktop` şeklinde kullanılır. Üst dizine geçmek için `cd ..` yapabilirsiniz.
**ls**
Sade kullanımı bulunduğunuz dizindeki alt dizinleri ve dosyaları görüntülemek için kullanılır. Farklı dizinlerin içeriğini merak ediyorsanız, `ls görüntülenecek/olan/dizinin/adresi` şeklinde kullanılır
## Dosya İşlemleri

### Dosya oluşturma
**touch**
Dosya yaratmak için kullanılır. `touch file.txt` şeklinde kullanılır
**cat**
Bir dosyanın içeriğini ekrana basar. `cat file.txt` şeklinde kullanılır.

### Dosya Taşıma, Kopyalama ve Silme
**cp**
Dosya kopyalamak için kullanılır. cp `kaynak hedef` şeklinde kulanılır.
**mv**
Dosya taşımak için kullanılır. `mv kaynak hedef` şeklinde kullanılır.
**rm**
Dosya silmek için kullanılır. `rm dosya` olarak kullanılır. `rm *.txt` şeklinde de kullanabilirsiniz. Bu şekilde bir kullanım bulunulan dizindeki sonu txt ile biten bütün dosyaları siler.

### Dizin Oluşturma ve Silme
**mkdir**
Dizin oluşturmak için kullanılır. `mkdir dizin_adı`  şeklinde kullanılır.
**rm**
Dizin silmek için de kullanılır. `rm -r dizin` ile dizin altındaki alt dizin ve dosyaların silinmesi sağlanabilir. `rm -rf dizin` ile güç kullanarak silme işlemini gerçekleştirebilirsiniz. Kullanırken dikkatli olun.

### Dosya Sıkıştırma, Açma ve Arşivleme
**tar**
Dosyaları arşivlemek için kullanılır. `tar cf dosyalar.tar dosya1 dosya2 dosya3` şeklinde kullanılır. Bu komut; dosya1 dosya2 ve dosya3 adlı dosyaları, dosyalar.tar adlı tar arşivinde birleştirir.
**gzip**
Dosya sıkıştırmak için kullanılır. `gzip dosya` şeklinde kullanılır. Sıkıştırılmış dosyanın uzantısı ".gz" olur.
**bzip2**
Dosya sıkıştırmak için kullanılır. `bzip2 dosya` şeklinde kullanılır. Sıkıştırılmış dosyanın uzantısı ".bz2" olur.
**gunzip**
gzip kullanılarak sıkıştırılmış dosyaları açar. `gunzip dosya.gz` şeklinde kullanılır.
**bunzip2**
bzip kullanılarak sıkıştırılmış dosyaları açar. `bunzip2 dosya.bz2` şeklinde kullanılır.
