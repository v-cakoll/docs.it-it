---
title: Tipi flessibili (F#)
description: 'Informazioni su come utilizzare F # annotazione di tipo flessibile, che indica che un parametro, una variabile o un valore è un tipo compatibile con un tipo specificato.'
ms.date: 05/16/2016
ms.openlocfilehash: b6c97c3cc19f15b2c8db74b2c55660a16b2858f7
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44698471"
---
# <a name="flexible-types"></a>Tipi flessibili

Oggetto *annotazione di tipo flessibile* indica che un parametro, una variabile o un valore ha un tipo compatibile con il tipo specificato, in cui compatibilità viene determinata dalla posizione in una gerarchia orientata agli oggetti di classi o interfacce. Tipi flessibili sono utili soprattutto quando non si verifica la conversione automatica a tipi di livello superiori nella gerarchia dei tipi, ma si desidera abilitare la funzionalità lavorare con qualsiasi tipo nella gerarchia o qualsiasi tipo che implementa un'interfaccia.

## <a name="syntax"></a>Sintassi

```fsharp
#type
```

## <a name="remarks"></a>Note

Nella sintassi precedente *tipo* rappresenta un'interfaccia o un tipo di base.

Un tipo flessibile è equivalente a un tipo generico che ha un vincolo che limita i tipi consentiti in tipi compatibili con il tipo di base o interfaccia. Vale a dire, le due righe di codice seguenti sono equivalenti.

```fsharp
#SomeType

'T when 'T :> SomeType
```

Tipi flessibili sono utili in diversi tipi di situazioni. Ad esempio, quando si dispone di una funzione di ordine superiore (una funzione che accetta una funzione come argomento), è spesso utile avere la funzione restituisce un tipo flessibile. Nell'esempio seguente, l'uso di un tipo flessibile con un argomento di sequenza in `iterate2` consente alla funzione di ordine superiore lavorare con le funzioni che generano le sequenze, matrici, elenchi e qualsiasi altro tipo enumerabile.

Prendere in considerazione le seguenti due funzioni, uno dei quali restituisce una sequenza, l'altro restituisce un tipo flessibile.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

Come ulteriore esempio, prendere in considerazione la [Seq. Concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) funzione della libreria:

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

È possibile passare una delle seguenti sequenze enumerabili a questa funzione:

- Un elenco di elenchi
- Un elenco di matrici
- Una matrice di elenchi
- Matrice di sequenze
- Qualsiasi altra combinazione di sequenze enumerabili

Il codice seguente usa `Seq.concat` per illustrare gli scenari che è possibile supportare usando tipi flessibili.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

L'output è indicato di seguito.

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

In F #, come in altri linguaggi orientati, vi sono contesti in cui i tipi che implementano interfacce o tipi derivati vengono convertiti automaticamente a un tipo di interfaccia o un tipo di base. Negli argomenti diretti, ma non quando il tipo è in una posizione subordinata, come parte di un tipo più complesso, ad esempio un tipo restituito di un tipo di funzione o come argomento di tipo, si verificano queste conversioni automatiche. Di conseguenza, la notazione di tipo flessibile risulta particolarmente utile quando il tipo a che si applica fa parte di un tipo più complesso.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Generics](generics/index.md)
