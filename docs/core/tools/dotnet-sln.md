---
title: Comando dotnet sln
description: Il comando dotnet-sln rappresenta un'opzione comoda per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.
ms.date: 02/14/2020
ms.openlocfilehash: 231287477d986f9ec4a5404cc5278e76c297faa4
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463405"
---
# <a name="dotnet-sln"></a>dotnet sln

**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive

## <a name="name"></a>Nome

`dotnet sln`- Elenca o modifica i progetti in un file di soluzione .NET Core.- Lists or modifies the projects in a .NET Core solution file.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command]

dotnet sln [command] -h|--help
```

## <a name="description"></a>Descrizione

Il `dotnet sln` comando fornisce un modo pratico per elencare e modificare i progetti in un file di soluzione.

Per usare il comando `dotnet sln`, il file di soluzione deve essere già esistente. Se è necessario crearne uno, utilizzare il comando [dotnet new,](dotnet-new.md) come nell'esempio seguente:

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a>Argomenti

- **`SOLUTION_FILE`**

  File di soluzione da utilizzare. Se questo argomento viene omesso, il comando ne cerca uno nella directory corrente. Se non trova alcun file di soluzione o più file di soluzione, il comando ha esito negativo.

## <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una descrizione dell'utilizzo del comando.

## <a name="commands"></a>Comandi:

### `list`

Elenca tutti i progetti in un file di soluzione.

#### <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a>Argomenti

- **`SOLUTION_FILE`**

  File di soluzione da utilizzare. Se questo argomento viene omesso, il comando ne cerca uno nella directory corrente. Se non trova alcun file di soluzione o più file di soluzione, il comando ha esito negativo.

#### <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una descrizione dell'utilizzo del comando.
  
### `add`

Aggiunge uno o più progetti al file di soluzione.

#### <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder <PATH>] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a>Argomenti

- **`SOLUTION_FILE`**

  File di soluzione da utilizzare. Se non è specificato, il comando cerca nella directory corrente uno e ha esito negativo se sono presenti più file di soluzione.

- **`PROJECT_PATH`**

  Percorso del progetto o dei progetti da aggiungere alla soluzione. Le espansioni del [modello di globbing](https://en.wikipedia.org/wiki/Glob_(programming)) `dotnet sln` della shell Unix/Linux vengono elaborate correttamente dal comando.

#### <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una descrizione dell'utilizzo del comando.

- **`--in-root`**

  Inserisce i progetti nella radice della soluzione, anziché creare una cartella della soluzione. Disponibile a partire da .NET Core 3.0 SDK.

- **`-s|--solution-folder <PATH>`**

  Percorso della cartella della soluzione di destinazione a cui aggiungere i progetti. Disponibile a partire da .NET Core 3.0 SDK.

### `remove`

Rimuove uno o più progetti dal file di soluzione.

#### <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a>Argomenti

- **`SOLUTION_FILE`**

  File di soluzione da utilizzare. Se non viene specificato, il comando cerca nella directory corrente uno e ha esito negativo se sono presenti più file di soluzione.

- **`PROJECT_PATH`**

  Percorso del progetto o dei progetti da aggiungere alla soluzione. Le espansioni del [modello di globbing](https://en.wikipedia.org/wiki/Glob_(programming)) `dotnet sln` della shell Unix/Linux vengono elaborate correttamente dal comando.

#### <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una descrizione dell'utilizzo del comando.

## <a name="examples"></a>Esempi

- Elencare i progetti in una soluzione:List the projects in a solution:

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- Aggiungere un progetto C# a una soluzione:

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- Rimuovere un progetto C# da una soluzione:

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- Aggiungere più progetti in linguaggio C, alla radice di una soluzione:Add multiple C ' c' to the root of a solution:

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- Aggiungere più progetti C# a una soluzione:

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- Rimuovere più progetti C# da una soluzione:

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- Aggiungere più progetti in linguaggio C, usando un modello di globbing (solo Unix/Linux):Add multiple C' projects to a solution using a globbing pattern (Unix/Linux only):

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- Aggiungere più progetti in linguaggio C, usando un modello di globbing (solo Windows PowerShell):Add multiple C' projects to a solution using a globbing pattern (Windows PowerShell only):

  ```dotnetcli
  dotnet sln todo.sln add (ls **/*.csproj)
  ```

- Rimuovere più progetti in c'è da una soluzione utilizzando un modello di globbing (solo Unix/Linux):Remove multiple C' projects from a solution using a globbing pattern (Unix/Linux only):

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```

- Rimuovere più progetti in c'è da una soluzione utilizzando un modello globbing (solo Windows PowerShell):

  ```dotnetcli
  dotnet sln todo.sln remove (ls **/*.csproj)
  ```
