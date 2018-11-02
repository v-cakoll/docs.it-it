---
title: Inferenza del tipo (F#)
description: 'Informazioni su come il compilatore F # deduce i tipi di valori, le variabili, parametri e valori restituiti.'
ms.date: 05/16/2016
ms.openlocfilehash: fd826ac48fb9a70aa6f4ff746599c11b7e21a02e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43865696"
---
# <a name="type-inference"></a>Inferenza di tipi

In questo argomento viene descritto come il compilatore F # deduce i tipi di valori, le variabili, parametri e valori restituiti.

## <a name="type-inference-in-general"></a>L'inferenza del tipo in generale

L'idea di inferenza del tipo è che non è necessario specificare i tipi di costrutti F #, ad eccezione di quando il compilatore conseguenze lampanti non è possibile dedurre il tipo. L'omissione di informazioni sui tipi espliciti non significa che F # è un linguaggio tipizzato in modo dinamico o che i valori in F # sono debolmente tipizzata. F # è un linguaggio tipizzato in modo statico, il che significa che il compilatore deduce un tipo esatto di ogni costrutto durante la compilazione. Se non esiste informazioni sufficienti per consentire al compilatore di dedurre i tipi di ogni costrutto, è necessario fornire informazioni aggiuntive sui tipi, in genere mediante l'aggiunta di annotazioni del tipo esplicito in una posizione nel codice.

## <a name="inference-of-parameter-and-return-types"></a>Inferenza di tipi restituiti e parametri

In un elenco di parametri, non è necessario specificare il tipo di ogni parametro. Ancora, F # è un linguaggio tipizzato in modo statico e pertanto ogni valore e l'espressione con un tipo definito in fase di compilazione. Per i tipi che non si specifica in modo esplicito, il compilatore deduce il tipo in base al contesto. Se il tipo non è in caso contrario specificato, si viene dedotto come generici. Se il codice Usa un valore in modo incoerente, in modo che non è disponibile un unico tipo derivato che soddisfi tutti gli usi di un valore, che il compilatore segnala un errore.

Il tipo restituito di una funzione è determinato dal tipo dell'ultima espressione nella funzione.

Ad esempio, nel codice seguente, i tipi di parametro `a` e `b` e il tipo restituito vengono tutti considerati `int` perché il valore letterale `100` JE typu `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

È possibile influenzare l'inferenza del tipo modificando i valori letterali. Se si apportano le `100` una `uint32` aggiungendo il suffisso `u`, i tipi di `a`, `b`, e il valore restituito sono considerati come `uint32`.

È anche possibile influenzare l'inferenza del tipo tramite altri costrutti che implicano le restrizioni sul tipo, ad esempio le funzioni e metodi che funzionano con solo un determinato tipo.

Inoltre, è possibile applicare le annotazioni di tipo espliciti per i parametri di metodo o una funzione o per le variabili nelle espressioni, come illustrato negli esempi seguenti. Se si verificano conflitti tra i diversi vincoli generati errori.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

È possibile specificare il valore restituito di una funzione in modo esplicito fornendo un'annotazione di tipo dopo che tutti i parametri.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

Un caso comune in cui è utile in un parametro di un'annotazione di tipo è quando il parametro è un tipo di oggetto e si vuole usare un membro.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a>Generalizzazione automatica

Se il codice della funzione non dipende dal tipo di un parametro, il compilatore considera il parametro generico. Questa operazione viene definita *generalizzazione automatica*, e può essere molto utile per la scrittura di codice generico senza aumentare la complessità.

Ad esempio, la funzione seguente combina due parametri di qualsiasi tipo in una tupla.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

Il tipo viene dedotto per essere

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a>Informazioni aggiuntive

L'inferenza del tipo è descritto più dettagliatamente nella specifica del linguaggio F #.

## <a name="see-also"></a>Vedere anche

- [Generalizzazione automatica](generics/automatic-generalization.md)
