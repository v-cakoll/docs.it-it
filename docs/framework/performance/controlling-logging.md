---
title: Controllo della registrazione di .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
ms.openlocfilehash: e7d7d6e60b2f582a579f5811225f4027c37c7876
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504107"
---
# <a name="controlling-net-framework-logging"></a>Controllo della registrazione di .NET Framework

È possibile utilizzare Traccia eventi per Windows (ETW) per registrare eventi CLR (Common Language Runtime). Tramite i seguenti strumenti si possono creare e visualizzare tracce:

- Gli strumenti da riga di comando [Logman](/windows-server/administration/windows-commands/logman) e [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1), inclusi nel sistema operativo Windows.

- Gli strumenti [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) in [Windows Performance Toolkit](/windows-hardware/test/wpt/). Per altre informazioni su Xperf, vedere il [blog sulle prestazioni di Windows](https://docs.microsoft.com/archive/blogs/pigscanfly/).

Per acquisire informazioni sugli eventi CLR, è necessario installare il provider CLR nel computer in uso. Per confermare la corretta installazione del provider, digitare `logman query providers` al prompt dei comandi. Verrà visualizzato un elenco di provider. L'elenco deve contenere una voce relativa al provider CLR, come riportato di seguito.

```output
Provider                                 GUID
-------------------------------------------------------------------------------
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.
```

Se il provider CLR non compare nell'elenco, è possibile installarlo in Windows Vista e nei sistemi operativi successivi tramite lo strumento da riga di comando [Wevtutil](/windows-server/administration/windows-commands/wevtutil) di Windows. Aprire la finestra del prompt dei comandi come amministratore. Modificare la directory dei messaggi di richiesta nella cartella .NET Framework 4 (%WINDIR%\Microsoft.NET\Framework [64] \v4.\<.NET Version > \). Questa cartella contiene il file CLR-ETW.man. Al prompt dei comandi digitare il comando seguente per installare il provider CLR:

`wevtutil im CLR-ETW.man`

## <a name="capturing-clr-etw-events"></a>Acquisizione di eventi ETW CLR

È possibile usare gli strumenti da riga di comando [Logman](/windows-server/administration/windows-commands/logman) e [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) per acquisire gli eventi ETW e gli strumenti [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) e [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) per decodificare gli eventi di traccia.

Per attivare la registrazione, un utente deve specificare tre impostazioni:

- Il provider a cui comunicare.

- Un numero a 64 bit che rappresenta un set di parole chiave. Ogni parola chiave rappresenta un set di eventi che il provider può attivare. Il numero rappresenta un set combinato di parole chiave da attivare.

- Un numero piccolo che rappresenta il livello (livello di dettaglio) a cui registrare. Il livello 1 è il livello di dettaglio minore e il livello 5 è il livello dettaglio maggiore. Il livello 0 è un'impostazione predefinita il cui significato è specifico del provider.

### <a name="to-capture-clr-etw-events-using-logman"></a>Per acquisire eventi ETW CLR tramite Logman

1. Al prompt dei comandi digitare:

     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`

     dove:

    - Il parametro `-p` identifica il GUID del provider.

    - `0x1CCBD` specifica le categorie degli eventi che saranno generati.

    - `0x5` imposta il livello di registrazione, in questo caso Verbose (5).

    - Il parametro `-ets` indica a Logman di inviare comandi alle sessioni di traccia degli eventi.

    - Il parametro `-ct perf` specifica che la funzione `QueryPerformanceCounter` verrà utilizzata per registrare il timestamp per ogni evento.

2. Per interrompere la registrazione degli eventi, digitare:

     `logman stop clrevents -ets`

     Questo comando crea un file di traccia binario denominato clrevents.etl.

### <a name="to-capture-clr-etw-events-using-xperf"></a>Per acquisire eventi ETW CLR tramite Xperf

1. Al prompt dei comandi digitare:

     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`

     dove il GUID è il GUID del provider ETW CLR e `0x1CCBD:5` traccia qualsiasi evento appartenente al livello 5 (verbose) e ai livelli inferiori.

2. Per interrompere la traccia, digitare:

     `Xperf -stop clr`

     Questo comando crea un file di traccia denominato clrevents.etl.

## <a name="viewing-clr-etw-events"></a>Visualizzazione di eventi ETW CLR

Utilizzare i comandi elencati di seguito per visualizzare gli eventi ETW CLR. Per una descrizione degli eventi, vedere [Eventi ETW di CLR](clr-etw-events.md).

### <a name="to-view-clr-etw-events-using-tracerpt"></a>Per visualizzare gli eventi ETW CLR tramite Tracerpt

- Al prompt dei comandi digitare:

     `tracerpt clrevents.etl`

     Questo comando crea due file: dumpfile.xml e summary.txt. Nel file dumpfile.xml sono elencati tutti gli eventi, mentre summary.txt fornisce un riepilogo degli eventi.

### <a name="to-view-clr-etw-events-using-xperf"></a>Per visualizzare gli eventi ETW CLR tramite Xperf

- Al prompt dei comandi digitare:

     `xperf clrevents.etl`

     Questo comando apre il visualizzatore di file ETL Xperf. In questo visualizzatore, gli eventi CLR compaiono nella vista **Eventi generici**. Per visualizzare una griglia dei dati di eventi suddivisi in categorie in base al tipo, selezionare un'area temporale in questa visualizzazione e quindi fare clic con il pulsante destro del mouse e selezionare **Riepilogo**.

### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a>Per convertire il file con estensione etl in un file con valori delimitati da virgole

- Al prompt dei comandi digitare:

     `xperf -i clrevents.etl -f clrevents.csv`

     Questo comando fa in modo che XPerf esegua il dump degli eventi come un file (CSV) con valori delimitati da virgole visualizzabile. Poiché eventi diversi dispongono di campi diversi, questo file con estensione CSV contiene più di una riga di intestazione prima dei dati. Il primo campo di ogni riga è il tipo di evento che indica quale intestazione deve essere utilizzata per determinare gli altri campi.

## <a name="see-also"></a>Vedere anche

- [Windows Performance Toolkit](/windows-hardware/test/wpt/)
- [Eventi ETW in Common Language Runtime](etw-events-in-the-common-language-runtime.md)
