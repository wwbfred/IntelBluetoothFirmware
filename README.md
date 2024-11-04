用以解决MacOS下蓝牙由于HCI_OP_LE_SET_SCAN_ENABLE无法成功开启导致的随机崩溃，现象为日志中出现  
  
bluetoothd: [com.apple.bluetooth:Stack.HCI] HCI expected event 14 with opcode OI_DHCI_CMD_ID_LE_SET_SCAN_PARAMETERS_OPCODE (0x0000200B) timedout, reason is  STATUS 621  
  
bluetoothd: [com.apple.bluetooth:Stack.HCI] HCI expected event 14 with opcode  
OI_DHCI_CMD_ID_LE_SET_SCAN_ENABLE_OPCODE (0x0000200C) timedout, reason is  STATUS 621  
  
错误后bluetoothd进程崩溃，蓝牙设备中断。方法为禁止将HCI_OP_LE_SET_SCAN_ENABLE设置为关闭。  
模板是IntelBluetoothFirmware的，仅需加载IntelBTPatcher即可。
