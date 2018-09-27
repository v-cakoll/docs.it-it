---
title: Script dotnet-install
description: Informazioni sugli script dotnet-install per l'installazione degli strumenti dell'interfaccia della riga di comando di .NET Core e del runtime condiviso.
author: blackdwarf
ms.author: mairaw
ms.date: 09/11/2017
ms.openlocfilehash: 8d1c6ebb30bd45575bb61206799c9c3e5c47ff0c
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004010"
---
# <a name="dotnet-install-scripts-reference"></a>Riferimento agli script dotnet-install

## <a name="name"></a>nome

`dotnet-install.ps1` | `dotnet-install.sh`: script usato per l'installazione degli strumenti dell'interfaccia della riga di comando e del runtime condiviso di .NET Core.

## <a name="synopsis"></a>Riepilogo

Windows:

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress] [--Verbose] [--Help]`

macOS/Linux:

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--dry-run] [--no-path] [--azure-feed] [--verbose] [--help]`

## <a name="description"></a>Descrizione

Gli script `dotnet-install` vengono usati per eseguire un'installazione non amministrativa di .NET Core SDK, che include gli strumenti dell'interfaccia della riga di comando e il runtime condiviso di .NET Core.

È consigliabile usare la versione stabile ospitata nel [sito Web principale di .NET Core](https://dot.net). I percorsi diretti per gli script sono:

* https://dot.net/v1/dotnet-install.sh (Bash, UNIX)
* https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)

Gli script vengono usati principalmente negli scenari di automazione e nelle installazioni senza privilegi di amministratore. Sono disponibili due script, uno per PowerShell, che funziona in Windows, L'altro script è uno script bash che funziona su Linux/macOS. Entrambi gli script hanno lo stesso comportamento. Lo script bash legge anche le opzioni PowerShell, che possono quindi essere usate con lo script in sistemi Linux/macOS.

Gli script di installazione scaricano il file ZIP/tarball da destinazioni di compilazione dell'interfaccia della riga di comando e lo installano nel percorso predefinito o in un percorso specificato da `-InstallDir|--install-dir`. Per impostazione predefinita, lo script di installazione scarica e installa l'SDK. Se si vuole ottenere solo il runtime condiviso, è possibile specificare l'argomento `--shared-runtime`.

Per impostazione predefinita, lo script aggiunge il percorso di installazione a $PATH per la sessione corrente. Eseguire l'override di questo comportamento predefinito specificando l'argomento `--no-path`.

Prima di eseguire lo script, installare le [dipendenze](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necessarie.

È possibile installare una versione specifica usando l'argomento `--version`. La versione deve essere specificata con un numero a tre parti (ad esempio, 1.0.0-13232). Se omessa, viene usata la versione `latest`.

## <a name="options"></a>Opzioni

`-Channel <CHANNEL>`

Specifica il canale di origine per l'installazione. I valori possibili sono:

- `Current` - Versione corrente
- `LTS` - Canale di supporto a lungo termine (versione supportata corrente)
- Versione in due parti nel formato X.Y che rappresenta una versione specifica, ad esempio `2.0` o `1.0`
- Nome del ramo, ad esempio, `release/2.0.0`, `release/2.0.0-preview2` o `master` per la versione più recente dal ramo `master` (versioni notturne "all'avanguardia")

Il valore predefinito è `LTS`. Per altre informazioni sui canali di supporto per .NET, vedere l'argomento [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) (Ciclo di vita del supporto per .NET Core).

`-Version <VERSION>`

Rappresenta una versione di build specifica. I valori possibili sono:

- `latest` - Ultima build sul canale (valore usato con l'opzione `-Channel`)
- `coherent` - Ultima build coerente sul canale; usa la combinazione di pacchetti stabile più recente (valore usato con le opzioni `-Channel` del nome di ramo)
- Versione in tre parti nel formato X.Y.Z che rappresenta una versione di build specifica; sostituisce l'opzione `-Channel`. Ad esempio: `2.0.0-preview2-006120`

Se omesso, `-Version` viene impostato automaticamente su `latest`.

`-InstallDir <DIRECTORY>`

Specifica il percorso di installazione. Se la directory non esiste, verrà creata. Il valore predefinito è *%LocalAppData%\.dotnet*. Si noti che i file binari vengono inseriti direttamente nella directory.

`-Architecture <ARCHITECTURE>`

Architettura dei file binari di .NET Core da installare. I valori possibili sono `auto`, `x64` e `x86`. Il valore predefinito è `auto`, che rappresenta l'architettura del sistema operativo attualmente in esecuzione.

`-SharedRuntime`

Se impostata, questa opzione limita l'installazione al runtime condiviso. Non viene installato l'intero SDK.

`-DryRun`

Se impostata, lo script non esegue l'installazione, ma visualizza la riga di comando da usare per installare in modo coerente la versione attualmente richiesta dell'interfaccia della riga di comando di .NET Core. Se ad esempio si specifica la versione `latest`, verrà visualizzato un collegamento con la versione specifica in modo che questo comando possa essere usato in modo deterministico in uno script di compilazione. Viene visualizzato anche il percorso del file binario se si preferisce installarlo o scaricarlo manualmente.

`-NoPath`

Se impostata, il prefisso o la directory di installazione non viene esportata nel percorso per la sessione corrente. Per impostazione predefinita, lo script modifica il percorso rendendo disponibili gli strumenti dell'interfaccia della riga di comando immediatamente dopo l'installazione.

`-AzureFeed`

Specifica l'URL del feed di Azure per il programma di installazione. È consigliabile non modificare questo valore. Il valore predefinito è `https://dotnetcli.azureedge.net/dotnet`.

`-ProxyAddress`

Se impostata, il programma di installazione usa il proxy durante le richieste Web. (Valido solo per Windows)

`--verbose`

Visualizza le informazioni di diagnostica.

`--help`

Stampa la Guida per lo script.

## <a name="examples"></a>Esempi

Installare la versione LTS (Long Term Support) più recente nel percorso predefinito:

Windows:

`./dotnet-install.ps1 -Channel LTS`

macOS/Linux:

`./dotnet-install.sh --channel LTS`

Installare la versione più recente dal canale 2.0 nel percorso specificato:

Windows:

`./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli`

macOS/Linux:

`./dotnet-install.sh --channel 2.0 --install-dir ~/cli`

Installare la versione 1.1.0 del runtime condiviso:

Windows:

`./dotnet-install.ps1 -SharedRuntime -Version 1.1.0`

macOS/Linux:

`./dotnet-install.sh --shared-runtime --version 1.1.0`

Ottenere lo script e installare gli esempi di .NET Core CLI di una singola riga di codice:

Windows:

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"`

macOS/Linux:

`curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>`

## <a name="see-also"></a>Vedere anche

* [.NET Core releases](https://github.com/dotnet/core/releases) (Versioni di .NET Core)
* [.NET Core Runtime and SDK download archive](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md) (Archivio di download per runtime e SDK di .NET Core)
