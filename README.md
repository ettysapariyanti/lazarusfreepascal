# lazarusfreepascal

Catatan ini berfungsi untuk merekam sejarah coding menggunakan aplikasi Lazarus dan Free Pascal.


```pascal

program Latihan1;

{$mode objfpc}{$H+}

uses
  {$IFDEF UNIX}
  cthreads,
  {$ENDIF}
  Classes
  { you can add units after this };


const pesan = 'Latihan Pemrograman Pascal';

type nama = string;

var namaawal, namabelakang: nama;



begin

  writeln('Masukan Nama Awal Anda : ');

  readln(namaawal);


  writeln('Silahkan Masukan Nama Belakang Anda : ');

  readln(namabelakang);


  writeln;

  writeln(pesan, ' ', namaawal, ' ', namabelakang);

  readln;

end.


```





