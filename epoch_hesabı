#include <stdio.h>
#include <time.h>

struct tarih {
    int gun;
    int ay;
    int yil;
};

union zaman {
    int toplam_saniye;
};

// Zamanı saniyeye çeviren fonksiyon
int zamani_saniyeye_cevir(int saat, int dakika, int saniye) {
    return saat * 3600 + dakika * 60 + saniye;
}

int main() {
    struct tarih birinci_tarih, ikinci_tarih;
    union zaman birinci_zaman, ikinci_zaman;
    int saat, dakika, saniye;

    // İlk tarihi al
    printf("Lutfen bir gun giriniz (1-31): ");
    scanf("%d", &birinci_tarih.gun);
    printf("Lutfen bir ay giriniz (1-12): ");
    scanf("%d", &birinci_tarih.ay);
    printf("Lutfen bir yil giriniz: ");
    scanf("%d", &birinci_tarih.yil);
    
    printf("Lutfen bir saat giriniz (0-23): ");
    scanf("%d", &saat);
    printf("Lutfen bir dakika giriniz (0-59): ");
    scanf("%d", &dakika);
    printf("Lutfen bir saniye giriniz (0-59): ");
    scanf("%d", &saniye);

    birinci_zaman.toplam_saniye = zamani_saniyeye_cevir(saat, dakika, saniye);

    // İkinci tarihi al
    printf("\nIkinci tarihi giriniz:\n");
    printf("Lutfen bir gun giriniz (1-31): ");
    scanf("%d", &ikinci_tarih.gun);
    printf("Lutfen bir ay giriniz (1-12): ");
    scanf("%d", &ikinci_tarih.ay);
    printf("Lutfen bir yil giriniz: ");
    scanf("%d", &ikinci_tarih.yil);
    
    printf("Lutfen bir saat giriniz (0-23): ");
    scanf("%d", &saat);
    printf("Lutfen bir dakika giriniz (0-59): ");
    scanf("%d", &dakika);
    printf("Lutfen bir saniye giriniz (0-59): ");
    scanf("%d", &saniye);

    ikinci_zaman.toplam_saniye = zamani_saniyeye_cevir(saat, dakika, saniye);

    // Tarihleri struct tm'ye çevir
    struct tm t1 = {0}, t2 = {0};

    t1.tm_mday = birinci_tarih.gun;
    t1.tm_mon = birinci_tarih.ay - 1;
    t1.tm_year = birinci_tarih.yil - 1900;
    t1.tm_sec = birinci_zaman.toplam_saniye; // Zamanı doğrudan saniye olarak kullan

    t2.tm_mday = ikinci_tarih.gun;
    t2.tm_mon = ikinci_tarih.ay - 1;
    t2.tm_year = ikinci_tarih.yil - 1900;
    t2.tm_sec = ikinci_zaman.toplam_saniye; // Zamanı doğrudan saniye olarak kullan

    // Epoch zamanlarını hesapla
    time_t epoch1 = mktime(&t1);
    time_t epoch2 = mktime(&t2);

    if (epoch1 == -1 || epoch2 == -1) {
        printf("Gecersiz tarih girdiniz!\n");
        return 1;
    }

    // Farkı hesapla
    double fark = difftime(epoch2, epoch1);

    printf("\nTarih farkinin epoch degeri: %.0f saniye\n", fark);

    return 0;
}
