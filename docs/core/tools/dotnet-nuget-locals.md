---
title: Comando dotnet nuget locals
description: Il comando dotnet nuget locals cancella o elenca le risorse NuGet locali, quali cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: b57c127650555e412af08df6656fb62d75c8ed7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734074"
---
# <a name="dotnet-nuget-locals"></a>dotnet nuget locals

**Questo articolo si applica a:** ✔️ .NET Core 1. x SDK e versioni successive

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>Name

`dotnet nuget locals`: cancella o elenca risorse NuGet locali.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a>Descrizione

Il comando `dotnet nuget locals` cancella o elenca risorse NuGet locali presenti nella cache delle richieste HTTP, nella cache temporanea o nella cartella globale dei pacchetti a livello di computer.

## <a name="arguments"></a>Argomenti

* **`CACHE_LOCATION`**

  Il percorso della cache da visualizzare o cancellare. Il valore può essere uno dei seguenti:

  * `all` - Indica che l'operazione specificata viene applicata a tutti i tipi di cache, ovvero alla cache delle richieste HTTP, alla cache globale dei pacchetti e alla cache temporanea.
  * `http-cache` - Indica che l'operazione specificata viene applicata soltanto alla cache delle richieste HTTP. Gli altri percorsi della cache non sono interessati.
  * `global-packages` - Indica che l'operazione specificata viene applicata soltanto alla cache dei pacchetti globale. Gli altri percorsi della cache non sono interessati.
  * `temp` - Indica che l'operazione specificata viene applicata soltanto alla cache temporanea. Gli altri percorsi della cache non sono interessati.

## <a name="options"></a>Options

* **`--force-english-output`**

  Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.

* **`-h|--help`**

  Stampa una breve guida per il comando.

* **`-c|--clear`**

  L'opzione "clear" consente di eseguire un'operazione di cancellazione sul tipo di cache specificato. Il contenuto delle directory della cache viene eliminato in modo ricorsivo. L'utente o il gruppo che esegue l'operazione deve disporre delle autorizzazioni per i file presenti nelle directory della cache. In caso contrario, viene visualizzato un messaggio di errore con l'indicazione delle cartelle e/o dei file che non sono stati cancellati.

* **`-l|--list`**

  L'opzione "list" viene usata per visualizzare la posizione del tipo di cache specificato.

## <a name="examples"></a>Esempi

* Visualizza i percorsi di tutte le directory locali della cache, ovvero directory della cache HTTP, directory della cache globale dei pacchetti e directory della cache temporanea:

  ```dotnetcli
  dotnet nuget locals all –l
  ```

* Visualizza il percorso della directory locale della cache HTTP:

  ```dotnetcli
  dotnet nuget locals http-cache --list
  ```

* Cancella tutti i file da tutte le directory locali della cache, ovvero directory della cache HTTP, directory della cache globale dei pacchetti e directory della cache temporanea:

  ```dotnetcli
  dotnet nuget locals all --clear
  ```

* Cancella tutti i file presenti nella directory locale della cache globale dei pacchetti:

  ```dotnetcli
  dotnet nuget locals global-packages -c
  ```

* Cancella tutti i file presenti nella directory locale della cache temporanea:

  ```dotnetcli
  dotnet nuget locals temp -c
  ```

## <a name="troubleshooting"></a>Risoluzione dei problemi

Per informazioni su problemi ed errori comuni relativi all'uso del comando `dotnet nuget locals`, vedere [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache) (Gestione della cache NuGet).
