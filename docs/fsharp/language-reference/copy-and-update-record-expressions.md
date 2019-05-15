---
title: Copiare e aggiornare espressioni di record
description: Informazioni su come scrivere un 'copia e aggiorna record expression' in cui vengono copiati un esistente gli aggiornamenti dei record, campi specificati e restituisce il record aggiornato.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 7657b0295c9437890baea258295f9e9ab10073dd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645575"
---
# <a name="copy-and-update-record-expressions"></a>Copiare e aggiornare espressioni di record

Oggetto *copiare e aggiornare l'espressione di record* è un'espressione che consente di copiare un record esistente, aggiorna i campi specificati e restituisce il record aggiornato.

## <a name="syntax"></a>Sintassi

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a>Note

I record non sono modificabili per impostazione predefinita, in modo che non sono presenti aggiornamenti per un record esistente possibili. Per creare un record aggiornato tutti i campi di un record dovrà essere specificato nuovamente. Per semplificare questa attività una *copiare e aggiornare l'espressione di record* può essere utilizzato. Questa espressione accetta un record esistente, crea una nuova istanza dello stesso tipo con campi specificati dall'espressione e il campo mancante specificati dall'espressione.
Ciò risulta utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori di campo.

Consideriamo ad esempio un record appena creato.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Se si intende aggiornare solo nel campo del record è possibile usare la *copiare e aggiornare l'espressione di record* analogo al seguente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Vedere anche

- [Record](records.md)
- [Riferimenti per il linguaggio F#](index.md)
