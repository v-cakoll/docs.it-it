---
title: Enumerazioni (F#)
description: Informazioni su come utilizzare F# enumerazioni anziché valori letterali per rendere il codice più leggibile e gestibile.
ms.date: 05/16/2016
ms.openlocfilehash: 47fb353c2698f8b1474834ebbd1b0eff2c7f76e7
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "46003165"
---
# <a name="enumerations"></a>Enumerazioni

*Le enumerazioni*, noto anche come *enumerazioni*, sono tipi integrali, in cui le etichette vengono assegnate a un sottoinsieme dei valori. È possibile usarle in sostituzione ai valori letterali per rendere il codice più leggibile e gestibile.

## <a name="syntax"></a>Sintassi

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>Note

Un'enumerazione sembra molto simile a un'unione discriminata che dispone di valori semplici, ad eccezione del fatto che i valori possono essere specificati. In genere, i valori sono numeri interi che iniziano da 0 o 1, o numeri interi che rappresentano posizioni di bit. Se un'enumerazione deve rappresentare posizioni dei bit, è anche consigliabile usare la [flag](xref:System.FlagsAttribute) attributo.

Il tipo sottostante dell'enumerazione è determinato dal valore letterale che viene usato, in modo che, ad esempio, è possibile usare valori letterali con un suffisso, ad esempio `1u`, `2u`e così via, per un intero senza segno (`uint32`) tipo.

Quando si fa riferimento ai valori denominati, è necessario usare il nome del tipo di enumerazione se stesso come un qualificatore, vale a dire `enum-name.value1`e non semplicemente `value1`. Questo comportamento è diverso da quello delle unioni discriminate. Questo avviene perché le enumerazioni avere sempre la [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attributo.

Il codice seguente illustra la dichiarazione e l'uso di un'enumerazione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

È possibile convertire facilmente enumerazioni per il tipo sottostante utilizzando l'operatore appropriato, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

I tipi enumerati possono avere uno dei seguenti tipi sottostanti: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, e `char`. I tipi di enumerazione sono rappresentati in .NET Framework come tipi dalla quale vengono ereditati `System.Enum`, che a sua volta viene ereditata dalla `System.ValueType`. In questo modo, si tratta di tipi di valore che si trovano nello stack o inline nell'oggetto che contiene e qualsiasi valore del tipo sottostante è un valore valido dell'enumerazione. Ciò è importante quando i valori di criteri di ricerca su enumerazione, in quanto è necessario specificare un modello che memorizza nella cache i valori senza nome.

Il `enum` funzione nella libreria di F# può essere utilizzata per generare un valore di enumerazione, anche un valore diverso da quello dell'oggetto predefinito, valori denominati. Si utilizza il `enum` funzione come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

Il valore predefinito `enum` funzionamento della funzione con tipo `int32`. Pertanto, non è utilizzabile con i tipi di enumerazione con altri tipi sottostante. In alternativa, usare quanto segue.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

I casi, inoltre, per le enumerazioni vengono sempre generate come `public`. Si tratta in modo da poter essere allineate con c# e il resto della piattaforma .NET.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Cast e conversioni](casting-and-conversions.md)
