---
title: Comando dotnet nuget push - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet nuget push effettua il push di un pacchetto nel server e lo pubblica.
author: karann-msft
ms.author: mairaw
ms.date: 09/04/2018
ms.openlocfilehash: 23d27cef29008955850f9ed9f4a8baed9e7ad982
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45610007"
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet nuget push`: effettua il push di un pacchetto nel server e lo pubblica.

## <a name="synopsis"></a>Riepilogo

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a>Descrizione

Il comando `dotnet nuget push` effettua il push di un pacchetto nel server e lo pubblica. Il comando di push usa dettagli del server e delle credenziali presenti nel file di configurazione NuGet o nella catena di file di configurazione del sistema. Per altre informazioni sui file di configurazione, vedere [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configurazione del comportamento di NuGet). La configurazione predefinita di NuGet si ottiene caricando *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS) e quindi caricando qualsiasi file *nuget.config* o *.nuget\nuget.config* dalla directory radice dell'unità nella directory corrente.

## <a name="arguments"></a>Argomenti

`ROOT`

Specifica il percorso del file del pacchetto di cui eseguire il push.

## <a name="options"></a>Opzioni

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`-d|--disable-buffering`

Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.

`--force-english-output`

Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.

`-h|--help`

Stampa una breve guida per il comando.

`-k|--api-key <API_KEY>`

Chiave API per il server.

`-n|--no-symbols`

Non effettua il push dei simboli (anche se presenti).

`--no-service-endpoint`

Non aggiunge "api/v2/package" all'URL di origine.

`-s|--source <SOURCE>`

Specifica l'URL del server. Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.

`-sk|--symbol-api-key <API_KEY>`

Chiave API per il server di simboli.

`-ss|--symbol-source <SOURCE>`

Specifica l'URL del server di simboli.

`-t|--timeout <TIMEOUT>`

Specifica il timeout (in secondi) per il push a un server. Il valore predefinito è 300 secondi (5 minuti). Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`-d|--disable-buffering`

Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.

`--force-english-output`

Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.

`-h|--help`

Stampa una breve guida per il comando.

`-k|--api-key <API_KEY>`

Chiave API per il server.

`-n|--no-symbols`

Non effettua il push dei simboli (anche se presenti).

`-s|--source <SOURCE>`

Specifica l'URL del server. Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.

`-sk|--symbol-api-key <API_KEY>`

Chiave API per il server di simboli.

`-ss|--symbol-source <SOURCE>`

Specifica l'URL del server di simboli.

`-t|--timeout <TIMEOUT>`

Specifica il timeout (in secondi) per il push a un server. Il valore predefinito è 300 secondi (5 minuti). Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-d|--disable-buffering`

Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.

`--force-english-output`

Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.

`-h|--help`

Stampa una breve guida per il comando.

`-k|--api-key <API_KEY>`

Chiave API per il server.

`-n|--no-symbols`

Non effettua il push dei simboli (anche se presenti).

`-s|--source <SOURCE>`

Specifica l'URL del server. Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.

`-sk|--symbol-api-key <API_KEY>`

Chiave API per il server di simboli.

`-ss|--symbol-source <SOURCE>`

Specifica l'URL del server di simboli.

`-t|--timeout <TIMEOUT>`

Specifica il timeout (in secondi) per il push a un server. Il valore predefinito è 300 secondi (5 minuti). Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.

---

## <a name="examples"></a>Esempi

Esegue il push di *foo.nupkg* all'origine push predefinita, specificando una chiave API:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

Esegue il push di *foo.nupkg* all'origine push personalizzata `http://customsource`, specificando una chiave API:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

Effettua il push di *foo.nupkg* all'origine push predefinita:

`dotnet nuget push foo.nupkg`

Effettua il push di *foo.symbols.nupkg* all'origine simboli predefinita:

`dotnet nuget push foo.symbols.nupkg`

Esegue il push di *foo.nupkg* all'origine push predefinita, specificando un timeout di 360 secondi:

`dotnet nuget push foo.nupkg --timeout 360`

Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita:

`dotnet nuget push *.nupkg`
