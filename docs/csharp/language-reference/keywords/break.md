---
title: break (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- break
- break_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
caps.latest.revision: 21
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
ms.openlocfilehash: 73f6b6a37513b3aed796d811672fa43fa9e1c0b1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="break-c-reference"></a><span data-ttu-id="27d94-102">break (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="27d94-102">break (C# Reference)</span></span>
<span data-ttu-id="27d94-103">L'istruzione `break` termina il ciclo di inclusione più vicino o l'istruzione [switch](../../../csharp/language-reference/keywords/switch.md) in cui appare.</span><span class="sxs-lookup"><span data-stu-id="27d94-103">The `break` statement terminates the closest enclosing loop or [switch](../../../csharp/language-reference/keywords/switch.md) statement in which it appears.</span></span> <span data-ttu-id="27d94-104">Il controllo viene passato all'istruzione che segue l'istruzione terminata, se presente.</span><span class="sxs-lookup"><span data-stu-id="27d94-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27d94-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="27d94-105">Example</span></span>  
 <span data-ttu-id="27d94-106">In questo esempio, l'istruzione condizionale contiene un contatore che dovrebbe contare da 1 a 100. L'istruzione `break` tuttavia termina il ciclo dopo 4 conteggi.</span><span class="sxs-lookup"><span data-stu-id="27d94-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>  
  
 <span data-ttu-id="27d94-107">[!code-cs[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="27d94-107">[!code-cs[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="27d94-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="27d94-108">Example</span></span>  
 <span data-ttu-id="27d94-109">In questo esempio, l'istruzione `break` viene usata per interrompere un ciclo annidato interno e restituire il controllo al ciclo esterno.</span><span class="sxs-lookup"><span data-stu-id="27d94-109">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>  
  
 <span data-ttu-id="27d94-110">[!code-cs[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="27d94-110">[!code-cs[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="27d94-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="27d94-111">Example</span></span>  
 <span data-ttu-id="27d94-112">Questo esempio illustra l'uso di `break` in un'istruzione [switch](../../../csharp/language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="27d94-112">This example demonstrates the use of `break` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 <span data-ttu-id="27d94-113">[!code-cs[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="27d94-113">[!code-cs[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_3.cs)]</span></span>  
  
 <span data-ttu-id="27d94-114">Se è stato immesso `4`, l'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="27d94-114">If you entered `4`, the output would be:</span></span>  
  
```  
Enter your selection (1, 2, or 3): 4  
Sorry, invalid selection.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="27d94-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="27d94-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="27d94-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27d94-116">See Also</span></span>  
 <span data-ttu-id="27d94-117">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="27d94-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="27d94-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="27d94-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="27d94-119">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="27d94-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="27d94-120">[switch](../../../csharp/language-reference/keywords/switch.md) </span><span class="sxs-lookup"><span data-stu-id="27d94-120">[switch](../../../csharp/language-reference/keywords/switch.md) </span></span>  
 <span data-ttu-id="27d94-121">[Istruzioni di spostamento](../../../csharp/language-reference/keywords/jump-statements.md) </span><span class="sxs-lookup"><span data-stu-id="27d94-121">[Jump Statements](../../../csharp/language-reference/keywords/jump-statements.md) </span></span>  
 [<span data-ttu-id="27d94-122">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="27d94-122">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

