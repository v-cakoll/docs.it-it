---
title: Comando dotnet nuget push
description: Il comando dotnet nuget push effettua il push di un pacchetto nel server e lo pubblica.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 608cd05d94dd6b5cdc53d582cfaa0407f011ff37
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925514"
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive

## <a name="name"></a>Nome

`dotnet nuget push`: effettua il push di un pacchetto nel server e lo pubblica.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [-n|--no-symbols true]
    [--no-service-endpoint] [-s|--source <SOURCE>] [--skip-duplicate]
    [-sk|--symbol-api-key <API_KEY>] [-ss|--symbol-source <SOURCE>]
    [-t|--timeout <TIMEOUT>]

dotnet nuget push -h|--help
```

## <a name="description"></a>Descrizione

Il comando `dotnet nuget push` effettua il push di un pacchetto nel server e lo pubblica. Il comando di push usa dettagli del server e delle credenziali presenti nel file di configurazione NuGet o nella catena di file di configurazione del sistema. Per altre informazioni sui file di configurazione, vedere [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configurazione del comportamento di NuGet). La configurazione predefinita di NuGet si ottiene caricando *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS) e quindi caricando qualsiasi file *nuget.config* o *.nuget\nuget.config* dalla directory radice dell'unità nella directory corrente.

Il comando effettua il push di un pacchetto esistente. Non crea un pacchetto. Per creare un pacchetto, usare [`dotnet pack`](dotnet-pack.md) .

## <a name="arguments"></a>Argomenti

- **`ROOT`**

  Specifica il percorso del file del pacchetto di cui eseguire il push.

## <a name="options"></a>Opzioni

- **`-d|--disable-buffering`**

  Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.

- **`--force-english-output`**

  Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--interactive`**

  Consente al comando di bloccare operazioni quali l'autenticazione e richiede un intervento manuale. Opzione disponibile a partire da .NET Core 2.2 SDK.

- **`-k|--api-key <API_KEY>`**

  Chiave API per il server.

- **`-n|--no-symbols true`**

  Non effettua il push dei simboli (anche se presenti).

- **`--no-service-endpoint`**

  Non aggiunge "api/v2/package" all'URL di origine. Opzione disponibile a partire da .NET Core 2.1 SDK.

- **`-s|--source <SOURCE>`**

  Specifica l'URL del server. Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.

- **`--skip-duplicate`**

  Quando si esegue il push di più pacchetti in un server HTTP (S), tratta qualsiasi risposta di conflitto 409 come un avviso, in modo che il push possa continuare. Disponibile a partire da .NET Core 3,1 SDK.

- **`-sk|--symbol-api-key <API_KEY>`**

  Chiave API per il server di simboli.

- **`-ss|--symbol-source <SOURCE>`**

  Specifica l'URL del server di simboli.

- **`-t|--timeout <TIMEOUT>`**

  Specifica il timeout (in secondi) per il push a un server. Il valore predefinito è 300 secondi (5 minuti). Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.

## <a name="examples"></a>Esempi

- Eseguire il push di *foo. nupkg* nell'origine push predefinita, specificando una chiave API:

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- Eseguire il push di *foo. nupkg* nel server NuGet ufficiale, specificando una chiave API:

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * Esegue il push di *foo.nupkg* all'origine push personalizzata `https://customsource`, specificando una chiave API:

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- Eseguire il push di *foo. nupkg* all'origine push predefinita:

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- Eseguire il push di *foo. symbols. nupkg* all'origine simboli predefinita:

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- Eseguire il push di *foo. nupkg* all'origine push predefinita, specificando un timeout di 360 secondi:

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- Eseguire il push di tutti i file con *estensione nupkg* nella directory corrente all'origine push predefinita:

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```

  > [!NOTE]
  > Il mancato funzionamento di questo comando può dipendere da un bug che era presente nelle versioni precedenti del SDK (.NET Core 2.1 SDK e versioni precedenti).
  > Per risolvere questo problema, aggiornare la versione del SDK oppure eseguire il comando seguente: `dotnet nuget push **/*.nupkg`

- Eseguire il push di tutti i file con *estensione nupkg* anche se una risposta di conflitto 409 viene restituita da un server http (S):

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```

- Eseguire il push di tutti i file con *estensione nupkg* nella directory corrente in una directory di feed locale:

  ```dotnetcli
  dotnet nuget push *.nupkg -s c:\mydir
  ```

  Questo comando non archivia i pacchetti in una struttura di cartelle gerarchica, consigliata per ottimizzare le prestazioni. Per ulteriori informazioni, vedere [feed locali](/nuget/hosting-packages/local-feeds).  
