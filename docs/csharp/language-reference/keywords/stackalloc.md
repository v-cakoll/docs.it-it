---
title: stackalloc (Riferimenti per C#)
ms.date: 04/12/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c4cde254bb6a5601d10619c4a3bd2f00f1f146d3
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
---
# <a name="stackalloc-c-reference"></a>stackalloc (Riferimenti per C#)
La parola chiave `stackalloc` viene usata in un contesto di codice unsafe per allocare un blocco di memoria nello stack.

```csharp
int* block = stackalloc int[100];
```

## <a name="remarks"></a>Note

La parola chiave è valida solo per gli inizializzatori di variabili locali. Il codice seguente causa errori di compilazione.

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
```

A partire da C# 7.3, è possibile usare la sintassi dell'inizializzatore di matrice per le matrici `stackalloc`. Tutte le dichiarazioni seguenti dichiarano una matrice con tre elementi i cui valori sono i numeri interi `1`, `2` e `3`:

```csharp
// Valid starting with C# 7.3
int* first = stackalloc int[3] { 1, 2, 3 };
int* second = stackalloc int[] { 1, 2, 3 };
int* third = stackalloc[] { 1, 2, 3 };
```

Poiché vengono usati tipi puntatore, `stackalloc` richiede un contesto [unsafe](unsafe.md). Per altre informazioni, vedere [Codice unsafe e puntatori](../../programming-guide/unsafe-code-pointers/index.md). 

La parola chiave `stackalloc` è come [_alloca](/cpp/c-runtime-library/reference/alloca) nella libreria di runtime del linguaggio C.

## <a name="examples"></a>Esempi

Nell'esempio seguente vengono calcolati e visualizzati i primi 20 numeri della sequenza di Fibonacci. Ogni numero corrisponde alla somma dei due numeri precedenti. Nel codice, un blocco di memoria di dimensioni sufficienti a contenere 20 elementi di tipo `int` viene allocato nello stack, non nell'heap. L'indirizzo del blocco è archiviato nel puntatore `fib`. Questa memoria non viene sottoposta alla procedura di Garbage Collection e non deve quindi essere bloccata con [fixed](fixed-statement.md). La durata del blocco di memoria è limitata alla durata del metodo che lo definisce. Non è possibile liberare la memoria prima della restituzione del metodo.

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

L'esempio seguente inizializza una matrice `stackalloc` di interi su una maschera di bit con un bit impostato in ogni elemento. Questo esempio dimostra la nuova sintassi dell'inizializzatore disponibile a partire da C# 7.3:

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a>Sicurezza

Il codice di tipo unsafe è meno sicuro delle alternative di tipo safe. Tuttavia, l'uso di `stackalloc` attiva automaticamente le funzionalità di rilevazione del sovraccarico del buffer in Common Language Runtime (CLR). Se viene rilevato un sovraccarico del buffer, il processo viene terminato il più rapidamente possibile per ridurre al minimo la possibilità che venga eseguito codice dannoso.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Parole chiave per gli operatori](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
