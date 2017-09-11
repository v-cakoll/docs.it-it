---
title: 'Procedura: Eseguire alberi delle espressioni (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: get-started-article
dev_langs:
- CSharp
ms.assetid: b8c40db5-2464-4bb9-9001-8c2bc7f006c5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d230adee877c214dfef0f60ae2c6e7547fedb869
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-execute-expression-trees-c"></a><span data-ttu-id="2371d-102">Procedura: Eseguire alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="2371d-102">How to: Execute Expression Trees (C#)</span></span>
<span data-ttu-id="2371d-103">In questo argomento viene illustrato come eseguire un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="2371d-103">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="2371d-104">L'esecuzione di un albero delle espressioni può restituire un valore o può eseguire solo un'azione, ad esempio la chiamata a un metodo.</span><span class="sxs-lookup"><span data-stu-id="2371d-104">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="2371d-105">Possono essere eseguite solo gli alberi delle espressioni che rappresentano espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="2371d-105">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="2371d-106">Gli alberi delle espressioni che rappresentano espressioni lambda sono di tipo <xref:System.Linq.Expressions.LambdaExpression> o <xref:System.Linq.Expressions.Expression%601>.</span><span class="sxs-lookup"><span data-stu-id="2371d-106">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="2371d-107">Per eseguire gli alberi delle espressioni, chiamare il metodo <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> per creare un delegato eseguibile e quindi richiamare il delegato.</span><span class="sxs-lookup"><span data-stu-id="2371d-107">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2371d-108">Se il tipo del delegato non è noto, ovvero l'espressione lambda è di tipo <xref:System.Linq.Expressions.LambdaExpression> e non <xref:System.Linq.Expressions.Expression%601>, è necessario chiamare il metodo <xref:System.Delegate.DynamicInvoke%2A> sul delegato invece che richiamarlo direttamente.</span><span class="sxs-lookup"><span data-stu-id="2371d-108">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="2371d-109">Se un albero delle espressioni non rappresenta un'espressione lambda, è possibile creare una nuova espressione lambda con l'albero delle espressioni originale come corpo, chiamando il metodo <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>.</span><span class="sxs-lookup"><span data-stu-id="2371d-109">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="2371d-110">Sarà quindi possibile eseguire l'espressione lambda come descritto precedentemente in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="2371d-110">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2371d-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="2371d-111">Example</span></span>  
 <span data-ttu-id="2371d-112">Nell'esempio di codice seguente viene descritto come eseguire un albero delle espressioni che rappresenta l'elevamento di un numero a una potenza mediante la creazione e l'esecuzione di un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="2371d-112">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="2371d-113">Verrà visualizzato il risultato che rappresenta il numero elevato a potenza.</span><span class="sxs-lookup"><span data-stu-id="2371d-113">The result, which represents the number raised to the power, is displayed.</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="2371d-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2371d-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="2371d-115">Aggiungere un riferimento di progetto a System.Core.dll, se non è già presente.</span><span class="sxs-lookup"><span data-stu-id="2371d-115">Add a project reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="2371d-116">Includere lo spazio dei nomi System.Linq.Expressions.</span><span class="sxs-lookup"><span data-stu-id="2371d-116">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2371d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2371d-117">See Also</span></span>  
 <span data-ttu-id="2371d-118">[Alberi delle espressioni (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="2371d-118">[Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md) </span></span>  
 [<span data-ttu-id="2371d-119">Procedura: Modificare alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="2371d-119">How to: Modify Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)

