---
title: Buffer a dimensione fissa - Guida per programmatori C#
ms.date: 04/23/2020
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 5920dd125ded34969d60feb299568b56402056ab
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140548"
---
# <a name="fixed-size-buffers-c-programming-guide"></a>Buffer a dimensione fissa (Guida per programmatori C#)

In C# è possibile usare l'istruzione [fixed](../../language-reference/keywords/fixed-statement.md) per creare un buffer con una matrice di dimensioni fisse in una struttura di dati. I buffer a dimensione fissa sono utili quando si scrivono metodi con interoperabilità con origini dati di altri linguaggi o piattaforme. La matrice fissa può accettare attributi o modificatori consentiti per i membri struct normali. L'unica restrizione è rappresentata dal fatto che il tipo di matrice deve essere `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` o `double`.

```csharp
private fixed char name[30];
```

## <a name="remarks"></a>Osservazioni

Nel codice safe, uno struct C# che contiene una matrice non contiene gli elementi della matrice. Lo struct contiene invece un riferimento agli elementi. È possibile incorporare una matrice di dimensioni fisse in uno [struct](../../language-reference/builtin-types/struct.md) quando viene usata in un blocco di codice [unsafe](../../language-reference/keywords/unsafe.md).

Le dimensioni del codice `struct` seguente non dipendono dal numero di elementi nella matrice, poiché `pathName` è un riferimento:

[!code-csharp[Struct with embedded array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#6)]

Un oggetto `struct` può contenere una matrice incorporata in codice unsafe. Nell'esempio seguente la matrice `fixedBuffer` è di dimensioni fisse. Viene usata un'istruzione `fixed` per definire un puntatore al primo elemento. Gli elementi della matrice sono accessibili tramite il puntatore. L'istruzione `fixed` blocca un'istanza di `fixedBuffer` in un percorso specifico nella memoria.

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#7)]

Le dimensioni della matrice `char` a 128 elementi sono di 256 byte. I buffer [char](../../language-reference/builtin-types/char.md) a dimensione fissa accettano sempre due byte per carattere, indipendentemente dalla codifica. Questo vale anche quando viene eseguito il marshalling di buffer char in metodi API o struct con `CharSet = CharSet.Auto` o `CharSet = CharSet.Ansi`. Per altre informazioni, vedere <xref:System.Runtime.InteropServices.CharSet>.

L'esempio precedente mostra l'accesso ai campi `fixed` senza blocco, opzione disponibile a partire da C# 7.3.

Un'altra matrice a dimensione fissa comune è la matrice [bool](../../language-reference/builtin-types/bool.md). Gli elementi in una matrice `bool` hanno sempre le dimensioni di un byte. Le matrici `bool` non sono adatte per la creazione di matrici o buffer di bit.

I buffer a dimensione fissa vengono compilati con l'oggetto <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>, che indica al Common Language Runtime (CLR) che un tipo contiene una matrice non gestita che può causare un overflow. Questa operazione è simile alla memoria creata con [stackalloc](../../language-reference/operators/stackalloc.md), che abilita automaticamente le funzionalità di rilevamento del sovraccarico del buffer in CLR. Nell'esempio precedente viene illustrato come potrebbe esistere un buffer a dimensione fissa `unsafe struct`in un oggetto.

```csharp
internal unsafe struct Buffer
{
    public fixed char fixedBuffer[128];
}
```

Il compilatore genera C# per `Buffer`, è attribuito come segue:

```csharp
internal struct Buffer
{
    [StructLayout(LayoutKind.Sequential, Size = 256)]
    [CompilerGenerated]
    [UnsafeValueType]
    public struct <fixedBuffer>e__FixedBuffer
    {
        public char FixedElementField;
    }

    [FixedBuffer(typeof(char), 128)]
    public <fixedBuffer>e__FixedBuffer fixedBuffer;
}
```

I buffer a dimensione fissa differiscono dalle matrici normali nei modi seguenti:

- Può essere utilizzato solo in un contesto [unsafe](../../language-reference/keywords/unsafe.md) .
- Può essere solo campi di istanza di struct.
- Sono sempre vettori o matrici unidimensionali.
- La dichiarazione deve includere la lunghezza, ad esempio `fixed char id[8]`. Non è possibile usare `fixed char id[]`.

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Codice unsafe e puntatori](index.md)
- [Istruzione fixed](../../language-reference/keywords/fixed-statement.md)
- [Interoperabilità](../interop/index.md)
