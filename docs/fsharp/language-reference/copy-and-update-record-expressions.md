---
title: 'Copia e aggiorna le espressioni del Record (F #)'
description: Informazioni su come scrivere un 'copia e aggiornamento record expression' che consente di copiare un esistente gli aggiornamenti dei record, campi specificati e restituisce il record aggiornato.
keywords: visual f#, f#, programmazione funzionale
author: ChrSteinert
ms.author: phcart
ms.date: 06/04/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b5fc4ef0-64eb-4272-96a7-bb4dffbb634a
ms.openlocfilehash: 2eb51842b678780a1d6da96e237ebb92d1ea5cec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
