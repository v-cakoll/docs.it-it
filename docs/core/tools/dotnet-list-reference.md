---
title: Comando dotnet list reference
description: Il comando dotnet list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
ms.date: 12/03/2018
ms.openlocfilehash: d22ea27f8e8f6b94d763e44a6d8644f814663797
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169833"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet list reference`: visualizza un elenco dei riferimenti da progetto a progetto.

## <a name="synopsis"></a>Riepilogo

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>Description

Il comando `dotnet list reference` offre un'opzione utile per visualizzare un elenco dei riferimenti al progetto per un progetto o una soluzione specificata.

## <a name="arguments"></a>Argomenti

* **`PROJECT`**

  Specifica il file di progetto da usare per l'elenco dei riferimenti. Se non specificato, il comando cerca un file di progetto nella directory corrente.

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