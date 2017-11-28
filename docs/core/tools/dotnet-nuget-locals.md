---
title: Comando dotnet nuget locals - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet nuget locals cancella o elenca le risorse NuGet locali, quali cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 2b66198ac3e33c640abda0c96fb05944f5ea91df
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-nuget-locals"></a>dotnet nuget locals

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Nome

`dotnet nuget locals`: cancella o elenca risorse NuGet locali.

## <a name="synopsis"></a>Riepilogo

`dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output] [-h|--help]`

## <a name="description"></a>Descrizione

Il comando `dotnet nuget locals` cancella o elenca risorse NuGet locali presenti nella cache delle richieste HTTP, nella cache temporanea o nella cartella globale dei pacchetti a livello di computer.

## <a name="arguments"></a>Argomenti

`CACHE_LOCATION`

Uno dei valori seguenti:

* `all` - Indica che l'operazione specificata viene applicata a tutti i tipi di cache, ovvero alla cache delle richieste HTTP, alla cache globale dei pacchetti e alla cache temporanea.
* `http-cache` - Indica che l'operazione specificata viene applicata soltanto alla cache delle richieste HTTP. Le altre posizioni di cache non sono interessate.
* `global-packages` - Indica che l'operazione specificata viene applicata soltanto alla cache dei pacchetti globale. Le altre posizioni di cache non sono interessate.
* `temp` - Indica che l'operazione specificata viene applicata soltanto alla cache temporanea. Le altre posizioni di cache non sono interessate.

## <a name="options"></a>Opzioni

`-h|--help`

Stampa una breve guida per il comando.

`-c|--clear`

L'opzione "clear" consente di eseguire un'operazione di cancellazione sul tipo di cache specificato. Il contenuto delle directory della cache viene eliminato in modo ricorsivo. L'utente o il gruppo che esegue l'operazione deve disporre delle autorizzazioni per i file presenti nelle directory della cache. In caso contrario, viene visualizzato un messaggio di errore con l'indicazione delle cartelle e/o dei file che non sono stati cancellati.

`-l|--list`

L'opzione "list" viene usata per visualizzare la posizione del tipo di cache specificato. 

`--force-english-output`

Forza la visualizzazione dell'output della riga di comando in inglese.

## <a name="examples"></a>Esempi

Visualizza i percorsi di tutte le directory locali della cache, ovvero directory della cache HTTP, directory della cache globale dei pacchetti e directory della cache temporanea:

`dotnet nuget locals –l all`

Visualizza il percorso della directory locale della cache HTTP:

`dotnet nuget locals --list http-cache`

Cancella tutti i file da tutte le directory locali della cache, ovvero directory della cache HTTP, directory della cache globale dei pacchetti e directory della cache temporanea:

`dotnet nuget locals --clear all`

Cancella tutti i file presenti nella directory locale della cache globale dei pacchetti:

`dotnet nuget locals -c global-packages`

Cancella tutti i file presenti nella directory locale della cache temporanea:

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a>Risoluzione dei problemi

Per informazioni su problemi ed errori comuni relativi all'uso del comando `dotnet nuget locals`, vedere [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache) (Gestione della cache NuGet).