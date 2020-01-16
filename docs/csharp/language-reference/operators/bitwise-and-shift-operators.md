---
title: Operatori di scorrimento e bit per bit - Riferimenti per C#
description: Di seguito sono descritti gli operatori C# che eseguono operazioni di scorrimento o logiche bit per bit con operandi di tipi integrali.
ms.date: 04/18/2019
author: pkulikov
f1_keywords:
- ~_CSharpKeyword
- <<_CSharpKeyword
- '>>_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise logical operators [C#]
- shift operators [C#]
- tilde operator [C#]
- one's complement operator [C#]
- bitwise complement operator [C#]
- ~ operator [C#]
- left shift operator [C#]
- << operator [C#]
- right shift operator [C#]
- '>> operator [C#]'
- bitwise logical AND operator [C#]
- ampersand operator [C#]
- '& operator [C#]'
- bitwise logical exclusive OR operator [C#]
- bitwise logical XOR operator [C#]
- ^ operator [C#]
- bitwise logical OR operator [C#]
- '| operator [C#]'
ms.openlocfilehash: 4e4dbe085b11751416f69c9fa7f790f18a68f5d7
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964365"
---
# <a name="bitwise-and-shift-operators-c-reference"></a>Operatori di scorrimento e bit per bit (Riferimenti per C#)

Gli operatori seguenti eseguono operazioni di spostamento or bit per bit con operandi dei [tipi numerici integrali](../builtin-types/integral-numeric-types.md) o del tipo [char](../builtin-types/char.md) :

- Operatore unario [`~` (complemento bit per bit)](#bitwise-complement-operator-)
- Operatori di scorrimento binari [`<<` (scorrimento a sinistra)](#left-shift-operator-) e [`>>` (scorrimento a destra)](#right-shift-operator-)
- Operatori binari [`&` (AND logico)](#logical-and-operator-), [`|` (OR logico)](#logical-or-operator-) e [`^` (OR esclusivo logico)](#logical-exclusive-or-operator-)

Questi operatori sono definiti per i tipi `int`, `uint`, `long` e `ulong`. Quando entrambi gli operandi sono di altri tipi integrali (`sbyte`, `byte`, `short`, `ushort` o `char`), i relativi valori vengono convertiti nel tipo `int`, che è anche il tipo di risultato di un'operazione. Quando gli operandi sono di tipi integrali diversi, i relativi valori vengono convertiti nel tipo integrale più vicino. Per altre informazioni, vedere la sezione [Promozioni numeriche](~/_csharplang/spec/expressions.md#numeric-promotions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

Gli operatori `&`, `|`e `^` sono definiti anche per gli operandi del tipo di `bool`. Per altre informazioni, vedere [Operatori logici booleani](boolean-logical-operators.md).

Le operazioni di scorrimento non causano mai overflow e producono gli stessi risultati nei contesti [Checked e Unchecked](../keywords/checked-and-unchecked.md).

## <a name="bitwise-complement-operator-"></a>Operatore di complemento bit per bit ~

L'operatore `~` produce un complemento bit per bit del relativo operando invertendo ogni bit:

[!code-csharp-interactive[bitwise NOT](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseComplement)]

È anche possibile usare il simbolo `~` per dichiarare i finalizzatori. Per altre informazioni, vedere [Finalizzatori](../../programming-guide/classes-and-structs/destructors.md).

## <a name="left-shift-operator-"></a>Operatore di scorrimento a sinistra \<\<

L'operatore `<<` sposta l'operando sinistro a sinistra del [numero di bit definito dall'operando destro](#shift-count-of-the-shift-operators).

L'operazione di scorrimento a sinistra rimuove i bit più significativi che non rientrano nell'intervallo del tipo di risultato e imposta le posizioni dei bit vuoti meno significativi su zero, come illustrato nell'esempio seguente:

[!code-csharp-interactive[left shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShift)]

Poiché gli operatori di scorrimento sono definiti solo per i tipi `int`, `uint`, `long` e `ulong`, il risultato di un'operazione contiene almeno 32 bit. Se l'operando di sinistra e di un tipo integrale diverso (`sbyte`, `byte`, `short`, `ushort` o `char`), il relativo valore viene convertito nel tipo `int`, come illustrato nell'esempio seguente:

[!code-csharp-interactive[left shift with promotion](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShiftPromoted)]

Per informazioni su come l'operando di destra dell'operatore `<<` definisce il conteggio degli scorrimenti, vedere la sezione [Conteggio degli scorrimenti degli operatori di scorrimento](#shift-count-of-the-shift-operators).

## <a name="right-shift-operator-"></a>Operatore di scorrimento a destra >>

L'operatore `>>` sposta l'operando sinistro a destra del [numero di bit definito dall'operando destro](#shift-count-of-the-shift-operators).

L'operazione di scorrimento a destra rimuove i bit meno significativi, come illustrato nell'esempio seguente:

[!code-csharp-interactive[right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#RightShift)]

Le posizioni dei bit vuoti più significativi vengono impostate in base al tipo dell'operando di sinistra come segue:

- Se l'operando sinistro è di tipo `int` o `long`, l'operatore di spostamento a destra esegue un turno *aritmetico* : il valore del bit più significativo (il bit di segno) dell'operando di sinistra viene propagato nelle posizioni di bit vuote di ordine superiore. Vale a dire, le posizioni dei bit vuoti più significativi vengono impostate su zero se l'operando di sinistra è un valore non negativo e impostate su uno se è negativo.

  [!code-csharp-interactive[arithmetic right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ArithmeticRightShift)]

- Se l'operando sinistro è di tipo `uint` o `ulong`, l'operatore di spostamento a destra esegue un spostamento *logico* : le posizioni dei bit vuote di ordine superiore sono sempre impostate su zero.

  [!code-csharp-interactive[logical right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LogicalRightShift)]

Per informazioni su come l'operando di destra dell'operatore `>>` definisce il conteggio degli scorrimenti, vedere la sezione [Conteggio degli scorrimenti degli operatori di scorrimento](#shift-count-of-the-shift-operators).

## <a name="logical-and-operator-"></a> Operatore AND logico &amp;

L'operatore `&` calcola l'AND logico bit per bit dei relativi operandi:

[!code-csharp-interactive[bitwise AND](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseAnd)]

Per `bool` operandi, l'operatore di `&` calcola l'operatore [and logico](boolean-logical-operators.md#logical-and-operator-) degli operandi. L'operatore unario `&` è l'[operatore address-of](pointer-related-operators.md#address-of-operator-).

## <a name="logical-exclusive-or-operator-"></a>Operatore OR esclusivo logico: ^

L'operatore `^` calcola l'OR esclusivo logico bit per bit, chiamato anche XOR logico bit per bit, dei relativi operandi:

[!code-csharp-interactive[bitwise XOR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseXor)]

Per `bool` operandi, l'operatore di `^` calcola l' [OR esclusivo logico](boolean-logical-operators.md#logical-exclusive-or-operator-) degli operandi.

## <a name="logical-or-operator-"></a>Operatore OR logico |

L'operatore `|` calcola l'OR logico bit per bit dei relativi operandi:

[!code-csharp-interactive[bitwise OR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseOr)]

Per `bool` operandi, l'operatore `|` calcola l' [OR logico](boolean-logical-operators.md#logical-or-operator-) degli operandi.

## <a name="compound-assignment"></a>Assegnazione composta

Per un operatore binario `op`, un'espressione di assegnazione composta in formato

```csharp
x op= y
```

equivale a

```csharp
x = x op y
```

con la differenza che `x` viene valutato una sola volta.

L'esempio seguente illustra l'uso dell'assegnazione composta con gli operatori di scorrimento e bit per bit:

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignment)]

In ragione delle [promozioni numeriche](~/_csharplang/spec/expressions.md#numeric-promotions) il risultato dell'operazione `op` potrebbe non essere convertibile in modo implicito nel tipo `T` di `x`. In questo caso, se `op` è un operatore già definito e il risultato dell'operazione è convertibile in modo esplicito nel tipo `T` di `x`, un'espressione di assegnazione composta nel formato `x op= y` equivale a `x = (T)(x op y)`, con la differenza che `x` viene valutato una sola volta. L'esempio seguente illustra questo comportamento:

[!code-csharp-interactive[compound assignment with cast](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignmentWithCast)]

## <a name="operator-precedence"></a>Precedenza tra gli operatori

Nell'elenco seguente gli operatori di scorrimento e bit per bit sono ordinati dalla precedenza più elevata a quella più bassa:

- Operatore di complemento bit per bit `~`
- Operatori di scorrimento `<<` e `>>`
- Operatore AND logico `&`
- Operatore OR esclusivo logico `^`
- Operatore OR logico `|`

Usare le parentesi, `()`, per cambiare l'ordine di valutazione imposto dalla precedenza tra gli operatori:

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#Precedence)]

Per l'elenco completo degli C# operatori ordinati in base al livello di precedenza, vedere la sezione [precedenza](index.md#operator-precedence) degli [ C# operatori](index.md) dell'articolo operatori.

## <a name="shift-count-of-the-shift-operators"></a>Conteggio degli scorrimenti degli operatori di scorrimento

Per gli operatori shift `<<` e `>>`, il tipo dell'operando destro deve essere `int` o un tipo con una [conversione numerica implicita predefinita](../builtin-types/numeric-conversions.md#implicit-numeric-conversions) in `int`.

Per le espressioni `x << count` e `x >> count`, il conteggio effettivo degli scorrimenti varia a seconda del tipo di `x` come segue:

- Se il tipo di `x` è `int` o `uint`, il conteggio dello spostamento viene definito dai *cinque* bit di ordine inferiore dell'operando destro. Vale a dire, il conteggio degli scorrimenti viene calcolato da `count & 0x1F` (o `count & 0b_1_1111`).

- Se il tipo di `x` è `long` o `ulong`, il conteggio dello spostamento viene definito dai *sei* bit di ordine inferiore dell'operando destro. Vale a dire, il conteggio degli scorrimenti viene calcolato da `count & 0x3F` (o `count & 0b_11_1111`).

L'esempio seguente illustra questo comportamento:

[!code-csharp-interactive[shift count example](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ShiftCount)]

> [!NOTE]
> Come illustrato nell'esempio precedente, il risultato di un'operazione di spostamento può essere diverso da zero, anche se il valore dell'operando destro è maggiore del numero di bit nell'operando sinistro.

## <a name="enumeration-logical-operators"></a>Operatori logici di enumerazione

Gli operatori `~`, `&`, `|`e `^` sono supportati anche da qualsiasi tipo di [enumerazione](../builtin-types/enum.md) . Per gli operandi dello stesso tipo di enumerazione, viene eseguita un'operazione logica sui valori corrispondenti del tipo integrale sottostante. Ad esempio, per qualsiasi `x` e `y` di un tipo di enumerazione `T` con un tipo sottostante `U`, l'espressione `x & y` produce lo stesso risultato dell'espressione `(T)((U)x & (U)y)`.

Gli operatori logici bit per bit vengono in genere usati con un tipo di enumerazione definito con l'attributo [Flags](xref:System.FlagsAttribute). Per altre informazioni, vedere la sezione [Tipi di enumerazione come flag di bit](../builtin-types/enum.md#enumeration-types-as-bit-flags) dell'articolo [Tipi di enumerazione](../builtin-types/enum.md).

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente può eseguire l'[overload](operator-overloading.md) degli operatori `~`, `<<`, `>>`, `&`, `|` e `^`. Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione composta corrispondente. Un tipo definito dall'utente non può eseguire in modo esplicito l'overload di un operatore di assegnazione composta.

Se un tipo definito dall'utente `T` esegue l'overload dell'operatore `<<` o `>>`, il tipo dell'operando di sinistra deve essere `T` e il tipo dell'operando di destra deve essere `int`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Operatore di complemento bit per bit](~/_csharplang/spec/expressions.md#bitwise-complement-operator)
- [Operatori shift](~/_csharplang/spec/expressions.md#shift-operators)
- [Operatori logici](~/_csharplang/spec/expressions.md#logical-operators)
- [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment)
- [Promozioni numeriche](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [Operatori logici booleani](boolean-logical-operators.md)
