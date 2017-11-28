---
title: 'Procedura: eseguire alberi delle espressioni (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dfb5ab3-f48f-417e-975f-f8f6f1cdc18d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45a13f13659472b7620b6df070815ace1d6fb0de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-execute-expression-trees-visual-basic"></a><span data-ttu-id="85a9c-102">Procedura: eseguire alberi delle espressioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85a9c-102">How to: Execute Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="85a9c-103">In questo argomento viene illustrato come eseguire un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="85a9c-103">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="85a9c-104">L'esecuzione di un albero delle espressioni può restituire un valore o può eseguire solo un'azione, ad esempio la chiamata a un metodo.</span><span class="sxs-lookup"><span data-stu-id="85a9c-104">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="85a9c-105">Possono essere eseguite solo gli alberi delle espressioni che rappresentano espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="85a9c-105">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="85a9c-106">Gli alberi delle espressioni che rappresentano espressioni lambda sono di tipo <xref:System.Linq.Expressions.LambdaExpression> o <xref:System.Linq.Expressions.Expression%601>.</span><span class="sxs-lookup"><span data-stu-id="85a9c-106">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="85a9c-107">Per eseguire gli alberi delle espressioni, chiamare il metodo <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> per creare un delegato eseguibile e quindi richiamare il delegato.</span><span class="sxs-lookup"><span data-stu-id="85a9c-107">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85a9c-108">Se il tipo del delegato non è noto, ovvero l'espressione lambda è di tipo <xref:System.Linq.Expressions.LambdaExpression> e non <xref:System.Linq.Expressions.Expression%601>, è necessario chiamare il metodo <xref:System.Delegate.DynamicInvoke%2A> sul delegato invece che richiamarlo direttamente.</span><span class="sxs-lookup"><span data-stu-id="85a9c-108">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="85a9c-109">Se un albero delle espressioni non rappresenta un'espressione lambda, è possibile creare una nuova espressione lambda con l'albero delle espressioni originale come corpo, chiamando il metodo <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>.</span><span class="sxs-lookup"><span data-stu-id="85a9c-109">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="85a9c-110">Sarà quindi possibile eseguire l'espressione lambda come descritto precedentemente in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="85a9c-110">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85a9c-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="85a9c-111">Example</span></span>  
 <span data-ttu-id="85a9c-112">Nell'esempio di codice seguente viene descritto come eseguire un albero delle espressioni che rappresenta l'elevamento di un numero a una potenza mediante la creazione e l'esecuzione di un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="85a9c-112">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="85a9c-113">Verrà visualizzato il risultato che rappresenta il numero elevato a potenza.</span><span class="sxs-lookup"><span data-stu-id="85a9c-113">The result, which represents the number raised to the power, is displayed.</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="85a9c-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="85a9c-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="85a9c-115">Aggiungere un riferimento di progetto a System.Core.dll, se non è già presente.</span><span class="sxs-lookup"><span data-stu-id="85a9c-115">Add a project reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="85a9c-116">Includere lo spazio dei nomi System.Linq.Expressions.</span><span class="sxs-lookup"><span data-stu-id="85a9c-116">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a9c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85a9c-117">See Also</span></span>  
 [<span data-ttu-id="85a9c-118">Alberi delle espressioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85a9c-118">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)  
 [<span data-ttu-id="85a9c-119">Procedura: modificare alberi delle espressioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85a9c-119">How to: Modify Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
