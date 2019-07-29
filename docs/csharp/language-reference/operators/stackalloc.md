---
title: Operatore stackalloc - Riferimenti per C#
ms.custom: seodec18
ms.date: 06/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: f211acaa8c47ab42a1f7f06cff6c35570cd22b75
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433834"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="8d3b4-102">Operatore stackalloc (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="8d3b4-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="8d3b4-103">L'operatore `stackalloc` alloca un blocco di memoria nello stack.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="8d3b4-104">Un blocco di memoria allocato nello stack, creato durante l'esecuzione del metodo, viene automaticamente eliminato alla restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="8d3b4-105">Non è possibile eliminare esplicitamente memoria allocata con l'operatore `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="8d3b4-106">Un blocco di memoria allocato nello stack non è soggetto a una [Garbage Collection](../../../standard/garbage-collection/index.md) e non deve necessariamente essere aggiunto con l'[istruzione `fixed`](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8d3b4-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with the [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="8d3b4-107">Nell'espressione `stackalloc T[E]`, `T` deve essere un [tipo non gestito](../builtin-types/unmanaged-types.md) e `E` deve essere un'espressione di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-107">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must be an expression of type `int`.</span></span>

<span data-ttu-id="8d3b4-108">È possibile assegnare il risultato dell'operatore `stackalloc` a una variabile di uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d3b4-108">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="8d3b4-109">A partire da C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> o <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-109">Starting with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="8d3b4-110">Non è necessario usare un contesto [unsafe](../keywords/unsafe.md) quando si assegna un blocco di memoria allocato nello stack a una variabile <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-110">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="8d3b4-111">Se si usano questi tipi, è possibile applicare un'espressione `stackalloc` in espressioni [condizionali](conditional-operator.md) o di assegnazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-111">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  > [!NOTE]
  > <span data-ttu-id="8d3b4-112">In presenza di memoria allocata nello stack, è consigliabile usare il tipo <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> ogni qualvolta sia possibile.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="8d3b4-113">Un [tipo di puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md), come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="8d3b4-114">Come illustrato nell'esempio precedente, quando si usa un tipo di puntatore è necessario adottare un contesto `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

<span data-ttu-id="8d3b4-115">Il contenuto della memoria appena allocata non è definito.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-115">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="8d3b4-116">A partire da C# 7.3, è possibile usare la sintassi dell'inizializzatore di matrice per definire il contenuto della memoria appena allocata.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-116">Starting with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="8d3b4-117">Nell'esempio seguente vengono illustrati vari modi per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-117">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a><span data-ttu-id="8d3b4-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8d3b4-118">Security</span></span>

<span data-ttu-id="8d3b4-119">L'uso di `stackalloc` attiva automaticamente le funzionalità di rilevazione del sovraccarico del buffer in Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8d3b4-119">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="8d3b4-120">Se viene rilevato un sovraccarico del buffer, il processo viene terminato il più rapidamente possibile per ridurre al minimo la possibilità che venga eseguito codice dannoso.</span><span class="sxs-lookup"><span data-stu-id="8d3b4-120">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8d3b4-121">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="8d3b4-121">C# language specification</span></span>

<span data-ttu-id="8d3b4-122">Per altre informazioni, vedere la sezione [Allocazione nello stack](~/_csharplang/spec/unsafe-code.md#stack-allocation) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="8d3b4-122">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8d3b4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d3b4-123">See also</span></span>

- [<span data-ttu-id="8d3b4-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="8d3b4-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8d3b4-125">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="8d3b4-125">C# operators</span></span>](index.md)
- [<span data-ttu-id="8d3b4-126">Operatori relativi al puntatore</span><span class="sxs-lookup"><span data-stu-id="8d3b4-126">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="8d3b4-127">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="8d3b4-127">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="8d3b4-128">Tipi correlati alla memoria e agli intervalli</span><span class="sxs-lookup"><span data-stu-id="8d3b4-128">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
