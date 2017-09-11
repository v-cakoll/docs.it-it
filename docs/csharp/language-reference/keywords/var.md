---
title: var (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- var
- var_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: 13
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
ms.openlocfilehash: 2a96d1c8869edd96cec913f1a868bcc3253dd14f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="var-c-reference"></a><span data-ttu-id="edcd1-102">var (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="edcd1-102">var (C# Reference)</span></span>
<span data-ttu-id="edcd1-103">A partire da Visual C# 3.0, le variabili dichiarate in corrispondenza dell'ambito del metodo possono contenere un oggetto `var` di"tipo" implicito.</span><span class="sxs-lookup"><span data-stu-id="edcd1-103">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="edcd1-104">Una variabile locale tipizzata in modo implicito è fortemente tipizzata come se si fosse dichiarato il tipo stesso, ma è il compilatore ha determinare il tipo.</span><span class="sxs-lookup"><span data-stu-id="edcd1-104">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="edcd1-105">Le due dichiarazioni seguenti di `i` sono equivalenti dal punto di vista funzionale:</span><span class="sxs-lookup"><span data-stu-id="edcd1-105">The following two declarations of `i` are functionally equivalent:</span></span>  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 <span data-ttu-id="edcd1-106">Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) e [Relazioni tra i tipi nelle operazioni di query LINQ](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="edcd1-106">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="edcd1-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="edcd1-107">Example</span></span>  
 <span data-ttu-id="edcd1-108">L'esempio seguente illustra due espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="edcd1-108">The following example shows two query expressions.</span></span> <span data-ttu-id="edcd1-109">Nella prima espressione l'uso di `var` è consentito, ma non necessario, perché il tipo del risultato della query può essere dichiarato in modo esplicito come `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="edcd1-109">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="edcd1-110">Nella seconda espressione è invece necessario usare `var`, perché il risultato è una raccolta di tipi anonimi e il nome di tale tipo non è accessibile tranne che al compilatore stesso.</span><span class="sxs-lookup"><span data-stu-id="edcd1-110">However, in the second expression, `var` must be used because the result is a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="edcd1-111">Si noti che nel secondo esempio anche la variabile di iterazione `foreach``item` deve essere tipizzata in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="edcd1-111">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>  
  
 <span data-ttu-id="edcd1-112">[!code-cs[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="edcd1-112">[!code-cs[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edcd1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edcd1-113">See Also</span></span>  
 <span data-ttu-id="edcd1-114">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="edcd1-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="edcd1-115">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="edcd1-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="edcd1-116">Variabili locali tipizzate in modo implicito</span><span class="sxs-lookup"><span data-stu-id="edcd1-116">Implicitly Typed Local Variables</span></span>](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)

