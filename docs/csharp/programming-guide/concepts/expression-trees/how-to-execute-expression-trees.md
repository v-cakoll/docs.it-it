---
title: Come eseguire gli alberi delle espressioni (C#)
description: Informazioni su come eseguire un albero delle espressioni per restituire un valore o eseguire un'azione, ad esempio la chiamata a un metodo.
ms.date: 07/20/2015
ms.assetid: b8c40db5-2464-4bb9-9001-8c2bc7f006c5
ms.openlocfilehash: 9e306da545ba6c6275f36b8f6dd4e98bb91ed54e
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105622"
---
# <a name="how-to-execute-expression-trees-c"></a><span data-ttu-id="86140-103">Come eseguire gli alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="86140-103">How to execute expression trees (C#)</span></span>
<span data-ttu-id="86140-104">In questo argomento viene illustrato come eseguire un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="86140-104">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="86140-105">L'esecuzione di un albero delle espressioni può restituire un valore o può eseguire solo un'azione, ad esempio la chiamata a un metodo.</span><span class="sxs-lookup"><span data-stu-id="86140-105">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="86140-106">Possono essere eseguite solo gli alberi delle espressioni che rappresentano espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="86140-106">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="86140-107">Gli alberi delle espressioni che rappresentano espressioni lambda sono di tipo <xref:System.Linq.Expressions.LambdaExpression> o <xref:System.Linq.Expressions.Expression%601>.</span><span class="sxs-lookup"><span data-stu-id="86140-107">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="86140-108">Per eseguire gli alberi delle espressioni, chiamare il metodo <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> per creare un delegato eseguibile e quindi richiamare il delegato.</span><span class="sxs-lookup"><span data-stu-id="86140-108">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86140-109">Se il tipo del delegato non è noto, ovvero l'espressione lambda è di tipo <xref:System.Linq.Expressions.LambdaExpression> e non <xref:System.Linq.Expressions.Expression%601>, è necessario chiamare il metodo <xref:System.Delegate.DynamicInvoke%2A> sul delegato invece che richiamarlo direttamente.</span><span class="sxs-lookup"><span data-stu-id="86140-109">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="86140-110">Se un albero delle espressioni non rappresenta un'espressione lambda, è possibile creare una nuova espressione lambda con l'albero delle espressioni originale come corpo, chiamando il metodo <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>.</span><span class="sxs-lookup"><span data-stu-id="86140-110">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="86140-111">Sarà quindi possibile eseguire l'espressione lambda come descritto precedentemente in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="86140-111">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86140-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="86140-112">Example</span></span>  
 <span data-ttu-id="86140-113">Nell'esempio di codice seguente viene descritto come eseguire un albero delle espressioni che rappresenta l'elevamento di un numero a una potenza mediante la creazione e l'esecuzione di un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="86140-113">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="86140-114">Verrà visualizzato il risultato che rappresenta il numero elevato a potenza.</span><span class="sxs-lookup"><span data-stu-id="86140-114">The result, which represents the number raised to the power, is displayed.</span></span>  
  
```csharp  
// The expression tree to execute.  
BinaryExpression be = Expression.Power(Expression.Constant(2D), Expression.Constant(3D));  
  
// Create a lambda expression.  
Expression<Func<double>> le = Expression.Lambda<Func<double>>(be);  
  
// Compile the lambda expression.  
Func<double> compiledExpression = le.Compile();  
  
// Execute the lambda expression.  
double result = compiledExpression();  
  
// Display the result.  
Console.WriteLine(result);  
  
// This code produces the following output:  
// 8  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="86140-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="86140-115">Compiling the Code</span></span>  
  
- <span data-ttu-id="86140-116">Includere lo spazio dei nomi System.Linq.Expressions.</span><span class="sxs-lookup"><span data-stu-id="86140-116">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86140-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86140-117">See also</span></span>

- [<span data-ttu-id="86140-118">Alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="86140-118">Expression Trees (C#)</span></span>](./index.md)
- [<span data-ttu-id="86140-119">Come modificare gli alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="86140-119">How to modify expression trees (C#)</span></span>](./how-to-modify-expression-trees.md)
