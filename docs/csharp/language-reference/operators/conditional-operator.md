---
title: 'Operatore ?: (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 150149453a67d8e5319461266865cb25be180347
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43421504"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="15ea2-102">Operatore ?: (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="15ea2-102">?: Operator (C# Reference)</span></span>
<span data-ttu-id="15ea2-103">L'operatore condizionale (`?:`), noto come operatore condizionale ternario, restituisce uno di due valori in base al valore di un'espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="15ea2-103">The conditional operator (`?:`), commonly known as the ternary conditional operator, returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="15ea2-104">Di seguito è riportata la sintassi per l'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="15ea2-104">Following is the syntax for the conditional operator.</span></span>  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a><span data-ttu-id="15ea2-105">Note</span><span class="sxs-lookup"><span data-stu-id="15ea2-105">Remarks</span></span>  
 <span data-ttu-id="15ea2-106">L' oggetto `condition` deve restituire `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="15ea2-106">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="15ea2-107">Se `condition` è `true`, `first_expression` viene valutato e diventa il risultato.</span><span class="sxs-lookup"><span data-stu-id="15ea2-107">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="15ea2-108">Se `condition` è `false`, `second_expression` viene valutato e diventa il risultato.</span><span class="sxs-lookup"><span data-stu-id="15ea2-108">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="15ea2-109">Viene valutata soltanto una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="15ea2-109">Only one of the two expressions is evaluated.</span></span>  
  
 <span data-ttu-id="15ea2-110">Il tipo di `first_expression` e di `second_expression` deve essere lo stesso o deve esistere una conversione implicita da un tipo a un altro.</span><span class="sxs-lookup"><span data-stu-id="15ea2-110">Either the type of `first_expression` and `second_expression` must be the same, or an implicit conversion must exist from one type to the other.</span></span>  
  
 <span data-ttu-id="15ea2-111">I calcoli che richiedono una costruzione `if-else` possono essere espressi più concisamente mediante l'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="15ea2-111">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="15ea2-112">Ad esempio, il codice seguente viene utilizzato prima un'istruzione `if`, quindi un operatore condizionale per classificare un integer come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="15ea2-112">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>  
  
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
  
 <span data-ttu-id="15ea2-113">L'operatore condizionale si associa all'operando a destra.</span><span class="sxs-lookup"><span data-stu-id="15ea2-113">The conditional operator is right-associative.</span></span> <span data-ttu-id="15ea2-114">L'espressione `a ? b : c ? d : e` viene valutata come `a ? b : (c ? d : e)`, non come `(a ? b : c) ? d : e`.</span><span class="sxs-lookup"><span data-stu-id="15ea2-114">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
 <span data-ttu-id="15ea2-115">Non è possibile eseguire l'overload dell'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="15ea2-115">The conditional operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15ea2-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="15ea2-116">Example</span></span>  
 [!code-csharp[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="15ea2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15ea2-117">See Also</span></span>

- [<span data-ttu-id="15ea2-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="15ea2-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="15ea2-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="15ea2-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="15ea2-120">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="15ea2-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="15ea2-121">if-else</span><span class="sxs-lookup"><span data-stu-id="15ea2-121">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
- <span data-ttu-id="15ea2-122">[Operatori ?. e ?[]](../../../csharp/language-reference/operators/null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="15ea2-122">[?. and ?[] Operators](../../../csharp/language-reference/operators/null-conditional-operators.md)</span></span>  
- [<span data-ttu-id="15ea2-123">?? (operatore)</span><span class="sxs-lookup"><span data-stu-id="15ea2-123">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)
