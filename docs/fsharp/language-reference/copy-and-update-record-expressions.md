---
title: Copiare e aggiornare espressioni di record
description: Informazioni su come scrivere un 'copia e aggiorna expression' in cui vengono copiati un record esistente o record anonimi, gli aggiornamenti specificati campi e restituisce il record aggiornato o anonimo.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: d16f5ca337047ab2eecc8828b21d8a423bf39a1f
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041736"
---
# <a name="copy-and-update-record-expressions"></a>Copiare e aggiornare espressioni di record

Oggetto *copiare e aggiornare l'espressione di record* è un'espressione che consente di copiare un record esistente, aggiorna i campi specificati e restituisce il record aggiornato.

## <a name="syntax"></a>Sintassi

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a>Note

I record e record anonimi non sono modificabili per impostazione predefinita, in modo che non sono presenti aggiornamenti per un record esistente possibili. Per creare un record aggiornato tutti i campi di un record dovrà essere specificato nuovamente. Per semplificare questa attività una *copiare e aggiornare espressioni* può essere utilizzato. Questa espressione accetta un record esistente, crea una nuova istanza dello stesso tipo con campi specificati dall'espressione e il campo mancante specificati dall'espressione.

Ciò risulta utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori di campo.

Consideriamo ad esempio un record appena creato.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Se si intende aggiornare solo nel campo del record è possibile usare la *copiare e aggiornare l'espressione di record* analogo al seguente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Vedere anche

- [Record](records.md)
- [Record anonimi](anonymous-records.md)
- [Riferimenti per il linguaggio F#](index.md)
