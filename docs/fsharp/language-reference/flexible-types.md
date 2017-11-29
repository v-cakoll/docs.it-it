---
title: Tipi flessibili (F#)
description: "Informazioni sull'utilizzo di F # annotazione di tipo flessibile, che indica che un parametro, una variabile o un valore è un tipo compatibile con un tipo specificato."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c8b510f2-3405-4cc9-b55b-e47b35e2b15b
ms.openlocfilehash: 7c5e4eb97791b9c6c56fe2847755866e8240e038
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2017
---
# <a name="flexible-types"></a>Tipi flessibili

Oggetto *annotazione di tipo flessibile* indica che un parametro, una variabile o un valore è un tipo che è compatibile con un tipo specificato, in cui viene determinata la compatibilità in base alla posizione in una gerarchia orientata agli oggetti di classi o interfacce. Tipi flessibili sono utili in particolare quando non si verifica la conversione automatica per i tipi di livello superiori nella gerarchia dei tipi, ma si desidera abilitare l'utilizzo con qualsiasi tipo nella gerarchia o qualsiasi tipo che implementa un'interfaccia della funzionalità.

## <a name="syntax"></a>Sintassi

```fsharp
#type
```

## <a name="remarks"></a>Note

Nella sintassi precedente, *tipo* rappresenta un'interfaccia o un tipo di base.

Un tipo flessibile è equivalente a un tipo generico che ha un vincolo che limita i tipi consentiti in tipi compatibili con il tipo di base o interfaccia. Vale a dire le due righe di codice seguenti sono equivalenti.

```fsharp
#SomeType

'T when 'T :> SomeType
```

Tipi flessibili sono utili in situazioni diverse. Ad esempio, quando si dispone di una funzione di ordine superiore (una funzione che accetta una funzione come argomento), è spesso utile avere la funzione restituisca un tipo flessibile. Nell'esempio seguente, l'utilizzo di un tipo flessibile con un argomento di sequenza in `iterate2` consente alla funzione di ordine superiore lavorare con le funzioni che generano le sequenze, matrici, elenchi e qualsiasi altro tipo enumerabile.

Prendere in considerazione le seguenti due funzioni, uno di cui viene restituita una sequenza, l'altro che restituisce un tipo flessibile.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

Un altro esempio, considerare il [SEQ](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) funzione della libreria:

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

È possibile passare una delle seguenti sequenze di enumerabile a questa funzione:

- Un elenco di elenchi
- Un elenco di matrici
- Matrice di elenchi
- Matrice di sequenze
- Qualsiasi altra combinazione di sequenze enumerabili

Il codice seguente usa `Seq.concat` per illustrare gli scenari in grado di supportare utilizzando tipi flessibili.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

L'output è indicato di seguito.

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

In F #, come in altri linguaggi orientati, vi sono contesti in cui i tipi derivati o tipi che implementano le interfacce vengono convertiti automaticamente in un tipo di base o un tipo di interfaccia. Negli argomenti diretti, ma non quando il tipo è in una posizione subordinata, come parte di un tipo più complesso, ad esempio un tipo restituito di un tipo di funzione o come argomento di tipo, si verificano queste conversioni automatico. Di conseguenza, la notazione di tipo flessibile è particolarmente utile quando il tipo a che si applica fa parte di un tipo più complesso.

## <a name="see-also"></a>Vedere anche

[Riferimenti per il linguaggio F#](index.md)

[Generics](generics/index.md)
