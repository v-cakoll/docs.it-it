---
title: Buffer a dimensione fissa (Guida per programmatori C#)
ms.date: 04/20/2018
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 310c5eed5507f75239efc78b6132fbc91211d29e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339592"
---
# <a name="fixed-size-buffers-c-programming-guide"></a>Buffer a dimensione fissa (Guida per programmatori C#)

In C# è possibile usare l'istruzione [fixed](../../language-reference/keywords/fixed-statement.md) per creare un buffer con una matrice di dimensioni fisse in una struttura di dati. I buffer a dimensione fissa sono utili quando si scrivono metodi con interoperabilità con origini dati di altri linguaggi o piattaforme. La matrice fissa può accettare attributi o modificatori consentiti per i membri struct normali. L'unica restrizione è rappresentata dal fatto che il tipo di matrice deve essere `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` o `double`.

```csharp
private fixed char name[30];
```

## <a name="remarks"></a>Note

Nel codice safe, uno struct C# che contiene una matrice non contiene gli elementi della matrice. Lo struct contiene invece un riferimento agli elementi. È possibile incorporare una matrice di dimensioni fisse in uno [struct](../../language-reference/keywords/struct.md) quando viene usata in un blocco di codice [unsafe](../../language-reference/keywords/unsafe.md).

Lo `struct` seguente ha una dimensione di 8 byte. La matrice `pathName` è un riferimento:

[!code-csharp[Struct with embedded array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#6)]

Un oggetto `struct` può contenere una matrice incorporata in codice unsafe. Nell'esempio seguente la matrice `fixedBuffer` è di dimensioni fisse. Viene usata un'istruzione `fixed` per definire un puntatore al primo elemento. Gli elementi della matrice sono accessibili tramite il puntatore. L'istruzione `fixed` blocca un'istanza di `fixedBuffer` in un percorso specifico nella memoria.

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#7)]

Le dimensioni della matrice `char` a 128 elementi sono di 256 byte. I buffer [char](../../language-reference/keywords/char.md) a dimensione fissa accettano sempre due byte per carattere, indipendentemente dalla codifica. Questo vale anche quando viene eseguito il marshalling di buffer char in metodi API o struct con `CharSet = CharSet.Auto` o `CharSet = CharSet.Ansi`. Per altre informazioni, vedere <xref:System.Runtime.InteropServices.CharSet>.

L'esempio precedente illustra l'accesso ai cambi `fixed` senza blocco, opzione disponibile a partire da C# 7.3.

Un'altra matrice a dimensione fissa comune è la matrice [bool](../../language-reference/keywords/bool.md). Gli elementi in una matrice `bool` hanno sempre le dimensioni di un byte. Le matrici `bool` non sono adatte per la creazione di matrici o buffer di bit.

> [!NOTE]
> Eccezione fatta per la memoria creata con [stackalloc](../../language-reference/keywords/stackalloc.md), il compilatore C# e Common Language Runtime (CLR) non eseguono controlli di sicurezza per sovraccarico del buffer. Come per tutto il codice unsafe, è necessario prestare la massima attenzione.

I buffer unsafe sono diversi dalle normali matrici per i motivi seguenti:

- È possibile usare i buffer unsafe solo in un contesto unsafe.
- I buffer unsafe sono sempre vettori, ovvero matrici unidimensionali.
- La dichiarazione della matrice deve includere un conteggio, ad esempio `char id[8]`. Non è possibile usare `char id[]`.
- I buffer unsafe possono essere solo campi di istanza di struct in un contesto unsafe.

## <a name="see-also"></a>Vedere anche

[Guida per programmatori C#](../index.md)  
[Codice unsafe e puntatori](index.md)  
[Istruzione fixed](../../language-reference/keywords/fixed-statement.md)  
[Interoperabilità](../interop/index.md)
