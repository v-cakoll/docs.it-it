---
title: as (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- as_CSharpKeyword
- as
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
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
ms.openlocfilehash: 7a55c696ac295eee8d5d35ed56038f3c4a90b215
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="as-c-reference"></a><span data-ttu-id="9aced-102">as (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="9aced-102">as (C# Reference)</span></span>
<span data-ttu-id="9aced-103">È possibile usare l'operatore `as` per eseguire determinati tipi di conversioni tra tipi di riferimenti compatibili o [tipi nullable](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="9aced-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="9aced-104">Il codice seguente illustra un esempio.</span><span class="sxs-lookup"><span data-stu-id="9aced-104">The following code shows an example.</span></span>  
  
 <span data-ttu-id="9aced-105">[!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9aced-105">[!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9aced-106">Note</span><span class="sxs-lookup"><span data-stu-id="9aced-106">Remarks</span></span>  
 <span data-ttu-id="9aced-107">L'operatore `as` è simile a un'operazione cast.</span><span class="sxs-lookup"><span data-stu-id="9aced-107">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="9aced-108">Tuttavia, se la conversione non è possibile, `as` restituisce `null` anziché generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9aced-108">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="9aced-109">Si consideri l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="9aced-109">Consider the following example:</span></span>  
  
```  
expression as type  
```  
  
 <span data-ttu-id="9aced-110">Il codice è equivalente all'espressione seguente, ad eccezione della variabile `expression` che viene restituita una sola volta.</span><span class="sxs-lookup"><span data-stu-id="9aced-110">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="9aced-111">Si noti che l'operatore `as` esegue solo conversioni di riferimenti, conversioni nullable e conversioni boxing.</span><span class="sxs-lookup"><span data-stu-id="9aced-111">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="9aced-112">L'operatore `as` non può eseguire altre conversioni, ad esempio conversioni definite dall'utente, le quali devono invece essere eseguite tramite le espressioni cast.</span><span class="sxs-lookup"><span data-stu-id="9aced-112">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9aced-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="9aced-113">Example</span></span>  
 <span data-ttu-id="9aced-114">[!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9aced-114">[!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9aced-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="9aced-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9aced-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9aced-116">See Also</span></span>  
 <span data-ttu-id="9aced-117">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9aced-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9aced-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9aced-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9aced-119">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="9aced-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="9aced-120">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="9aced-120">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 <span data-ttu-id="9aced-121">[Operatore ?:](../../../csharp/language-reference/operators/conditional-operator.md) </span><span class="sxs-lookup"><span data-stu-id="9aced-121">[?: Operator](../../../csharp/language-reference/operators/conditional-operator.md) </span></span>  
 [<span data-ttu-id="9aced-122">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="9aced-122">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

