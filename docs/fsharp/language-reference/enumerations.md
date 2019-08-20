---
title: Enumerazioni
description: Informazioni su come usare F# le enumerazioni al posto dei valori letterali per rendere il codice più leggibile e gestibile.
ms.date: 05/16/2016
ms.openlocfilehash: 784cd9612b199e4648bb64432d3b4422ad35f649
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630346"
---
# <a name="enumerations"></a>Enumerazioni

Le enumerazioni, note anchecome enumerazioni, sono tipi integrali in cui le etichette vengono assegnate a un subset di valori. È possibile usarle in sostituzione ai valori letterali per rendere il codice più leggibile e gestibile.

## <a name="syntax"></a>Sintassi

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>Note

Un'enumerazione è simile a un'unione discriminata con valori semplici, ad eccezione del fatto che è possibile specificare i valori. I valori sono in genere numeri interi che iniziano da 0 o 1 oppure numeri interi che rappresentano posizioni di bit. Se un'enumerazione è progettata per rappresentare posizioni di bit, è necessario utilizzare anche l'attributo [Flags](xref:System.FlagsAttribute).

Il tipo sottostante dell'enumerazione è determinato dal valore letterale usato, in modo che, ad esempio, è possibile usare valori letterali con un suffisso, ad `1u`esempio `2u`, e così via, per un tipo di`uint32`Unsigned Integer ().

Quando si fa riferimento ai valori denominati, è necessario usare il nome del tipo di enumerazione stesso come qualificatore, ovvero `enum-name.value1`, non solo `value1`. Questo comportamento è diverso da quello delle unioni discriminate. Questo perché le enumerazioni hanno sempre l'attributo [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) .

Il codice seguente illustra la dichiarazione e l'uso di un'enumerazione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

È possibile convertire facilmente le enumerazioni nel tipo sottostante usando l'operatore appropriato, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

I tipi enumerati possono avere uno dei seguenti tipi sottostanti `sbyte`: `byte` `int16`,, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, e `char`. I tipi di enumerazione sono rappresentati nella .NET Framework come tipi ereditati `System.Enum`da, che a sua volta viene `System.ValueType`ereditato da. Sono pertanto tipi di valore che si trovano nello stack o inline nell'oggetto contenitore e qualsiasi valore del tipo sottostante è un valore valido dell'enumerazione. Questa operazione è significativa quando si verificano criteri di ricerca sui valori di enumerazione, perché è necessario fornire un modello che catturi i valori senza nome.

La `enum` funzione nella F# libreria può essere usata per generare un valore di enumerazione, anche un valore diverso da uno dei valori denominati predefiniti. Usare la `enum` funzione come indicato di seguito.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

La funzione `enum` predefinita funziona con il `int32`tipo. Pertanto, non può essere utilizzato con tipi di enumerazione con altri tipi sottostanti. Usare invece il comando seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

Inoltre, i case per le enumerazioni vengono sempre emessi `public`come. In questo modo si allineano C# con e il resto della piattaforma .NET.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Cast e conversioni](casting-and-conversions.md)
