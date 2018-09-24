---
title: Come rimuovere il runtime e l'SDK .NET
description: Istruzioni per rimuovere i componenti Runtime di .NET Core e .NET Core SDK su Windows, Mac e Linux
ms.date: 07/28/2018
author: billwagner
ms.author: wiwagn
ms.openlocfilehash: 1806d1af3b10e44ccc2eff788d8958ca976fe85b
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "45989813"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a>Come rimuovere Runtime di .NET Core e .NET Core SDK

Nel corso del tempo, via via che si installano le versioni aggiornate di runtime e SDK di .NET Core l'utente potrebbe voler rimuovere le versioni obsolete di .NET Core dal computer. La rimozione delle versioni precedenti del runtime può cambiare il runtime scelto per eseguire le applicazioni di framework condiviso, come descritto in dettaglio nell'articolo [Scelta della versione di .NET Core](selection.md).

A partire da .NET Core 2.1, la CLI di .NET include opzioni che è possibile usare per elencare le versioni di SDK e runtime installate nel computer.  Usare [`dotnet --list-sdks`](../tools/dotnet.md#options) per visualizzare l'elenco degli SDK installati nel computer. Usare [`dotnet --list-runtimes`](../tools/dotnet.md#options) per visualizzare l'elenco dei runtime installati nel computer. Il testo seguente illustra un output tipico per Windows, macOS o Linux:

# <a name="windowstabwindows"></a>[Windows](#tab/Windows)

```console
C:\> dotnet --list-sdks
2.1.200-preview-007474 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007480 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007509 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007570 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007576 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007587 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007589 [C:\Program Files\dotnet\sdk]
2.1.200 [C:\Program Files\dotnet\sdk]
2.1.201 [C:\Program Files\dotnet\sdk]
2.1.202 [C:\Program Files\dotnet\sdk]
2.1.300-preview2-008533 [C:\Program Files\dotnet\sdk]
2.1.300 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009063 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009088 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009171 [C:\Program Files\dotnet\sdk]

C:\> dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.0.6 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.7 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.9 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
```

# <a name="linuxtablinux"></a>[Linux](#tab/Linux)

```console
$ dotnet --list-sdks
1.0.1 [/usr/share/dotnet/sdk]
1.0.4 [/usr/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/share/dotnet/sdk]
2.0.0 [/usr/share/dotnet/sdk]
2.1.4 [/usr/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/share/dotnet/sdk]
2.1.300 [/usr/share/dotnet/sdk]
2.1.301 [/usr/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
```

# <a name="macostabmacos"></a>[macOS](#tab/macOS)

```console
$ dotnet --list-sdks
1.0.1 [/usr/local/share/dotnet/sdk]
1.0.4 [/usr/local/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/local/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/local/share/dotnet/sdk]
2.0.0 [/usr/local/share/dotnet/sdk]
2.1.4 [/usr/local/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/local/share/dotnet/sdk]
2.1.300 [/usr/local/share/dotnet/sdk]
2.1.301 [/usr/local/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

***

## <a name="uninstalling-net-core"></a>Disinstallazione di .NET Core

# <a name="windowstabwindows"></a>[Windows](#tab/Windows)

.NET Core usa la finestra di dialogo **Installazione applicazioni** di Windows per rimuovere le versioni di runtime e SDK di .NET Core. La figura seguente illustra la finestra di dialogo **Installazione applicazioni** con diverse versioni di runtime e SDK di .NET Core installati.

![Installazione applicazioni per la rimozione di .NET Core](./media/remove-runtime-sdk-versions/programs-and-features.png)

Selezionare tutte le versioni da rimuovere dal computer e fare clic su **Disinstalla**.

# <a name="linuxtablinux"></a>[Linux](#tab/Linux)

Per disinstallare .NET Core (SDK o runtime) in Linux sono disponibili varie opzioni. Il modo migliore per disinstallare .NET Core è eseguire il mirroring dell'azione usata per installare .NET Core. Le specifiche variano in base alla distribuzione scelta e al metodo di installazione.

> [!IMPORTANT]
> Per le installazioni di Red Hat, vedere l'[introduzione a Red Hat](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) per informazioni sull'installazione e la disinstallazione di .NET Core.

A partire da .NET Core 2.1, non è necessario disinstallare .NET Core SDK quando si esegue l'aggiornamento tramite uno strumento di gestione pacchetti. La gestione pacchetti o i comandi `update` o `refresh` rimuoveranno automaticamente la versione precedente al termine dell'installazione di una versione più recente.

Se si è installato .NET Core usando uno strumento di gestione pacchetti, si userà la stessa gestione pacchetti per la disinstallazione dell'SDK o runtime .NET. Le installazioni di .NET Core supportano gli strumenti di gestione pacchetti più diffusi. Vedere la documentazione relativa alla gestione pacchetti della propria distribuzione per l'esatta sintassi nel proprio ambiente:

- [apt-get(8)](https://linux.die.net/man/8/apt-get) viene usato dai sistemi basati su Debian, tra cui Ubuntu.
- [yum(8)](https://linux.die.net/man/8/yum) viene usato in Fedora, CentOS e Oracle Linux.
- [zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) viene usato in openSUSE e SUSE Linux Enterprise System (SLES).
- [dnf(8)](https://dnf.readthedocs.io/latest/command_ref.html) viene usato in Fedora.

Nella quasi totalità dei casi, il comando per rimuovere un pacchetto è `remove`.

Il nome del pacchetto per l'installazione di .NET Core SDK per la maggior parte degli strumenti di gestione pacchetti è `dotnet-sdk`, seguito dal numero di versione. A partire dalla versione 2.1.300 di .NET Core SDK e dalla versione `2.1` del runtime, sono necessari solo i numeri di versione principale e secondario: ad esempio, .NET Core SDK versione 2.1.300 può essere indicato come pacchetto `dotnet-sdk-2.1`. Le versioni precedenti richiedono l'intera stringa di versione: ad esempio, per la versione 2.1.200 di .NET Core SDK sarebbe necessario `dotnet-sdk-2.1.200`.

Per i computer su cui è installato solo il runtime e non l'SDK, il nome del pacchetto è `dotnet-runtime-<version>` per il runtime di .NET Core e `aspnetcore-runtime-<version>` per lo stack di runtime intero.

Le installazioni di .NET Core precedenti a 2.0 non disinstallano l'applicazione host se l'SDK è stato disinstallato tramite uno strumento di gestione pacchetti. Usando `apt-get`, il comando è:

```bash
apt-get remove dotnet-host
```

Si noti che non è presente alcuna versione collegata a `dotnet-host`.

Se è l'installazione è stata eseguita tramite un file tarball, è necessario rimuovere .NET Core usando il metodo manuale.

Rimuovere separatamente gli SDK e i runtime rimuovendo la directory contenente la relativa versione. Ad esempio, per rimuovere l'SDK e il runtime versione 1.0.1, è necessario usare i comandi bash seguenti:

```bash
sudo rm -rf /usr/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/host/fxr/1.0.1
```

Le directory padre per l'SDK e il runtime sono elencate nell'output dai comandi `dotnet --list-sdks` e `dotnet --list-runtimes`, come illustrato nella tabella precedente.

# <a name="macostabmacos"></a>[macOS](#tab/macOS)

In Mac, rimuovere separatamente gli SDK e i runtime rimuovendo la directory contenente la relativa versione. Ad esempio, per rimuovere l'SDK e il runtime versione 1.0.1, è necessario usare i comandi bash seguenti:

```bash
sudo rm -rf /usr/local/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/host/fxr/1.0.1
```

Le directory padre per l'SDK e il runtime sono elencate nell'output dai comandi `dotnet --list-sdks` e `dotnet --list-runtimes`, come illustrato nella tabella precedente.

A partire da .NET Core 2.1, non è necessario disinstallare .NET Core SDK quando si esegue l'aggiornamento tramite uno strumento di gestione pacchetti. La gestione pacchetti o i comandi `update` o `refresh` rimuoveranno automaticamente la versione precedente al termine dell'installazione di una versione più recente.

---
