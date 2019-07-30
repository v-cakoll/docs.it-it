---
title: Tipi flessibili
description: Informazioni su come usare F# l'annotazione di tipo flessibile, che indica che un parametro, una variabile o un valore ha un tipo compatibile con un tipo specificato.
ms.date: 05/16/2016
ms.openlocfilehash: 43caa6cd35630df648beda5cc43cffae2ecd6f6a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630258"
---
# <a name="flexible-types"></a>Tipi flessibili

Un'annotazione di *tipo flessibile* indica che un parametro, una variabile o un valore ha un tipo compatibile con un tipo specificato, in cui la compatibilità è determinata dalla posizione in una gerarchia orientata a oggetti di classi o interfacce. I tipi flessibili sono utili in particolare quando la conversione automatica a tipi di livello superiore nella gerarchia dei tipi non si verifica, ma si desidera comunque abilitare la funzionalità per l'utilizzo di qualsiasi tipo nella gerarchia o di qualsiasi tipo che implementa un'interfaccia.

## <a name="syntax"></a>Sintassi

```fsharp
#type
```

## <a name="remarks"></a>Note

Nella sintassi precedente, *Type* rappresenta un tipo di base o un'interfaccia.

Un tipo flessibile è equivalente a un tipo generico con un vincolo che limita i tipi consentiti ai tipi compatibili con il tipo di interfaccia o di base. Ovvero le due righe di codice seguenti sono equivalenti.

```fsharp
#SomeType

'T when 'T :> SomeType
```

I tipi flessibili sono utili in diversi tipi di situazioni. Ad esempio, quando si dispone di una funzione di ordine superiore (una funzione che accetta una funzione come argomento), spesso è utile che la funzione restituisca un tipo flessibile. Nell'esempio seguente, l'uso di un tipo flessibile con un argomento Sequence in `iterate2` consente alla funzione di ordine superiore di funzionare con le funzioni che generano sequenze, matrici, elenchi e qualsiasi altro tipo enumerabile.

Si considerino le due funzioni seguenti, una delle quali restituisce una sequenza, l'altra delle quali restituisce un tipo flessibile.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

Per un altro esempio, si consideri la funzione della libreria [Seq. Concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) :

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

È possibile passare una qualsiasi delle sequenze enumerabili seguenti a questa funzione:

- Elenco di elenchi
- Elenco di matrici
- Matrice di elenchi
- Una matrice di sequenze
- Qualsiasi altra combinazione di sequenze enumerabili

Il codice seguente usa `Seq.concat` per illustrare gli scenari che è possibile supportare con i tipi flessibili.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

L'output è indicato di seguito.

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

In F#, come in altri linguaggi orientati a oggetti, esistono contesti in cui i tipi derivati o i tipi che implementano le interfacce vengono convertiti automaticamente in un tipo di base o di interfaccia. Queste conversioni automatiche si verificano negli argomenti diretti, ma non quando il tipo si trova in una posizione subordinata, come parte di un tipo più complesso, ad esempio un tipo restituito di un tipo di funzione, o come argomento di tipo. Pertanto, la notazione flessibile del tipo è particolarmente utile quando il tipo a cui si sta applicando fa parte di un tipo più complesso.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Generics](./generics/index.md)
