---
title: Buffer a dimensione fissa (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.assetid: 6220d454-947c-4977-ac9d-9308c6ed5051
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3f99c2c6d477fca988fcca77de5ca5c2f8addd4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="3b3e9-102">Buffer a dimensione fissa (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3b3e9-102">Fixed Size Buffers (C# Programming Guide)</span></span>
<span data-ttu-id="3b3e9-103">In C# è possibile usare l'istruzione [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) per creare un buffer con una matrice di dimensioni fisse in una struttura di dati.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-103">In C#, you can use the [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="3b3e9-104">Ciò si rivela utile quando si usa codice esistente, ad esempio codice scritto in altri linguaggi, DLL preesistenti o progetti COM.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-104">This is useful when you are working with existing code, such as code written in other languages, pre-existing DLLs or COM projects.</span></span> <span data-ttu-id="3b3e9-105">La matrice fissa può accettare attributi o modificatori consentiti per i membri struct normali.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="3b3e9-106">L'unica restrizione è rappresentata dal fatto che il tipo di matrice deve essere `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>  
  
```  
private fixed char name[30];  
```  
  
## <a name="remarks"></a><span data-ttu-id="3b3e9-107">Note</span><span class="sxs-lookup"><span data-stu-id="3b3e9-107">Remarks</span></span>  
 <span data-ttu-id="3b3e9-108">Nelle versioni precedenti di C# era difficile dichiarare una struttura a dimensioni fisse di tipo C++, in quanto uno struct C# contenente una matrice non include gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-108">In early versions of C#, declaring a C++ style fixed-size structure was difficult because a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="3b3e9-109">Lo struct contiene invece un riferimento agli elementi.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-109">Instead, the struct contains a reference to the elements.</span></span>  
  
 <span data-ttu-id="3b3e9-110">In C# 2.0 è stata aggiunta la possibilità di incorporare una matrice di dimensioni fisse in uno [struct](../../../csharp/language-reference/keywords/struct.md) quando viene usata in un blocco di codice [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="3b3e9-110">C# 2.0 added the ability to embed an array of fixed size in a [struct](../../../csharp/language-reference/keywords/struct.md) when it is used in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) code block.</span></span>  
  
 <span data-ttu-id="3b3e9-111">Ad esempio, prima di C# 2.0, lo struct `struct` seguente avrebbe avuto una dimensione di 8 byte.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-111">For example, before C# 2.0, the following `struct` would be 8 bytes in size.</span></span> <span data-ttu-id="3b3e9-112">La matrice `pathName` è un riferimento alla matrice con allocazione heap:</span><span class="sxs-lookup"><span data-stu-id="3b3e9-112">The `pathName` array is a reference to the heap-allocated array:</span></span>  
  
 [!code-csharp[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]  
  
 <span data-ttu-id="3b3e9-113">A partire da C# 2.0, un oggetto `struct` può contenere una matrice incorporata.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-113">Beginning with C# 2.0, a `struct` can contain an embedded array.</span></span> <span data-ttu-id="3b3e9-114">Nell'esempio seguente la matrice `fixedBuffer` è di dimensioni fisse.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-114">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="3b3e9-115">Per accedere agli elementi della matrice, si usa un'istruzione `fixed` per definire un puntatore al primo elemento.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-115">To access the elements of the array, you use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="3b3e9-116">L'istruzione `fixed` blocca un'istanza di `fixedBuffer` a un percorso specifico nella memoria.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-116">The `fixed` statement pins an instance of `fixedBuffer` to a specific location in memory.</span></span>  
  
 [!code-csharp[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]  
  
 <span data-ttu-id="3b3e9-117">Le dimensioni della matrice `char` a 128 elementi sono di 256 byte.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-117">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="3b3e9-118">I buffer [char](../../../csharp/language-reference/keywords/char.md) a dimensione fissa accettano sempre due byte per carattere, indipendentemente dalla codifica.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-118">Fixed size [char](../../../csharp/language-reference/keywords/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="3b3e9-119">Questo vale anche quando viene eseguito il marshalling di buffer char in metodi API o struct con `CharSet = CharSet.Auto` o `CharSet = CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-119">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="3b3e9-120">Per altre informazioni, vedere <xref:System.Runtime.InteropServices.CharSet>.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-120">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>  
  
 <span data-ttu-id="3b3e9-121">Un'altra matrice a dimensione fissa comune è la matrice [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="3b3e9-121">Another common fixed-size array is the [bool](../../../csharp/language-reference/keywords/bool.md) array.</span></span> <span data-ttu-id="3b3e9-122">Gli elementi in una matrice `bool` hanno sempre le dimensioni di un byte.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-122">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="3b3e9-123">Le matrici `bool` non sono adatte per la creazione di matrici o buffer di bit.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-123">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b3e9-124">Eccezione fatta per la memoria creata con [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md), il compilatore C# e Common Language Runtime (CLR) non eseguono controlli di sicurezza per sovraccarico del buffer.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-124">Except for memory created by using [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md), the C# compiler and the common language runtime (CLR) do not perform any security buffer overrun checks.</span></span> <span data-ttu-id="3b3e9-125">Come per tutto il codice unsafe, è necessario prestare la massima attenzione.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-125">As with all unsafe code, use caution.</span></span>  
  
 <span data-ttu-id="3b3e9-126">I buffer unsafe sono diversi dalle normali matrici per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b3e9-126">Unsafe buffers differ from regular arrays in the following ways:</span></span>  
  
-   <span data-ttu-id="3b3e9-127">È possibile usare i buffer unsafe solo in un contesto unsafe.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-127">You can only use unsafe buffers in an unsafe context.</span></span>  
  
-   <span data-ttu-id="3b3e9-128">I buffer unsafe sono sempre vettori, ovvero matrici unidimensionali.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-128">Unsafe buffers are always vectors, or one-dimensional arrays.</span></span>  
  
-   <span data-ttu-id="3b3e9-129">La dichiarazione della matrice deve includere un conteggio, ad esempio `char id[8]`.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-129">The declaration of the array should include a count, such as `char id[8]`.</span></span> <span data-ttu-id="3b3e9-130">Non è invece possibile usare `char id[]`.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-130">You cannot use `char id[]` instead.</span></span>  
  
-   <span data-ttu-id="3b3e9-131">I buffer unsafe possono essere solo campi di istanza di struct in un contesto unsafe.</span><span class="sxs-lookup"><span data-stu-id="3b3e9-131">Unsafe buffers can only be instance fields of structs in an unsafe context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b3e9-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b3e9-132">See Also</span></span>  
 [<span data-ttu-id="3b3e9-133">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3b3e9-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3b3e9-134">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="3b3e9-134">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="3b3e9-135">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="3b3e9-135">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="3b3e9-136">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="3b3e9-136">Interoperability</span></span>](../../../csharp/programming-guide/interop/index.md)
