---
title: return (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 90c84b51c6ee57864eac552bc488c9f9c15e9394
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="return-c-reference"></a><span data-ttu-id="aacf1-102">return (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="aacf1-102">return (C# Reference)</span></span>
<span data-ttu-id="aacf1-103">L'istruzione `return` termina l'esecuzione del metodo in cui viene visualizzata e restituisce il controllo al metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="aacf1-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="aacf1-104">Può restituire anche un valore facoltativo.</span><span class="sxs-lookup"><span data-stu-id="aacf1-104">It can also return an optional value.</span></span> <span data-ttu-id="aacf1-105">Se il metodo è un tipo `void`, l'istruzione `return` può essere omessa.</span><span class="sxs-lookup"><span data-stu-id="aacf1-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="aacf1-106">Se l'istruzione return è all'interno di un blocco `try`, il blocco `finally`, se presente, verrà eseguito prima che il controllo venga restituito al metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="aacf1-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aacf1-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="aacf1-107">Example</span></span>  
 <span data-ttu-id="aacf1-108">Nell'esempio seguente, il metodo `CalculateArea()` restituisce la variabile locale `area` come un [doppie](../../../csharp/language-reference/keywords/double.md) valore.</span><span class="sxs-lookup"><span data-stu-id="aacf1-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="aacf1-109">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="aacf1-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aacf1-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aacf1-110">See Also</span></span>  
 [<span data-ttu-id="aacf1-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="aacf1-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="aacf1-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="aacf1-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="aacf1-113">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="aacf1-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="aacf1-114">Istruzione return</span><span class="sxs-lookup"><span data-stu-id="aacf1-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)  
 [<span data-ttu-id="aacf1-115">Istruzioni di spostamento</span><span class="sxs-lookup"><span data-stu-id="aacf1-115">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
