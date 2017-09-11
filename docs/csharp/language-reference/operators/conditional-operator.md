---
title: 'Operatore ?: (Riferimenti per C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 794ff53fe471ef23163503f59599b528df127e2e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="cf6c0-102">Operatore ?: (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="cf6c0-102">?: Operator (C# Reference)</span></span>
<span data-ttu-id="cf6c0-103">L'operatore condizionale (`?:`) restituisce uno tra due valori in base al valore di un'espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="cf6c0-103">The conditional operator (`?:`) returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="cf6c0-104">Di seguito è riportata la sintassi per l'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="cf6c0-104">Following is the syntax for the conditional operator.</span></span>  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a><span data-ttu-id="cf6c0-105">Note</span><span class="sxs-lookup"><span data-stu-id="cf6c0-105">Remarks</span></span>  
 <span data-ttu-id="cf6c0-106">L' oggetto `condition` deve restituire `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="cf6c0-106">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="cf6c0-107">Se `condition` è `true`, `first_expression` viene valutato e diventa il risultato.</span><span class="sxs-lookup"><span data-stu-id="cf6c0-107">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="cf6c0-108">Se `condition` è `false`, `second_expression` viene valutato e diventa il risultato.</span><span class="sxs-lookup"><span data-stu-id="cf6c0-108">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="cf6c0-109">Viene valutata soltanto una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="cf6c0-109">Only one of the two expressions is evaluated.</span></span>  
  
 <span data-ttu-id="cf6c0-110">Il tipo di `first_expression` e di `second_expression` deve essere lo stesso o deve esistere una conversione implicita da un tipo a un altro.</span><span class="sxs-lookup"><span data-stu-id="cf6c0-110">Either the type of `first_expression` and `second_expression` must be the same, or an implicit conversion must exist from one type to the other.</span></span>  
  
 <span data-ttu-id="cf6c0-111">I calcoli che richiedono una costruzione `if-else` possono essere espressi più concisamente mediante l'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="cf6c0-111">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="cf6c0-112">Ad esempio, il codice seguente viene utilizzato prima un'istruzione `if`, quindi un operatore condizionale per classificare un integer come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="cf6c0-112">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>  
  
```  
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```  
  
 <span data-ttu-id="cf6c0-113">L'operatore condizionale si associa all'operando a destra.</span><span class="sxs-lookup"><span data-stu-id="cf6c0-113">The conditional operator is right-associative.</span></span> <span data-ttu-id="cf6c0-114">L'espressione `a ? b : c ? d : e` viene valutata come `a ? b : (c ? d : e)`, non come `(a ? b : c) ? d : e`.</span><span class="sxs-lookup"><span data-stu-id="cf6c0-114">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
 <span data-ttu-id="cf6c0-115">Non è possibile eseguire l'overload dell'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="cf6c0-115">The conditional operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf6c0-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf6c0-116">Example</span></span>  
 <span data-ttu-id="cf6c0-117">[!code-cs[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cf6c0-117">[!code-cs[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf6c0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf6c0-118">See Also</span></span>  
 <span data-ttu-id="cf6c0-119">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf6c0-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="cf6c0-120">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf6c0-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="cf6c0-121">[Operatori C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf6c0-121">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="cf6c0-122">[if-else](../../../csharp/language-reference/keywords/if-else.md) </span><span class="sxs-lookup"><span data-stu-id="cf6c0-122">[if-else](../../../csharp/language-reference/keywords/if-else.md) </span></span>  
 <span data-ttu-id="cf6c0-123">[Operatori ?. e ?](../../../csharp/language-reference/operators/null-conditional-operators.md) </span><span class="sxs-lookup"><span data-stu-id="cf6c0-123">[?. and ?Operators](../../../csharp/language-reference/operators/null-conditional-operators.md) </span></span>  
 [<span data-ttu-id="cf6c0-124">?? (operatore)</span><span class="sxs-lookup"><span data-stu-id="cf6c0-124">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)

