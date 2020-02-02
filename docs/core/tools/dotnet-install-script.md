---
title: Script dotnet-install
description: Informazioni sugli script DotNet-install per installare il .NET Core SDK e il runtime condiviso.
ms.date: 01/23/2020
ms.openlocfilehash: 76055627c6b2016396209c9594dba36e56eb841c
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920567"
---
# <a name="dotnet-install-scripts-reference"></a>Riferimento agli script dotnet-install

## <a name="name"></a>Name

`dotnet-install.ps1` | `dotnet-install.sh` script utilizzato per installare il .NET Core SDK e il runtime condiviso.

## <a name="synopsis"></a>Riepilogo

Windows:

```powershell
dotnet-install.ps1 [-Channel] [-Version] [-JSonFile] [-InstallDir] [-Architecture]
    [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential]
    [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]
```

Linux/macOs:

```bash
dotnet-install.sh [--channel] [--version] [--jsonfile] [--install-dir] [--architecture]
    [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential]
    [--runtime-id] [--skip-non-versioned-files] [--help]
```

## <a name="description"></a>Descrizione

Gli script di `dotnet-install` vengono usati per eseguire un'installazione non amministrativa del .NET Core SDK, che include il interfaccia della riga di comando di .NET Core e il runtime condiviso.

Si consiglia di utilizzare la versione stabile degli script:

- Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh>
- PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1>

Gli script vengono usati principalmente negli scenari di automazione e nelle installazioni senza privilegi di amministratore. Sono disponibili due script: uno è uno script PowerShell, che funziona in Windows, e l'altro è uno script Bash, che funziona in Linux/macOS. Entrambi gli script hanno lo stesso comportamento. Lo script bash legge anche le opzioni PowerShell, che possono quindi essere usate con lo script in sistemi Linux/macOS.

Gli script di installazione scaricano il file ZIP/tarball da destinazioni di compilazione dell'interfaccia della riga di comando e lo installano nel percorso predefinito o in un percorso specificato da `-InstallDir|--install-dir`. Per impostazione predefinita, lo script di installazione scarica e installa l'SDK. Se si vuole ottenere solo il runtime condiviso, è possibile specificare l'argomento `-Runtime|--runtime`.

Per impostazione predefinita, lo script aggiunge il percorso di installazione a $PATH per la sessione corrente. Eseguire l'override di questo comportamento predefinito specificando l'argomento `-NoPath|--no-path`.

Prima di eseguire lo script, installare le [dipendenze](../install/dependencies.md) necessarie.

È possibile installare una versione specifica usando l'argomento `-Version|--version`. La versione deve essere specificata come versione in tre parti, ad esempio `2.1.0`. Se non viene fornita, viene usata la versione `latest`.

## <a name="options"></a>Options

- **`-Channel|--channel <CHANNEL>`**

  Specifica il canale di origine per l'installazione. I valori possibili sono:

  - `Current`: versione più recente.
  - `LTS`: canale di supporto a lungo termine (versione supportata più recente).
  - Versione in due parti nel formato X.Y che rappresenta una versione specifica, ad esempio `2.1` o `3.0`.
  - Nome del ramo: ad esempio, `release/3.1.1xx` o `master` (per le versioni notturne). Usare questa opzione per installare una versione da un canale di anteprima. Usare il nome del canale come elencato in [programmi di installazione e file binari](https://github.com/dotnet/core-sdk#installers-and-binaries).

  Il valore predefinito è `LTS`. Per altre informazioni sui canali di supporto per .NET, vedere la pagina [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) (Criteri di supporto per .NET).

- **`-Version|--version <VERSION>`**

  Rappresenta una versione di build specifica. I valori possibili sono:

  - `latest`: ultima build sul canale (valore usato con l'opzione `-Channel`).
  - `coherent`: ultima build coerente sul canale. Usa la combinazione di pacchetti stabile più recente (valore usato con le opzioni `-Channel` del nome del ramo).
  - Versione in tre parti nel formato X.Y.Z che rappresenta una versione di build specifica; sostituisce l'opzione `-Channel`. Ad esempio: `2.0.0-preview2-006120`.

  Se non viene specificata, `-Version` viene impostata automaticamente su `latest`.

- **`-JSonFile|--jsonfile <JSONFILE>`**

  Specifica il percorso di un file [Global. JSON](global-json.md) che verrà usato per determinare la versione dell'SDK. Il file *Global. JSON* deve avere un valore per `sdk:version`.

- **`-InstallDir|--install-dir <DIRECTORY>`**

  Specifica il percorso di installazione. Se la directory non esiste, verrà creata. Il valore predefinito è *%LocalAppData%\Microsoft\dotnet*. I file binari vengono inseriti direttamente in questa directory.

- **`-Architecture|--architecture <ARCHITECTURE>`**

  Architettura dei file binari di .NET Core da installare. I valori consentiti sono `<auto>`, `amd64`, `x64`, `x86`, `arm64` e `arm`. Il valore predefinito è `<auto>`, che rappresenta l'architettura del sistema operativo attualmente in esecuzione.

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > Questo parametro è obsoleto e potrebbe essere rimosso in una versione futura dello script. L'alternativa consigliata è l'opzione `-Runtime|--runtime`.

  Installa solo i bit del runtime condiviso, non l'intero SDK. Questa opzione equivale a specificare `-Runtime|--runtime dotnet`.

- **`-Runtime|--runtime <RUNTIME>`**

  Installa solo il runtime condiviso, non l'intero SDK. I valori possibili sono:

  - `dotnet`: runtime condiviso `Microsoft.NETCore.App`.
  - `aspnetcore`: runtime condiviso `Microsoft.AspNetCore.App`.
  - `windowsdesktop`: runtime condiviso `Microsoft.WindowsDesktop.App`.

- **`-DryRun|--dry-run`**

  Se impostata, lo script non eseguirà l'installazione. Visualizza invece la riga di comando da usare per installare in modo coerente la versione attualmente richiesta dell'interfaccia della riga di comando di .NET Core. Se ad esempio si specifica la versione `latest`, verrà visualizzato un collegamento con la versione specifica in modo che questo comando possa essere usato in modo deterministico in uno script di compilazione. Viene visualizzato anche il percorso del file binario se si preferisce installarlo o scaricarlo manualmente.

- **`-NoPath|--no-path`**

  Se impostata, la cartella di installazione non viene esportata nel percorso per la sessione corrente. Per impostazione predefinita, lo script modifica il percorso, rendendo il interfaccia della riga di comando di .NET Core disponibile subito dopo l'installazione.

- **`-Verbose|--verbose`**

  Visualizza le informazioni di diagnostica.

- **`-AzureFeed|--azure-feed`**

  Specifica l'URL del feed di Azure per il programma di installazione. È consigliabile non modificare questo valore. Il valore predefinito è `https://dotnetcli.azureedge.net/dotnet`.

- **`-UncachedFeed|--uncached-feed`**

  Consente di modificare l'URL per il feed non memorizzato nella cache usato da questo programma di installazione. È consigliabile non modificare questo valore.

- **`-NoCdn|--no-cdn`**

  Disabilita il download dalla [Rete di distribuzione dei contenuti di Azure (rete CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) e usa direttamente il feed non memorizzato nella cache.

- **`-FeedCredential|--feed-credential`**

  Usata come stringa di query da accodare al feed di Azure. Consente la modifica dell'URL per usare account di archiviazione BLOB pubblici.

- **`--runtime-id`**

  Specifica l' [identificatore di runtime](../rid-catalog.md) per il quale vengono installati gli strumenti. Usare `linux-x64` per Linux portatile. (Valido solo per Linux/macOS)

- **`-ProxyAddress`**

  Se impostata, il programma di installazione usa il proxy durante le richieste Web. (Valido solo per Windows)

- **`ProxyUseDefaultCredentials`**

  Se impostata, il programma di installazione usa le credenziali dell'utente corrente quando si usa l'indirizzo proxy. (Valido solo per Windows)

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  Ignora l'installazione dei file senza versione, ad esempio *dotnet.exe*, se esistono già.

- **`-Help|--help`**

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

- Installare la versione più recente dal canale 3,1 nel percorso specificato:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  macOS/Linux:

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- Installare la versione 3.0.0 del runtime condiviso:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  macOS/Linux:

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
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
