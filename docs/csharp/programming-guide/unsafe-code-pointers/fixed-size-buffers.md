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
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="45b4c-102">Buffer a dimensione fissa (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="45b4c-102">Fixed Size Buffers (C# Programming Guide)</span></span>

<span data-ttu-id="45b4c-103">In C# è possibile usare l'istruzione [fixed](../../language-reference/keywords/fixed-statement.md) per creare un buffer con una matrice di dimensioni fisse in una struttura di dati.</span><span class="sxs-lookup"><span data-stu-id="45b4c-103">In C#, you can use the [fixed](../../language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="45b4c-104">I buffer a dimensione fissa sono utili quando si scrivono metodi con interoperabilità con origini dati di altri linguaggi o piattaforme.</span><span class="sxs-lookup"><span data-stu-id="45b4c-104">Fixed size buffers are useful when you write methods that interop with data sources from other languages or platforms.</span></span> <span data-ttu-id="45b4c-105">La matrice fissa può accettare attributi o modificatori consentiti per i membri struct normali.</span><span class="sxs-lookup"><span data-stu-id="45b4c-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="45b4c-106">L'unica restrizione è rappresentata dal fatto che il tipo di matrice deve essere `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="45b4c-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>

```csharp
private fixed char name[30];
```

## <a name="remarks"></a><span data-ttu-id="45b4c-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="45b4c-107">Remarks</span></span>

<span data-ttu-id="45b4c-108">Nel codice safe, uno struct C# che contiene una matrice non contiene gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="45b4c-108">In safe code, a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="45b4c-109">Lo struct contiene invece un riferimento agli elementi.</span><span class="sxs-lookup"><span data-stu-id="45b4c-109">Instead, the struct contains a reference to the elements.</span></span> <span data-ttu-id="45b4c-110">È possibile incorporare una matrice di dimensioni fisse in uno [struct](../../language-reference/builtin-types/struct.md) quando viene usata in un blocco di codice [unsafe](../../language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="45b4c-110">You can embed an array of fixed size in a [struct](../../language-reference/builtin-types/struct.md) when it is used in an [unsafe](../../language-reference/keywords/unsafe.md) code block.</span></span>

<span data-ttu-id="45b4c-111">Le dimensioni del codice `struct` seguente non dipendono dal numero di elementi nella matrice, poiché `pathName` è un riferimento:</span><span class="sxs-lookup"><span data-stu-id="45b4c-111">Size of the following `struct` doesn't depend on the number of elements in the array, since `pathName` is a reference:</span></span>

[!code-csharp[Struct with embedded array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#6)]

<span data-ttu-id="45b4c-112">Un oggetto `struct` può contenere una matrice incorporata in codice unsafe.</span><span class="sxs-lookup"><span data-stu-id="45b4c-112">A `struct` can contain an embedded array in unsafe code.</span></span> <span data-ttu-id="45b4c-113">Nell'esempio seguente la matrice `fixedBuffer` è di dimensioni fisse.</span><span class="sxs-lookup"><span data-stu-id="45b4c-113">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="45b4c-114">Viene usata un'istruzione `fixed` per definire un puntatore al primo elemento.</span><span class="sxs-lookup"><span data-stu-id="45b4c-114">You use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="45b4c-115">Gli elementi della matrice sono accessibili tramite il puntatore.</span><span class="sxs-lookup"><span data-stu-id="45b4c-115">You access the elements of the array through this pointer.</span></span> <span data-ttu-id="45b4c-116">L'istruzione `fixed` blocca un'istanza di `fixedBuffer` in un percorso specifico nella memoria.</span><span class="sxs-lookup"><span data-stu-id="45b4c-116">The `fixed` statement pins the `fixedBuffer` instance field to a specific location in memory.</span></span>

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#7)]

<span data-ttu-id="45b4c-117">Le dimensioni della matrice `char` a 128 elementi sono di 256 byte.</span><span class="sxs-lookup"><span data-stu-id="45b4c-117">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="45b4c-118">I buffer [char](../../language-reference/builtin-types/char.md) a dimensione fissa accettano sempre due byte per carattere, indipendentemente dalla codifica.</span><span class="sxs-lookup"><span data-stu-id="45b4c-118">Fixed size [char](../../language-reference/builtin-types/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="45b4c-119">Questo vale anche quando viene eseguito il marshalling di buffer char in metodi API o struct con `CharSet = CharSet.Auto` o `CharSet = CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="45b4c-119">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="45b4c-120">Per altre informazioni, vedere <xref:System.Runtime.InteropServices.CharSet>.</span><span class="sxs-lookup"><span data-stu-id="45b4c-120">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>

<span data-ttu-id="45b4c-121">L'esempio precedente mostra l'accesso ai campi `fixed` senza blocco, opzione disponibile a partire da C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="45b4c-121">The  preceding example demonstrates accessing `fixed` fields without pinning, which is available starting with C# 7.3.</span></span>

<span data-ttu-id="45b4c-122">Un'altra matrice a dimensione fissa comune è la matrice [bool](../../language-reference/builtin-types/bool.md).</span><span class="sxs-lookup"><span data-stu-id="45b4c-122">Another common fixed-size array is the [bool](../../language-reference/builtin-types/bool.md) array.</span></span> <span data-ttu-id="45b4c-123">Gli elementi in una matrice `bool` hanno sempre le dimensioni di un byte.</span><span class="sxs-lookup"><span data-stu-id="45b4c-123">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="45b4c-124">Le matrici `bool` non sono adatte per la creazione di matrici o buffer di bit.</span><span class="sxs-lookup"><span data-stu-id="45b4c-124">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>

<span data-ttu-id="45b4c-125">I buffer a dimensione fissa vengono compilati con l'oggetto <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>, che indica al Common Language Runtime (CLR) che un tipo contiene una matrice non gestita che può causare un overflow.</span><span class="sxs-lookup"><span data-stu-id="45b4c-125">Fixed size buffers are compiled with the <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>, which instructs the common language runtime (CLR) that a type contains an unmanaged array that can potentially overflow.</span></span> <span data-ttu-id="45b4c-126">Questa operazione è simile alla memoria creata con [stackalloc](../../language-reference/operators/stackalloc.md), che abilita automaticamente le funzionalità di rilevamento del sovraccarico del buffer in CLR.</span><span class="sxs-lookup"><span data-stu-id="45b4c-126">This is similar to memory created using [stackalloc](../../language-reference/operators/stackalloc.md), which automatically enables buffer overrun detection features in the CLR.</span></span> <span data-ttu-id="45b4c-127">Nell'esempio precedente viene illustrato come potrebbe esistere un buffer a dimensione fissa `unsafe struct`in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="45b4c-127">The previous example shows how a fixed size buffer could exist in an `unsafe struct`.</span></span>

```csharp
internal unsafe struct Buffer
{
    public fixed char fixedBuffer[128];
}
```

<span data-ttu-id="45b4c-128">Il compilatore genera C# per `Buffer`, è attribuito come segue:</span><span class="sxs-lookup"><span data-stu-id="45b4c-128">The compiler generated C# for `Buffer`, is attributed as follows:</span></span>

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

<span data-ttu-id="45b4c-129">I buffer a dimensione fissa differiscono dalle matrici normali nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="45b4c-129">Fixed size buffers differ from regular arrays in the following ways:</span></span>

- <span data-ttu-id="45b4c-130">Può essere utilizzato solo in un contesto [unsafe](../../language-reference/keywords/unsafe.md) .</span><span class="sxs-lookup"><span data-stu-id="45b4c-130">May only be used in an [unsafe](../../language-reference/keywords/unsafe.md) context.</span></span>
- <span data-ttu-id="45b4c-131">Può essere solo campi di istanza di struct.</span><span class="sxs-lookup"><span data-stu-id="45b4c-131">May only be instance fields of structs.</span></span>
- <span data-ttu-id="45b4c-132">Sono sempre vettori o matrici unidimensionali.</span><span class="sxs-lookup"><span data-stu-id="45b4c-132">They're always vectors, or one-dimensional arrays.</span></span>
- <span data-ttu-id="45b4c-133">La dichiarazione deve includere la lunghezza, ad esempio `fixed char id[8]`.</span><span class="sxs-lookup"><span data-stu-id="45b4c-133">The declaration should include the length, such as `fixed char id[8]`.</span></span> <span data-ttu-id="45b4c-134">Non è possibile usare `fixed char id[]`.</span><span class="sxs-lookup"><span data-stu-id="45b4c-134">You cannot use `fixed char id[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="45b4c-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45b4c-135">See also</span></span>

- [<span data-ttu-id="45b4c-136">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="45b4c-136">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="45b4c-137">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="45b4c-137">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="45b4c-138">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="45b4c-138">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="45b4c-139">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="45b4c-139">Interoperability</span></span>](../interop/index.md)
