---
title: Comando dotnet nuget locals - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet nuget locals cancella o elenca le risorse NuGet locali, quali cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.
author: karann-msft
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 799acb92d6ab7439e15c23c9f0b7b572c966adda
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696871"
---
# <a name="dotnet-nuget-locals"></a>dotnet nuget locals

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet nuget locals`: cancella o elenca risorse NuGet locali.

## <a name="synopsis"></a>Riepilogo

```
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a>Descrizione

Il comando `dotnet nuget locals` cancella o elenca risorse NuGet locali presenti nella cache delle richieste HTTP, nella cache temporanea o nella cartella globale dei pacchetti a livello di computer.

## <a name="arguments"></a>Argomenti

`CACHE_LOCATION`

Il percorso della cache da visualizzare o cancellare. Il valore può essere uno dei seguenti:

* `all` - Indica che l'operazione specificata viene applicata a tutti i tipi di cache, ovvero alla cache delle richieste HTTP, alla cache globale dei pacchetti e alla cache temporanea.
* `http-cache` - Indica che l'operazione specificata viene applicata soltanto alla cache delle richieste HTTP. Gli altri percorsi della cache non sono interessati.
* `global-packages` - Indica che l'operazione specificata viene applicata soltanto alla cache dei pacchetti globale. Gli altri percorsi della cache non sono interessati.
* `temp` - Indica che l'operazione specificata viene applicata soltanto alla cache temporanea. Gli altri percorsi della cache non sono interessati.

## <a name="options"></a>Opzioni

`--force-english-output`

Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.

`-h|--help`

Stampa una breve guida per il comando.

`-c|--clear`

L'opzione "clear" consente di eseguire un'operazione di cancellazione sul tipo di cache specificato. Il contenuto delle directory della cache viene eliminato in modo ricorsivo. L'utente o il gruppo che esegue l'operazione deve disporre delle autorizzazioni per i file presenti nelle directory della cache. In caso contrario, viene visualizzato un messaggio di errore con l'indicazione delle cartelle e/o dei file che non sono stati cancellati.

`-l|--list`

L'opzione "list" viene usata per visualizzare la posizione del tipo di cache specificato.

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