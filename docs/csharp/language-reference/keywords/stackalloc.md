---
title: stackalloc (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ad4453f889a344fcd44dfad44a30fef07380b6a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="9d961-102">stackalloc (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="9d961-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="9d961-103">La parola chiave `stackalloc` viene usata in un contesto di codice unsafe per allocare un blocco di memoria nello stack.</span><span class="sxs-lookup"><span data-stu-id="9d961-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>  
  
```  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a><span data-ttu-id="9d961-104">Note</span><span class="sxs-lookup"><span data-stu-id="9d961-104">Remarks</span></span>  
 <span data-ttu-id="9d961-105">La parola chiave è valida solo per gli inizializzatori di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="9d961-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="9d961-106">Il codice seguente causa errori di compilazione.</span><span class="sxs-lookup"><span data-stu-id="9d961-106">The following code causes compiler errors.</span></span>  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 <span data-ttu-id="9d961-107">Poiché vengono usati tipi puntatore, `stackalloc` richiede un contesto [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="9d961-107">Because pointer types are involved, `stackalloc` requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="9d961-108">Per altre informazioni, vedere [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="9d961-108">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="9d961-109">La parola chiave `stackalloc` è come [_alloca](/cpp/c-runtime-library/reference/alloca) nella libreria di runtime del linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="9d961-109">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>  
  
 <span data-ttu-id="9d961-110">Nell'esempio seguente vengono calcolati e visualizzati i primi 20 numeri della sequenza di Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="9d961-110">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="9d961-111">Ogni numero corrisponde alla somma dei due numeri precedenti.</span><span class="sxs-lookup"><span data-stu-id="9d961-111">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="9d961-112">Nel codice, un blocco di memoria di dimensioni sufficienti a contenere 20 elementi di tipo `int` viene allocato nello stack, non nell'heap.</span><span class="sxs-lookup"><span data-stu-id="9d961-112">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="9d961-113">L'indirizzo del blocco è archiviato nel puntatore `fib`.</span><span class="sxs-lookup"><span data-stu-id="9d961-113">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="9d961-114">Questa memoria non viene sottoposta alla procedura di Garbage Collection e non deve quindi essere bloccata con [fixed](../../../csharp/language-reference/keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9d961-114">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span></span> <span data-ttu-id="9d961-115">La durata del blocco di memoria è limitata alla durata del metodo che lo definisce.</span><span class="sxs-lookup"><span data-stu-id="9d961-115">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="9d961-116">Non è possibile liberare la memoria prima della restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="9d961-116">You cannot free the memory before the method returns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d961-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d961-117">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]  
  
## <a name="security"></a><span data-ttu-id="9d961-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9d961-118">Security</span></span>  
 <span data-ttu-id="9d961-119">Il codice di tipo unsafe è meno sicuro delle alternative di tipo safe.</span><span class="sxs-lookup"><span data-stu-id="9d961-119">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="9d961-120">Tuttavia, l'uso di `stackalloc` attiva automaticamente le funzionalità di rilevazione del sovraccarico del buffer in Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9d961-120">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="9d961-121">Se viene rilevato un sovraccarico del buffer, il processo viene terminato il più rapidamente possibile per ridurre al minimo la possibilità che venga eseguito codice dannoso.</span><span class="sxs-lookup"><span data-stu-id="9d961-121">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9d961-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="9d961-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9d961-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d961-123">See Also</span></span>  
 [<span data-ttu-id="9d961-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="9d961-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9d961-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="9d961-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9d961-126">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="9d961-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="9d961-127">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="9d961-127">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="9d961-128">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="9d961-128">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
