---
title: 'Copia e aggiorna le espressioni del Record (F #)'
description: Informazioni su come scrivere un 'copia e aggiornamento record expression' che consente di copiare un esistente gli aggiornamenti dei record, campi specificati e restituisce il record aggiornato.
author: ChrSteinert
ms.author: phcart
ms.date: 06/04/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 98a515b5f053e9339588157185848e8315a580f4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="copy-and-update-record-expressions"></a>Copiare e aggiornare espressioni di record

Oggetto *espressione record copia e aggiornamento* è un'espressione che consente di copiare un record esistente, aggiorna i campi specificati e restituisce il record aggiornato.


## <a name="syntax"></a>Sintassi

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a>Note
Record non sono modificabili per impostazione predefinita, in modo che non sia possibile alcun aggiornamento a un record esistente. Per creare un record aggiornato tutti i campi di un record dovranno essere specificato nuovamente. Per semplificare questa attività una *espressione record copia e aggiornamento* può essere utilizzato. Questa espressione accetta un record esistente, crea una nuova istanza dello stesso tipo con campi specificati dall'espressione e il campo mancante specificati dall'espressione.
Può essere utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori dei campi.

Prendere ad esempio un record appena creato.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Se si esegue l'aggiornamento solo su campo di tale record è possibile utilizzare il *espressione record copia e aggiornamento* simile alla seguente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Vedere anche
[Record](records.md)

[Riferimenti per il linguaggio F#](index.md)
