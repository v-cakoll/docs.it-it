---
title: Buffer a dimensione fissa - Guida per programmatori C#
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 5bfd9f3f559e4780b910a2e5a3430b08a2183ee3
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833496"
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="c7550-102">Buffer a dimensione fissa (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="c7550-102">Fixed Size Buffers (C# Programming Guide)</span></span>

<span data-ttu-id="c7550-103">In C# è possibile usare l'istruzione [fixed](../../language-reference/keywords/fixed-statement.md) per creare un buffer con una matrice di dimensioni fisse in una struttura di dati.</span><span class="sxs-lookup"><span data-stu-id="c7550-103">In C#, you can use the [fixed](../../language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="c7550-104">I buffer a dimensione fissa sono utili quando si scrivono metodi con interoperabilità con origini dati di altri linguaggi o piattaforme.</span><span class="sxs-lookup"><span data-stu-id="c7550-104">Fixed size buffers are useful when you write methods that interop with data sources from other languages or platforms.</span></span> <span data-ttu-id="c7550-105">La matrice fissa può accettare attributi o modificatori consentiti per i membri struct normali.</span><span class="sxs-lookup"><span data-stu-id="c7550-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="c7550-106">L'unica restrizione è rappresentata dal fatto che il tipo di matrice deve essere `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="c7550-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>

```csharp
private fixed char name[30];
```

## <a name="remarks"></a><span data-ttu-id="c7550-107">Note</span><span class="sxs-lookup"><span data-stu-id="c7550-107">Remarks</span></span>

<span data-ttu-id="c7550-108">Nel codice safe, uno struct C# che contiene una matrice non contiene gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="c7550-108">In safe code, a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="c7550-109">Lo struct contiene invece un riferimento agli elementi.</span><span class="sxs-lookup"><span data-stu-id="c7550-109">Instead, the struct contains a reference to the elements.</span></span> <span data-ttu-id="c7550-110">È possibile incorporare una matrice di dimensioni fisse in uno [struct](../../language-reference/keywords/struct.md) quando viene usata in un blocco di codice [unsafe](../../language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="c7550-110">You can embed an array of fixed size in a [struct](../../language-reference/keywords/struct.md) when it is used in an [unsafe](../../language-reference/keywords/unsafe.md) code block.</span></span>

<span data-ttu-id="c7550-111">Lo `struct` seguente ha una dimensione di 8 byte.</span><span class="sxs-lookup"><span data-stu-id="c7550-111">The following `struct` is 8 bytes in size.</span></span> <span data-ttu-id="c7550-112">La matrice `pathName` è un riferimento:</span><span class="sxs-lookup"><span data-stu-id="c7550-112">The `pathName` array is a reference:</span></span>

[!code-csharp[Struct with embedded array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#6)]

<span data-ttu-id="c7550-113">Un oggetto `struct` può contenere una matrice incorporata in codice unsafe.</span><span class="sxs-lookup"><span data-stu-id="c7550-113">A `struct` can contain an embedded array in unsafe code.</span></span> <span data-ttu-id="c7550-114">Nell'esempio seguente la matrice `fixedBuffer` è di dimensioni fisse.</span><span class="sxs-lookup"><span data-stu-id="c7550-114">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="c7550-115">Viene usata un'istruzione `fixed` per definire un puntatore al primo elemento.</span><span class="sxs-lookup"><span data-stu-id="c7550-115">You use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="c7550-116">Gli elementi della matrice sono accessibili tramite il puntatore.</span><span class="sxs-lookup"><span data-stu-id="c7550-116">You access the elements of the array through this pointer.</span></span> <span data-ttu-id="c7550-117">L'istruzione `fixed` blocca un'istanza di `fixedBuffer` in un percorso specifico nella memoria.</span><span class="sxs-lookup"><span data-stu-id="c7550-117">The `fixed` statement pins the `fixedBuffer` instance field to a specific location in memory.</span></span>

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#7)]

<span data-ttu-id="c7550-118">Le dimensioni della matrice `char` a 128 elementi sono di 256 byte.</span><span class="sxs-lookup"><span data-stu-id="c7550-118">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="c7550-119">I buffer [char](../../language-reference/keywords/char.md) a dimensione fissa accettano sempre due byte per carattere, indipendentemente dalla codifica.</span><span class="sxs-lookup"><span data-stu-id="c7550-119">Fixed size [char](../../language-reference/keywords/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="c7550-120">Questo vale anche quando viene eseguito il marshalling di buffer char in metodi API o struct con `CharSet = CharSet.Auto` o `CharSet = CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="c7550-120">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="c7550-121">Per ulteriori informazioni, vedere <xref:System.Runtime.InteropServices.CharSet>.</span><span class="sxs-lookup"><span data-stu-id="c7550-121">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>

<span data-ttu-id="c7550-122">L'esempio precedente mostra l'accesso ai campi `fixed` senza blocco, opzione disponibile a partire da C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="c7550-122">The  preceding example demonstrates accessing `fixed` fields without pinning, which is available starting with C# 7.3.</span></span>

<span data-ttu-id="c7550-123">Un'altra matrice a dimensione fissa comune è la matrice [bool](../../language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="c7550-123">Another common fixed-size array is the [bool](../../language-reference/keywords/bool.md) array.</span></span> <span data-ttu-id="c7550-124">Gli elementi in una matrice `bool` hanno sempre le dimensioni di un byte.</span><span class="sxs-lookup"><span data-stu-id="c7550-124">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="c7550-125">Le matrici `bool` non sono adatte per la creazione di matrici o buffer di bit.</span><span class="sxs-lookup"><span data-stu-id="c7550-125">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>

> [!NOTE]
> <span data-ttu-id="c7550-126">Eccezione fatta per la memoria creata con [stackalloc](../../language-reference/operators/stackalloc.md), il compilatore C# e Common Language Runtime (CLR) non eseguono controlli di sicurezza per sovraccarico del buffer.</span><span class="sxs-lookup"><span data-stu-id="c7550-126">Except for memory created by using [stackalloc](../../language-reference/operators/stackalloc.md), the C# compiler and the common language runtime (CLR) do not perform any security buffer overrun checks.</span></span> <span data-ttu-id="c7550-127">Come per tutto il codice unsafe, è necessario prestare la massima attenzione.</span><span class="sxs-lookup"><span data-stu-id="c7550-127">As with all unsafe code, use caution.</span></span>

<span data-ttu-id="c7550-128">I buffer unsafe sono diversi dalle normali matrici per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7550-128">Unsafe buffers differ from regular arrays in the following ways:</span></span>

- <span data-ttu-id="c7550-129">È possibile usare i buffer unsafe solo in un contesto unsafe.</span><span class="sxs-lookup"><span data-stu-id="c7550-129">You can only use unsafe buffers in an unsafe context.</span></span>
- <span data-ttu-id="c7550-130">I buffer unsafe sono sempre vettori, ovvero matrici unidimensionali.</span><span class="sxs-lookup"><span data-stu-id="c7550-130">Unsafe buffers are always vectors, or one-dimensional arrays.</span></span>
- <span data-ttu-id="c7550-131">La dichiarazione della matrice deve includere un conteggio, ad esempio `char id[8]`.</span><span class="sxs-lookup"><span data-stu-id="c7550-131">The declaration of the array should include a count, such as `char id[8]`.</span></span> <span data-ttu-id="c7550-132">Non è possibile usare `char id[]`.</span><span class="sxs-lookup"><span data-stu-id="c7550-132">You cannot use `char id[]`.</span></span>
- <span data-ttu-id="c7550-133">I buffer unsafe possono essere solo campi di istanza di struct in un contesto unsafe.</span><span class="sxs-lookup"><span data-stu-id="c7550-133">Unsafe buffers can only be instance fields of structs in an unsafe context.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7550-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7550-134">See also</span></span>

- [<span data-ttu-id="c7550-135">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c7550-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c7550-136">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="c7550-136">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="c7550-137">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="c7550-137">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="c7550-138">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="c7550-138">Interoperability</span></span>](../interop/index.md)
