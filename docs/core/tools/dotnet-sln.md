---
title: Comando dotnet sln
description: Il comando dotnet-sln rappresenta un'opzione comoda per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.
ms.date: 06/13/2018
ms.openlocfilehash: 3f18d6a2851d955d07cecc0cbc4c161cf0ec3e08
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202798"
---
# <a name="dotnet-sln"></a>dotnet sln

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet sln`: consente di modificare un file di soluzione .NET Core.

## <a name="synopsis"></a>Riepilogo

```console
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a>DESCRIZIONE

Il comando `dotnet sln` offre un modo pratico per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.

Per usare il comando `dotnet sln`, il file di soluzione deve essere già esistente. Se è necessario crearne uno, usare il comando [dotnet new](dotnet-new.md), come nell'esempio seguente:

```console
dotnet new sln
```

## <a name="commands"></a>Comandi:

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

Aggiunge uno o più progetti più al file di soluzione. I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei terminali basati su Unix/Linux.

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

Rimuove uno o più progetti dal file di soluzione. I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei terminali basati su Unix/Linux.

`list`

Elenca tutti i progetti in un file di soluzione.

## <a name="arguments"></a>Argomenti

`SOLUTION_NAME`

File di soluzione da usare. Se non specificato, il comando ne cerca uno nella directory corrente. Se sono presenti più file di soluzione nella directory, è necessario specificarne uno.

## <a name="options"></a>Opzioni

`-h|--help`

Stampa una breve guida per il comando.

## <a name="examples"></a>Esempi

Aggiungere un progetto C# a una soluzione:

`dotnet sln todo.sln add todo-app/todo-app.csproj`

Rimuovere un progetto C# da una soluzione:

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

Aggiungere più progetti C# a una soluzione:

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

Rimuovere più progetti C# da una soluzione:

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

Aggiungere più progetti C# a una soluzione usando un criterio GLOB:

`dotnet sln todo.sln add **/*.csproj`

Rimuovere più progetti C# da una soluzione usando un criterio GLOB:

`dotnet sln todo.sln remove **/*.csproj`

> [!NOTE]
> L'utilizzo dei caratteri jolly non è una funzionalità dell'interfaccia della riga di comando, ma piuttosto una funzionalità della shell dei comandi. Per espandere correttamente i file, è necessario usare una shell che supporta l'utilizzo dei caratteri jolly. Per altre informazioni sull'utilizzo dei caratteri jolly, vedere [Wikipedia](https://en.wikipedia.org/wiki/Glob_(programming)).
