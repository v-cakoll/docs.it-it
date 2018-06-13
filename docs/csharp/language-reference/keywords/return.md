---
title: return (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 29d2b8e28ae6240b9d06b82695efe1736404c5cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266110"
---
# <a name="return-c-reference"></a><span data-ttu-id="6a6a9-102">return (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="6a6a9-102">return (C# Reference)</span></span>
<span data-ttu-id="6a6a9-103">L'istruzione `return` termina l'esecuzione del metodo in cui viene visualizzata e restituisce il controllo al metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a6a9-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="6a6a9-104">Può restituire anche un valore facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6a6a9-104">It can also return an optional value.</span></span> <span data-ttu-id="6a6a9-105">Se il metodo è un tipo `void`, l'istruzione `return` può essere omessa.</span><span class="sxs-lookup"><span data-stu-id="6a6a9-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="6a6a9-106">Se l'istruzione return è all'interno di un blocco `try`, il blocco `finally`, se presente, verrà eseguito prima che il controllo venga restituito al metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a6a9-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a6a9-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a6a9-107">Example</span></span>  
 <span data-ttu-id="6a6a9-108">Nell'esempio seguente il metodo `CalculateArea()` restituisce la variabile locale `area` come valore [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="6a6a9-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="6a6a9-109">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="6a6a9-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6a6a9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a6a9-110">See Also</span></span>  
 [<span data-ttu-id="6a6a9-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="6a6a9-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6a6a9-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="6a6a9-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6a6a9-113">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="6a6a9-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6a6a9-114">Istruzione return</span><span class="sxs-lookup"><span data-stu-id="6a6a9-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)  
 [<span data-ttu-id="6a6a9-115">Istruzioni di spostamento</span><span class="sxs-lookup"><span data-stu-id="6a6a9-115">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
