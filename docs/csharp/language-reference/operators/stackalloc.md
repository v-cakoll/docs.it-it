---
title: Operatore stackalloc - Riferimenti per C#
ms.date: 09/20/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 9c9767e0c9945a9589d049fa7abba192cb928ad5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846252"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="7f908-102">Operatore stackalloc (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7f908-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="7f908-103">L'operatore `stackalloc` alloca un blocco di memoria nello stack.</span><span class="sxs-lookup"><span data-stu-id="7f908-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="7f908-104">Un blocco di memoria allocato nello stack, creato durante l'esecuzione del metodo, viene automaticamente eliminato alla restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="7f908-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="7f908-105">Non è possibile eliminare esplicitamente memoria allocata con l'operatore `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="7f908-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="7f908-106">Un blocco di memoria allocato dello stack non è soggetto a [Garbage Collection](../../../standard/garbage-collection/index.md) e non deve essere bloccato con [ `fixed` un'istruzione](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7f908-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with a [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="7f908-107">È possibile assegnare il risultato dell'operatore `stackalloc` a una variabile di uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f908-107">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="7f908-108">A partire da C <xref:System.Span%601?displayProperty=nameWithType> , <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>7.2, o , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="7f908-108">Beginning with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](snippets/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="7f908-109">Non è necessario usare un contesto [unsafe](../keywords/unsafe.md) quando si assegna un blocco di memoria allocato nello stack a una variabile <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="7f908-109">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="7f908-110">Se si usano questi tipi, è possibile applicare un'espressione `stackalloc` in espressioni [condizionali](conditional-operator.md) o di assegnazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7f908-110">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](snippets/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="7f908-111">A partire dalla versione 8.0 `stackalloc` di C, è <xref:System.Span%601> <xref:System.ReadOnlySpan%601> possibile usare un'espressione all'interno di altre espressioni ogni volta che è consentita una variabile o, come illustrato nell'esempio seguente:At beginning with C's 8.0, you can use a expression inside other expressions whenever a or variable is allowed, as the following example shows:</span><span class="sxs-lookup"><span data-stu-id="7f908-111">Beginning with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](snippets/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="7f908-112">In presenza di memoria allocata nello stack, è consigliabile usare il tipo <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> ogni qualvolta sia possibile.</span><span class="sxs-lookup"><span data-stu-id="7f908-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="7f908-113">Un [tipo di puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md), come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7f908-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](snippets/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="7f908-114">Come illustrato nell'esempio precedente, quando si usa un tipo di puntatore è necessario adottare un contesto `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="7f908-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="7f908-115">Nel caso dei tipi puntatore, `stackalloc` è possibile utilizzare un'espressione solo in una dichiarazione di variabile locale per inizializzare la variabile.</span><span class="sxs-lookup"><span data-stu-id="7f908-115">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="7f908-116">Il contenuto della memoria appena allocata non è definito.</span><span class="sxs-lookup"><span data-stu-id="7f908-116">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="7f908-117">A partire dalla versione 7.3 di C, è possibile usare la sintassi dell'inizializzatore di matrice per definire il contenuto della memoria appena allocata.</span><span class="sxs-lookup"><span data-stu-id="7f908-117">Beginning with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="7f908-118">Nell'esempio seguente vengono illustrati vari modi per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="7f908-118">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](snippets/StackallocOperator.cs#StackallocInit)]

<span data-ttu-id="7f908-119">In `stackalloc T[E]`expression `T` , deve essere `E` un tipo non [gestito](../builtin-types/unmanaged-types.md) e deve essere un'espressione di tipo [int](../builtin-types/integral-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f908-119">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must be an expression of type [int](../builtin-types/integral-numeric-types.md).</span></span>

## <a name="security"></a><span data-ttu-id="7f908-120">Security</span><span class="sxs-lookup"><span data-stu-id="7f908-120">Security</span></span>

<span data-ttu-id="7f908-121">L'uso di `stackalloc` attiva automaticamente le funzionalità di rilevazione del sovraccarico del buffer in Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7f908-121">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="7f908-122">Se viene rilevato un sovraccarico del buffer, il processo viene terminato il più rapidamente possibile per ridurre al minimo la possibilità che venga eseguito codice dannoso.</span><span class="sxs-lookup"><span data-stu-id="7f908-122">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7f908-123">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7f908-123">C# language specification</span></span>

<span data-ttu-id="7f908-124">Per altre informazioni, vedere la sezione [Relativa all'allocazione dello stack](~/_csharplang/spec/unsafe-code.md#stack-allocation) della specifica del [linguaggio C](~/_csharplang/spec/introduction.md) ' e la nota proposta di funzionalità Consenti [ `stackalloc` nei contesti annidati.](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md)</span><span class="sxs-lookup"><span data-stu-id="7f908-124">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the [Permit `stackalloc` in nested contexts](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) feature proposal note.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f908-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f908-125">See also</span></span>

- [<span data-ttu-id="7f908-126">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="7f908-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="7f908-127">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="7f908-127">C# operators</span></span>](index.md)
- [<span data-ttu-id="7f908-128">Operatori relativi al puntatore</span><span class="sxs-lookup"><span data-stu-id="7f908-128">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="7f908-129">Tipi di puntatore</span><span class="sxs-lookup"><span data-stu-id="7f908-129">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="7f908-130">Tipi correlati alla memoria e agli intervalli</span><span class="sxs-lookup"><span data-stu-id="7f908-130">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
