---
title: 'Procedura: modificare strutture ad albero di espressione (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
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
ms.openlocfilehash: 2f0d383cbac639212519177fb1825875682f6233
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-modify-expression-trees-visual-basic"></a><span data-ttu-id="97e6c-102">Procedura: modificare strutture ad albero di espressione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97e6c-102">How to: Modify Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="97e6c-103">In questo argomento viene illustrato come modificare un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="97e6c-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="97e6c-104">Gli alberi delle espressioni non sono modificabili, il che significa che non può essere modificati direttamente.</span><span class="sxs-lookup"><span data-stu-id="97e6c-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="97e6c-105">Per modificare un albero delle espressioni, è necessario creare una copia di una struttura esistente e quando si crea la copia, apportare le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="97e6c-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="97e6c-106">È possibile utilizzare la <xref:System.Linq.Expressions.ExpressionVisitor>classe per attraversare una struttura esistente e copiare ogni nodo visitato.</xref:System.Linq.Expressions.ExpressionVisitor></span><span class="sxs-lookup"><span data-stu-id="97e6c-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="97e6c-107">Per modificare un albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="97e6c-107">To modify an expression tree</span></span>  
  
1.  <span data-ttu-id="97e6c-108">Creare un nuovo **applicazione Console** progetto.</span><span class="sxs-lookup"><span data-stu-id="97e6c-108">Create a new **Console Application** project.</span></span>  
  
2.  <span data-ttu-id="97e6c-109">Aggiungere un `Imports` istruzione per il file per il `System.Linq.Expressions` dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="97e6c-109">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3.  <span data-ttu-id="97e6c-110">Aggiungere la `AndAlsoModifier` classe al progetto.</span><span class="sxs-lookup"><span data-stu-id="97e6c-110">Add the `AndAlsoModifier` class to your project.</span></span>  
  
    ```vb  
    Public Class AndAlsoModifier  
        Inherits ExpressionVisitor  
  
        Public Function Modify(ByVal expr As Expression) As Expression  
            Return Visit(expr)  
        End Function  
  
        Protected Overrides Function VisitBinary(ByVal b As BinaryExpression) As Expression  
            If b.NodeType = ExpressionType.AndAlso Then  
                Dim left = Me.Visit(b.Left)  
                Dim right = Me.Visit(b.Right)  
  
                ' Make this binary expression an OrElse operation instead   
                ' of an AndAlso operation.  
                Return Expression.MakeBinary(ExpressionType.OrElse, left, right, _  
                                             b.IsLiftedToNull, b.Method)  
            End If  
  
            Return MyBase.VisitBinary(b)  
        End Function  
    End Class  
    ```  
  
     <span data-ttu-id="97e6c-111">Questa classe eredita la <xref:System.Linq.Expressions.ExpressionVisitor>classe ed è specializzata per modificare le espressioni che rappresentano condizionale `AND` operations.</xref:System.Linq.Expressions.ExpressionVisitor></span><span class="sxs-lookup"><span data-stu-id="97e6c-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="97e6c-112">Queste operazioni vengono modificate da un'istruzione condizionale `AND` a un'istruzione condizionale `OR`.</span><span class="sxs-lookup"><span data-stu-id="97e6c-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="97e6c-113">A tale scopo, la classe esegue l'override di <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A>metodo del tipo di base, poiché condizionale `AND` le espressioni sono rappresentate come espressioni binarie.</xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A></span><span class="sxs-lookup"><span data-stu-id="97e6c-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="97e6c-114">Nel `VisitBinary` (metodo), se l'espressione che viene passato al metodo rappresenta un'istruzione condizionale `AND` operazione, il codice costruisce una nuova espressione che contiene il condizionale `OR` operatore anziché condizionale `AND` operatore.</span><span class="sxs-lookup"><span data-stu-id="97e6c-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="97e6c-115">Se l'espressione che viene passato a `VisitBinary` non rappresenta un'istruzione condizionale `AND` operazione, il metodo rinvia all'implementazione della classe base.</span><span class="sxs-lookup"><span data-stu-id="97e6c-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="97e6c-116">I metodi della classe base costruiscono nodi sono come le strutture ad albero dell'espressione viene passati, ma i nodi dispongono delle strutture sub sostituite con le strutture ad albero dell'espressione che sono generati in modo ricorsivo dal visitatore.</span><span class="sxs-lookup"><span data-stu-id="97e6c-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4.  <span data-ttu-id="97e6c-117">Aggiungere un `Imports` istruzione per il file per il `System.Linq.Expressions` dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="97e6c-117">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5.  <span data-ttu-id="97e6c-118">Aggiungere codice per il `Main` metodo nel file Module1. vb per creare una struttura ad albero dell'espressione e passarla al metodo a cui verrà modificato in modo.</span><span class="sxs-lookup"><span data-stu-id="97e6c-118">Add code to the `Main` method in the Module1.vb file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
    ```vb  
    Dim expr As Expression(Of Func(Of String, Boolean)) = _  
        Function(name) name.Length > 10 AndAlso name.StartsWith("G")  
  
    Console.WriteLine(expr)  
  
    Dim modifier As New AndAlsoModifier()  
    Dim modifiedExpr = modifier.Modify(CType(expr, Expression))  
  
    Console.WriteLine(modifiedExpr)  
  
    ' This code produces the following output:  
    ' name => ((name.Length > 10) && name.StartsWith("G"))  
    ' name => ((name.Length > 10) || name.StartsWith("G"))  
    ```  
  
     <span data-ttu-id="97e6c-119">Il codice crea un'espressione che contiene un'istruzione condizionale `AND` operazione.</span><span class="sxs-lookup"><span data-stu-id="97e6c-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="97e6c-120">Viene quindi creata un'istanza del `AndAlsoModifier` classe e viene passata l'espressione per il `Modify` metodo di questa classe.</span><span class="sxs-lookup"><span data-stu-id="97e6c-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="97e6c-121">Per mostrare le modifiche restituite originale e le strutture ad albero dell'espressione modificata.</span><span class="sxs-lookup"><span data-stu-id="97e6c-121">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6.  <span data-ttu-id="97e6c-122">Compilare l'applicazione ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="97e6c-122">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97e6c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97e6c-123">See Also</span></span>  
 <span data-ttu-id="97e6c-124">[Procedura: eseguire alberi delle espressioni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span><span class="sxs-lookup"><span data-stu-id="97e6c-124">[How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span></span>  
<span data-ttu-id="97e6c-125"> [Alberi delle espressioni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span><span class="sxs-lookup"><span data-stu-id="97e6c-125"> [Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span></span>
