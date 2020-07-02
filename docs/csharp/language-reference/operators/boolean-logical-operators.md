---
title: Operatori logici booleani - Riferimenti per C#
description: Informazioni sugli operatori C# che eseguono operazioni logiche di negazione, congiunzione (AND) e disgiunzione inclusiva ed esclusiva (OR) con operandi booleani.
ms.date: 06/29/2020
author: pkulikov
f1_keywords:
- '!_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- '&&_CSharpKeyword'
- '||_CSharpKeyword'
helpviewer_keywords:
- logical operators [C#]
- short-circuiting operators [C#]
- logical negation operator [C#]
- NOT operator [C#]
- '! operator [C#]'
- AND operator [C#]
- ampersand operator [C#]
- conjunction operator [C#]
- '& operator [C#]'
- exclusive OR operator [C#]
- XOR operator [C#]
- ^ operator [C#]
- OR operator [C#]
- disjunction operator [C#]
- '| operator [C#]'
- conditional AND operator [C#]
- short-circuiting AND operator [C#]
- '&& operator [C#]'
- conditional OR operator [C#]
- short-circuiting OR operator [C#]
- '|| operator [C#]'
ms.openlocfilehash: a19c804c624153ef608885bc6493537302275765
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618194"
---
# <a name="boolean-logical-operators-c-reference"></a>Operatori logici booleani (Riferimenti per C#)

Gli operatori seguenti eseguono operazioni logiche con operandi [bool](../builtin-types/bool.md) :

- Operatore unario [ `!` (negazione logica)](#logical-negation-operator-) .
- Operatori di tipo binario [ `&` (and logico)](#logical-and-operator-), [ `|` (OR logico)](#logical-or-operator-)e [ `^` (OR esclusivo logico)](#logical-exclusive-or-operator-) . Questi operatori valutano sempre entrambi gli operandi.
- Operatori binari [ `&&` (and logico condizionale)](#conditional-logical-and-operator-) e [ `||` (OR logico condizionale)](#conditional-logical-or-operator-) . Questi operatori valutano l'operando di destra solo se è necessario.

Per gli operandi dei [tipi numerici integrali](../builtin-types/integral-numeric-types.md), gli `&` `|` operatori, e `^` eseguono operazioni logiche bit per bit. Per altre informazioni, vedere [Operatori di scorrimento e bit per bit](bitwise-and-shift-operators.md).

## <a name="logical-negation-operator-"></a>Operatore di negazione logica !

L'operatore di prefisso unario `!` Calcola la negazione logica del relativo operando. Vale a dire, produce `true` se l'operando restituisce `false` e `false` se l'operando restituisce `true`:

[!code-csharp-interactive[logical negation](snippets/BooleanLogicalOperators.cs#Negation)]

A partire da C# 8,0, l'operatore unario di suffisso `!` è l' [operatore che perdona i valori null](null-forgiving.md).

## <a name="logical-and-operator-amp"></a><a name="logical-and-operator-"></a>Operatore AND logico&amp;

L'operatore `&` calcola l'AND logico dei relativi operandi. Il risultato di `x & y` è `true` se `x` e `y` restituiscono `true`. In caso contrario, il risultato è `false`.

L' `&` operatore valuta entrambi gli operandi anche se l'operando sinistro restituisce `false` , in modo che il risultato dell'operazione sia `false` indipendentemente dal valore dell'operando destro.

Nell'esempio seguente l'operando di destra dell'operatore `&` è una chiamata a un metodo, che viene eseguita indipendentemente dal valore dell'operando di sinistra:

[!code-csharp-interactive[logical AND](snippets/BooleanLogicalOperators.cs#And)]

L'[operatore AND condizionale logico](#conditional-logical-and-operator-) `&&` calcola anche l'AND logico dei relativi operandi, ma non valuta l'operando di destra se l'operando di sinistra restituisce `false`.

Per gli operandi dei [tipi numerici integrali](../builtin-types/integral-numeric-types.md), l' `&` operatore calcola l' [and logico bit per bit](bitwise-and-shift-operators.md#logical-and-operator-) dei relativi operandi. L'operatore unario `&` è l'[operatore address-of](pointer-related-operators.md#address-of-operator-).

## <a name="logical-exclusive-or-operator-"></a>Operatore OR esclusivo logico: ^

L'operatore `^` calcola l'OR esclusivo logico, noto anche come XOR logico, dei relativi operandi. Il risultato di `x ^ y` è `true` se `x` restituisce `true` e `y` restituisce `false` oppure `x` restituisce `false` e `y` restituisce `true`. In caso contrario, il risultato è `false`. Vale a dire, per gli operandi `bool`, l'operatore `^` calcola lo stesso risultato dell'[operatore di disuguaglianza](equality-operators.md#inequality-operator-) `!=`.

[!code-csharp-interactive[logical exclusive OR](snippets/BooleanLogicalOperators.cs#Xor)]

Per gli operandi dei [tipi numerici integrali](../builtin-types/integral-numeric-types.md), l' `^` operatore calcola l' [OR esclusivo logico bit per bit](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) dei relativi operandi.

## <a name="logical-or-operator-"></a>Operatore OR logico |

L'operatore `|` calcola l'OR logico dei relativi operandi. Il risultato di `x | y` è `true` se `x` o `y` restituisce `true`. In caso contrario, il risultato è `false`.

L' `|` operatore valuta entrambi gli operandi anche se l'operando sinistro restituisce `true` , in modo che il risultato dell'operazione sia `true` indipendentemente dal valore dell'operando destro.

Nell'esempio seguente l'operando di destra dell'operatore `|` è una chiamata a un metodo, che viene eseguita indipendentemente dal valore dell'operando di sinistra:

[!code-csharp-interactive[logical OR](snippets/BooleanLogicalOperators.cs#Or)]

L'[operatore OR condizionale logico](#conditional-logical-or-operator-) `||` calcola anche l'OR logico dei relativi operandi, ma non valuta l'operando di destra se l'operando di sinistra restituisce `true`.

Per gli operandi dei [tipi numerici integrali](../builtin-types/integral-numeric-types.md), l' `|` operatore calcola l' [OR logico bit per bit](bitwise-and-shift-operators.md#logical-or-operator-) dei relativi operandi.

## <a name="conditional-logical-and-operator-ampamp"></a><a name="conditional-logical-and-operator-"></a>Operatore logico AND condizionale&amp;&amp;

L'operatore AND condizionale logico `&&`, chiamato anche operatore AND logico di "corto circuito", calcola l'AND logico dei relativi operandi. Il risultato di `x && y` è `true` se `x` e `y` restituiscono `true`. In caso contrario, il risultato è `false`. Se `x` è `false`, `y` non viene valutato.

Nell'esempio seguente l'operando di destra dell'operatore `&&` è una chiamata a un metodo, che non viene eseguita se l'operando di sinistra restituisce `false`:

[!code-csharp-interactive[conditional logical AND](snippets/BooleanLogicalOperators.cs#ConditionalAnd)]

L' [operatore logico and](#logical-and-operator-) `&` Calcola anche l'and logico degli operandi, ma valuta sempre entrambi gli operandi.

## <a name="conditional-logical-or-operator-"></a>Operatore OR condizionale logico ||

L'operatore OR condizionale logico `||`, chiamato anche operatore OR logico di "corto circuito", calcola l'OR logico dei relativi operandi. Il risultato di `x || y` è `true` se `x` o `y` restituisce `true`. In caso contrario, il risultato è `false`. Se `x` è `true`, `y` non viene valutato.

Nell'esempio seguente l'operando di destra dell'operatore `||` è una chiamata a un metodo, che non viene eseguita se l'operando di sinistra restituisce `true`:

[!code-csharp-interactive[conditional logical OR](snippets/BooleanLogicalOperators.cs#ConditionalOr)]

L' [operatore OR logico](#logical-or-operator-) `|` Calcola anche l'OR logico degli operandi, ma valuta sempre entrambi gli operandi.

## <a name="nullable-boolean-logical-operators"></a>Operatori logici booleani nullable

Per gli `bool?` operandi, gli operatori [ `&` (and logico)](#logical-and-operator-) e [ `|` (OR logico)](#logical-or-operator-) supportano la logica a tre valori come segue:

- L' `&` operatore produce `true` solo se entrambi gli operandi restituiscono `true` . Se `x` o `y` restituisce `false` , `x & y` produce `false` (anche se un altro operando restituisce `null` ). In caso contrario, il risultato di `x & y` è `null` .

- L' `|` operatore produce `false` solo se entrambi gli operandi restituiscono `false` . Se `x` o `y` restituisce `true` , `x | y` produce `true` (anche se un altro operando restituisce `null` ). In caso contrario, il risultato di `x | y` è `null` .

Nella tabella seguente viene illustrata la semantica:

|x|y|x&y|x&#124;y|  
|----|----|----|----|  
|true|true|true|true|  
|true|false|false|true|  
|true|Null|Null|true|  
|false|true|false|true|  
|false|false|false|false|  
|false|Null|false|Null|  
|Null|true|Null|true|  
|Null|false|false|Null|  
|Null|Null|Null|Null|  

Il comportamento di questi operatori è diverso dal comportamento tipico degli operatori con tipi valore nullable. In genere un operatore definito per gli operandi di un tipo valore può essere usato anche con gli operandi del tipo valore nullable corrispondente. Questo operatore produce `null` se uno qualsiasi degli operandi restituisce `null` . Tuttavia, gli `&` `|` operatori e possono produrre un valore diverso da null anche se uno degli operandi restituisce `null` . Per ulteriori informazioni sul comportamento dell'operatore con i tipi di valore Nullable, vedere la sezione [operatori rimossi](../builtin-types/nullable-value-types.md#lifted-operators) dell'articolo [tipi di valore Nullable](../builtin-types/nullable-value-types.md) .

È anche possibile usare gli `!` `^` operatori e con `bool?` operandi, come illustrato nell'esempio seguente:

[!code-csharp-interactive[lifted negation and xor](snippets/BooleanLogicalOperators.cs#WithNullableBoolean)]

Gli operatori logici condizionali `&&` e `||` non supportano gli `bool?` operandi.

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

Gli operatori `&`, `|` e `^` supportano l'assegnazione composta, come illustrato nell'esempio seguente:

[!code-csharp-interactive[compound assignment](snippets/BooleanLogicalOperators.cs#CompoundAssignment)]

> [!NOTE]
> Gli operatori condizionali logici `&&` e `||` non supportano l'assegnazione composta.

## <a name="operator-precedence"></a>Precedenza degli operatori

Nell'elenco seguente gli operatori logici sono ordinati dalla precedenza più elevata a quella più bassa:

- Operatore di negazione logico `!`
- Operatore AND logico `&`
- Operatore OR esclusivo logico `^`
- Operatore OR logico `|`
- Operatore AND condizionale logico `&&`
- Operatore OR condizionale logico `||`

Usare le parentesi, `()`, per cambiare l'ordine di valutazione imposto dalla precedenza tra gli operatori:

[!code-csharp-interactive[operator precedence](snippets/BooleanLogicalOperators.cs#Precedence)]

Per l'elenco completo degli operatori C# ordinati in base al livello di precedenza, vedere la sezione [precedenza](index.md#operator-precedence) degli operatori dell'articolo [operatori c#](index.md) .

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente può eseguire l' [Overload](operator-overloading.md) degli `!` operatori, `&` , `|` e `^` . Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione composta corrispondente. Un tipo definito dall'utente non può eseguire in modo esplicito l'overload di un operatore di assegnazione composta.

Un tipo definito dall'utente non può eseguire l'overload degli operatori condizionali logici `&&` e `||`. Tuttavia, se un tipo definito dall'utente esegue l'overload degli [operatori true e false](true-false-operators.md) e dell'operatore `&` o `|` in un determinato modo, l'operazione `&&` o `||` può essere valutata per gli operandi di quel tipo. Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) di [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Operatore di negazione logica](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [Operatori logici](~/_csharplang/spec/expressions.md#logical-operators)
- [Operatori logici condizionali](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Operatori di spostamento e bit per bit](bitwise-and-shift-operators.md)
