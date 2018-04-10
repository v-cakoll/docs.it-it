---
title: goto (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aa12a7547cfcd4a2076b5b0a308139f8a823f482
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="goto-c-reference"></a><span data-ttu-id="f945b-102">goto (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f945b-102">goto (C# Reference)</span></span>
<span data-ttu-id="f945b-103">L'istruzione `goto` passa direttamente il controllo del programma a un'istruzione con etichetta.</span><span class="sxs-lookup"><span data-stu-id="f945b-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>  
  
 <span data-ttu-id="f945b-104">L'istruzione `goto` viene generalmente usata per trasferire il controllo a un'etichetta switch case specifica o all'etichetta predefinita di un'istruzione `switch`.</span><span class="sxs-lookup"><span data-stu-id="f945b-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>  
  
 <span data-ttu-id="f945b-105">L'istruzione `goto` viene anche usata per uscire da cicli annidati più interni.</span><span class="sxs-lookup"><span data-stu-id="f945b-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f945b-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="f945b-106">Example</span></span>  
 <span data-ttu-id="f945b-107">Nell'esempio riportato di seguito viene illustrato l'uso di `goto` in un'istruzione [switch](../../../csharp/language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="f945b-107">The following example demonstrates using `goto` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="f945b-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="f945b-108">Example</span></span>  
 <span data-ttu-id="f945b-109">Nell'esempio riportato di seguito viene illustrato come usare `goto` per uscire da cicli annidati.</span><span class="sxs-lookup"><span data-stu-id="f945b-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f945b-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f945b-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f945b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f945b-111">See Also</span></span>  
 [<span data-ttu-id="f945b-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f945b-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f945b-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f945b-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f945b-114">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="f945b-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f945b-115">Istruzione goto</span><span class="sxs-lookup"><span data-stu-id="f945b-115">goto Statement</span></span>](/cpp/cpp/goto-statement-cpp)  
 [<span data-ttu-id="f945b-116">Istruzioni di spostamento</span><span class="sxs-lookup"><span data-stu-id="f945b-116">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
