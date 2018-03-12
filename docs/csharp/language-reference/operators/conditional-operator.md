---
title: 'Operatore ?: (Riferimenti per C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bbd434e02ece4843bab4ffded6877f81f622950c
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a2b5e-102">Operatore ?: (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a2b5e-102">?: Operator (C# Reference)</span></span>
<span data-ttu-id="a2b5e-103">L'operatore condizionale (`?:`), noto come operatore condizionale ternario, restituisce uno di due valori in base al valore di un'espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="a2b5e-103">The conditional operator (`?:`), commonly known as the ternary conditional operator, returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="a2b5e-104">Di seguito è riportata la sintassi per l'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="a2b5e-104">Following is the syntax for the conditional operator.</span></span>  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a><span data-ttu-id="a2b5e-105">Note</span><span class="sxs-lookup"><span data-stu-id="a2b5e-105">Remarks</span></span>  
 <span data-ttu-id="a2b5e-106">L' oggetto `condition` deve restituire `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="a2b5e-106">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="a2b5e-107">Se `condition` è `true`, `first_expression` viene valutato e diventa il risultato.</span><span class="sxs-lookup"><span data-stu-id="a2b5e-107">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="a2b5e-108">Se `condition` è `false`, `second_expression` viene valutato e diventa il risultato.</span><span class="sxs-lookup"><span data-stu-id="a2b5e-108">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="a2b5e-109">Viene valutata soltanto una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="a2b5e-109">Only one of the two expressions is evaluated.</span></span>  
  
 <span data-ttu-id="a2b5e-110">Il tipo di `first_expression` e di `second_expression` deve essere lo stesso o deve esistere una conversione implicita da un tipo a un altro.</span><span class="sxs-lookup"><span data-stu-id="a2b5e-110">Either the type of `first_expression` and `second_expression` must be the same, or an implicit conversion must exist from one type to the other.</span></span>  
  
 <span data-ttu-id="a2b5e-111">I calcoli che richiedono una costruzione `if-else` possono essere espressi più concisamente mediante l'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="a2b5e-111">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="a2b5e-112">Ad esempio, il codice seguente viene utilizzato prima un'istruzione `if`, quindi un operatore condizionale per classificare un integer come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="a2b5e-112">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="a2b5e-113">L'operatore condizionale si associa all'operando a destra.</span><span class="sxs-lookup"><span data-stu-id="a2b5e-113">The conditional operator is right-associative.</span></span> <span data-ttu-id="a2b5e-114">L'espressione `a ? b : c ? d : e` viene valutata come `a ? b : (c ? d : e)`, non come `(a ? b : c) ? d : e`.</span><span class="sxs-lookup"><span data-stu-id="a2b5e-114">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
 <span data-ttu-id="a2b5e-115">Non è possibile eseguire l'overload dell'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="a2b5e-115">The conditional operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2b5e-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2b5e-116">Example</span></span>  
 [!code-csharp[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a2b5e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2b5e-117">See Also</span></span>  
 [<span data-ttu-id="a2b5e-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a2b5e-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a2b5e-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a2b5e-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a2b5e-120">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="a2b5e-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="a2b5e-121">if-else</span><span class="sxs-lookup"><span data-stu-id="a2b5e-121">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
 [<span data-ttu-id="a2b5e-122">Operatori ?. e ?</span><span class="sxs-lookup"><span data-stu-id="a2b5e-122">?. and ?Operators</span></span>](../../../csharp/language-reference/operators/null-conditional-operators.md)  
 [<span data-ttu-id="a2b5e-123">?? (operatore)</span><span class="sxs-lookup"><span data-stu-id="a2b5e-123">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)
