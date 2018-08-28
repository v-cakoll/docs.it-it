---
title: as (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: aee80b3262ccd9432d7c311dddec47185b66d05f
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "43003073"
---
# <a name="as-c-reference"></a><span data-ttu-id="4b688-102">as (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4b688-102">as (C# Reference)</span></span>
<span data-ttu-id="4b688-103">È possibile usare l'operatore `as` per eseguire determinati tipi di conversioni tra tipi di riferimenti compatibili o [tipi nullable](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="4b688-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="4b688-104">Il codice seguente illustra un esempio.</span><span class="sxs-lookup"><span data-stu-id="4b688-104">The following code shows an example.</span></span>  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]
  
## <a name="remarks"></a><span data-ttu-id="4b688-105">Note</span><span class="sxs-lookup"><span data-stu-id="4b688-105">Remarks</span></span>  
 <span data-ttu-id="4b688-106">L'operatore `as` è simile a un'operazione cast.</span><span class="sxs-lookup"><span data-stu-id="4b688-106">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="4b688-107">Tuttavia, se la conversione non è possibile, `as` restituisce `null` anziché generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4b688-107">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="4b688-108">Si consideri l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4b688-108">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="4b688-109">Il codice è equivalente all'espressione seguente, ad eccezione della variabile `expression` che viene restituita una sola volta.</span><span class="sxs-lookup"><span data-stu-id="4b688-109">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="4b688-110">Si noti che l'operatore `as` esegue solo conversioni di riferimenti, conversioni nullable e conversioni boxing.</span><span class="sxs-lookup"><span data-stu-id="4b688-110">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="4b688-111">L'operatore `as` non può eseguire altre conversioni, ad esempio conversioni definite dall'utente, le quali devono invece essere eseguite tramite le espressioni cast.</span><span class="sxs-lookup"><span data-stu-id="4b688-111">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b688-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b688-112">Example</span></span>  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a><span data-ttu-id="4b688-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="4b688-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4b688-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b688-114">See Also</span></span>  
- [<span data-ttu-id="4b688-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4b688-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="4b688-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4b688-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="4b688-117">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="4b688-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="4b688-118">is</span><span class="sxs-lookup"><span data-stu-id="4b688-118">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
- [<span data-ttu-id="4b688-119">Operatore ?:</span><span class="sxs-lookup"><span data-stu-id="4b688-119">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)  
- [<span data-ttu-id="4b688-120">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="4b688-120">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
