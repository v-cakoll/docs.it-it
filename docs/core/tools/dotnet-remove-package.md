---
title: Comando dotnet remove package
description: Il comando dotnet remove package offre un'opzione utile per rimuovere il riferimento del pacchetto NuGet a un progetto.
ms.date: 02/14/2020
ms.openlocfilehash: fc74ac1364a0ed027b83dab270d382f238dc00e5
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463448"
---
# <a name="dotnet-remove-package"></a>dotnet remove package

**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive

## <a name="name"></a>Nome

`dotnet remove package`: rimuove il riferimento al pacchetto da un file di progetto.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME>

dotnet remove package -h|--help
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

- Rimuovere `Newtonsoft.Json` il pacchetto NuGet da un progetto nella directory corrente:Remove NuGet package from a project in the current directory:

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
