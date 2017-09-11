---
title: Istruzione fixed (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
dev_langs:
- CSharp
helpviewer_keywords:
- fixed keyword [C#]
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
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
ms.openlocfilehash: 4e1f810f6e6cfaef3a65c7391f074b414ef18b5a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="6c24c-102">Istruzione fixed (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="6c24c-102">fixed Statement (C# Reference)</span></span>
<span data-ttu-id="6c24c-103">L'istruzione `fixed` impedisce che il Garbage Collector esegua la rilocazione di una variabile mobile.</span><span class="sxs-lookup"><span data-stu-id="6c24c-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="6c24c-104">L'istruzione `fixed` è consentita solo in un contesto di tipo [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="6c24c-104">The `fixed` statement is only permitted in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="6c24c-105">È possibile usare `Fixed` anche per creare [buffer a dimensione fissa](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="6c24c-105">`Fixed` can also be used to create [fixed size buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 <span data-ttu-id="6c24c-106">L'istruzione `fixed` imposta un puntatore a una variabile gestita e la blocca durante l'esecuzione dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="6c24c-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="6c24c-107">Senza `fixed`, i puntatori alle variabili gestite mobili risulterebbero poco utili poiché il Garbage Collection potrebbe eseguire una rilocazione delle variabili in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="6c24c-107">Without `fixed`, pointers to movable managed variables would be of little use since garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="6c24c-108">Il compilatore C# consente di assegnare un puntatore a una variabile gestita in un'istruzione `fixed`.</span><span class="sxs-lookup"><span data-stu-id="6c24c-108">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>  
  
 <span data-ttu-id="6c24c-109">[!code-cs[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6c24c-109">[!code-cs[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]</span></span>  
  
 <span data-ttu-id="6c24c-110">È possibile inizializzare un puntatore usando una matrice, una stringa, un buffer a dimensione fissa o l'indirizzo di una variabile.</span><span class="sxs-lookup"><span data-stu-id="6c24c-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="6c24c-111">Nell'esempio seguente viene illustrato l'uso di indirizzi, matrici e stringhe di una variabile.</span><span class="sxs-lookup"><span data-stu-id="6c24c-111">The following example illustrates the use of variable addresses, arrays, and strings.</span></span> <span data-ttu-id="6c24c-112">Per altre informazioni sui buffer a dimensione fissa, vedere [Buffer a dimensione fissa](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="6c24c-112">For more information about fixed-size buffers, see [Fixed Size Buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 <span data-ttu-id="6c24c-113">[!code-cs[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6c24c-113">[!code-cs[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]</span></span>  
  
 <span data-ttu-id="6c24c-114">È possibile inizializzare più puntatori, purché siano tutti dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="6c24c-114">You can initialize multiple pointers, as long as they are all of the same type.</span></span>  
  
```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```
  
 <span data-ttu-id="6c24c-115">Per inizializzare puntatori di tipi diversi, annidare semplicemente le istruzioni `fixed` come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6c24c-115">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>  
  
 <span data-ttu-id="6c24c-116">[!code-cs[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="6c24c-116">[!code-cs[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]</span></span>  
  
 <span data-ttu-id="6c24c-117">Dopo aver eseguito il codice nell'istruzione, le variabili bloccate vengono sbloccate e sottoposte al Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6c24c-117">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="6c24c-118">Di conseguenza, evitare di puntare alle variabili esterne all'istruzione `fixed`.</span><span class="sxs-lookup"><span data-stu-id="6c24c-118">Therefore, do not point to those variables outside the `fixed` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c24c-119">I puntatori inizializzati nelle istruzioni fixed non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="6c24c-119">Pointers initialized in fixed statements cannot be modified.</span></span>  
  
 <span data-ttu-id="6c24c-120">Nella modalità di tipo unsafe è possibile allocare la memoria nello stack, che non è necessario bloccare perché non viene sottoposto al Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6c24c-120">In unsafe mode, you can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="6c24c-121">Per altre informazioni, vedere [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="6c24c-121">For more information, see [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c24c-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c24c-122">Example</span></span>  
 <span data-ttu-id="6c24c-123">[!code-cs[csrefKeywordsFixedLock n. 4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="6c24c-123">[!code-cs[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6c24c-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="6c24c-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6c24c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c24c-125">See Also</span></span>  
 <span data-ttu-id="6c24c-126">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6c24c-126">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6c24c-127">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6c24c-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6c24c-128">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="6c24c-128">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="6c24c-129">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="6c24c-129">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 [<span data-ttu-id="6c24c-130">Buffer a dimensione fissa</span><span class="sxs-lookup"><span data-stu-id="6c24c-130">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)

