---
title: Stackalloc espressione - Riferimento c'è
ms.date: 03/13/2020
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc expression [C#]
ms.openlocfilehash: 2e99ce8b1e44dfa040c1acac799a3a55b375bd91
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546601"
---
# <a name="stackalloc-expression-c-reference"></a><span data-ttu-id="8ce5b-102">stackalloc (riferimenti per C</span><span class="sxs-lookup"><span data-stu-id="8ce5b-102">stackalloc expression (C# reference)</span></span>

<span data-ttu-id="8ce5b-103">Un'espressione `stackalloc` alloca un blocco di memoria nello stack.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-103">A `stackalloc` expression allocates a block of memory on the stack.</span></span> <span data-ttu-id="8ce5b-104">Un blocco di memoria allocato nello stack, creato durante l'esecuzione del metodo, viene automaticamente eliminato alla restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="8ce5b-105">Non è possibile liberare `stackalloc`in modo esplicito la memoria allocata con .</span><span class="sxs-lookup"><span data-stu-id="8ce5b-105">You cannot explicitly free the memory allocated with `stackalloc`.</span></span> <span data-ttu-id="8ce5b-106">Un blocco di memoria allocato dello stack non è soggetto a [Garbage Collection](../../../standard/garbage-collection/index.md) e non deve essere bloccato con [ `fixed` un'istruzione](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8ce5b-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with a [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="8ce5b-107">È possibile assegnare `stackalloc` il risultato di un'espressione a una variabile di uno dei seguenti tipi:</span><span class="sxs-lookup"><span data-stu-id="8ce5b-107">You can assign the result of a `stackalloc` expression to a variable of one of the following types:</span></span>

- <span data-ttu-id="8ce5b-108">A partire da C <xref:System.Span%601?displayProperty=nameWithType> , <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>7.2, o , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8ce5b-108">Beginning with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](snippets/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="8ce5b-109">Non è necessario usare un contesto [unsafe](../keywords/unsafe.md) quando si assegna un blocco di memoria allocato nello stack a una variabile <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-109">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="8ce5b-110">Se si usano questi tipi, è possibile applicare un'espressione `stackalloc` in espressioni [condizionali](conditional-operator.md) o di assegnazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-110">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](snippets/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="8ce5b-111">A partire dalla versione 8.0 `stackalloc` di C, è <xref:System.Span%601> <xref:System.ReadOnlySpan%601> possibile usare un'espressione all'interno di altre espressioni ogni volta che è consentita una variabile o, come illustrato nell'esempio seguente:At beginning with C's 8.0, you can use a expression inside other expressions whenever a or variable is allowed, as the following example shows:</span><span class="sxs-lookup"><span data-stu-id="8ce5b-111">Beginning with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](snippets/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="8ce5b-112">In presenza di memoria allocata nello stack, è consigliabile usare il tipo <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> ogni qualvolta sia possibile.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="8ce5b-113">Un [tipo di puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md), come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](snippets/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="8ce5b-114">Come illustrato nell'esempio precedente, quando si usa un tipo di puntatore è necessario adottare un contesto `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="8ce5b-115">Nel caso dei tipi puntatore, `stackalloc` è possibile utilizzare un'espressione solo in una dichiarazione di variabile locale per inizializzare la variabile.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-115">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="8ce5b-116">La quantità di memoria disponibile nello stack è limitata.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-116">The amount of memory available on the stack is limited.</span></span> <span data-ttu-id="8ce5b-117">Se si alloca troppa memoria <xref:System.StackOverflowException> nello stack, viene generata un'eccezione .</span><span class="sxs-lookup"><span data-stu-id="8ce5b-117">If you allocate too much memory on the stack, a <xref:System.StackOverflowException> is thrown.</span></span> <span data-ttu-id="8ce5b-118">Per evitare che, seguire le regole riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="8ce5b-118">To avoid that, follow the rules below:</span></span>

- <span data-ttu-id="8ce5b-119">Limitare la quantità di `stackalloc`memoria allocata con:</span><span class="sxs-lookup"><span data-stu-id="8ce5b-119">Limit the amount of memory you allocate with `stackalloc`:</span></span>

  [!code-csharp[limit stackalloc](snippets/StackallocOperator.cs#LimitStackalloc)]

  <span data-ttu-id="8ce5b-120">Poiché la quantità di memoria disponibile nello stack dipende dall'ambiente in cui viene eseguito il codice, essere conservativi quando si definisce il valore limite effettivo.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-120">Because the amount of memory available on the stack depends on the environment in which the code is executed, be conservative when you define the actual limit value.</span></span>

- <span data-ttu-id="8ce5b-121">Evitare `stackalloc` di utilizzare loop interni.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-121">Avoid using `stackalloc` inside loops.</span></span> <span data-ttu-id="8ce5b-122">Allocare il blocco di memoria all'esterno di un ciclo e riutilizzarlo all'interno del ciclo.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-122">Allocate the memory block outside a loop and reuse it inside the loop.</span></span>

<span data-ttu-id="8ce5b-123">Il contenuto della memoria appena allocata non è definito.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-123">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="8ce5b-124">È necessario inizializzarlo prima dell'uso.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-124">You should initialize it before the use.</span></span> <span data-ttu-id="8ce5b-125">Ad esempio, è <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> possibile utilizzare il metodo che imposta `T`tutti gli elementi sul valore predefinito di tipo .</span><span class="sxs-lookup"><span data-stu-id="8ce5b-125">For example, you can use the <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> method that sets all the items to the default value of type `T`.</span></span>

<span data-ttu-id="8ce5b-126">A partire dalla versione 7.3 di C, è possibile usare la sintassi dell'inizializzatore di matrice per definire il contenuto della memoria appena allocata.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-126">Beginning with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="8ce5b-127">Nell'esempio seguente vengono illustrati vari modi per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-127">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](snippets/StackallocOperator.cs#StackallocInit)]

<span data-ttu-id="8ce5b-128">In `stackalloc T[E]`expression `T` , deve essere `E` un tipo non [gestito](../builtin-types/unmanaged-types.md) e deve restituire un valore [int](../builtin-types/integral-numeric-types.md) non negativo.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-128">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must evaluate to a non-negative [int](../builtin-types/integral-numeric-types.md) value.</span></span>

## <a name="security"></a><span data-ttu-id="8ce5b-129">Security</span><span class="sxs-lookup"><span data-stu-id="8ce5b-129">Security</span></span>

<span data-ttu-id="8ce5b-130">L'uso di `stackalloc` attiva automaticamente le funzionalità di rilevazione del sovraccarico del buffer in Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8ce5b-130">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="8ce5b-131">Se viene rilevato un sovraccarico del buffer, il processo viene terminato il più rapidamente possibile per ridurre al minimo la possibilità che venga eseguito codice dannoso.</span><span class="sxs-lookup"><span data-stu-id="8ce5b-131">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8ce5b-132">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="8ce5b-132">C# language specification</span></span>

<span data-ttu-id="8ce5b-133">Per altre informazioni, vedere la sezione [Relativa all'allocazione dello stack](~/_csharplang/spec/unsafe-code.md#stack-allocation) della specifica del [linguaggio C](~/_csharplang/spec/introduction.md) ' e la nota proposta di funzionalità Consenti [ `stackalloc` nei contesti annidati.](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md)</span><span class="sxs-lookup"><span data-stu-id="8ce5b-133">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the [Permit `stackalloc` in nested contexts](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) feature proposal note.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ce5b-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ce5b-134">See also</span></span>

- [<span data-ttu-id="8ce5b-135">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="8ce5b-135">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8ce5b-136">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="8ce5b-136">C# operators</span></span>](index.md)
- [<span data-ttu-id="8ce5b-137">Operatori relativi al puntatore</span><span class="sxs-lookup"><span data-stu-id="8ce5b-137">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="8ce5b-138">Tipi puntatore</span><span class="sxs-lookup"><span data-stu-id="8ce5b-138">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="8ce5b-139">Tipi correlati alla memoria e agli intervalli</span><span class="sxs-lookup"><span data-stu-id="8ce5b-139">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="8ce5b-140">Cosa fare e cosa non fare di stackalloc</span><span class="sxs-lookup"><span data-stu-id="8ce5b-140">Dos and Don'ts of stackalloc</span></span>](https://vcsjones.dev/2020/02/24/stackalloc/)
