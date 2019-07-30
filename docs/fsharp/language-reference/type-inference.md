---
title: Inferenza di tipi
description: Informazioni sul modo F# in cui il compilatore deduce i tipi di valori, variabili, parametri e valori restituiti.
ms.date: 05/16/2016
ms.openlocfilehash: 4b18c1a67a8b7ddadb4fb334ea4736e9fd29feb0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630191"
---
# <a name="type-inference"></a>Inferenza di tipi

In questo argomento viene descritto F# il modo in cui il compilatore deduce i tipi di valori, variabili, parametri e valori restituiti.

## <a name="type-inference-in-general"></a>Inferenza del tipo in generale

Il concetto di inferenza del tipo è che non è necessario specificare i tipi di F# costrutti tranne quando il compilatore non può dedurre definitivamente il tipo. Omettendo le informazioni sul tipo esplicito non significa F# che è un linguaggio tipizzato in modo dinamico o F# che i valori in sono debolmente tipizzati. F#è un linguaggio tipizzato in modo statico, ovvero il compilatore deduce un tipo esatto per ogni costrutto durante la compilazione. Se non sono disponibili informazioni sufficienti per consentire al compilatore di dedurre i tipi di ogni costrutto, è necessario fornire informazioni sui tipi aggiuntive, in genere aggiungendo annotazioni di tipo esplicite in un punto qualsiasi del codice.

## <a name="inference-of-parameter-and-return-types"></a>Inferenza dei tipi Parameter e Return

In un elenco di parametri non è necessario specificare il tipo di ogni parametro. F# È ancora un linguaggio tipizzato in modo statico, pertanto ogni valore ed espressione ha un tipo definito in fase di compilazione. Per i tipi non specificati in modo esplicito, il compilatore deduce il tipo in base al contesto. Se il tipo non è specificato diversamente, viene dedotto come generico. Se il codice usa un valore in modo incoerente, in modo che non esistano singoli tipi dedotti che soddisfino tutti gli usi di un valore, il compilatore segnala un errore.

Il tipo restituito di una funzione è determinato dal tipo dell'ultima espressione nella funzione.

Nel codice seguente, ad `a` esempio, i tipi di `int` parametro e `b` e il tipo restituito sono tutti dedotti perché il valore letterale `100` è di tipo `int`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

È possibile influenzare l'inferenza del tipo modificando i valori letterali. Se si imposta l' `100` oggetto `uint32` accodando il suffisso `u`, i tipi di `a`, `b`e il valore restituito vengono dedotti come `uint32`.

È anche possibile influenzare l'inferenza del tipo usando altri costrutti che implicano restrizioni sul tipo, ad esempio funzioni e metodi che funzionano solo con un determinato tipo.

Inoltre, è possibile applicare annotazioni di tipo esplicito a parametri di funzione o di metodo o a variabili nelle espressioni, come illustrato negli esempi seguenti. Gli errori risultano se si verificano conflitti tra vincoli diversi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

È anche possibile specificare in modo esplicito il valore restituito di una funzione fornendo un'annotazione di tipo dopo tutti i parametri.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

Un caso comune in cui un'annotazione del tipo è utile per un parametro è quando il parametro è un tipo di oggetto e si vuole usare un membro.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a>Generalizzazione automatica

Se il codice della funzione non dipende dal tipo di un parametro, il compilatore considera il parametro come generico. Questa operazione è detta *generalizzazione automatica*e può essere un potente strumento per scrivere codice generico senza aumentare la complessità.

La funzione seguente, ad esempio, combina due parametri di qualsiasi tipo in una tupla.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

Il tipo viene dedotto come

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a>Informazioni aggiuntive

L'inferenza del tipo è descritta più dettagliatamente nella specifica del F# linguaggio.

## <a name="see-also"></a>Vedere anche

- [Generalizzazione automatica](./generics/automatic-generalization.md)
