---
title: Copiare e aggiornare espressioni di record
description: Informazioni su come scrivere un'espressione di copia e aggiornamento che copia un record esistente o un record Anonimo, aggiorna i campi specificati e restituisce il record aggiornato o il record anonimo.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: dfb20a6ff8282ae5988772cc0f0841db23aad942
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630383"
---
# <a name="copy-and-update-record-expressions"></a>Copiare e aggiornare espressioni di record

Un' *espressione di record di copia e aggiornamento* è un'espressione che copia un record esistente, aggiorna i campi specificati e restituisce il record aggiornato.

## <a name="syntax"></a>Sintassi

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a>Note

I record e i record anonimi non sono modificabili per impostazione predefinita, pertanto non è possibile eseguire l'aggiornamento a un record esistente. Per creare un record aggiornato, è necessario specificare nuovamente tutti i campi di un record. Per semplificare questa attività, è possibile utilizzare un' *espressione di copia e aggiornamento* . Questa espressione accetta un record esistente, ne crea uno nuovo dello stesso tipo usando i campi specificati dall'espressione e il campo mancante specificato dall'espressione.

Questa operazione può essere utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori di campo.

Prendere ad esempio un record appena creato.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Se si desidera eseguire l'aggiornamento solo sul campo di tale record, è possibile utilizzare l' *espressione di copia e aggiornamento del record* come la seguente:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Vedere anche

- [Record](records.md)
- [Record anonimi](anonymous-records.md)
- [Riferimenti per il linguaggio F#](index.md)
