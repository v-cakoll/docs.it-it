---
title: 'Procedura: eseguire alberi delle espressioni (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9dfb5ab3-f48f-417e-975f-f8f6f1cdc18d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4cc2c9890c1f5efbc4036d94eef1adb05094ae40
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-execute-expression-trees-visual-basic"></a><span data-ttu-id="c5ec2-102">Procedura: eseguire alberi delle espressioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5ec2-102">How to: Execute Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="c5ec2-103">In questo argomento viene illustrato come eseguire una struttura ad albero dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="c5ec2-103">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="c5ec2-104">L'esecuzione di una struttura ad albero dell'espressione potrebbe restituire un valore, o può eseguire solo un'azione, ad esempio si chiama un metodo.</span><span class="sxs-lookup"><span data-stu-id="c5ec2-104">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="c5ec2-105">Solo gli alberi delle espressioni che rappresentano le espressioni lambda possono essere eseguite.</span><span class="sxs-lookup"><span data-stu-id="c5ec2-105">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="c5ec2-106">Gli alberi delle espressioni che rappresentano le espressioni lambda sono di tipo <xref:System.Linq.Expressions.LambdaExpression>o <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression></span><span class="sxs-lookup"><span data-stu-id="c5ec2-106">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="c5ec2-107">Per eseguire tali alberi delle espressioni, chiamare il <xref:System.Linq.Expressions.LambdaExpression.Compile%2A>per creare un delegato eseguibile e quindi richiamare il delegato.</xref:System.Linq.Expressions.LambdaExpression.Compile%2A></span><span class="sxs-lookup"><span data-stu-id="c5ec2-107">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5ec2-108">Se non è noto il tipo del delegato, ovvero l'espressione lambda è di tipo <xref:System.Linq.Expressions.LambdaExpression>e non <xref:System.Linq.Expressions.Expression%601>, è necessario chiamare il <xref:System.Delegate.DynamicInvoke%2A>metodo sul delegato anziché richiamarlo direttamente.</xref:System.Delegate.DynamicInvoke%2A> </xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression></span><span class="sxs-lookup"><span data-stu-id="c5ec2-108">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="c5ec2-109">Se una struttura ad albero dell'espressione non rappresenta un'espressione lambda, è possibile creare una nuova espressione lambda che utilizza l'albero delle espressioni originale come corpo, chiamando il <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>(metodo).</xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29></span><span class="sxs-lookup"><span data-stu-id="c5ec2-109">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="c5ec2-110">Quindi, è possibile eseguire l'espressione lambda come descritto in precedenza in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="c5ec2-110">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5ec2-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5ec2-111">Example</span></span>  
 <span data-ttu-id="c5ec2-112">Esempio di codice seguente viene illustrato come eseguire una struttura ad albero dell'espressione che rappresenta l'elevamento di un numero a una potenza creando un'espressione lambda e dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c5ec2-112">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="c5ec2-113">Il risultato, che rappresenta il numero elevato alla potenza, viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="c5ec2-113">The result, which represents the number raised to the power, is displayed.</span></span>  
  
```vb  
' The expression tree to execute.  
Dim be As BinaryExpression = Expression.Power(Expression.Constant(2.0R), Expression.Constant(3.0R))  
  
' Create a lambda expression.  
Dim le As Expression(Of Func(Of Double)) = Expression.Lambda(Of Func(Of Double))(be)  
  
' Compile the lambda expression.  
Dim compiledExpression As Func(Of Double) = le.Compile()  
  
' Execute the lambda expression.  
Dim result As Double = compiledExpression()  
  
' Display the result.  
MsgBox(result)  
  
' This code produces the following output:  
' 8  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c5ec2-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c5ec2-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="c5ec2-115">Aggiungere un riferimento a System.Core.dll progetto se non è già fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="c5ec2-115">Add a project reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="c5ec2-116">Includere lo spazio dei nomi System.Linq.Expressions.</span><span class="sxs-lookup"><span data-stu-id="c5ec2-116">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5ec2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5ec2-117">See Also</span></span>  
 <span data-ttu-id="c5ec2-118">[Alberi delle espressioni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="c5ec2-118">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="c5ec2-119"> [Procedura: modificare strutture ad albero di espressione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)</span><span class="sxs-lookup"><span data-stu-id="c5ec2-119"> [How to: Modify Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)</span></span>
