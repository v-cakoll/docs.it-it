---
title: Parola chiave stackalloc - Riferimenti per C#
ms.custom: seodec18
ms.date: 04/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: 654e225ef98b13aeb4f689e17b1ff378e6002d28
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063922"
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="b154b-102">stackalloc (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b154b-102">stackalloc (C# Reference)</span></span>

<span data-ttu-id="b154b-103">La parola chiave `stackalloc` viene usata per allocare un blocco di memoria nello stack.</span><span class="sxs-lookup"><span data-stu-id="b154b-103">The `stackalloc` keyword is used to allocate a block of memory on the stack.</span></span>

```csharp
Span<int> block = stackalloc int[100];
```

<span data-ttu-id="b154b-104">L'assegnazione del blocco allocato a un <xref:System.Span%601?displayName=nameWithType> invece che a un `int*` consente le allocazioni di stack in un blocco sicuro.</span><span class="sxs-lookup"><span data-stu-id="b154b-104">Assigning the allocated block to a <xref:System.Span%601?displayName=nameWithType> instead of an `int*` allows stack allocations in a safe block.</span></span> <span data-ttu-id="b154b-105">Il contesto `unsafe` non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b154b-105">The `unsafe` context is not required.</span></span>

## <a name="remarks"></a><span data-ttu-id="b154b-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b154b-106">Remarks</span></span>

<span data-ttu-id="b154b-107">La parola chiave è valida solo per gli inizializzatori di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="b154b-107">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="b154b-108">Il codice seguente causa errori di compilazione.</span><span class="sxs-lookup"><span data-stu-id="b154b-108">The following code causes compiler errors.</span></span>

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
Span<int> span;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
span = stackalloc int[100];
```

<span data-ttu-id="b154b-109">A partire da C# 7.3, è possibile usare la sintassi dell'inizializzatore di matrice per le matrici `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="b154b-109">Beginning with C# 7.3, you can use array initializer syntax for `stackalloc` arrays.</span></span> <span data-ttu-id="b154b-110">Tutte le dichiarazioni seguenti dichiarano una matrice con tre elementi i cui valori sono i numeri interi `1`, `2` e `3`.</span><span class="sxs-lookup"><span data-stu-id="b154b-110">All the following declarations declare an array with three elements whose values are the integers `1`, `2`, and `3`.</span></span> <span data-ttu-id="b154b-111">La seconda inizializzazione assegna la memoria a un <xref:System.ReadOnlySpan%601>, a indicare che la memoria non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="b154b-111">The second initialization assigns the memory to a <xref:System.ReadOnlySpan%601>, indicating that the memory cannot be modified.</span></span>

```csharp
// Valid starting with C# 7.3
Span<int> first = stackalloc int[3] { 1, 2, 3 };
ReadOnlySpan<int> second = stackalloc int[] { 1, 2, 3 };
Span<int> third = stackalloc[] { 1, 2, 3 };
```

<span data-ttu-id="b154b-112">Quando vengono usati tipi puntatore, `stackalloc` richiede un contesto [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="b154b-112">When pointer types are involved, `stackalloc` requires an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="b154b-113">Per altre informazioni, vedere [Codice unsafe e puntatori](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="b154b-113">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="b154b-114">La parola chiave `stackalloc` è come [_alloca](/cpp/c-runtime-library/reference/alloca) nella libreria di runtime del linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="b154b-114">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>

## <a name="examples"></a><span data-ttu-id="b154b-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="b154b-115">Examples</span></span>

<span data-ttu-id="b154b-116">Nell'esempio seguente vengono calcolati e visualizzati i primi 20 numeri della sequenza di Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="b154b-116">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="b154b-117">Ogni numero corrisponde alla somma dei due numeri precedenti.</span><span class="sxs-lookup"><span data-stu-id="b154b-117">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="b154b-118">Nel codice, un blocco di memoria di dimensioni sufficienti a contenere 20 elementi di tipo `int` viene allocato nello stack, non nell'heap.</span><span class="sxs-lookup"><span data-stu-id="b154b-118">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="b154b-119">L'indirizzo del blocco è archiviato nel `fib` `Span`.</span><span class="sxs-lookup"><span data-stu-id="b154b-119">The address of the block is stored in the `Span` `fib`.</span></span> <span data-ttu-id="b154b-120">Questa memoria non viene sottoposta alla procedura di Garbage Collection e non deve quindi essere bloccata con [fixed](fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b154b-120">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](fixed-statement.md)).</span></span> <span data-ttu-id="b154b-121">La durata del blocco di memoria è limitata alla durata del metodo che lo definisce.</span><span class="sxs-lookup"><span data-stu-id="b154b-121">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="b154b-122">Non è possibile liberare la memoria prima della restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="b154b-122">You cannot free the memory before the method returns.</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

<span data-ttu-id="b154b-123">L'esempio seguente inizializza una matrice `stackalloc` di interi su una maschera di bit con un bit impostato in ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="b154b-123">The following example initializes a `stackalloc` array of integers to a bit mask with one bit set in each element.</span></span> <span data-ttu-id="b154b-124">Questo esempio dimostra la nuova sintassi dell'inizializzatore disponibile a partire da C# 7.3:</span><span class="sxs-lookup"><span data-stu-id="b154b-124">This demonstrates the new initializer syntax available starting in C# 7.3:</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a><span data-ttu-id="b154b-125">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b154b-125">Security</span></span>

<span data-ttu-id="b154b-126">È consigliabile usare <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> quando possibile perché il codice di tipo unsafe è meno sicuro delle alternative di tipo safe.</span><span class="sxs-lookup"><span data-stu-id="b154b-126">You should use <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> when possible because unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="b154b-127">Anche in presenza di puntatori, l'uso di `stackalloc` attiva automaticamente le funzionalità di rilevazione del sovraccarico del buffer in Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b154b-127">Even when used with pointers, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="b154b-128">Se viene rilevato un sovraccarico del buffer, il processo viene terminato il più rapidamente possibile per ridurre al minimo la possibilità che venga eseguito codice dannoso.</span><span class="sxs-lookup"><span data-stu-id="b154b-128">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b154b-129">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b154b-129">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b154b-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b154b-130">See also</span></span>

- [<span data-ttu-id="b154b-131">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b154b-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b154b-132">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b154b-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b154b-133">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="b154b-133">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b154b-134">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="b154b-134">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="b154b-135">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="b154b-135">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
