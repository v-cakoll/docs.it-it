---
title: Come modificare gli alberi delle espressioni (c'è)How to modify expression trees (C
ms.date: 07/20/2015
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
ms.openlocfilehash: e921c594497d02f5eb16cc60294e947e83636d7a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73969895"
---
# <a name="how-to-modify-expression-trees-c"></a>Come modificare gli alberi delle espressioni (c'è)How to modify expression trees (C
In questo argomento viene illustrato come modificare un albero delle espressioni. Gli alberi delle espressioni non sono modificabili, il che significa che non possono essere modificati direttamente. Per modificare un albero delle espressioni, è necessario creare una copia dell'albero esistente e solo in seguito apportare le modifiche necessarie. È possibile usare la classe <xref:System.Linq.Expressions.ExpressionVisitor> per attraversare un albero delle espressioni esistente e copiare ogni nodo visitato.  
  
### <a name="to-modify-an-expression-tree"></a>Per modificare un albero delle espressioni  
  
1. Creare un nuovo progetto **Applicazione console.**  
  
2. Aggiungere al file una direttiva `using` per lo spazio dei nomi `System.Linq.Expressions`.  
  
3. Aggiungere la classe `AndAlsoModifier` al progetto.  
  
    ```csharp  
    public class AndAlsoModifier : ExpressionVisitor  
    {  
        public Expression Modify(Expression expression)  
        {  
            return Visit(expression);  
        }  
  
        protected override Expression VisitBinary(BinaryExpression b)  
        {  
            if (b.NodeType == ExpressionType.AndAlso)  
            {  
                Expression left = this.Visit(b.Left);  
                Expression right = this.Visit(b.Right);  
  
                // Make this binary expression an OrElse operation instead of an AndAlso operation.  
                return Expression.MakeBinary(ExpressionType.OrElse, left, right, b.IsLiftedToNull, b.Method);  
            }  
  
            return base.VisitBinary(b);  
        }  
    }  
    ```  
  
     La classe eredita la classe <xref:System.Linq.Expressions.ExpressionVisitor> ed è specializzata per modificare le espressioni che rappresentano operazioni `AND` condizionali. Modifica tali operazioni da un'operazione `AND` condizionale a un'operazione `OR` condizionale. A tale scopo, la classe esegue l'override del metodo <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> del tipo di base, perché le espressioni `AND` condizionali sono rappresentate come espressioni binarie. Se l'espressione che viene passata al metodo `VisitBinary` rappresenta un'operazione `AND` condizionale, il codice costruisce una nuova espressione che contiene l'operatore condizionale `OR` anziché l'operatore condizionale `AND`. Se l'espressione che viene passata a `VisitBinary` non rappresenta un'operazione `AND` condizionale, il metodo rimanda all'implementazione della classe base. I metodi della classe base costruiscono nodi uguali agli alberi delle espressione passati, ma i sottoalberi dei nodi vengono sostituiti con gli alberi delle espressioni che vengono generati in modo ricorsivo dal visitatore.  
  
4. Aggiungere al file una direttiva `using` per lo spazio dei nomi `System.Linq.Expressions`.  
  
5. Aggiungere codice al metodo `Main` nel file Program.cs per creare un albero delle espressioni e passarlo al metodo che lo modificherà.  
  
    ```csharp  
    Expression<Func<string, bool>> expr = name => name.Length > 10 && name.StartsWith("G");  
    Console.WriteLine(expr);  
  
    AndAlsoModifier treeModifier = new AndAlsoModifier();  
    Expression modifiedExpr = treeModifier.Modify((Expression) expr);  
  
    Console.WriteLine(modifiedExpr);  
  
    /*  This code produces the following output:  
  
        name => ((name.Length > 10) && name.StartsWith("G"))  
        name => ((name.Length > 10) || name.StartsWith("G"))  
    */  
    ```  
  
     Il codice crea un'espressione che contiene un'operazione `AND` condizionale. Viene quindi creata un'istanza della classe `AndAlsoModifier` e l'espressione viene passata al metodo `Modify` della classe. Sia l'albero delle espressioni originale che quello modificato vengono inclusi nell'output per illustrare le modifiche.  
  
6. Compilare l'applicazione ed eseguirla.  
  
## <a name="see-also"></a>Vedere anche

- [Come eseguire gli alberi delle espressioni (c'è)How to execute expression trees (C](./how-to-execute-expression-trees.md)
- [Alberi delle espressioni (C#)](./index.md)
