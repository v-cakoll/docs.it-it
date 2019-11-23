---
title: 'Procedura: Modificare alberi delle espressioni'
ms.date: 07/20/2015
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
ms.openlocfilehash: 12ccad6df7d6c7d91ebc290163db362eae173209
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353752"
---
# <a name="how-to-modify-expression-trees-visual-basic"></a>How to: Modify Expression Trees (Visual Basic)

In questo argomento viene illustrato come modificare un albero delle espressioni. Gli alberi delle espressioni non sono modificabili, il che significa che non possono essere modificati direttamente. Per modificare un albero delle espressioni, è necessario creare una copia dell'albero esistente e solo in seguito apportare le modifiche necessarie. È possibile usare la classe <xref:System.Linq.Expressions.ExpressionVisitor> per attraversare un albero delle espressioni esistente e copiare ogni nodo visitato.

## <a name="to-modify-an-expression-tree"></a>Per modificare un albero delle espressioni

1. Creare un nuovo progetto **applicazione console**.

2. Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.

3. Aggiungere la classe `AndAlsoModifier` al progetto.

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

    La classe eredita la classe <xref:System.Linq.Expressions.ExpressionVisitor> ed è specializzata per modificare le espressioni che rappresentano operazioni `AND` condizionali. Modifica tali operazioni da un'operazione `AND` condizionale a un'operazione `OR` condizionale. A tale scopo, la classe esegue l'override del metodo <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> del tipo di base, perché le espressioni `AND` condizionali sono rappresentate come espressioni binarie. Se l'espressione che viene passata al metodo `VisitBinary` rappresenta un'operazione `AND` condizionale, il codice costruisce una nuova espressione che contiene l'operatore condizionale `OR` anziché l'operatore condizionale `AND`. Se l'espressione che viene passata a `VisitBinary` non rappresenta un'operazione `AND` condizionale, il metodo rimanda all'implementazione della classe base. I metodi della classe base costruiscono nodi uguali agli alberi delle espressione passati, ma i sottoalberi dei nodi vengono sostituiti con gli alberi delle espressioni che vengono generati in modo ricorsivo dal visitatore.

4. Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.

5. Add code to the `Main` method in the Module1.vb file to create an expression tree and pass it to the method that will modify it.

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

    Il codice crea un'espressione che contiene un'operazione `AND` condizionale. Viene quindi creata un'istanza della classe `AndAlsoModifier` e l'espressione viene passata al metodo `Modify` della classe. Sia l'albero delle espressioni originale che quello modificato vengono inclusi nell'output per illustrare le modifiche.

6. Compilare l'applicazione ed eseguirla.

## <a name="see-also"></a>Vedere anche

- [How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
- [Alberi delle espressioni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
