---
title: "Procedura: modificare strutture ad albero dell'espressione"
ms.date: 07/20/2015
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
ms.openlocfilehash: 1f052120a2e7e12f5a985adce3ae193afec0e9af
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410992"
---
# <a name="how-to-modify-expression-trees-visual-basic"></a><span data-ttu-id="6c3ac-102">How to: Modify Expression Trees (Visual Basic) (Procedura: Modificare alberi delle espressioni (Visual Basic)).</span><span class="sxs-lookup"><span data-stu-id="6c3ac-102">How to: Modify Expression Trees (Visual Basic)</span></span>

<span data-ttu-id="6c3ac-103">In questo argomento viene illustrato come modificare un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="6c3ac-104">Gli alberi delle espressioni non sono modificabili, il che significa che non possono essere modificati direttamente.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="6c3ac-105">Per modificare un albero delle espressioni, è necessario creare una copia dell'albero esistente e solo in seguito apportare le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="6c3ac-106">È possibile usare la classe <xref:System.Linq.Expressions.ExpressionVisitor> per attraversare un albero delle espressioni esistente e copiare ogni nodo visitato.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>

## <a name="to-modify-an-expression-tree"></a><span data-ttu-id="6c3ac-107">Per modificare un albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="6c3ac-107">To modify an expression tree</span></span>

1. <span data-ttu-id="6c3ac-108">Creare un nuovo progetto di **applicazione console** .</span><span class="sxs-lookup"><span data-stu-id="6c3ac-108">Create a new **Console Application** project.</span></span>

2. <span data-ttu-id="6c3ac-109">Aggiungere un' `Imports` istruzione al file per lo `System.Linq.Expressions` spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-109">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>

3. <span data-ttu-id="6c3ac-110">Aggiungere la classe `AndAlsoModifier` al progetto.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-110">Add the `AndAlsoModifier` class to your project.</span></span>

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

    <span data-ttu-id="6c3ac-111">La classe eredita la classe <xref:System.Linq.Expressions.ExpressionVisitor> ed è specializzata per modificare le espressioni che rappresentano operazioni `AND` condizionali.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="6c3ac-112">Modifica tali operazioni da un'operazione `AND` condizionale a un'operazione `OR` condizionale.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="6c3ac-113">A tale scopo, la classe esegue l'override del metodo <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> del tipo di base, perché le espressioni `AND` condizionali sono rappresentate come espressioni binarie.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="6c3ac-114">Se l'espressione che viene passata al metodo `VisitBinary` rappresenta un'operazione `AND` condizionale, il codice costruisce una nuova espressione che contiene l'operatore condizionale `OR` anziché l'operatore condizionale `AND`.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="6c3ac-115">Se l'espressione che viene passata a `VisitBinary` non rappresenta un'operazione `AND` condizionale, il metodo rimanda all'implementazione della classe base.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="6c3ac-116">I metodi della classe base costruiscono nodi uguali agli alberi delle espressione passati, ma i sottoalberi dei nodi vengono sostituiti con gli alberi delle espressioni che vengono generati in modo ricorsivo dal visitatore.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>

4. <span data-ttu-id="6c3ac-117">Aggiungere un' `Imports` istruzione al file per lo `System.Linq.Expressions` spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-117">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>

5. <span data-ttu-id="6c3ac-118">Aggiungere il codice al `Main` metodo nel file Module1. vb per creare un albero delle espressioni e passarlo al metodo che lo modificherà.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-118">Add code to the `Main` method in the Module1.vb file to create an expression tree and pass it to the method that will modify it.</span></span>

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

    <span data-ttu-id="6c3ac-119">Il codice crea un'espressione che contiene un'operazione `AND` condizionale.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="6c3ac-120">Viene quindi creata un'istanza della classe `AndAlsoModifier` e l'espressione viene passata al metodo `Modify` della classe.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="6c3ac-121">Sia l'albero delle espressioni originale che quello modificato vengono inclusi nell'output per illustrare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-121">Both the original and the modified expression trees are outputted to show the change.</span></span>

6. <span data-ttu-id="6c3ac-122">Compilare l'applicazione ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-122">Compile and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c3ac-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c3ac-123">See also</span></span>

- <span data-ttu-id="6c3ac-124">[How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md) (Procedura: Eseguire alberi delle espressioni (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="6c3ac-124">[How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md)</span></span>
- [<span data-ttu-id="6c3ac-125">Alberi delle espressioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c3ac-125">Expression Trees (Visual Basic)</span></span>](index.md)
