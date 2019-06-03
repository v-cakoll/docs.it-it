---
title: Parola chiave stackalloc - Riferimenti per C#
ms.custom: seodec18
ms.date: 04/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: c72daa58d2fceb05d9cc9c388a9d2e5dbe062796
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422435"
---
# <a name="stackalloc-c-reference"></a>stackalloc (Riferimenti per C#)

La parola chiave `stackalloc` viene usata per allocare un blocco di memoria nello stack.

```csharp
Span<int> block = stackalloc int[100];
```

L'assegnazione del blocco allocato a un <xref:System.Span%601?displayName=nameWithType> invece che a un `int*` consente le allocazioni di stack in un blocco sicuro. Il contesto `unsafe` non è obbligatorio.

## <a name="remarks"></a>Osservazioni

La parola chiave è valida solo per gli inizializzatori di variabili locali. Il codice seguente causa errori di compilazione.

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
Span<int> span;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
span = stackalloc int[100];
```

A partire da C# 7.3, è possibile usare la sintassi dell'inizializzatore di matrice per le matrici `stackalloc`. Tutte le dichiarazioni seguenti dichiarano una matrice con tre elementi i cui valori sono i numeri interi `1`, `2` e `3`. La seconda inizializzazione assegna la memoria a un <xref:System.ReadOnlySpan%601>, a indicare che la memoria non può essere modificata.

```csharp
// Valid starting with C# 7.3
Span<int> first = stackalloc int[3] { 1, 2, 3 };
ReadOnlySpan<int> second = stackalloc int[] { 1, 2, 3 };
Span<int> third = stackalloc[] { 1, 2, 3 };
```

Quando vengono usati tipi puntatore, `stackalloc` richiede un contesto [unsafe](unsafe.md). Per altre informazioni, vedere [Codice unsafe e puntatori](../../programming-guide/unsafe-code-pointers/index.md).

La parola chiave `stackalloc` è come [_alloca](/cpp/c-runtime-library/reference/alloca) nella libreria di runtime del linguaggio C.

## <a name="examples"></a>Esempi

Nell'esempio seguente vengono calcolati e visualizzati i primi 20 numeri della sequenza di Fibonacci. Ogni numero corrisponde alla somma dei due numeri precedenti. Nel codice, un blocco di memoria di dimensioni sufficienti a contenere 20 elementi di tipo `int` viene allocato nello stack, non nell'heap. L'indirizzo del blocco è archiviato nel `fib` `Span`. Questa memoria non viene sottoposta alla procedura di Garbage Collection e non deve quindi essere bloccata con [fixed](fixed-statement.md). La durata del blocco di memoria è limitata alla durata del metodo che lo definisce. Non è possibile liberare la memoria prima della restituzione del metodo.

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

L'esempio seguente inizializza una matrice `stackalloc` di interi su una maschera di bit con un bit impostato in ogni elemento. Questo esempio dimostra la nuova sintassi dell'inizializzatore disponibile a partire da C# 7.3:

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a>Sicurezza

È consigliabile usare <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> quando possibile perché il codice di tipo unsafe è meno sicuro delle alternative di tipo safe. Anche in presenza di puntatori, l'uso di `stackalloc` attiva automaticamente le funzionalità di rilevazione del sovraccarico del buffer in Common Language Runtime (CLR). Se viene rilevato un sovraccarico del buffer, il processo viene terminato il più rapidamente possibile per ridurre al minimo la possibilità che venga eseguito codice dannoso.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Codice unsafe e puntatori](../../programming-guide/unsafe-code-pointers/index.md)
