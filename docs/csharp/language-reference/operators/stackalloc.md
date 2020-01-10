---
title: Operatore stackalloc - Riferimenti per C#
ms.date: 09/20/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 5654cae622cd94c8dad7e58fbc8a99fcf48391a9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712624"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="60427-102">Operatore stackalloc (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="60427-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="60427-103">L'operatore `stackalloc` alloca un blocco di memoria nello stack.</span><span class="sxs-lookup"><span data-stu-id="60427-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="60427-104">Un blocco di memoria allocato nello stack, creato durante l'esecuzione del metodo, viene automaticamente eliminato alla restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="60427-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="60427-105">Non è possibile eliminare esplicitamente memoria allocata con l'operatore `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="60427-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="60427-106">Un blocco di memoria allocata nello stack non è soggetto a [Garbage Collection](../../../standard/garbage-collection/index.md) e non deve essere aggiunto con un' [istruzione`fixed`](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="60427-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with a [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="60427-107">È possibile assegnare il risultato dell'operatore `stackalloc` a una variabile di uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="60427-107">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="60427-108">A partire C# da 7,2, <xref:System.Span%601?displayProperty=nameWithType> o <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="60427-108">Beginning with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="60427-109">Non è necessario usare un contesto [unsafe](../keywords/unsafe.md) quando si assegna un blocco di memoria allocato nello stack a una variabile <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="60427-109">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="60427-110">Se si usano questi tipi, è possibile applicare un'espressione `stackalloc` in espressioni [condizionali](conditional-operator.md) o di assegnazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="60427-110">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="60427-111">A partire C# da 8,0, è possibile usare un'espressione `stackalloc` all'interno di altre espressioni ogni volta che è consentita una variabile <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="60427-111">Beginning with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](~/samples/csharp/language-reference/operators/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="60427-112">In presenza di memoria allocata nello stack, è consigliabile usare il tipo <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> ogni qualvolta sia possibile.</span><span class="sxs-lookup"><span data-stu-id="60427-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="60427-113">Un [tipo di puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md), come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="60427-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="60427-114">Come illustrato nell'esempio precedente, quando si usa un tipo di puntatore è necessario adottare un contesto `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="60427-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="60427-115">Nel caso dei tipi di puntatore, è possibile usare un'espressione `stackalloc` solo in una dichiarazione di variabile locale per inizializzare la variabile.</span><span class="sxs-lookup"><span data-stu-id="60427-115">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="60427-116">Il contenuto della memoria appena allocata non è definito.</span><span class="sxs-lookup"><span data-stu-id="60427-116">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="60427-117">A partire C# da 7,3, è possibile usare la sintassi dell'inizializzatore di matrici per definire il contenuto della memoria appena allocata.</span><span class="sxs-lookup"><span data-stu-id="60427-117">Beginning with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="60427-118">Nell'esempio seguente vengono illustrati vari modi per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="60427-118">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

<span data-ttu-id="60427-119">Nell'espressione `stackalloc T[E]``T` deve essere un [tipo non gestito](../builtin-types/unmanaged-types.md) e `E` deve essere un'espressione di tipo [int](../builtin-types/integral-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="60427-119">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must be an expression of type [int](../builtin-types/integral-numeric-types.md).</span></span>

## <a name="security"></a><span data-ttu-id="60427-120">Sicurezza -</span><span class="sxs-lookup"><span data-stu-id="60427-120">Security</span></span>

<span data-ttu-id="60427-121">L'uso di `stackalloc` attiva automaticamente le funzionalità di rilevazione del sovraccarico del buffer in Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="60427-121">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="60427-122">Se viene rilevato un sovraccarico del buffer, il processo viene terminato il più rapidamente possibile per ridurre al minimo la possibilità che venga eseguito codice dannoso.</span><span class="sxs-lookup"><span data-stu-id="60427-122">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="60427-123">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="60427-123">C# language specification</span></span>

<span data-ttu-id="60427-124">Per ulteriori informazioni, vedere la sezione [allocazione dello stack](~/_csharplang/spec/unsafe-code.md#stack-allocation) della [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md) e la nota relativa alla funzionalità [Consenti `stackalloc` in contesti annidati](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) .</span><span class="sxs-lookup"><span data-stu-id="60427-124">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the [Permit `stackalloc` in nested contexts](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) feature proposal note.</span></span>

## <a name="see-also"></a><span data-ttu-id="60427-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60427-125">See also</span></span>

- [<span data-ttu-id="60427-126">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="60427-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="60427-127">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="60427-127">C# operators</span></span>](index.md)
- [<span data-ttu-id="60427-128">Operatori relativi al puntatore</span><span class="sxs-lookup"><span data-stu-id="60427-128">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="60427-129">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="60427-129">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="60427-130">Tipi correlati alla memoria e agli intervalli</span><span class="sxs-lookup"><span data-stu-id="60427-130">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
