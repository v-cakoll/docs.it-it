---
title: Istruzione fixed - Riferimenti per C#
ms.date: 05/10/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: e527e8a54a739391d18b180532372b5b70f34d37
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713527"
---
# <a name="fixed-statement-c-reference"></a>Istruzione fixed (Riferimenti per C#)

L'istruzione `fixed` impedisce che il Garbage Collector esegua la rilocazione di una variabile mobile. L'istruzione `fixed` è consentita solo in un contesto di tipo [unsafe](unsafe.md). È anche possibile usare la parola chiave `fixed` per creare [buffer a dimensione fissa](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).

L'istruzione `fixed` imposta un puntatore a una variabile gestita e la blocca durante l'esecuzione dell'istruzione. I puntatori alle variabili mobili gestite sono utili solo in un contesto `fixed`. Senza un contesto `fixed`, l'operazione di garbage collection potrebbe spostare le variabili in modo imprevedibile. Il compilatore C# consente di assegnare un puntatore a una variabile gestita in un'istruzione `fixed`.

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

È possibile inizializzare un puntatore usando una matrice, una stringa, un buffer a dimensione fissa o l'indirizzo di una variabile. L'esempio seguente illustra l'uso di indirizzi di variabili, matrici e stringhe:

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

A partire da C# 7.3, l'istruzione `fixed` opera su tipi aggiuntivi oltre a matrici, stringhe, buffer a dimensione fissa o variabili non gestite. È possibile bloccare qualsiasi tipo che implementa un metodo denominato `GetPinnableReference`. `GetPinnableReference` deve restituire una variabile `ref` di un [tipo non gestito](../builtin-types/unmanaged-types.md). I tipi .NET <xref:System.Span%601?displayProperty=nameWithType> e <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> introdotti in .NET Core 2.0 usano questo modello e possono essere bloccati. Questa operazione è illustrata nell'esempio seguente:

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#FixedSpan)]

Se si creano tipi che devono partecipare a questo modello, vedere <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> per un esempio di implementazione del modello.

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

È possibile allocare memoria nello stack, dove non è soggetta a Garbage Collection e pertanto non deve essere bloccata. A questo scopo, usare l'operatore [`stackalloc`](../operators/stackalloc.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Istruzione fixed](~/_csharplang/spec/unsafe-code.md#the-fixed-statement) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [unsafe](unsafe.md)
- [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Buffer a dimensione fissa](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
