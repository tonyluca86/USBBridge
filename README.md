# USB Bridge

**Bring your USB smart-home coordinators to Home Assistant over your local network.**

![Windows](https://img.shields.io/badge/Windows-x64-0078D4) ![Version](https://img.shields.io/badge/version-1.3.1-blue) ![Status](https://img.shields.io/badge/status-beta%20candidate-orange) ![Distribution](https://img.shields.io/badge/distribution-freeware-green)

[English](#english) · [Italiano](#italiano) · [Releases](https://github.com/tonyluca86/USBBridge/releases) · [Issues](https://github.com/tonyluca86/USBBridge/issues) · [Release notes / Note versione](docs/RELEASE-1.3.1.md)

> **Download status / Stato download:** the 1.3.1 binary package is prepared but not yet released. Third-party notices and final Windows testing remain pending. / Il pacchetto 1.3.1 è predisposto, ma non ancora pubblicato: restano da completare gli avvisi di licenza di terze parti e il collaudo finale Windows.

## English

USB Bridge is an independent Windows x64 serial-to-TCP gateway for Home Assistant on Hyper-V and other LAN hosts. Connect a compatible USB serial coordinator to a Windows PC and access it from your Home Assistant installation without USB passthrough.

```text
USB coordinator <-- COM --> USB Bridge (Windows) <-- TCP / LAN --> Home Assistant
```

### Features

- Guided configuration, serial adapter detection and model profiles.
- Bidirectional raw serial TCP with configurable COM, baud rate and listening port.
- Windows service with automatic startup and integrated installation, update and removal.
- Italian / English interface, system tray, traffic counters, status and diagnostic logs.
- Authorized client IP, configuration import/export and integration setup guidance.
- Self-contained Windows x64 executable; no separate .NET SDK or build scripts needed.

### Compatibility

| Integration / hardware | Status |
| --- | --- |
| SONOFF ZBDongle-P + ZHA | Physically tested on an earlier version |
| SONOFF ZBDongle-E, other Zigbee serial adapters | Candidate profiles; not physically tested |
| Zigbee2MQTT | Not physically tested with USB Bridge |
| Z-Wave JS | Candidate profiles; not physically tested |
| Bluetooth LE | Excluded from the public binary package |

### Getting started

1. Once released, download the official Windows ZIP from [Releases](https://github.com/tonyluca86/USBBridge/releases).
2. Extract all files, close any old tray panel, run USBBridge.exe and follow the integrated installation.
3. Choose the correct coordinator, COM port, serial settings, Windows LAN IP, authorized client IP and TCP port.
4. Save and apply, then configure the matching Home Assistant integration.
5. For ZHA use a serial network endpoint such as `socket://PC_IP:6638`. For Zigbee2MQTT use `tcp://PC_IP:6638` with the matching adapter type. For Z-Wave JS use the TCP path in the driver; Home Assistant connects to the driver's WebSocket server.

Use one driver per coordinator. Back up your existing networks before migration. Raw serial TCP is **not encrypted**: use a trusted LAN and never expose the port to the Internet. This is beta software, not universal USB passthrough or RFC2217.

## Italiano

USB Bridge è un gateway seriale/TCP per Windows x64, dedicato a Home Assistant su Hyper-V e altri host di rete. Permette di collegare un coordinatore USB seriale compatibile al PC Windows e utilizzarlo da Home Assistant senza passthrough USB.

```text
Coordinatore USB <-- COM --> USB Bridge (Windows) <-- TCP / LAN --> Home Assistant
```

### Funzionalità

- Configurazione guidata, riconoscimento chiavette e profili per modello.
- Trasferimento seriale/TCP bidirezionale con porta COM, baud rate e porta TCP configurabili.
- Servizio Windows ad avvio automatico; installazione, aggiornamento e rimozione integrati.
- Interfaccia italiana e inglese, icona nell'area di notifica, contatori e registro eventi.
- Filtro IP del client, importazione/esportazione configurazione e diagnostica.
- Eseguibile autonomo Windows x64; non serve compilare o installare l'SDK .NET.

### Compatibilità

| Integrazione / hardware | Stato |
| --- | --- |
| SONOFF ZBDongle-P + ZHA | Collaudato fisicamente su una versione precedente |
| SONOFF ZBDongle-E e altri adattatori Zigbee seriali | Profili predisposti, non collaudati fisicamente |
| Zigbee2MQTT | Non collaudato fisicamente con USB Bridge |
| Z-Wave JS | Profili predisposti, non collaudati fisicamente |
| Bluetooth LE | Escluso dal pacchetto binario pubblico |

### Installazione

1. Quando disponibile, scaricare lo ZIP Windows ufficiale dalla sezione [Releases](https://github.com/tonyluca86/USBBridge/releases).
2. Estrarre tutti i file, chiudere l'eventuale pannello precedente e avviare USBBridge.exe. Seguire l'installazione integrata.
3. Selezionare modello, COM, parametri seriali, IP LAN del PC, IP del client autorizzato e porta TCP.
4. Salvare e applicare. Configurare l'integrazione Home Assistant corrispondente.
5. Per ZHA usare ad esempio `socket://IP_PC:6638`; per Zigbee2MQTT `tcp://IP_PC:6638` con il profilo corretto. Per Z-Wave JS il TCP va configurato nel driver; Home Assistant usa il WebSocket del server.

Un solo driver per coordinatore. Eseguire il backup della rete prima della migrazione. Il TCP seriale **non è cifrato**: usare una LAN fidata e non esporre la porta a Internet. Beta da collaudare; non è passthrough USB universale né RFC2217.

## Support / Sostieni il progetto

Free compiled application; source code remains private. Donations are optional. / Applicativo compilato destinato alla distribuzione gratuita; sorgenti privati. Donazioni facoltative.

[Support with PayPal / Dona con PayPal](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=ebay%40lucagiardina.com&item_name=Donazione%20per%20lo%20sviluppo%20di%20USB%20Bridge)

Use [GitHub Issues](https://github.com/tonyluca86/USBBridge/issues) for feedback. Include adapter, version and redacted logs; never post passwords, tokens or private configuration.

**© 2026 Luca Giardina. All rights reserved / Tutti i diritti riservati.**

Independent project, not affiliated with Home Assistant or hardware manufacturers. / Progetto indipendente, non affiliato a Home Assistant o ai produttori hardware.
