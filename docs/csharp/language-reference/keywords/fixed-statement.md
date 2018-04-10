---
title: Istruzione fixed (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 13633e71c863b075eede41c9a18419d65350bdb0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="b7694-102">Istruzione fixed (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b7694-102">fixed Statement (C# Reference)</span></span>
<span data-ttu-id="b7694-103">L'istruzione `fixed` impedisce che il Garbage Collector esegua la rilocazione di una variabile mobile.</span><span class="sxs-lookup"><span data-stu-id="b7694-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="b7694-104">L'istruzione `fixed` è consentita solo in un contesto di tipo [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="b7694-104">The `fixed` statement is only permitted in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="b7694-105">È possibile usare `Fixed` anche per creare [buffer a dimensione fissa](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="b7694-105">`Fixed` can also be used to create [fixed size buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 <span data-ttu-id="b7694-106">L'istruzione `fixed` imposta un puntatore a una variabile gestita e la blocca durante l'esecuzione dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="b7694-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="b7694-107">Senza `fixed`, i puntatori alle variabili gestite mobili risulterebbero poco utili poiché il Garbage Collection potrebbe eseguire una rilocazione delle variabili in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="b7694-107">Without `fixed`, pointers to movable managed variables would be of little use since garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="b7694-108">Il compilatore C# consente di assegnare un puntatore a una variabile gestita in un'istruzione `fixed`.</span><span class="sxs-lookup"><span data-stu-id="b7694-108">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]  
  
 <span data-ttu-id="b7694-109">È possibile inizializzare un puntatore usando una matrice, una stringa, un buffer a dimensione fissa o l'indirizzo di una variabile.</span><span class="sxs-lookup"><span data-stu-id="b7694-109">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="b7694-110">Nell'esempio seguente viene illustrato l'uso di indirizzi, matrici e stringhe di una variabile.</span><span class="sxs-lookup"><span data-stu-id="b7694-110">The following example illustrates the use of variable addresses, arrays, and strings.</span></span> <span data-ttu-id="b7694-111">Per altre informazioni sui buffer a dimensione fissa, vedere [Buffer a dimensione fissa](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="b7694-111">For more information about fixed-size buffers, see [Fixed Size Buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]  
  
 <span data-ttu-id="b7694-112">È possibile inizializzare più puntatori, purché siano tutti dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="b7694-112">You can initialize multiple pointers, as long as they are all of the same type.</span></span>  
  
```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```
  
 <span data-ttu-id="b7694-113">Per inizializzare puntatori di tipi diversi, annidare semplicemente le istruzioni `fixed` come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b7694-113">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]  
  
 <span data-ttu-id="b7694-114">Dopo aver eseguito il codice nell'istruzione, le variabili bloccate vengono sbloccate e sottoposte al Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b7694-114">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="b7694-115">Di conseguenza, evitare di puntare alle variabili esterne all'istruzione `fixed`.</span><span class="sxs-lookup"><span data-stu-id="b7694-115">Therefore, do not point to those variables outside the `fixed` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7694-116">I puntatori inizializzati nelle istruzioni fixed non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="b7694-116">Pointers initialized in fixed statements cannot be modified.</span></span>  
  
 <span data-ttu-id="b7694-117">Nella modalità di tipo unsafe è possibile allocare la memoria nello stack, che non è necessario bloccare perché non viene sottoposto al Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b7694-117">In unsafe mode, you can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="b7694-118">Per altre informazioni, vedere [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="b7694-118">For more information, see [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7694-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7694-119">Example</span></span>  
 [!code-csharp[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b7694-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b7694-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7694-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7694-121">See Also</span></span>  
 [<span data-ttu-id="b7694-122">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b7694-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b7694-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b7694-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b7694-124">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="b7694-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="b7694-125">unsafe</span><span class="sxs-lookup"><span data-stu-id="b7694-125">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="b7694-126">Buffer a dimensione fissa</span><span class="sxs-lookup"><span data-stu-id="b7694-126">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
