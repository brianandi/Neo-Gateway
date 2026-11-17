# NEO-G - Omron CX-Simulator Gateway

Modbus TCP & OPC UA gateway between Factory IO (or any other client) and CX-Simulator.
Each table (0x, 1x, 3x, 4x) uses the full address range 0 to 65535.

## Usage
1. In CX-Programmer: PLC > Work Online Simulator (Ctrl+Shift+W), then switch to RUN mode.
2. Launch `NEO-G.exe`. The mapping from `mapping_config.json` in the same folder is loaded automatically.
3. Click **▶ Start Tunnel** (default port 502; check OPC UA if needed, port 4841).
4. In Factory IO: configure the Modbus TCP Client driver with 127.0.0.1, port 502 > Connect > Play,
   or connect an OPC DA/UA client to `opc.tcp://127.0.0.1:4841/omron/server/`.

## Files in This Folder
- `NEO-G.exe`             application (single executable, no Python required)
- `mapping_config.json`   mapping file, saved automatically on every change
- `certs\`                OPC UA certificates (generated automatically on first OPC UA launch)

To relocate the application together with its mapping, move the entire folder.
Command-line options: `NEO-G.exe --port 502 --opcua --autostart` or `--nogui --config map.json`.
Full documentation: Help > Documentation (F1).
