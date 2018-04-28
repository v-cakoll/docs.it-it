---
title: Enumerazioni (F#)
description: 'Informazioni su come utilizzare le enumerazioni di F # al posto di valori letterali per rendere il codice più leggibile e conservabile.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4b1a61fb69403f826733893667e55991d39867c6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="enumerations"></a>Enumerazioni

*Le enumerazioni*, noto anche come *enumerazioni*, sono tipi integrali in cui le etichette vengono assegnate a un sottoinsieme dei valori. È possibile usarle in sostituzione ai valori letterali per rendere il codice più leggibile e gestibile.


## <a name="syntax"></a>Sintassi

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>Note
Un'enumerazione è molto simile a un'unione discriminata che dispone di valori semplici, ad eccezione del fatto che i valori possono essere specificati. In genere, i valori sono valori interi che iniziano da 0 o 1, o numeri interi che rappresentano posizioni dei bit. Se un'enumerazione è progettata per rappresentare le posizioni di bit, è necessario utilizzare anche il [flag](xref:System.FlagsAttribute) attributo.

Il tipo sottostante dell'enumerazione è determinato dal valore letterale che viene utilizzato, in modo che, ad esempio, è possibile utilizzare valori letterali con un suffisso, ad esempio `1u`, `2u`e così via, per un intero senza segno (`uint32`) tipo.

Quando si fa riferimento ai valori denominati, è necessario utilizzare il nome del tipo di enumerazione stesso come un qualificatore, vale a dire `enum-name.value1`, non solo `value1`. Questo comportamento è diverso da quello delle unioni discriminate. Infatti, le enumerazioni dispongono sempre di [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attributo.

Il codice seguente illustra la dichiarazione e utilizzo di un'enumerazione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

È possibile convertire facilmente enumerazioni per il tipo sottostante utilizzando l'operatore appropriato, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

Tipi enumerati possono avere uno dei seguenti tipi sottostanti: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, e `char`. Tipi di enumerazione sono rappresentati in .NET Framework come tipi ereditati da `System.Enum`, che a sua volta viene ereditata dalla `System.ValueType`. Di conseguenza, sono tipi di valore che si trovano nello stack o inline nell'oggetto contenitore e qualsiasi valore del tipo sottostante è un valore valido dell'enumerazione. Questo è importante quando i valori di criteri di ricerca in una enumerazione, in quanto è necessario specificare un modello che memorizza nella cache i valori senza nome.

Il `enum` funzione nella libreria F # può essere utilizzata per generare un valore di enumerazione, anche un valore diverso da uno degli operatori, valori denominati. Utilizzare il `enum` funzione come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

Il valore predefinito `enum` funzione funziona con tipo `int32`. Non può pertanto essere utilizzato con tipi di enumerazione che dispongono di altri tipi sottostanti. Utilizzare invece le operazioni seguenti.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]
    
## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Cast e conversioni](casting-and-conversions.md)
