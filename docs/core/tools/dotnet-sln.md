---
title: Comando dotnet sln
description: Il comando dotnet-sln rappresenta un'opzione comoda per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.
ms.date: 02/14/2020
ms.openlocfilehash: b2455c04a46b2a10b8142d8ddc2d8129f2154b27
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543482"
---
# <a name="dotnet-sln"></a>dotnet sln

**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive

## <a name="name"></a>Nome

`dotnet sln`-elenca o modifica i progetti in un file di soluzione .NET Core.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a>Descrizione

Il `dotnet sln` comando rappresenta un modo pratico per elencare e modificare i progetti in un file di soluzione.

Per usare il comando `dotnet sln`, il file di soluzione deve essere già esistente. Se è necessario crearne uno, usare il comando [DotNet New](dotnet-new.md) , come nell'esempio seguente:

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a>Argomenti

- **`SOLUTION_FILE`**

  File di soluzione da utilizzare. Se questo argomento viene omesso, il comando Cerca una directory corrente. Se non viene trovato alcun file di soluzione o più file di soluzione, il comando ha esito negativo.

## <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una descrizione dell'uso del comando.

## <a name="commands"></a>Comandi:

### `list`

Elenca tutti i progetti in un file di soluzione.

#### <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a>Argomenti

- **`SOLUTION_FILE`**

  File di soluzione da utilizzare. Se questo argomento viene omesso, il comando Cerca una directory corrente. Se non viene trovato alcun file di soluzione o più file di soluzione, il comando ha esito negativo.

#### <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una descrizione dell'uso del comando.
  
### `add`

Aggiunge uno o più progetti al file di soluzione.

#### <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a>Argomenti

- **`SOLUTION_FILE`**

  File di soluzione da utilizzare. Se non è specificato, il comando Cerca una directory corrente e non riesce se sono presenti più file di soluzione.

- **`PROJECT_PATH`**

  Percorso del progetto o dei progetti da aggiungere alla soluzione. Le espansioni del [modello glob](https://en.wikipedia.org/wiki/Glob_(programming)) della shell UNIX/Linux vengono elaborate correttamente tramite il comando `dotnet sln`.

#### <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una descrizione dell'uso del comando.

- **`--in-root`**

  Inserisce i progetti nella radice della soluzione, anziché creare una cartella della soluzione. Disponibile a partire da .NET Core 3.0 SDK.

- **`-s|--solution-folder`**

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

  File di soluzione da utilizzare. Se non viene specificato, il comando Cerca una directory corrente e non riesce se sono presenti più file di soluzione.

- **`PROJECT_PATH`**

  Percorso del progetto o dei progetti da aggiungere alla soluzione. Le espansioni del [modello glob](https://en.wikipedia.org/wiki/Glob_(programming)) della shell UNIX/Linux vengono elaborate correttamente tramite il comando `dotnet sln`.

#### <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una descrizione dell'uso del comando.

## <a name="examples"></a>Esempi

- Elencare i progetti in una soluzione:

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

- Aggiungere più C# progetti alla radice di una soluzione:

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

- Aggiungere più C# progetti a una soluzione usando un modello glob (solo UNIX/Linux):

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- Rimuovere più C# progetti da una soluzione usando un modello glob (solo UNIX/Linux):

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```
