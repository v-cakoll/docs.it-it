---
title: Comando dotnet nuget push
description: Il comando dotnet nuget push effettua il push di un pacchetto nel server e lo pubblica.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 3299f79ec62aebdcdbef38f1e8b09a2dc5529ec4
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117501"
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

**Questo argomento si applica a: ✓** .NET Core 2.1.x SDK e versioni successive

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>nome

`dotnet nuget push`: effettua il push di un pacchetto nel server e lo pubblica.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a>Descrizione

Il comando `dotnet nuget push` effettua il push di un pacchetto nel server e lo pubblica. Il comando di push usa dettagli del server e delle credenziali presenti nel file di configurazione NuGet o nella catena di file di configurazione del sistema. Per altre informazioni sui file di configurazione, vedere [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configurazione del comportamento di NuGet). La configurazione predefinita di NuGet si ottiene caricando *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS) e quindi caricando qualsiasi file *nuget.config* o *.nuget\nuget.config* dalla directory radice dell'unità nella directory corrente.

## <a name="arguments"></a>Argomenti

* **`ROOT`**

  Specifica il percorso del file del pacchetto di cui eseguire il push.

## <a name="options"></a>Opzioni

* **`-d|--disable-buffering`**

  Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.

* **`--force-english-output`**

  Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.

* **`-h|--help`**

Stampa una breve guida per il comando.

* **`--interactive`**

  Consente al comando di bloccare operazioni quali l'autenticazione e richiede un intervento manuale. Opzione disponibile a partire da .NET Core 2.2 SDK.

* **`-k|--api-key <API_KEY>`**

  Chiave API per il server.

* **`-n|--no-symbols`**

  Non effettua il push dei simboli (anche se presenti).

* **`--no-service-endpoint`**

  Non aggiunge "api/v2/package" all'URL di origine. Opzione disponibile a partire da .NET Core 2.1 SDK.

* **`-s|--source <SOURCE>`**

  Specifica l'URL del server. Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.

* **`-sk|--symbol-api-key <API_KEY>`**

  Chiave API per il server di simboli.

* **`-ss|--symbol-source <SOURCE>`**

  Specifica l'URL del server di simboli.

* **`-t|--timeout <TIMEOUT>`**

  Specifica il timeout (in secondi) per il push a un server. Il valore predefinito è 300 secondi (5 minuti). Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.

## <a name="examples"></a>Esempi

* Esegue il push di *foo.nupkg* all'origine push predefinita, specificando una chiave API:

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* Esegue il push di *foo.nupkg* all'origine push personalizzata `https://customsource`, specificando una chiave API:

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* Effettua il push di *foo.nupkg* all'origine push predefinita:

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

* Effettua il push di *foo.symbols.nupkg* all'origine simboli predefinita:

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

* Esegue il push di *foo.nupkg* all'origine push predefinita, specificando un timeout di 360 secondi:

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

* Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita:

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```
  
  > [!NOTE]
  > Il mancato funzionamento di questo comando può dipendere da un bug che era presente nelle versioni precedenti del SDK (.NET Core 2.1 SDK e versioni precedenti).
  > Per risolvere questo problema, aggiornare la versione del SDK oppure eseguire il comando seguente: `dotnet nuget push **/*.nupkg`
