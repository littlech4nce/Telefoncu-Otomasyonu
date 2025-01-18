#include <iostream>
#include <fstream>
#include <cstring>
#define STOCK 1000
#define MAX 100

using namespace std;

// Telefon ozellikleri -------------------------
struct telefon {
    char marka[MAX] = "";
    char model[MAX] = "";
    char hafiza[MAX] = "";
    char RAM[MAX] = "";
    char renk[MAX] = "";
    char fiyat[MAX] = "";
};

// Globaller ------------------------------------
string serit = "------------------------------------";
telefon telefonlar[STOCK];

// Fonksiyonlar -------------------------------

void menu() {
    cout << "1) Telefon Arat" << endl;
    cout << serit << endl;
    cout << "2) Stoklari Listele" << endl;
    cout << serit << endl;
    cout << "3) Telefon Ekle" << endl;
    cout << serit << endl;
    cout << "4) Telefon Kaldir" << endl;
    cout << serit << endl;
    cout << "5) Fiyat Guncelle" << endl;
    cout << serit << endl;
    cout << "6) Kaydet" << endl;
    cout << serit << endl;
    cout << "0) Cikis" << endl;
}

bool onaylama(const char* onay) {
    char cevap;
    cout << onay << " Onayliyor musunuz? [e/h] "; cin >> cevap;
    if (cevap == 'e' || cevap == 'E') return true;
    if (cevap == 'h' || cevap == 'H') return false;
    return onaylama(onay);
}

void telefonArat() {
    cout << serit << endl;
    char marka[MAX], model[MAX];
    cout << "Aratmak istediginiz telefonun markasini giriniz: ";
    cin.getline(marka, MAX);  //Newline Aldigi Icin Koymak Zorundayim
    cin.getline(marka, MAX);
    cout << "Aratmak istediginiz telefonun modelini giriniz: ";
    cin.getline(model, MAX);
    cout << serit << endl;

    int sayac = 0;
    for (int i = 0; i < STOCK; i++) {
        if (telefonlar[i].model[0] == '\0') continue;
        if (strcmp(telefonlar[i].model, model) == 0 && strcmp(telefonlar[i].marka, marka) == 0) {
            sayac++;
        }
    }
    cout << "Telefon: " << marka << " " << model
         << " " << "Stoklarda: " << sayac << " tane" << endl;
    cout << serit << endl;
}

void stoklariListele() {
    int sayac = 0;
    cout << serit << endl;
    for (int i = 0; i < STOCK; i++) {
        if (telefonlar[i].marka[0] == '\0') continue;
        sayac++;
        cout << sayac << ") Telefon: " << telefonlar[i].marka << " " << telefonlar[i].model
             << endl << "Hafiza ve RAM: " << telefonlar[i].hafiza << " " << telefonlar[i].RAM
             << endl << "Renk ve Fiyat: " << telefonlar[i].renk << " " << telefonlar[i].fiyat << endl;
        cout << serit << endl;
    }
}

void telefonEkle() {
    int bos;
    for (int i = 0; i < STOCK; i++) {
        if (telefonlar[i].marka[0] == '\0') {
            bos = i;
            break;
        }
    }

    cout << "Telefonun markasini giriniz: "; cin.ignore(); cin.getline(telefonlar[bos].marka, MAX);
    cout << "Telefonun modelini giriniz: "; cin.getline(telefonlar[bos].model, MAX);
    cout << "Telefonun hafizasini giriniz: "; cin.getline(telefonlar[bos].hafiza, MAX);
    cout << "Telefonun RAM'ini giriniz: "; cin.getline(telefonlar[bos].RAM, MAX);
    cout << "Telefonun rengini giriniz: "; cin.getline(telefonlar[bos].renk, MAX);
    cout << "Telefonun fiyatini giriniz: "; cin.getline(telefonlar[bos].fiyat, MAX);
    cout << endl << serit << endl;

    cout << "Telefonun markasi: " << telefonlar[bos].marka << endl;
    cout << "Telefonun modeli: " << telefonlar[bos].model << endl;
    cout << "Telefonun hafizasi: " << telefonlar[bos].hafiza << endl;
    cout << "Telefonun RAM'i: " << telefonlar[bos].RAM << endl;
    cout << "Telefonun rengin: " << telefonlar[bos].renk << endl;
    cout << "Telefonun fiyati: " << telefonlar[bos].fiyat << endl;
    cout << endl << serit << endl;

    if (!onaylama("Bu telefon eklenecek.")) {
        cout << "Telefon eklenmedi." << endl << serit << endl;
        telefonlar[bos].marka[0] = '\0';
        telefonlar[bos].model[0] = '\0';
        telefonlar[bos].hafiza[0] = '\0';
        telefonlar[bos].RAM[0] = '\0';
        telefonlar[bos].renk[0] = '\0';
        telefonlar[bos].fiyat[0] = '\0';
        return;
    }

    cout << "Telefon basariyla eklendi." << endl << serit << endl;
}

void telefonKaldir() {
    int kaldir[STOCK];
    int sec = 0, secim = 0;
    stoklariListele();
    for (int i = 0; i < STOCK; i++) {
        if (telefonlar[i].marka[0] == '\0') continue;
        kaldir[sec++] = i;
    }
    cout << "Kaldirmak istediginiz telefonun numarasini giriniz: ";
    cin >> secim;
    cout << serit << endl;

    cout << "Telefon: " << telefonlar[kaldir[secim - 1]].marka << " " << telefonlar[kaldir[secim - 1]].model << endl;
    cout << "Hafiza ve Ram: " << telefonlar[kaldir[secim - 1]].hafiza << " " << telefonlar[kaldir[secim - 1]].RAM << endl;
    cout << "Renk ve Fiyat: " << telefonlar[kaldir[secim - 1]].renk << " " << telefonlar[kaldir[secim - 1]].fiyat << endl;
    if (!onaylama("Bu telefon kaldiriliyor.")) {
        cout << "Telefon kaldirilmadi." << endl << serit << endl;
        return;
    }

    telefonlar[kaldir[secim - 1]].marka[0] = '\0';
    telefonlar[kaldir[secim - 1]].model[0] = '\0';
    telefonlar[kaldir[secim - 1]].hafiza[0] = '\0';
    telefonlar[kaldir[secim - 1]].RAM[0] = '\0';
    telefonlar[kaldir[secim - 1]].renk[0] = '\0';
    telefonlar[kaldir[secim - 1]].fiyat[0] = '\0';

    cout << "Telefon basariyla kaldirildi." << endl << serit << endl;
}

void fiyatGuncelle() {
    int kaldir[STOCK];
    int sec = 0, secim = 0;
    char yeniFiyat[MAX] = "";
    stoklariListele();
    for (int i = 0; i < STOCK; i++) {
        if (telefonlar[i].marka[0] == '\0') continue;
        kaldir[sec++] = i;
    }
    cout << "Fiyatini guncellemek istediginiz telefonun numarasini giriniz: ";
    cin >> secim;
    cout << serit << endl;

    cin.ignore();
    cout << "Guncel fiyati giriniz: "; cin.getline(yeniFiyat, MAX);
    strcpy(telefonlar[kaldir[secim - 1]].fiyat, yeniFiyat);

    cout << "Fiyat basariyla guncellendi." << endl << serit << endl;
}

void kaydet() {
    ofstream dosya("kayit.dat", ios::binary);
    for(int i=0; i<STOCK; i++){
        dosya.write(reinterpret_cast<char*>(&telefonlar[i]), sizeof(telefonlar));
    }
    cout << endl << "Degisiklikler basariyla kaydedildi." << endl << serit << endl;
}

void yukle() {
    ifstream dosya("kayit.dat", ios::binary);
    for(int i=0; i<STOCK; i++){
        dosya.read(reinterpret_cast<char*>(&telefonlar[i]), sizeof(telefon));
    }
}

int main() {
    // Verileri geri yukleme --------------------
    yukle();

    // Acilis -----------------------------------
    cout << "   ______   ______            _______ " << endl;
    cout << "  /_  __/  / __  /           /__  __/ " << endl;
    cout << "   / /    / / / /              / /  " << endl;
    cout << "  / /    / /_/ /        __  __/ /__ " << endl;
    cout << " /_/    /_____/        /_/ /______/" << endl;
    cout << serit << endl;
    cout << "Telefoncu Otomasyonu V1" << endl << serit << endl;

    // Test products ----------------------------
    strcpy(telefonlar[0].marka, "samsung");
    strcpy(telefonlar[0].model, "galaxy");
    strcpy(telefonlar[0].hafiza, "128 GB");
    strcpy(telefonlar[0].RAM, "16 GB");
    strcpy(telefonlar[0].renk, "Kirmizi");
    strcpy(telefonlar[0].fiyat, "17.500 TL");
    strcpy(telefonlar[10].marka, "xiomi");
    strcpy(telefonlar[10].model, "redmi note 10");
    strcpy(telefonlar[10].hafiza, "256 GB");
    strcpy(telefonlar[10].RAM, "16 GB");
    strcpy(telefonlar[10].renk, "Siyah");
    strcpy(telefonlar[10].fiyat, "20.000 TL");
    strcpy(telefonlar[100].marka, "xiomi");
    strcpy(telefonlar[100].model, "redmi note 12");
    strcpy(telefonlar[100].hafiza, "256 GB");
    strcpy(telefonlar[100].RAM, "16 GB");
    strcpy(telefonlar[100].renk, "Mavi");
    strcpy(telefonlar[100].fiyat, "21.000 TL");
    strcpy(telefonlar[150].marka, "iphone");
    strcpy(telefonlar[150].model, "15");
    strcpy(telefonlar[150].hafiza, "256 GB");
    strcpy(telefonlar[150].RAM, "16 GB");
    strcpy(telefonlar[150].renk, "Lacivert");
    strcpy(telefonlar[150].fiyat, "25.000 TL");


    //Main Code
    int secim;
    bool calis = true;
    while (calis) {
        menu();
        cin >> secim;
        switch (secim) {
        case 1:
            telefonArat();
            break;
        case 2:
            stoklariListele();
            break;
        case 3:
            telefonEkle();
            break;
        case 4:
            telefonKaldir();
            break;
        case 5:
            fiyatGuncelle();
            break;
        case 6:
            kaydet();
            break;
        case 0:
            if (onaylama("Cikis yapiyorsunuz.")) {
                calis = false;
                cout << endl << "Basariyla cikis yaptiniz." << endl << serit << endl;
            }
            else
                calis = true;
            break;
        }
    }
    return 0;
}
