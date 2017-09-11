---
title: stackalloc (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
dev_langs:
- CSharp
helpviewer_keywords:
- stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 53d61cfdcf4d356a28881c57ad923017c2b479ae
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="b5fef-102">stackalloc (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b5fef-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="b5fef-103">La parola chiave `stackalloc` viene usata in un contesto di codice unsafe per allocare un blocco di memoria nello stack.</span><span class="sxs-lookup"><span data-stu-id="b5fef-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>  
  
```  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a><span data-ttu-id="b5fef-104">Note</span><span class="sxs-lookup"><span data-stu-id="b5fef-104">Remarks</span></span>  
 <span data-ttu-id="b5fef-105">La parola chiave è valida solo per gli inizializzatori di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="b5fef-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="b5fef-106">Il codice seguente causa errori di compilazione.</span><span class="sxs-lookup"><span data-stu-id="b5fef-106">The following code causes compiler errors.</span></span>  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 <span data-ttu-id="b5fef-107">Poiché vengono usati tipi puntatore, `stackalloc` richiede un contesto [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="b5fef-107">Because pointer types are involved, `stackalloc` requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="b5fef-108">Per altre informazioni, vedere [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="b5fef-108">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="b5fef-109">La parola chiave `stackalloc` è come [_alloca](/cpp/c-runtime-library/reference/alloca) nella libreria di runtime del linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="b5fef-109">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>  
  
 <span data-ttu-id="b5fef-110">Nell'esempio seguente vengono calcolati e visualizzati i primi 20 numeri della sequenza di Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="b5fef-110">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="b5fef-111">Ogni numero corrisponde alla somma dei due numeri precedenti.</span><span class="sxs-lookup"><span data-stu-id="b5fef-111">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="b5fef-112">Nel codice, un blocco di memoria di dimensioni sufficienti a contenere 20 elementi di tipo `int` viene allocato nello stack, non nell'heap.</span><span class="sxs-lookup"><span data-stu-id="b5fef-112">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="b5fef-113">L'indirizzo del blocco è archiviato nel puntatore `fib`.</span><span class="sxs-lookup"><span data-stu-id="b5fef-113">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="b5fef-114">Questa memoria non viene sottoposta alla procedura di Garbage Collection e non deve quindi essere bloccata con [fixed](../../../csharp/language-reference/keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b5fef-114">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span></span> <span data-ttu-id="b5fef-115">La durata del blocco di memoria è limitata alla durata del metodo che lo definisce.</span><span class="sxs-lookup"><span data-stu-id="b5fef-115">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="b5fef-116">Non è possibile liberare la memoria prima della restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="b5fef-116">You cannot free the memory before the method returns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5fef-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5fef-117">Example</span></span>  
 <span data-ttu-id="b5fef-118">[!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b5fef-118">[!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]</span></span>  
  
## <a name="security"></a><span data-ttu-id="b5fef-119">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b5fef-119">Security</span></span>  
 <span data-ttu-id="b5fef-120">Il codice di tipo unsafe è meno sicuro delle alternative di tipo safe.</span><span class="sxs-lookup"><span data-stu-id="b5fef-120">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="b5fef-121">Tuttavia, l'uso di `stackalloc` attiva automaticamente le funzionalità di rilevazione del sovraccarico del buffer in Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b5fef-121">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="b5fef-122">Se viene rilevato un sovraccarico del buffer, il processo viene terminato il più rapidamente possibile per ridurre al minimo la possibilità che venga eseguito codice dannoso.</span><span class="sxs-lookup"><span data-stu-id="b5fef-122">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b5fef-123">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b5fef-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b5fef-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5fef-124">See Also</span></span>  
 <span data-ttu-id="b5fef-125">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b5fef-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b5fef-126">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b5fef-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b5fef-127">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="b5fef-127">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="b5fef-128">[Parole chiave per gli operatori](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="b5fef-128">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 [<span data-ttu-id="b5fef-129">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="b5fef-129">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)

