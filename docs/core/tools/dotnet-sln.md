---
title: Comando dotnet sln
description: Il comando dotnet-sln rappresenta un'opzione comoda per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.
ms.date: 10/29/2019
ms.openlocfilehash: c0badfeba1438a795106691a86c09a8b1675829b
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937243"
---
# <a name="dotnet-sln"></a>dotnet sln

**Questo articolo si applica a: ✓** .NET Core 1.x SDK e versioni successive

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>Name

`dotnet sln`: consente di modificare un file di soluzione .NET Core.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a>Descrizione

Il comando `dotnet sln` offre un modo pratico per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.

Per usare il comando `dotnet sln`, il file di soluzione deve essere già esistente. Se è necessario crearne uno, usare il comando [dotnet new](dotnet-new.md), come nell'esempio seguente:

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a>Argomenti

- **`SOLUTION_FILE`**

  File di soluzione da utilizzare. Se non specificato, il comando ne cerca uno nella directory corrente. Se sono presenti più file di soluzione nella directory, è necessario specificarne uno.

## <a name="options"></a>Options

- **`-h|--help`**

  Stampa una breve guida per il comando.

## <a name="commands"></a>Comandi

### `add`

Aggiunge uno o più progetti più al file di soluzione.

#### <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH>
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a>Argomenti

- **`SOLUTION_FILE`**

  File di soluzione da utilizzare. Se non specificato, il comando ne cerca uno nella directory corrente. Se sono presenti più file di soluzione nella directory, è necessario specificarne uno.

- **`PROJECT_PATH`**

  Percorso del progetto da aggiungere alla soluzione. Aggiungere più progetti aggiungendoli uno dopo l'altro separati da spazi. Le espansioni del [modello glob](https://en.wikipedia.org/wiki/Glob_(programming)) della shell UNIX/Linux vengono elaborate correttamente tramite il comando `dotnet sln`.

#### <a name="options"></a>Options

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--in-root`**

  Inserisce i progetti nella radice della soluzione, anziché creare una cartella della soluzione. Disponibile a partire da .NET Core 3.0 SDK.

- **`-s|--solution-folder`**

  Percorso della cartella della soluzione di destinazione a cui aggiungere i progetti. Disponibile a partire da .NET Core 3.0 SDK.

### `remove`

Rimuove uno o più progetti dal file di soluzione.

#### <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH>
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a>Argomenti

- **`SOLUTION_FILE`**

  File di soluzione da utilizzare. Se non specificato, il comando ne cerca uno nella directory corrente. Se sono presenti più file di soluzione nella directory, è necessario specificarne uno.

- **`PROJECT_PATH`**

  Percorso del progetto da rimuovere dalla soluzione. Rimuovere più progetti aggiungendoli uno dopo l'altro separati da spazi. Le espansioni del [modello glob](https://en.wikipedia.org/wiki/Glob_(programming)) della shell UNIX/Linux vengono elaborate correttamente tramite il comando `dotnet sln`.

#### <a name="options"></a>Options

- **`-h|--help`**

  Stampa una breve guida per il comando.

### `list`

Elenca tutti i progetti in un file di soluzione.

#### <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet sln list [-h|--help]
```
  
#### <a name="arguments"></a>Argomenti

- **`SOLUTION_FILE`**

  File di soluzione da utilizzare. Se non specificato, il comando ne cerca uno nella directory corrente. Se sono presenti più file di soluzione nella directory, è necessario specificarne uno.

#### <a name="options"></a>Options

- **`-h|--help`**

  Stampa una breve guida per il comando.

## <a name="examples"></a>Esempi

- Aggiungere un progetto C# a una soluzione:

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj
  ```

- Rimuovere un progetto C# da una soluzione:

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj
  ```

- Aggiungere più progetti C# a una soluzione:

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- Rimuovere più progetti C# da una soluzione:

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- Aggiungere più C# progetti a una soluzione usando un modello glob (solo UNIX/Linux):

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- Rimuovere più C# progetti da una soluzione usando un modello glob (solo UNIX/Linux):

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```
