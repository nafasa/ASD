#ifndef PESAWAT_H_INCLUDED
#define PESAWAT_H_INCLUDED
#define nil NULL
#define firstA(P) P->firstA
#define next(P) P->next
#define info(P) P->info
#define next(P) P->next
#define prev(P) P->prev
#include <iostream>

using namespace std;

typedef struct elment_list_pesawat *adr;
typedef struct element_list_pemesan *adr_anak;


struct pesawat
{
    string nama_pesawat;
    string tanggal;
    string jam_berangkat;
    int kapasitas;

};

struct pemesan
{
    string no_ktp;
    string nama_pemesan;
    string alamat_pemesan;
    string no_hp;
};

typedef pesawat infotypepesawat;
typedef pemesan infotypepemesan;

struct elment_list_pesawat
{
    infotypepesawat info;
    adr next;
    adr prev;
    adr_anak firstA;
};

struct listpesawat
{
    adr first;
    adr last;
};

struct element_list_pemesan
{
    infotypepemesan info;
    adr_anak next;
    adr_anak firstA;
    adr_anak last;

};

void CreateListP(listpesawat &L);
adr alokasi(infotypepesawat datapesawat);
adr_anak alokasiK(infotypepemesan datapemesan);
void dealokasiP(adr Psw);
void dealokasiK(adr_anak Pms);
void insertFirstP(listpesawat &L, adr Psw);
void insertAfterP(listpesawat &L, adr Psw, adr prec);
void insertLastP(listpesawat &L, adr Psw);
void insertFirstK(listpesawat &L,adr Psw, adr_anak Pms);
void insertAfterK(listpesawat &L, adr_anak Pms, adr_anak prec);
void insertLastK(listpesawat &L, adr Psw,adr_anak Pms);
void edi(adr &Psw, string tgl, string jam);
adr_anak deletefirstK(listpesawat &L);
adr_anak deleteafterK(listpesawat &L, adr_anak prec);
adr_anak deletelastK(listpesawat &L);
adr findElmP(listpesawat L,string tgl, string jam);
void findElm(listpesawat L, infotypepemesan datapemesan);
void printInfo();
void input_dataP(pesawat &L);
void input_dataK(pemesan &L);




#endif // PESAWAT_H_INCLUDED
