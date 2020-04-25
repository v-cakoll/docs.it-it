---
title: Comando dotnet remove reference
description: Il comando dotnet remove reference offre un'opzione utile per rimuovere riferimenti da progetto a progetto.
ms.date: 02/14/2020
ms.openlocfilehash: a45153376d7d6eb764c1d2c6b473d04a273a2de1
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158333"
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive

## <a name="name"></a>Nome

`dotnet remove reference`-Rimuove i riferimenti da progetto a progetto (P2P).

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework <FRAMEWORK>]
     <PROJECT_REFERENCES>

dotnet remove reference -h|--help
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

  Rimuove il riferimento solo quando la destinazione è un [Framework](../../standard/frameworks.md) specifico usando il formato TFM.

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
