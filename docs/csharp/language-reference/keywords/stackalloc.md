---
title: stackalloc (Riferimenti per C#)
ms.date: 04/12/2018
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: 905873cf7f576ff35a9bc1c182ce7ebe17920288
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269168"
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="f61e4-102">stackalloc (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f61e4-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="f61e4-103">La parola chiave `stackalloc` viene usata in un contesto di codice unsafe per allocare un blocco di memoria nello stack.</span><span class="sxs-lookup"><span data-stu-id="f61e4-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>

```csharp
int* block = stackalloc int[100];
```

## <a name="remarks"></a><span data-ttu-id="f61e4-104">Note</span><span class="sxs-lookup"><span data-stu-id="f61e4-104">Remarks</span></span>

<span data-ttu-id="f61e4-105">La parola chiave è valida solo per gli inizializzatori di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="f61e4-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="f61e4-106">Il codice seguente causa errori di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f61e4-106">The following code causes compiler errors.</span></span>

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
```

<span data-ttu-id="f61e4-107">A partire da C# 7.3, è possibile usare la sintassi dell'inizializzatore di matrice per le matrici `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="f61e4-107">Beginning with C# 7.3, you can use array initializer syntax for `stackalloc` arrays.</span></span> <span data-ttu-id="f61e4-108">Tutte le dichiarazioni seguenti dichiarano una matrice con tre elementi i cui valori sono i numeri interi `1`, `2` e `3`:</span><span class="sxs-lookup"><span data-stu-id="f61e4-108">All the following declarations declare an array with three elements whose values are the integers `1`, `2`, and `3`:</span></span>

```csharp
// Valid starting with C# 7.3
int* first = stackalloc int[3] { 1, 2, 3 };
int* second = stackalloc int[] { 1, 2, 3 };
int* third = stackalloc[] { 1, 2, 3 };
```

<span data-ttu-id="f61e4-109">Poiché vengono usati tipi puntatore, `stackalloc` richiede un contesto [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="f61e4-109">Because pointer types are involved, `stackalloc` requires an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="f61e4-110">Per altre informazioni, vedere [Codice unsafe e puntatori](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="f61e4-110">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md)</span></span> 

<span data-ttu-id="f61e4-111">La parola chiave `stackalloc` è come [_alloca](/cpp/c-runtime-library/reference/alloca) nella libreria di runtime del linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="f61e4-111">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>

## <a name="examples"></a><span data-ttu-id="f61e4-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="f61e4-112">Examples</span></span>

<span data-ttu-id="f61e4-113">Nell'esempio seguente vengono calcolati e visualizzati i primi 20 numeri della sequenza di Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="f61e4-113">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="f61e4-114">Ogni numero corrisponde alla somma dei due numeri precedenti.</span><span class="sxs-lookup"><span data-stu-id="f61e4-114">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="f61e4-115">Nel codice, un blocco di memoria di dimensioni sufficienti a contenere 20 elementi di tipo `int` viene allocato nello stack, non nell'heap.</span><span class="sxs-lookup"><span data-stu-id="f61e4-115">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="f61e4-116">L'indirizzo del blocco è archiviato nel puntatore `fib`.</span><span class="sxs-lookup"><span data-stu-id="f61e4-116">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="f61e4-117">Questa memoria non viene sottoposta alla procedura di Garbage Collection e non deve quindi essere bloccata con [fixed](fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f61e4-117">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](fixed-statement.md)).</span></span> <span data-ttu-id="f61e4-118">La durata del blocco di memoria è limitata alla durata del metodo che lo definisce.</span><span class="sxs-lookup"><span data-stu-id="f61e4-118">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="f61e4-119">Non è possibile liberare la memoria prima della restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="f61e4-119">You cannot free the memory before the method returns.</span></span>

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

<span data-ttu-id="f61e4-120">L'esempio seguente inizializza una matrice `stackalloc` di interi su una maschera di bit con un bit impostato in ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="f61e4-120">The following example initializes a `stackalloc` array of integers to a bit mask with one bit set in each element.</span></span> <span data-ttu-id="f61e4-121">Questo esempio dimostra la nuova sintassi dell'inizializzatore disponibile a partire da C# 7.3:</span><span class="sxs-lookup"><span data-stu-id="f61e4-121">This demonstrates the new initializer syntax available starting in C# 7.3:</span></span>

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a><span data-ttu-id="f61e4-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f61e4-122">Security</span></span>

<span data-ttu-id="f61e4-123">Il codice di tipo unsafe è meno sicuro delle alternative di tipo safe.</span><span class="sxs-lookup"><span data-stu-id="f61e4-123">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="f61e4-124">Tuttavia, l'uso di `stackalloc` attiva automaticamente le funzionalità di rilevazione del sovraccarico del buffer in Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f61e4-124">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="f61e4-125">Se viene rilevato un sovraccarico del buffer, il processo viene terminato il più rapidamente possibile per ridurre al minimo la possibilità che venga eseguito codice dannoso.</span><span class="sxs-lookup"><span data-stu-id="f61e4-125">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f61e4-126">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f61e4-126">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f61e4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f61e4-127">See Also</span></span>
 [<span data-ttu-id="f61e4-128">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f61e4-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f61e4-129">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f61e4-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f61e4-130">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="f61e4-130">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f61e4-131">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="f61e4-131">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="f61e4-132">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="f61e4-132">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
