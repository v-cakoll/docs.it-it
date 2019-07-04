---
title: Comando dotnet list reference
description: Il comando dotnet list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
ms.date: 06/26/2019
ms.openlocfilehash: 1f87ff89997cdaa6d0095a4db9f28a2e7cb7e6a9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67421834"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**Questo argomento si applica a: ✓** .NET Core 2.1.x SDK e versioni successive

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>nome

`dotnet list reference`: visualizza un elenco dei riferimenti da progetto a progetto.

## <a name="synopsis"></a>Riepilogo

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a>DESCRIZIONE

Il comando `dotnet list reference` offre un'opzione utile per visualizzare un elenco dei riferimenti al progetto per un progetto o una soluzione specificata.

## <a name="arguments"></a>Argomenti

* **`PROJECT | SOLUTION`**

  Specifica il file di progetto o di soluzione da usare per l'elenco dei riferimenti. Se non specificato, il comando cerca un file di progetto nella directory corrente.

## <a name="options"></a>Opzioni

* **`-h|--help`**

  Stampa una breve guida per il comando.

## <a name="examples"></a>Esempi

* Visualizzare l'elenco dei riferimenti al progetto per il progetto specificato:

  ```console
  dotnet list app/app.csproj reference
  ```

* Visualizzare l'elenco dei riferimenti al progetto per il progetto nella directory corrente:

  ```console
  dotnet list reference
  ```
