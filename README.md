Epoch Hesaplayan Bir C programı

Epoch Nedir?

Bilgisayar sistemlerinde sistem saati için bir başlangıç zamanına ihtiyaç duyulmuştur bu zaman 1 Ocak 1970 tarihi olarak kararlaştırılmıştır
epoch işte bu başlangıç zamanını ifade eder,kelime anlamı olarak da tarihin başlangıcı anlamına gelir.

Bilgi

1 Ocak 1970 tarihinden itibaren bugüne kadar geçen saniye sayısı bilgisayar sistemlerinin şuan ki zamanıdır.

Peki bu programın işlevi nedir?

Bu program kullanıcıdan dinamik olarak 2 farklı tarih ve 2 farklı zaman verilerini dinamik olarak alıp epoch değerini hesaplar ve ekranda
çıktı olarak gösterir.

1. Kullanılan Kütüphaneler
   
#include <stdio.h>:

Standart Giriş/Çıkış kütüphanesidir. printf ve scanf gibi giriş ve çıkış fonksiyonlarını sağlar.
#include <time.h>:

Zamanla ilgili işlemler için kullanılan kütüphanedir. struct tm, time_t, mktime, difftime gibi zamanla ilgili veri türlerini ve fonksiyonları içerir.

2. Fonksiyonlar:

printf:

Konsola çıktı yazdırmak için kullanılır. Örneğin, printf("Lutfen bir gun giriniz: "); komutu, kullanıcıdan bir giriş almak için ekranda mesaj gösterir.

scanf:

Kullanıcıdan veri almak için kullanılır. Örneğin, scanf("%d", &birinci_tarih.gun); komutu, kullanıcının girdiği değeri birinci_tarih.gun değişkenine atar.

mktime:

struct tm türündeki tarihi, Unix epoch zamanına (1970-01-01 00:00:00 UTC) göre saniye cinsinden dönüştüren bir fonksiyondur.
mktime(&t1) gibi bir kullanım, t1 yapısındaki tarihi epoch zamanına çevirir ve time_t türünde bir değer döndürür.

difftime:

İki time_t türündeki zaman arasındaki farkı saniye cinsinden hesaplar.
Örneğin, difftime(epoch2, epoch1) komutu, epoch2 ile epoch1 arasındaki farkı saniye cinsinden hesaplar.


3. Kullanılan Veri Türleri:
   
struct tm:

Bu yapı, bir tarihi ve zamanı temsil eder. Yıl, ay, gün, saat, dakika, saniye gibi alanları içerir. Örneğin, t1.tm_year, yıl bilgisini tutar.

time_t:

time_t, Unix epoch zamanını saniye cinsinden temsil etmek için kullanılan bir veri türüdür. mktime ve difftime fonksiyonları bu türdeki verilerle çalışır.
Bu kütüphane ve fonksiyonlar, tarihler arası hesaplamaları, tarihleri epoch zamanına dönüştürmeyi ve zaman farklarını hesaplamayı sağlar.
