---
title: Script dotnet-install
description: Informazioni sugli script DotNet-install per installare il .NET Core SDK e il runtime condiviso.
ms.date: 04/30/2020
ms.openlocfilehash: d03877d76212f7b22de0a1075cf50fc75bd104b6
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324426"
---
# <a name="dotnet-install-scripts-reference"></a>Riferimento agli script dotnet-install

## <a name="name"></a>Nome

`dotnet-install.ps1` | `dotnet-install.sh`: Script usato per installare il .NET Core SDK e il runtime condiviso.

## <a name="synopsis"></a>Riepilogo

Windows:

```powershell
dotnet-install.ps1 [-Architecture <ARCHITECTURE>] [-AzureFeed]
    [-Channel <CHANNEL>] [-DryRun] [-FeedCredential]
    [-InstallDir <DIRECTORY>] [-JSonFile <JSONFILE>]
    [-NoCdn] [-NoPath] [-ProxyAddress]
    [-ProxyUseDefaultCredentials] [-Runtime <RUNTIME>]
    [-SkipNonVersionedFiles] [-UncachedFeed] [-Verbose]
    [-Version <VERSION>]

Get-Help ./dotnet-install.ps1
```

Linux/macOS:

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

Lo script bash legge anche le opzioni PowerShell, che possono quindi essere usate con lo script in sistemi Linux/macOS.

## <a name="description"></a>Description

Gli `dotnet-install` script eseguono un'installazione non amministrativa del .NET Core SDK, che include i interfaccia della riga di comando di .NET Core e il runtime condiviso. Sono disponibili due script:

* Uno script di PowerShell che funziona in Windows.
* Uno script bash che funziona in Linux/macOS.

### <a name="purpose"></a>Scopo

 L'uso previsto degli script è per gli scenari di integrazione continua (CI), in cui:

* È necessario installare l'SDK senza l'intervento dell'utente e senza diritti di amministratore.
* Non è necessario che l'installazione dell'SDK venga mantenute tra più esecuzioni CI.

  Sequenza di eventi tipica:
  * CI viene attivato.
  * CI installa l'SDK usando uno di questi script.
  * CI termina il suo lavoro e cancella i dati temporanei, inclusa l'installazione dell'SDK.

Per configurare un ambiente di sviluppo o per eseguire app, usare i programmi di installazione anziché questi script.

### <a name="recommended-version"></a>Versione consigliata

Si consiglia di utilizzare la versione stabile degli script:

- Bash (Linux/macOS):<https://dot.net/v1/dotnet-install.sh>
- PowerShell (Windows):<https://dot.net/v1/dotnet-install.ps1>

### <a name="script-behavior"></a>Comportamento dello script

Entrambi gli script hanno lo stesso comportamento. Scaricano il file ZIP/tarball dalle gocce di compilazione dell'interfaccia della riga di comando e lo installano nel percorso predefinito o in un percorso specificato da `-InstallDir|--install-dir` .

Per impostazione predefinita, lo script di installazione scarica e installa l'SDK. Se si vuole ottenere solo il runtime condiviso, è possibile specificare l'argomento `-Runtime|--runtime`.

Per impostazione predefinita, lo script aggiunge il percorso di installazione a $PATH per la sessione corrente. Eseguire l'override di questo comportamento predefinito specificando l'argomento `-NoPath|--no-path`. Lo script non imposta la `DOTNET_ROOT` variabile di ambiente.

Prima di eseguire lo script, installare le [dipendenze](../install/dependencies.md) necessarie.

È possibile installare una versione specifica usando l'argomento `-Version|--version`. La versione deve essere specificata come numero di versione in tre parti, ad esempio `2.1.0` . Se la versione non è specificata, lo script installa la `latest` versione.

Gli script di installazione non aggiornano il registro di sistema in Windows. Scaricano semplicemente i file binari compressi e li copiano in una cartella. Se si vogliono aggiornare i valori delle chiavi del registro di sistema, usare i programmi di installazione di .NET Core.

## <a name="options"></a>Opzioni

- **`-Architecture|--architecture <ARCHITECTURE>`**

  Architettura dei file binari di .NET Core da installare. I valori consentiti sono `<auto>`, `amd64`, `x64`, `x86`, `arm64` e `arm`. Il valore predefinito è `<auto>`, che rappresenta l'architettura del sistema operativo attualmente in esecuzione.

- **`-AzureFeed|--azure-feed`**

  Specifica l'URL del feed di Azure per il programma di installazione. È consigliabile non modificare questo valore. Il valore predefinito è `https://dotnetcli.azureedge.net/dotnet`.

- **`-Channel|--channel <CHANNEL>`**

  Specifica il canale di origine per l'installazione. I valori possibili sono:

  - `Current`: versione più recente.
  - `LTS`: canale di supporto a lungo termine (versione supportata più recente).
  - Versione in due parti nel formato X.Y che rappresenta una versione specifica, ad esempio `2.1` o `3.0`.
  - Nome del ramo: ad esempio `release/3.1.1xx` o `master` (per le versioni notturne). Usare questa opzione per installare una versione da un canale di anteprima. Usare il nome del canale come elencato in [programmi di installazione e file binari](https://github.com/dotnet/core-sdk#installers-and-binaries).

  Il valore predefinito è `LTS`. Per altre informazioni sui canali di supporto per .NET, vedere la pagina [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) (Criteri di supporto per .NET).

- **`-DryRun|--dry-run`**

  Se impostata, lo script non eseguirà l'installazione. Visualizza invece la riga di comando da usare per installare in modo coerente la versione attualmente richiesta dell'interfaccia della riga di comando di .NET Core. Se ad esempio si specifica la versione `latest`, verrà visualizzato un collegamento con la versione specifica in modo che questo comando possa essere usato in modo deterministico in uno script di compilazione. Viene visualizzato anche il percorso del file binario se si preferisce installarlo o scaricarlo manualmente.

- **`-FeedCredential|--feed-credential`**

  Usata come stringa di query da accodare al feed di Azure. Consente la modifica dell'URL per usare account di archiviazione BLOB pubblici.

- **`--help`**

  Stampa la Guida per lo script. Si applica solo allo script bash. Per PowerShell, usare `Get-Help ./dotnet-install.ps1` .

- **`-InstallDir|--install-dir <DIRECTORY>`**

  Specifica il percorso di installazione. Se la directory non esiste, verrà creata. Il valore predefinito è *%LocalAppData%\Microsoft\dotnet* in Windows e */usr/share/DotNet* in Linux/MacOS. I file binari vengono inseriti direttamente in questa directory.

- **`-JSonFile|--jsonfile <JSONFILE>`**

  Specifica il percorso di un [global.jsnel](global-json.md) file che verrà usato per determinare la versione dell'SDK. Il *global.jsnel* file deve avere un valore per `sdk:version` .

- **`-NoCdn|--no-cdn`**

  Disabilita il download dalla [Rete di distribuzione dei contenuti di Azure (rete CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) e usa direttamente il feed non memorizzato nella cache.

- **`-NoPath|--no-path`**

  Se impostata, la cartella di installazione non viene esportata nel percorso per la sessione corrente. Per impostazione predefinita, lo script modifica il percorso, rendendo il interfaccia della riga di comando di .NET Core disponibile subito dopo l'installazione.

- **`-ProxyAddress`**

  Se impostata, il programma di installazione usa il proxy durante le richieste Web. (Valido solo per Windows).

- **`ProxyUseDefaultCredentials`**

  Se impostata, il programma di installazione usa le credenziali dell'utente corrente quando si usa l'indirizzo proxy. (Valido solo per Windows).

- **`-Runtime|--runtime <RUNTIME>`**

  Installa solo il runtime condiviso, non l'intero SDK. I valori possibili sono:

  - `dotnet`: runtime condiviso `Microsoft.NETCore.App`.
  - `aspnetcore`: runtime condiviso `Microsoft.AspNetCore.App`.
  - `windowsdesktop`: runtime condiviso `Microsoft.WindowsDesktop.App`.

- **`--runtime-id <RID>`**

  Specifica l' [identificatore di runtime](../rid-catalog.md) per il quale vengono installati gli strumenti. Usare `linux-x64` per Linux portatile. (Valido solo per Linux/macOS).

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > Questo parametro è obsoleto e potrebbe essere rimosso in una versione futura dello script. L'alternativa consigliata è l'opzione `-Runtime|--runtime`.

  Installa solo i bit del runtime condiviso, non l'intero SDK. Questa opzione equivale a specificare `-Runtime|--runtime dotnet` .

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  Ignora l'installazione dei file senza versione, ad esempio *dotnet.exe*, se esistono già.

- **`-UncachedFeed|--uncached-feed`**

  Consente di modificare l'URL per il feed non memorizzato nella cache usato da questo programma di installazione. È consigliabile non modificare questo valore.

- **`-Verbose|--verbose`**

  Visualizza le informazioni di diagnostica.

- **`-Version|--version <VERSION>`**

  Rappresenta una versione di build specifica. I valori possibili sono:

  - `latest`: ultima build sul canale (valore usato con l'opzione `-Channel`).
  - `coherent`: ultima build coerente sul canale. Usa la combinazione di pacchetti stabile più recente (valore usato con le opzioni `-Channel` del nome del ramo).
  - Versione in tre parti nel formato X.Y.Z che rappresenta una versione di build specifica; sostituisce l'opzione `-Channel`. Ad esempio: `2.0.0-preview2-006120`.

  Se non viene specificata, `-Version` viene impostata automaticamente su `latest`.

## <a name="examples"></a>Esempio

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
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a>Vedi anche

- [.NET Core releases](https://github.com/dotnet/core/releases) (Versioni di .NET Core)
- [.NET Core Runtime and SDK download archive](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md) (Archivio di download per runtime e SDK di .NET Core)
