---
title: Comando dotnet list reference
description: Il comando dotnet list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
ms.date: 06/26/2019
ms.openlocfilehash: 496cbcd8fa4d921e30b363904ad0273bd5ebacd5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733216"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**Questo articolo si applica a:** ✔️ .NET Core 1. x SDK e versioni successive

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>Name

`dotnet list reference`: visualizza un elenco dei riferimenti da progetto a progetto.

## <a name="synopsis"></a>Riepilogo

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a>Descrizione

Il comando `dotnet list reference` offre un'opzione utile per visualizzare un elenco dei riferimenti al progetto per un progetto o una soluzione specificata.

## <a name="arguments"></a>Argomenti

* **`PROJECT | SOLUTION`**

  Specifica il file di progetto o di soluzione da usare per l'elenco dei riferimenti. Se non specificato, il comando cerca un file di progetto nella directory corrente.

## <a name="options"></a>Options

* **`-h|--help`**

  Stampa una breve guida per il comando.

## <a name="examples"></a>Esempi

* Visualizzare l'elenco dei riferimenti al progetto per il progetto specificato:

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* Visualizzare l'elenco dei riferimenti al progetto per il progetto nella directory corrente:

  ```dotnetcli
  dotnet list reference
  ```
