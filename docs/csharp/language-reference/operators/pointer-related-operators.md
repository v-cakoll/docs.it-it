---
title: Operatori correlati ai puntatori - Riferimento C#
description: Di seguito sono descritti gli operatori C# che è possibile usare con i puntatori.
ms.date: 05/20/2019
author: pkulikov
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- pointer related operators [C#]
- address-of operator [C#]
- '& operator [C#]'
- pointer indirection operator [C#]
- dereference operator [C#]
- '* operator [C#]'
- pointer member access operator [C#]
- -> operator [C#]
- pointer element access [C#]
- '[] operator [C#]'
- pointer arithmetic [C#]
- pointer increment [C#]
- pointer decrement [C#]
- pointer comparison [C#]
ms.openlocfilehash: 7c95fe07220a78b388a5c6850e4123feb029d951
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399546"
---
# <a name="pointer-related-operators-c-reference"></a>Operatori correlati ai puntatori (Riferimento C#)

È possibile usare gli operatori seguenti con i puntatori:

- Operatore unario [ `&` (indirizzo di):](#address-of-operator-) per ottenere l'indirizzo di una variabile
- Operatore unario [ `*` (riferimento indiretto puntatore):](#pointer-indirection-operator-) per ottenere la variabile a punta di un puntatore
- Gli [ `->` operatori (accesso ai membri)](#pointer-member-access-operator--) e [ `[]` (accesso agli elementi)](#pointer-element-access-operator-)
- Operatori aritmetici [ `+`, `-` `++`, , e`--`](#pointer-arithmetic-operators)
- Operatori [ `==`di `!=` `<`confronto `>` `<=`, , , , , e`>=`](#pointer-comparison-operators)

Per informazioni sui tipi di puntatori, vedere [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md).

> [!NOTE]
> Qualsiasi operazione con i puntatori richiede un contesto [unsafe](../keywords/unsafe.md). Il codice che contiene blocchi unsafe [`-unsafe`](../compiler-options/unsafe-compiler-option.md) deve essere compilato con l'opzione del compilatore.

## <a name="address-of-operator-"></a>Indirizzo dell'operatore&amp;

L'operatore `&` unario restituisce l'indirizzo del relativo operando:

[!code-csharp[address of local](snippets/PointerOperators.cs#AddressOf)]

L'operando dell'operatore `&` deve essere una variabile fissa. Le variabili *fisse* sono variabili che si trovano in posizioni di archiviazione non interessate dall'operazione di [Garbage Collector](../../../standard/garbage-collection/index.md). Nell'esempio precedente la variabile locale `number` è una variabile fissa perché si trova nello stack. Le variabili che si trovano in posizioni di archiviazione che possono essere influenzate da Garbage Collector (ad esempio rilocate) sono chiamate variabili *mobili*. I campi degli oggetti e gli elementi delle matrici sono esempi di variabili mobili. È possibile ottenere l'indirizzo di una variabile mobile se si "correzione", o "pin", con [ `fixed` un'istruzione](../keywords/fixed-statement.md). L'indirizzo ottenuto è valido `fixed` solo all'interno del blocco di un'istruzione. Nell'esempio seguente viene `fixed` illustrato come `&` utilizzare un'istruzione e l'operatore:The following example shows how to use a statement and the operator:

[!code-csharp[address of fixed](snippets/PointerOperators.cs#AddressOfFixed)]

Non è possibile ottenere l'indirizzo di una costante o di un valore.

Per altre informazioni sulle variabili fisse e mobili, vedere la sezione [Variabili fisse e mobili](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) dell'articolo relativo alla [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

L'operatore `&` binario calcola l'[AND logico](boolean-logical-operators.md#logical-and-operator-) dei relativi operandi booleani o l'[AND logico bit per bit](bitwise-and-shift-operators.md#logical-and-operator-) dei relativi operandi integrali.

## <a name="pointer-indirection-operator-"></a>Operatore * (riferimento indiretto a puntatore)

L'operatore di riferimento indiretto a puntatore unario `*` ottiene la variabile a cui punta il relativo operando. L'operatore è chiamato anche operatore di dereferenziazione. L'operando dell'operatore `*` deve essere un tipo di puntatore.

[!code-csharp[pointer indirection](snippets/PointerOperators.cs#PointerIndirection)]

Non è possibile applicare l'operatore `*` a un'espressione di tipo `void*`.

L'operatore `*` binario calcola il [prodotto](arithmetic-operators.md#multiplication-operator-) dei relativi operandi numerici.

## <a name="pointer-member-access-operator--"></a>Operatore -> (accesso ai membri del puntatore)

L'operatore `->` unisce il [riferimento indiretto al puntatore](#pointer-indirection-operator-) e l'[accesso ai membri](member-access-operators.md#member-access-operator-). Ovvero, se `x` è un `T*` puntatore di tipo `y` `T`ed è un membro accessibile di tipo , un'espressione nel formato

```csharp
x->y
```

equivale a

```csharp
(*x).y
```

Nell'esempio seguente viene illustrato l'uso dell'operatore `->`:

[!code-csharp[pointer member access](snippets/PointerOperators.cs#MemberAccess)]

Non è possibile applicare l'operatore `->` a un'espressione di tipo `void*`.

## <a name="pointer-element-access-operator-"></a>Operatore [] (accesso agli elementi del puntatore)

Per un'espressione `p` di un tipo di puntatore, l'accesso a un elemento del puntatore nella forma `p[n]` viene calcolato come `*(p + n)`, dove `n` deve essere un tipo convertibile in modo implicito in `int`, `uint`, `long` o `ulong`. Per informazioni sul comportamento dell'operatore `+` con i puntatori, vedere la sezione [Addizione o sottrazione di un valore integrale da un puntatore](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer).

L'esempio seguente illustra come accedere agli elementi della matrice con un puntatore e l'operatore `[]`:

[!code-csharp[pointer element access](snippets/PointerOperators.cs#ElementAccess)]

Nell'esempio viene utilizzato [ `stackalloc` l'operatore](stackalloc.md) per allocare un blocco di memoria nello stack.

> [!NOTE]
> L'operatore di accesso agli elementi del puntatore non ricerca gli errori relativi a valori non compresi nell'intervallo.

Non è possibile usare `[]` per l'accesso agli elementi del puntatore con un'espressione di tipo `void*`.

È anche possibile usare l'operatore `[]` per l'[accesso agli elementi di una matrice o all'indicizzatore](member-access-operators.md#indexer-operator-).

## <a name="pointer-arithmetic-operators"></a>Operatori aritmetici dei puntatori

È possibile eseguire le operazioni aritmetiche seguenti con i puntatori:

- Aggiungere o sottrarre un valore integrale da un puntatore
- Sottrarre due puntatori
- Incrementare o decrementare un puntatore

Non è possibile eseguire queste operazioni con puntatori di tipo `void*`.

Per informazioni sulle operazioni aritmetiche supportate con i tipi numerici, vedere [Operatori aritmetici](arithmetic-operators.md).

### <a name="addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer"></a>Addizione o sottrazione di un valore integrale da un puntatore

Per un puntatore `p` di tipo `T*` e un'espressione `n` di tipo implicitamente convertibile in `int`, `uint`, `long` o `ulong`, l'addizione e la sottrazione sono definite come segue:

- Entrambe le espressioni `p + n` e `n + p` producono un puntatore di tipo `T*` risultante dalla somma di `n * sizeof(T)` all'indirizzo specificato da `p`.
- L'espressione `p - n` produce un puntatore di tipo `T*` risultante dalla sottrazione di `n * sizeof(T)` dall'indirizzo specificato da `p`.

[ `sizeof` L'operatore](sizeof.md) ottiene la dimensione di un tipo in byte.

L'esempio seguente illustra l'uso dell'operatore `+` con un puntatore:

[!code-csharp[pointer addition](snippets/PointerOperators.cs#AddNumber)]

### <a name="pointer-subtraction"></a>Sottrazione di puntatori

Per i due puntatori `p1` e `p2` di tipo `T*`, l'espressione `p1 - p2` produce la differenza tra gli indirizzi specificati da `p1` e `p2` divisi per `sizeof(T)`. Il tipo del risultato è `long`. Ovvero, `p1 - p2` viene calcolato come `((long)(p1) - (long)(p2)) / sizeof(T)`.

L'esempio seguente illustra la sottrazione del puntatore:

[!code-csharp[pointer subtraction](snippets/PointerOperators.cs#SubtractPointers)]

### <a name="pointer-increment-and-decrement"></a>Incremento e decremento dei puntatori

L'operatore di incremento `++`[somma](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 al relativo operando puntatore. L'operatore di decremento `--`[sottrae](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 dal relativo operando puntatore.

Entrambi gli operatori sono supportati in due forme: come suffisso (`p++` e `p--`) e come prefisso (`++p` e `--p`). Il risultato di `p++` e `p--` è il valore di `p` *prima* dell'operazione. Il risultato di `++p` e `--p` è il valore di `p` *dopo* l'operazione.

L'esempio seguente illustra il comportamento di entrambi gli operatori di incremento suffisso e prefisso:

[!code-csharp[pointer increment](snippets/PointerOperators.cs#Increment)]

## <a name="pointer-comparison-operators"></a>Operatori di confronto dei puntatori

È possibile usare gli operatori `==`, `!=`, `<`, `>`, `<=` e `>=` per confrontare gli operandi di qualsiasi tipo di puntatore, incluso `void*`. Questi operatori confrontano gli indirizzi specificati dai due operandi come se fossero interi senza segno.

Per informazioni sul comportamento di questi operatori per gli operandi di altri tipi, vedere gli articoli [Operatori di uguaglianza](equality-operators.md) e [Operatori di confronto](comparison-operators.md).

## <a name="operator-precedence"></a>Precedenza degli operatori

Nell'elenco seguente gli operatori correlati ai puntatori sono ordinati dalla precedenza più elevata a quella più bassa:

- Operatori di incremento `x++` e decremento `x--` suffisso e operatori `->` e `[]`
- Operatori di incremento `++x` e decremento `--x` prefisso e operatori `&` e `*`
- Operatori di addizione `+` e `-`
- Operatori di confronto `<`, `>`, `<=` e `>=`
- Operatori di uguaglianza `==` e `!=`

Usare le parentesi, `()`, per cambiare l'ordine di valutazione imposto dalla precedenza tra gli operatori.

Per l'elenco completo degli operatori di C, ordinati in base al livello di precedenza, vedere la sezione [Precedenza](index.md#operator-precedence) degli operatori dell'articolo Operatori di [C.](index.md)

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente non può eseguire l'overload degli operatori correlati ai puntatori `&`, `*`, `->` e `[]`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Variabili fisse e mobili](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables)
- [Operatore address-of](~/_csharplang/spec/unsafe-code.md#the-address-of-operator)
- [Riferimento indiretto a puntatore](~/_csharplang/spec/unsafe-code.md#pointer-indirection)
- [Accesso ai membri del puntatore](~/_csharplang/spec/unsafe-code.md#pointer-member-access)
- [Accesso agli elementi del puntatore](~/_csharplang/spec/unsafe-code.md#pointer-element-access)
- [Puntatore aritmetico](~/_csharplang/spec/unsafe-code.md#pointer-arithmetic)
- [Incremento e decremento dei puntatori](~/_csharplang/spec/unsafe-code.md#pointer-increment-and-decrement)
- [Confronto dei puntatori](~/_csharplang/spec/unsafe-code.md#pointer-comparison)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Tipi di puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Parola chiave unsafe](../keywords/unsafe.md)
- [parola chiave fissa](../keywords/fixed-statement.md)
- [Operatore stackalloc](stackalloc.md)
- [operatore sizeof](sizeof.md)
