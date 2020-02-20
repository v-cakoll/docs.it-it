---
title: Comando dotnet remove package
description: Il comando dotnet remove package offre un'opzione utile per rimuovere il riferimento del pacchetto NuGet a un progetto.
ms.date: 02/14/2020
ms.openlocfilehash: 8eaa311748c5627351ef149012dc4dddd2ab2793
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503640"
---
# <a name="dotnet-remove-package"></a>dotnet remove package

**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive

## <a name="name"></a>Nome

`dotnet remove package`: rimuove il riferimento al pacchetto da un file di progetto.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]
```

## <a name="description"></a>Descrizione

Il comando `dotnet remove package` offre un'opzione utile per rimuovere un riferimento al pacchetto NuGet da un progetto.

## <a name="arguments"></a>Argomenti

`PROJECT`

Specifica il file di progetto. Se non specificato, il comando ne cerca uno nella directory corrente.

`PACKAGE_NAME`

Riferimento al pacchetto da rimuovere.

## <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una breve guida per il comando.

## <a name="examples"></a>Esempi

- Rimuovere `Newtonsoft.Json` pacchetto NuGet da un progetto nella directory corrente:

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
