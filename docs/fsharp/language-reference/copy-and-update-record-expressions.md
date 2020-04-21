---
title: Copiare e aggiornare espressioni di record
description: Informazioni su come scrivere un'espressione di copia e aggiornamento che copia un record esistente o anonimo, aggiorna i campi specificati e restituisce il record aggiornato o anonimo.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: bec3e0ac2fb34e358b199c509c4599b55d7bf35e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739282"
---
# <a name="copy-and-update-record-expressions"></a>Copiare e aggiornare espressioni di record

Un'espressione di record di *copia e aggiornamento* è un'espressione che copia un record esistente, aggiorna i campi specificati e restituisce il record aggiornato.

## <a name="syntax"></a>Sintassi

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a>Osservazioni

I record e i record anonimi non sono modificabili per impostazione predefinita, pertanto non è possibile aggiornare un record esistente. Per creare un record aggiornato, è necessario specificare nuovamente tutti i campi di un record. Per semplificare questa attività è possibile utilizzare *un'espressione* di copia e aggiornamento. Questa espressione accetta un record esistente, ne crea uno nuovo dello stesso tipo utilizzando i campi specificati dall'espressione e il campo mancante specificato dall'espressione.

Ciò può essere utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni valori dei campi.

Si crei, ad esempio, un record appena creato.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Per aggiornare solo due campi in tale record è possibile utilizzare l'espressione di *copia e aggiornamento del record:*

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Vedere anche

- [Record](records.md)
- [Record anonimi](anonymous-records.md)
- [Guida di riferimento al linguaggio F](index.md)
