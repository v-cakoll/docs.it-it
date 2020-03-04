---
title: Operatore sizeof - Riferimenti per C#
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 711005479eea2757b4ef18f6710a4453bfca02f9
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78238833"
---
# <a name="sizeof-operator-c-reference"></a>Operatore sizeof (Riferimenti per C#)

L'operatore `sizeof` restituisce il numero di byte occupati da una variabile di un tipo specificato. L'argomento dell'operatore `sizeof` deve essere il nome di un [tipo non gestito](../builtin-types/unmanaged-types.md) o un parametro di tipo [vincolato](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) a un tipo non gestito.

L'operatore `sizeof` richiede un contesto [unsafe](../keywords/unsafe.md). Tuttavia, per le espressioni presentate nella tabella seguente vengono restituiti i valori costanti corrispondenti in fase di compilazione e non è richiesto un contesto unsafe:

|Expression|Valore costante|
|---------|---------------|
|`sizeof(sbyte)`|1|
|`sizeof(byte)`|1|
|`sizeof(short)`|2|
|`sizeof(ushort)`|2|
|`sizeof(int)`|4|
|`sizeof(uint)`|4|
|`sizeof(long)`|8|
|`sizeof(ulong)`|8|
|`sizeof(char)`|2|
|`sizeof(float)`|4|
|`sizeof(double)`|8|
|`sizeof(decimal)`|16|
|`sizeof(bool)`|1|

Non è inoltre necessario usare un contesto unsafe quando l'operando dell'operatore `sizeof` è il nome di un tipo [enum](../builtin-types/enum.md).

Nell'esempio seguente viene illustrato l'uso dell'operatore `sizeof`:

[!code-csharp[sizeof examples](~/samples/snippets/csharp/language-reference/operators/SizeOfOperator.cs)]

L'operatore `sizeof` restituisce un numero di byte che verrebbero allocati dal Common Language Runtime in managed memory. Per i tipi [struct](../builtin-types/struct.md) questo valore include l'eventuale riempimento, come illustrato nell'esempio precedente. Il risultato dell'operatore `sizeof` può essere diverso da quello del metodo <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, che restituisce le dimensioni di un tipo nella memoria *non gestita*.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatore sizeof](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [Operatori relativi al puntatore](pointer-related-operators.md)
- [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipi correlati alla memoria e agli intervalli](../../../standard/memory-and-spans/index.md)
- [Generics in .NET](../../../standard/generics/index.md)
