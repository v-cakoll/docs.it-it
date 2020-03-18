---
title: Comando dotnet remove reference
description: Il comando dotnet remove reference offre un'opzione utile per rimuovere riferimenti da progetto a progetto.
ms.date: 02/14/2020
ms.openlocfilehash: fcadf677faaf9281fb019c3c4bb16efc906b1aa1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503628"
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive

## <a name="name"></a>Nome

`dotnet remove reference`: rimuove i riferimenti da progetto a progetto.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]
```

## <a name="description"></a>Descrizione

Il comando `dotnet remove reference` offre un'opzione utile per rimuovere i riferimenti al progetto da un progetto.

## <a name="arguments"></a>Argomenti

`PROJECT`

File di progetto di destinazione. Se non specificato, il comando ne cerca uno nella directory corrente.

`PROJECT_REFERENCES`

Riferimenti da progetto a progetto da rimuovere. È possibile specificare uno o più progetti. I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei terminali basati su Unix/Linux.

## <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`-f|--framework <FRAMEWORK>`**

  Rimuove il riferimento solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.

## <a name="examples"></a>Esempi

- Rimuovere un riferimento al progetto dal progetto specificato:

  ```dotnetcli
  dotnet remove app/app.csproj reference lib/lib.csproj
  ```

- Rimuovere più riferimenti al progetto dal progetto nella directory corrente:

  ```dotnetcli
  dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- Rimuovere più riferimenti al progetto usando un criterio GLOB in Unix/Linux:

  ```dotnetcli
  dotnet remove app/app.csproj reference **/*.csproj`
  ```
