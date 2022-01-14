# Lazarus Free Pascal

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



Source Code untuk menampilkan data hasil query dari database **MariaDB** ke **TDBGrid** :

```pascal

unit file1;

{$mode objfpc}{$H+}

interface

uses
  Classes, SysUtils, odbcconn, SQLDB, DB, Forms, Controls, Graphics, Dialogs,
  DBGrids;

type

  { TForm1 }

  TForm1 = class(TForm)
    DataSource1: TDataSource;
    DBGrid1: TDBGrid;
    ODBCConnection1: TODBCConnection;
    SQLQuery1: TSQLQuery;
    SQLTransaction1: TSQLTransaction;

    procedure FormCreate(Sender: TObject);

  private

  public

  end;

var
  Form1: TForm1;

implementation

{$R *.lfm}

{ TForm1 }



procedure TForm1.FormCreate(Sender: TObject);

var hasilKueri : integer;

begin


  ODBCConnection1.DatabaseName := 'localmariadb';

  ODBCConnection1.HostName := 'localhost';

  ODBCConnection1.UserName := 'steven';

  ODBCConnection1.Connected := True;

  SQLQuery1.SQL.Text := 'SELECT * FROM tabel1 where namapegawai = "Budi";';

  SQLQuery1.Open;

  Datasource1.DataSet := SQLQuery1;

  DBGrid1.Columns[0].Title.Caption := 'ID Karyawan';

  DBGrid1.Columns[1].Title.Caption := 'Nama Karyawan';


end;

end.



```














