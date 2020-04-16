---
title: comando dotnet add reference (comando)add reference
description: Il comando dotnet add reference offre un'opzione utile per aggiungere riferimenti da progetto a progetto.
ms.date: 02/14/2020
ms.openlocfilehash: f2bd67d181784c4858b8971d05053d196df7818e
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463740"
---
# <a name="dotnet-add-reference"></a>dotnet add reference

**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive

## <a name="name"></a>Nome

`dotnet add reference`: aggiunge riferimenti da progetto a progetto.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet add [<PROJECT>] reference [-f|--framework <FRAMEWORK>]
     [--interactive] <PROJECT_REFERENCES>

dotnet add reference -h|--help
```

## <a name="description"></a>Descrizione

Il comando `dotnet add reference` offre un'opzione utile per aggiungere i riferimenti al progetto in un progetto. Dopo l'esecuzione del comando, al file di progetto vengono aggiunti gli elementi `<ProjectReference>`.

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>Argomenti

- **`PROJECT`**

  Specifica il file di progetto. Se non specificato, il comando ne cerca uno nella directory corrente.

- **`PROJECT_REFERENCES`**

  Riferimenti da progetto a progetto da aggiungere. Specificare uno o più progetti. I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei sistemi basati su Unix/Linux.

## <a name="options"></a>Opzioni

- **`-f|--framework <FRAMEWORK>`**

  Aggiunge riferimenti al progetto solo quando si sceglie come destinazione un [framework](../../standard/frameworks.md)specifico.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione). Disponibile a partire da .NET Core 3.0 SDK.

## <a name="examples"></a>Esempi

- Aggiungere un riferimento al progetto:

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- Aggiungere più riferimenti al progetto nella directory corrente:

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- Aggiungere più riferimenti al progetto usando un criterio GLOB in Linux/Unix:

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
