---
title: Inferenza del tipo (F#)
description: 'Informazioni su come il compilatore F # deduce i tipi di valori, variabili, parametri e valori restituiti.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2d5fa4b1-732a-4d71-a62d-07f7ee79fe06
ms.openlocfilehash: c23954c0a0828cc7d2aae0553d37d5ee1dfbe152
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="type-inference"></a>Inferenza di tipi

In questo argomento viene descritto come il compilatore F # deduce i tipi di valori, variabili, parametri e valori restituiti.

## <a name="type-inference-in-general"></a>L'inferenza del tipo in generale
L'idea di inferenza del tipo è che non è necessario specificare i tipi di costrutti di F #, ad eccezione di quando il compilatore non non è possibile dedurre il tipo. L'omissione di informazioni di tipo esplicito non significa che F # è un linguaggio tipizzato in modo dinamico o che i valori in F # sono debolmente tipizzata. F # è un linguaggio tipizzato in modo statico, il che significa che il compilatore deduce un tipo esatto di ogni costrutto durante la compilazione. Se non sono informazioni sufficienti per consentire al compilatore di dedurre i tipi di ogni costrutto, è necessario fornire informazioni aggiuntive sul tipo, in genere mediante l'aggiunta di annotazioni di tipo esplicita in un punto nel codice.


## <a name="inference-of-parameter-and-return-types"></a>Inferenza di tipi restituiti e parametri
In un elenco di parametri, non si dispone di specificare il tipo di ogni parametro. Ancora, F # è un linguaggio tipizzato in modo statico e pertanto ogni valore e l'espressione con un tipo definito in fase di compilazione. Per i tipi che non si specifica in modo esplicito, il compilatore deduce il tipo in base al contesto. Se il tipo non è specificata, viene dedotta generico. Se il codice utilizza un valore in modo incoerente, in modo che non è disponibile un unico tipo dedotto che soddisfi tutti gli usi di un valore, che il compilatore segnala un errore.

Il tipo restituito di una funzione è determinato dal tipo dell'ultima espressione nella funzione.

Ad esempio, nel codice seguente, i tipi di parametro `a` e `b` e il tipo restituito sono considerati come `int` perché il valore letterale `100` è di tipo `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

È possibile influenzare l'inferenza del tipo modificando i valori letterali. Se si apportano le `100` un `uint32` aggiungendo il suffisso `u`, i tipi di `a`, `b`, e il valore restituito sono considerati come `uint32`.

È anche possibile influenzare l'inferenza del tipo utilizzando altri costrutti che comportano restrizioni relative al tipo, ad esempio le funzioni e metodi che funzionano con solo un tipo specifico.

Inoltre, è possibile applicare le annotazioni di tipo esplicito per i parametri di funzione o un metodo o per le variabili nelle espressioni, come illustrato negli esempi seguenti. Verificarsi errori se si verificano conflitti tra i diversi vincoli.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

Anche in modo esplicito, è possibile specificare il valore restituito di una funzione, fornendo un'annotazione di tipo dopo che tutti i parametri.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

Un caso comune in cui è utile in un parametro di un'annotazione di tipo è quando il parametro è un tipo di oggetto e si desidera utilizzare un membro.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]
    
## <a name="automatic-generalization"></a>Generalizzazione automatica
Se il codice della funzione non dipende dal tipo di un parametro, il compilatore considera il parametro generico. Si tratta di *generalizzazione automatica*, e può essere molto utile per scrivere codice generico senza aumentare la complessità.

Ad esempio, la funzione seguente combina due parametri di qualsiasi tipo in una tupla.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

Il tipo viene dedotto da

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a>Informazioni aggiuntive
L'inferenza del tipo è descritto in dettaglio nella specifica del linguaggio F #.


## <a name="see-also"></a>Vedere anche
[Generalizzazione automatica](generics/automatic-generalization.md)
