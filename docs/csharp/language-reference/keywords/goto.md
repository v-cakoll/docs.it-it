---
title: goto (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- goto_CSharpKeyword
- goto
dev_langs:
- CSharp
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
caps.latest.revision: 22
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
ms.openlocfilehash: cd298809ab883f425f3bb88239f2951ab98cc03e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="goto-c-reference"></a><span data-ttu-id="d4b46-102">goto (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="d4b46-102">goto (C# Reference)</span></span>
<span data-ttu-id="d4b46-103">L'istruzione `goto` passa direttamente il controllo del programma a un'istruzione con etichetta.</span><span class="sxs-lookup"><span data-stu-id="d4b46-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>  
  
 <span data-ttu-id="d4b46-104">L'istruzione `goto` viene generalmente usata per trasferire il controllo a un'etichetta switch case specifica o all'etichetta predefinita di un'istruzione `switch`.</span><span class="sxs-lookup"><span data-stu-id="d4b46-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>  
  
 <span data-ttu-id="d4b46-105">L'istruzione `goto` viene anche usata per uscire da cicli annidati più interni.</span><span class="sxs-lookup"><span data-stu-id="d4b46-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4b46-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4b46-106">Example</span></span>  
 <span data-ttu-id="d4b46-107">Nell'esempio riportato di seguito viene illustrato l'uso di `goto` in un'istruzione [switch](../../../csharp/language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="d4b46-107">The following example demonstrates using `goto` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 <span data-ttu-id="d4b46-108">[!code-cs[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d4b46-108">[!code-cs[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4b46-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4b46-109">Example</span></span>  
 <span data-ttu-id="d4b46-110">Nell'esempio riportato di seguito viene illustrato come usare `goto` per uscire da cicli annidati.</span><span class="sxs-lookup"><span data-stu-id="d4b46-110">The following example demonstrates using `goto` to break out from nested loops.</span></span>  
  
 <span data-ttu-id="d4b46-111">[!code-cs[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d4b46-111">[!code-cs[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d4b46-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d4b46-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d4b46-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4b46-113">See Also</span></span>  
 <span data-ttu-id="d4b46-114">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d4b46-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d4b46-115">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d4b46-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d4b46-116">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d4b46-116">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d4b46-117">[Istruzione goto](/cpp/cpp/goto-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="d4b46-117">[goto Statement](/cpp/cpp/goto-statement-cpp) </span></span>  
 [<span data-ttu-id="d4b46-118">Istruzioni di spostamento</span><span class="sxs-lookup"><span data-stu-id="d4b46-118">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)

