---
title: Comando dotnet nuget push - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet nuget push effettua il push di un pacchetto nel server e lo pubblica.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 090b11646a81859eeadb5fe9d36b43721fc70a5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet nuget push`: effettua il push di un pacchetto nel server e lo pubblica.

## <a name="synopsis"></a>Riepilogo

`dotnet nuget push [<ROOT>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-h|--help]`

## <a name="description"></a>Descrizione

Il comando `dotnet nuget push` effettua il push di un pacchetto nel server e lo pubblica. Il comando di push usa dettagli del server e delle credenziali presenti nel file di configurazione NuGet o nella catena di file di configurazione del sistema. Per altre informazioni sui file di configurazione, vedere [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configurazione del comportamento di NuGet). La configurazione predefinita di NuGet si ottiene caricando *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS) e quindi caricando qualsiasi file *nuget.config* o *.nuget\nuget.config* dalla directory radice dell'unità nella directory corrente.

## <a name="arguments"></a>Argomenti

`ROOT`

Specifica il percorso del file del pacchetto di cui eseguire il push.

## <a name="options"></a>Opzioni

`-h|--help`

Stampa una breve guida per il comando.

`-s|--source <SOURCE>`

Specifica l'URL del server. Questa opzione è obbligatoria, a meno che il valore di configurazione `DefaultPushSource` non sia impostato nel file di configurazione NuGet.

`--symbol-source <SOURCE>`

Specifica l'URL del server di simboli.

`-t|--timeout <TIMEOUT>`

Specifica il timeout (in secondi) per il push a un server. Il valore predefinito è 300 secondi (5 minuti). Se si specifica 0 (zero secondi), viene comunque applicato il valore predefinito.

`-k|--api-key <API_KEY>`

Chiave API per il server.

`--symbol-api-key <API_KEY>`

Chiave API per il server di simboli.

`-d|--disable-buffering`

Disabilita la memorizzazione nel buffer quando si effettua il push a un server HTTP(S) per ridurre l'utilizzo della memoria.

`-n|--no-symbols`

Non effettua il push dei simboli (anche se presenti).

`--force-english-output`

Forza la visualizzazione di tutto l'output registrato in inglese.

## <a name="examples"></a>Esempi

Effettua il push di *foo.nupkg* all'origine push predefinita, specificando la chiave API:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

Effettua il push di *foo.nupkg* all'origine push personalizzata `http://customsource`, specificando la chiave API:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

Effettua il push di *foo.nupkg* all'origine push predefinita:

`dotnet nuget push foo.nupkg`

Effettua il push di *foo.symbols.nupkg* all'origine simboli predefinita:

`dotnet nuget push foo.symbols.nupkg`

Effettua il push di *foo.nupkg* all'origine push predefinita, specificando un timeout di 360 secondi:

`dotnet nuget push foo.nupkg --timeout 360`

Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita:

`dotnet nuget push *.nupkg`

Effettua il push di tutti i file con estensione *nupkg* presenti nella directory corrente all'origine push predefinita, specificando un file di configurazione personalizzato *./config/My.Config*:

`dotnet nuget push *.nupkg --config-file ./config/My.Config`
