---
title: Istruzione fixed (Riferimenti per C#)
ms.date: 04/20/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: e1664f508cb861ffa73b800eeb0da3a1f1cdc432
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="fixed-statement-c-reference"></a>Istruzione fixed (Riferimenti per C#)

L'istruzione `fixed` impedisce che il Garbage Collector esegua la rilocazione di una variabile mobile. L'istruzione `fixed` è consentita solo in un contesto di tipo [unsafe](unsafe.md). È possibile usare `Fixed` anche per creare [buffer a dimensione fissa](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).

L'istruzione `fixed` imposta un puntatore a una variabile gestita e la blocca durante l'esecuzione dell'istruzione. I puntatori alle variabili mobili gestite sono utili solo in un contesto `fixed`. Senza un contesto `fixed`, l'operazione di garbage collection potrebbe spostare le variabili in modo imprevedibile. Il compilatore C# consente di assegnare un puntatore a una variabile gestita in un'istruzione `fixed`.

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

È possibile inizializzare un puntatore usando una matrice, una stringa, un buffer a dimensione fissa o l'indirizzo di una variabile. Nell'esempio seguente viene illustrato l'uso di indirizzi, matrici e stringhe di una variabile. Per altre informazioni sui buffer a dimensione fissa, vedere [Buffer a dimensione fissa](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

Se sono dello stesso tipo, è possibile inizializzare più puntatori in un'unica istruzione:

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

Per inizializzare puntatori di tipi diversi, annidare semplicemente le istruzioni `fixed` come illustrato nell'esempio seguente.

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

Dopo aver eseguito il codice nell'istruzione, le variabili bloccate vengono sbloccate e sottoposte al Garbage Collection. Di conseguenza, evitare di puntare alle variabili esterne all'istruzione `fixed`. Le variabili dichiarate nell'istruzione `fixed` rientrano nell'ambito di tale istruzione, semplificandola:

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

I puntatori inizializzati nelle istruzioni `fixed` sono variabili di sola lettura. Per modificare il valore puntatore, è necessario dichiarare una seconda variabile e quindi modificarla. La variabile dichiarata nell'istruzione `fixed` non può essere modificata:

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```


Nella modalità di tipo unsafe è possibile allocare la memoria nello stack, che non è necessario bloccare perché non viene sottoposto al Garbage Collection. Per altre informazioni, vedere [stackalloc](stackalloc.md).

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

 [Riferimenti per C#](../index.md)  
 [Guida per programmatori C#](../../programming-guide/index.md)  
 [Parole chiave di C#](index.md)  
 [unsafe](unsafe.md)  
 [Buffer a dimensione fissa](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
