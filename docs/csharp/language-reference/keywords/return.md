---
title: return (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- return_CSharpKeyword
- return
dev_langs:
- CSharp
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
caps.latest.revision: 18
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
ms.openlocfilehash: 596375a1cba8f5ecbad636a6829c1a0599f8c0f4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="return-c-reference"></a><span data-ttu-id="fa46f-102">return (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="fa46f-102">return (C# Reference)</span></span>
<span data-ttu-id="fa46f-103">L'istruzione `return` termina l'esecuzione del metodo in cui viene visualizzata e restituisce il controllo al metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fa46f-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="fa46f-104">Può restituire anche un valore facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fa46f-104">It can also return an optional value.</span></span> <span data-ttu-id="fa46f-105">Se il metodo è un tipo `void`, l'istruzione `return` può essere omessa.</span><span class="sxs-lookup"><span data-stu-id="fa46f-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="fa46f-106">Se l'istruzione return è all'interno di un blocco `try`, il blocco `finally`, se presente, verrà eseguito prima che il controllo venga restituito al metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fa46f-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa46f-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa46f-107">Example</span></span>  
 <span data-ttu-id="fa46f-108">Nell'esempio seguente, il metodo `A()` restituisce la variabile `Area` come valore [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="fa46f-108">In the following example, the method `A()` returns the variable `Area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 <span data-ttu-id="fa46f-109">[!code-cs[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fa46f-109">[!code-cs[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fa46f-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="fa46f-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fa46f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa46f-111">See Also</span></span>  
 <span data-ttu-id="fa46f-112">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa46f-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="fa46f-113">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa46f-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fa46f-114">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa46f-114">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="fa46f-115">[Istruzione return](/cpp/cpp/return-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="fa46f-115">[return Statement](/cpp/cpp/return-statement-cpp) </span></span>  
 [<span data-ttu-id="fa46f-116">Istruzioni di spostamento</span><span class="sxs-lookup"><span data-stu-id="fa46f-116">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)

