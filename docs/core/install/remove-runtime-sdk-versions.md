---
title: Rimuovere il runtime di .NET Core e l'SDK
description: Questo articolo descrive come determinare le versioni del runtime di .NET Core e dell'SDK attualmente installate e quindi come rimuoverle in Windows, Mac e Linux.
author: adegeo
ms.author: adegeo
ms.date: 04/28/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 1e4a846cf5e3d0209f5ade873520ef64abc12e7c
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324642"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a>Come rimuovere Runtime di .NET Core e .NET Core SDK

Nel corso del tempo, via via che si installano le versioni aggiornate di runtime e SDK di .NET Core l'utente potrebbe voler rimuovere le versioni obsolete di .NET Core dal computer. La rimozione delle versioni precedenti del runtime può cambiare il runtime scelto per eseguire le applicazioni di framework condiviso, come descritto in dettaglio nell'articolo [Scelta della versione di .NET Core](../versions/selection.md).

## <a name="should-i-remove-a-version"></a>Stabilire se è necessario rimuovere una versione

La [selezione delle versioni di .NET Core](../versions/selection.md) e la compatibilità di runtime di .NET Core tra gli aggiornamenti consente la rimozione sicura delle versioni precedenti. Gli aggiornamenti al runtime di .NET Core sono compatibili all'interno delle versioni principali, ad esempio 1.x e 2.x. Inoltre, le nuove versioni di .NET Core SDK mantengono in genere la possibilità di creare applicazioni destinate a versioni precedenti del runtime in modo compatibile.

In generale, sono necessari solo l'SDK più recente e l'ultima versione patch dei runtime richiesti per l'applicazione. Le istanze in cui è possibile mantenere le versioni precedenti di SDK o Runtime includono la manutenzioneproject.jsapplicazioni basate *su*. Se l'applicazione non ha ragioni specifiche per mantenere le versioni precedenti di SDK o Runtime, è possibile rimuovere le versioni precedenti in modo sicuro.

## <a name="determine-what-is-installed"></a>Determinare che cosa è installato

A partire da .NET Core 2.1, la CLI di .NET include opzioni che è possibile usare per elencare le versioni di SDK e runtime installate nel computer.  Usare [`dotnet --list-sdks`](../tools/dotnet.md#options) per visualizzare l'elenco di SDK installati nel computer. Usare [`dotnet --list-runtimes`](../tools/dotnet.md#options) per visualizzare l'elenco dei runtime installati nel computer. Per ulteriori informazioni, vedere [come verificare che .NET Core sia già installato](how-to-detect-installed-versions.md).

## <a name="uninstall-net-core"></a>Disinstallare .NET Core

::: zone pivot="os-windows"

.NET Core usa la finestra di dialogo Windows **Apps & features** per rimuovere le versioni del runtime e dell'SDK di .NET Core. Nella figura seguente viene illustrata la finestra di dialogo **app & funzionalità** . È possibile cercare **Core SDK** per filtrare e visualizzare le versioni installate di .NET Core.

![Installazione applicazioni per la rimozione di .NET Core](./media/remove-runtime-sdk-versions/programs-and-features.png)

Selezionare tutte le versioni da rimuovere dal computer e fare clic su **Disinstalla**.

::: zone-end

::: zone pivot="os-linux"

Per disinstallare .NET Core (SDK o runtime) in Linux sono disponibili varie opzioni. Il modo migliore per disinstallare .NET Core è eseguire il mirroring dell'azione usata per installare .NET Core. Le specifiche variano in base alla distribuzione scelta e al metodo di installazione.

> [!IMPORTANT]
> Per le installazioni di Red Hat, vedere l'[introduzione a Red Hat](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) per informazioni sull'installazione e la disinstallazione di .NET Core.

A partire da .NET Core 2,1, non è necessario disinstallare il .NET Core SDK durante l'aggiornamento con gestione pacchetti. La gestione pacchetti o i comandi `update` o `refresh` rimuoveranno automaticamente la versione precedente al termine dell'installazione di una versione più recente.

Se si è installato .NET Core usando uno strumento di gestione pacchetti, si userà la stessa gestione pacchetti per la disinstallazione dell'SDK o runtime .NET. Le installazioni di .NET Core supportano gli strumenti di gestione pacchetti più diffusi. Per la sintassi precisa nell'ambiente, vedere la documentazione relativa a gestione pacchetti della distribuzione:

- [apt-get(8)](https://linux.die.net/man/8/apt-get) viene usato dai sistemi basati su Debian, tra cui Ubuntu.
- [yum(8)](https://linux.die.net/man/8/yum) viene usato in Fedora, CentOS e Oracle Linux.
- [zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) viene usato in openSUSE e SUSE Linux Enterprise System (SLES).
- [dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) viene usato in Fedora.

Nella quasi totalità dei casi, il comando per rimuovere un pacchetto è `remove`.

Il nome del pacchetto per l'installazione di .NET Core SDK per la maggior parte degli strumenti di gestione pacchetti è `dotnet-sdk`, seguito dal numero di versione. A partire dalla versione 2.1.300 di .NET Core SDK e dalla versione `2.1` del runtime, sono necessari solo i numeri di versione principale e secondario: ad esempio, .NET Core SDK versione 2.1.300 può essere indicato come pacchetto `dotnet-sdk-2.1`. Le versioni precedenti richiedono l'intera stringa di versione: ad esempio, per la versione 2.1.200 di .NET Core SDK sarebbe necessario `dotnet-sdk-2.1.200`.

Per i computer su cui è installato solo il runtime e non l'SDK, il nome del pacchetto è `dotnet-runtime-<version>` per il runtime di .NET Core e `aspnetcore-runtime-<version>` per lo stack di runtime intero.

Le installazioni di .NET Core precedenti alla 2,0 non hanno disinstallato l'applicazione host quando l'SDK è stato disinstallato tramite Gestione pacchetti. Usando `apt-get`, il comando è:

```bash
apt-get remove dotnet-host
```

Si noti che non è presente alcuna versione collegata a `dotnet-host` .

Se è l'installazione è stata eseguita tramite un file tarball, è necessario rimuovere .NET Core usando il metodo manuale.

In Linux è necessario rimuovere gli SDK e i runtime separatamente, rimuovendo le directory con versione. La rimozione dell'SDK e del runtime dal disco viene eliminato. Ad esempio, per rimuovere l'SDK e il runtime versione 1.0.1, è necessario usare i comandi bash seguenti:

```bash
version="1.0.1"
sudo rm -rf /usr/local/share/dotnet/sdk/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/local/share/dotnet/host/fxr/$version
```

Le directory padre per l'SDK e il runtime sono elencate nell'output dai comandi `dotnet --list-sdks` e `dotnet --list-runtimes`, come illustrato nella tabella precedente.

::: zone-end

::: zone pivot="os-macos"

In Mac è necessario rimuovere gli SDK e i runtime separatamente, rimuovendo le directory con versione. La rimozione dell'SDK e del runtime dal disco viene eliminato. Ad esempio, per rimuovere l'SDK e il runtime versione 1.0.1, è necessario usare i comandi bash seguenti:

```bash
version="1.0.1"
sudo rm -rf /usr/local/share/dotnet/sdk/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/local/share/dotnet/host/fxr/$version
```

Le directory padre per l'SDK e il runtime sono elencate nell'output dai comandi `dotnet --list-sdks` e `dotnet --list-runtimes`, come illustrato nella tabella precedente.

::: zone-end

## <a name="net-core-uninstall-tool"></a>Strumento di disinstallazione di .NET Core

Lo [strumento di disinstallazione di .NET Core](../additional-tools/uninstall-tool.md) ( `dotnet-core-uninstall` ) consente di rimuovere gli SDK e i runtime di .NET Core da un sistema. È disponibile una raccolta di opzioni per specificare le versioni che devono essere disinstallate.

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a>Dipendenza di Visual Studio dalle versioni .NET Core SDK

Prima di Visual Studio 2019 versione 16,3, i programmi di installazione di Visual Studio denominavano il programma di installazione .NET Core SDK autonomo. Di conseguenza, le versioni dell'SDK vengono visualizzate nella finestra di dialogo Windows **Apps & features** . La rimozione di SDK di .NET Core installati da Visual Studio usando il programma di installazione autonomo potrebbe interrompere Visual Studio. Se si verificano problemi in Visual Studio dopo la disinstallazione di SDK, eseguire Repair sulla versione specifica di Visual Studio. La tabella seguente illustra alcune delle dipendenze di Visual Studio sulle versioni .NET Core SDK:

| Versione di Visual Studio           | Versione .NET Core SDK          |
|---------------------------------|--------------------------------|
| Visual Studio 2019 versione 16.2 | .NET Core SDK 2.2.4 XX, 2.1.8 XX |
| Visual Studio 2019 versione 16.1 | .NET Core SDK 2.2.3 XX, 2.1.7 XX |
| Visual Studio 2019 versione 16,0 | .NET Core SDK 2.2.2 XX, 2.1.6 XX |
| Visual Studio 2017 versione 15,9 | .NET Core SDK 2.2.1 XX, 2.1.5 XX |
| Visual Studio 2017 versione 15.8 | .NET Core SDK 2.1.4 XX          |

A partire da Visual Studio 2019 versione 16,3, Visual Studio è responsabile della propria copia del .NET Core SDK. Per questo motivo, le versioni dell'SDK non vengono più visualizzate nella finestra di dialogo **app & funzionalità** .

## <a name="remove-the-nuget-fallback-folder"></a>Rimuovere la cartella di fallback NuGet

Prima di .NET Core 3,0 SDK, i programmi di .NET Core SDK hanno usato una cartella denominata *NuGetFallbackFolder* per archiviare una cache di pacchetti NuGet. Questa cache è stata utilizzata durante le operazioni, ad esempio `dotnet restore` o `dotnet build /t:Restore` . Il *NuGetFallbackFolder* si trova in *C:\Program Files\dotnet\sdk* in Windows e in */usr/local/share/DotNet/SDK* in MacOS.

Potrebbe essere necessario rimuovere questa cartella, se:

- Si sta sviluppando solo usando .NET Core 3,0 SDK o versioni successive.
- Si sta sviluppando usando .NET Core SDK versioni precedenti alla 3,0, ma è possibile lavorare online.

Se si vuole rimuovere la cartella fallback di NuGet, è possibile eliminarla, ma saranno necessari i privilegi di amministratore.

Non è consigliabile eliminare la cartella *DotNet* . Questa operazione rimuoverà tutti gli strumenti globali installati in precedenza. Inoltre, in Windows:

- Si interrompe Visual Studio 2019 versione 16,3 e versioni successive. È possibile eseguire **Repair** per il ripristino.
- Se sono presenti .NET Core SDK voci nella finestra di dialogo **app & features** , saranno orfane.
