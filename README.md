# NEO-G - Omron CX-Simulator Gateway

Gateway Modbus TCP & OPC UA antara Factory IO (atau klien lain) dan CX-Simulator.
Setiap tabel (0x, 1x, 3x, 4x) memakai alamat 0 sampai 65535.

## Pakai
1. CX-Programmer: PLC > Work Online Simulator (Ctrl+Shift+W), mode RUN.
2. Jalankan `NEO-G.exe`. Mapping dari `mapping_config.json` di folder ini dimuat otomatis.
3. Klik **▶ Start Tunnel** (port bawaan 502; centang OPC UA bila perlu, port 4841).
4. Factory IO: driver Modbus TCP Client 127.0.0.1 port 502 > Connect > Play,
   atau OPC Client DA/UA ke `opc.tcp://127.0.0.1:4841/omron/server/`.

## Berkas di folder ini
- `NEO-G.exe`             program (satu berkas, tidak butuh Python)
- `mapping_config.json`   mapping, disimpan otomatis setiap ada perubahan
- `certs\`                sertifikat OPC UA (dibuat otomatis saat OPC UA pertama kali dijalankan)

Pindahkan seluruh folder bila ingin memindah program beserta mapping-nya.
Opsi baris perintah: `NEO-G.exe --port 502 --opcua --autostart` atau `--nogui --config map.json`.
Dokumentasi lengkap: menu Help > Documentation (F1).
