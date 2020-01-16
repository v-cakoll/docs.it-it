---
title: Script dotnet-install
description: Informazioni sugli script dotnet-install per l'installazione degli strumenti dell'interfaccia della riga di comando di .NET Core e del runtime condiviso.
ms.date: 01/16/2019
ms.openlocfilehash: 765141ae92645db448ac7c9c3448a79b895faac6
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964339"
---
# <a name="dotnet-install-scripts-reference"></a>Riferimento agli script dotnet-install

## <a name="name"></a>Name

`dotnet-install.ps1` | `dotnet-install.sh`: script usato per l'installazione degli strumenti dell'interfaccia della riga di comando e del runtime condiviso di .NET Core.

## <a name="synopsis"></a>Riepilogo

Windows:

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential] [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]`

macOS/Linux:

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential] [--runtime-id] [--skip-non-versioned-files] [--help]`

## <a name="description"></a>Descrizione

Gli script `dotnet-install` vengono usati per eseguire un'installazione non amministrativa di .NET Core SDK, che include gli strumenti dell'interfaccia della riga di comando e il runtime condiviso di .NET Core.

È consigliabile usare la versione stabile ospitata nel [sito Web principale di .NET Core](https://dot.net). I percorsi diretti per gli script sono:

- <https://dot.net/v1/dotnet-install.sh> (Bash, UNIX)
- <https://dot.net/v1/dotnet-install.ps1> (Powershell, Windows)

Gli script vengono usati principalmente negli scenari di automazione e nelle installazioni senza privilegi di amministratore. Sono disponibili due script: uno è uno script PowerShell, che funziona in Windows, e l'altro è uno script Bash, che funziona in Linux/macOS. Entrambi gli script hanno lo stesso comportamento. Lo script bash legge anche le opzioni PowerShell, che possono quindi essere usate con lo script in sistemi Linux/macOS.

Gli script di installazione scaricano il file ZIP/tarball da destinazioni di compilazione dell'interfaccia della riga di comando e lo installano nel percorso predefinito o in un percorso specificato da `-InstallDir|--install-dir`. Per impostazione predefinita, lo script di installazione scarica e installa l'SDK. Se si vuole ottenere solo il runtime condiviso, è possibile specificare l'argomento `--runtime`.

Per impostazione predefinita, lo script aggiunge il percorso di installazione a $PATH per la sessione corrente. Eseguire l'override di questo comportamento predefinito specificando l'argomento `--no-path`.

Prima di eseguire lo script, installare le [dipendenze](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necessarie.

È possibile installare una versione specifica usando l'argomento `--version`. La versione deve essere specificata con un numero a tre parti (ad esempio, 1.0.0-13232). Se non viene fornita, viene usata la versione `latest`.

## <a name="options"></a>Options

- **`-Channel <CHANNEL>`**

  Specifica il canale di origine per l'installazione. I valori possibili sono:

  - `Current`: versione più recente.
  - `LTS`: canale di supporto a lungo termine (versione supportata più recente).
  - Versione in due parti nel formato X.Y che rappresenta una versione specifica, ad esempio `2.0` o `1.0`.
  - Nome ramo. Ad esempio, `release/2.0.0`, `release/2.0.0-preview2` o `master` (per le versione notturne).

  Il valore predefinito è `LTS`. Per altre informazioni sui canali di supporto per .NET, vedere la pagina [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) (Criteri di supporto per .NET).

- **`-Version <VERSION>`**

  Rappresenta una versione di build specifica. I valori possibili sono:

  - `latest`: ultima build sul canale (valore usato con l'opzione `-Channel`).
  - `coherent`: ultima build coerente sul canale. Usa la combinazione di pacchetti stabile più recente (valore usato con le opzioni `-Channel` del nome del ramo).
  - Versione in tre parti nel formato X.Y.Z che rappresenta una versione di build specifica; sostituisce l'opzione `-Channel`. Ad esempio: `2.0.0-preview2-006120`.

  Se non viene specificata, `-Version` viene impostata automaticamente su `latest`.

- **`-InstallDir <DIRECTORY>`**

  Specifica il percorso di installazione. Se la directory non esiste, verrà creata. Il valore predefinito è *%LocalAppData%\Microsoft\dotnet*. I file binari vengono inseriti direttamente in questa directory.

- **`-Architecture <ARCHITECTURE>`**

  Architettura dei file binari di .NET Core da installare. I valori consentiti sono `<auto>`, `amd64`, `x64`, `x86`, `arm64` e `arm`. Il valore predefinito è `<auto>`, che rappresenta l'architettura del sistema operativo attualmente in esecuzione.

- **`-SharedRuntime`**

  > [!NOTE]
  > Questo parametro è obsoleto e potrebbe essere rimosso in una versione futura dello script. L'alternativa consigliata è l'opzione `Runtime`.

  Installa solo i bit del runtime condiviso, non l'intero SDK. Ciò equivale a specificare `-Runtime dotnet`.

- **`-Runtime <RUNTIME>`**

  Installa solo il runtime condiviso, non l'intero SDK. I valori possibili sono:

  - `dotnet`: runtime condiviso `Microsoft.NETCore.App`.
  - `aspnetcore`: runtime condiviso `Microsoft.AspNetCore.App`.

- **`-DryRun`**

  Se impostata, lo script non eseguirà l'installazione. Visualizza invece la riga di comando da usare per installare in modo coerente la versione attualmente richiesta dell'interfaccia della riga di comando di .NET Core. Se ad esempio si specifica la versione `latest`, verrà visualizzato un collegamento con la versione specifica in modo che questo comando possa essere usato in modo deterministico in uno script di compilazione. Viene visualizzato anche il percorso del file binario se si preferisce installarlo o scaricarlo manualmente.

- **`-NoPath`**

  Se impostata, la cartella di installazione non viene esportata nel percorso per la sessione corrente. Per impostazione predefinita, lo script modifica il percorso rendendo disponibili gli strumenti dell'interfaccia della riga di comando immediatamente dopo l'installazione.

- **`-Verbose`**

  Visualizza le informazioni di diagnostica.

- **`-AzureFeed`**

  Specifica l'URL del feed di Azure per il programma di installazione. È consigliabile non modificare questo valore. Il valore predefinito è `https://dotnetcli.azureedge.net/dotnet`.

- **`-UncachedFeed`**

  Consente di modificare l'URL per il feed non memorizzato nella cache usato da questo programma di installazione. È consigliabile non modificare questo valore.

- **`-NoCdn`**

  Disabilita il download dalla [Rete di distribuzione dei contenuti di Azure (rete CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) e usa direttamente il feed non memorizzato nella cache.

- **`-FeedCredential`**

  Usata come stringa di query da accodare al feed di Azure. Consente la modifica dell'URL per usare account di archiviazione BLOB pubblici.

- **`-ProxyAddress`**

  Se impostata, il programma di installazione usa il proxy durante le richieste Web. (Valido solo per Windows)

- **`ProxyUseDefaultCredentials`**

  Se impostata, il programma di installazione usa le credenziali dell'utente corrente quando si usa l'indirizzo proxy. (Valido solo per Windows)

- **`-SkipNonVersionedFiles`**

  Ignora l'installazione dei file senza versione, ad esempio *dotnet.exe*, se esistono già.

- **`-Help`**

  Stampa la Guida per lo script.

## <a name="examples"></a>Esempi

- Installare la versione LTS (Long Term Support) più recente nel percorso predefinito:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  macOS/Linux:

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- Installare la versione più recente dal canale 2.0 nel percorso specificato:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli
  ```

  macOS/Linux:

  ```bash
  ./dotnet-install.sh --channel 2.0 --install-dir ~/cli
  ```

- Installare la versione 1.1.0 del runtime condiviso:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 1.1.0
  ```

  macOS/Linux:

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 1.1.0
  ```

- Ottenere lo script e installare la versione 2.1.2 versione dietro un proxy aziendale (solo Windows):

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- Ottenere lo script e installare gli esempi di .NET Core CLI di una singola riga di codice:

  Windows:

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  macOS/Linux:

  ```bash
  curl -ssl https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a>Vedere anche

- [.NET Core releases](https://github.com/dotnet/core/releases) (Versioni di .NET Core)
- [.NET Core Runtime and SDK download archive](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md) (Archivio di download per runtime e SDK di .NET Core)
