---
title: Come modificare gli alberi delle espressioni (C#)
description: Informazioni su come modificare un albero delle espressioni creando una copia di un albero delle espressioni esistente e apportando le modifiche necessarie.
ms.date: 07/20/2015
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
ms.openlocfilehash: 45aea18e253811d4e5c60f23f7f8496d4358f64c
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105602"
---
# <a name="how-to-modify-expression-trees-c"></a><span data-ttu-id="7df57-103">Come modificare gli alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="7df57-103">How to modify expression trees (C#)</span></span>
<span data-ttu-id="7df57-104">In questo argomento viene illustrato come modificare un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="7df57-104">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="7df57-105">Gli alberi delle espressioni non sono modificabili, il che significa che non possono essere modificati direttamente.</span><span class="sxs-lookup"><span data-stu-id="7df57-105">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="7df57-106">Per modificare un albero delle espressioni, è necessario creare una copia dell'albero esistente e solo in seguito apportare le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="7df57-106">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="7df57-107">È possibile usare la classe <xref:System.Linq.Expressions.ExpressionVisitor> per attraversare un albero delle espressioni esistente e copiare ogni nodo visitato.</span><span class="sxs-lookup"><span data-stu-id="7df57-107">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="7df57-108">Per modificare un albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="7df57-108">To modify an expression tree</span></span>  
  
1. <span data-ttu-id="7df57-109">Creare un nuovo progetto di **applicazione console** .</span><span class="sxs-lookup"><span data-stu-id="7df57-109">Create a new **Console Application** project.</span></span>  
  
2. <span data-ttu-id="7df57-110">Aggiungere al file una direttiva `using` per lo spazio dei nomi `System.Linq.Expressions`.</span><span class="sxs-lookup"><span data-stu-id="7df57-110">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3. <span data-ttu-id="7df57-111">Aggiungere la classe `AndAlsoModifier` al progetto.</span><span class="sxs-lookup"><span data-stu-id="7df57-111">Add the `AndAlsoModifier` class to your project.</span></span>  
  
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
  
     <span data-ttu-id="7df57-112">La classe eredita la classe <xref:System.Linq.Expressions.ExpressionVisitor> ed è specializzata per modificare le espressioni che rappresentano operazioni `AND` condizionali.</span><span class="sxs-lookup"><span data-stu-id="7df57-112">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="7df57-113">Modifica tali operazioni da un'operazione `AND` condizionale a un'operazione `OR` condizionale.</span><span class="sxs-lookup"><span data-stu-id="7df57-113">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="7df57-114">A tale scopo, la classe esegue l'override del metodo <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> del tipo di base, perché le espressioni `AND` condizionali sono rappresentate come espressioni binarie.</span><span class="sxs-lookup"><span data-stu-id="7df57-114">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="7df57-115">Se l'espressione che viene passata al metodo `VisitBinary` rappresenta un'operazione `AND` condizionale, il codice costruisce una nuova espressione che contiene l'operatore condizionale `OR` anziché l'operatore condizionale `AND`.</span><span class="sxs-lookup"><span data-stu-id="7df57-115">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="7df57-116">Se l'espressione che viene passata a `VisitBinary` non rappresenta un'operazione `AND` condizionale, il metodo rimanda all'implementazione della classe base.</span><span class="sxs-lookup"><span data-stu-id="7df57-116">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="7df57-117">I metodi della classe base costruiscono nodi uguali agli alberi delle espressione passati, ma i sottoalberi dei nodi vengono sostituiti con gli alberi delle espressioni che vengono generati in modo ricorsivo dal visitatore.</span><span class="sxs-lookup"><span data-stu-id="7df57-117">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4. <span data-ttu-id="7df57-118">Aggiungere al file una direttiva `using` per lo spazio dei nomi `System.Linq.Expressions`.</span><span class="sxs-lookup"><span data-stu-id="7df57-118">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5. <span data-ttu-id="7df57-119">Aggiungere codice al metodo `Main` nel file Program.cs per creare un albero delle espressioni e passarlo al metodo che lo modificherà.</span><span class="sxs-lookup"><span data-stu-id="7df57-119">Add code to the `Main` method in the Program.cs file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
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
  
     <span data-ttu-id="7df57-120">Il codice crea un'espressione che contiene un'operazione `AND` condizionale.</span><span class="sxs-lookup"><span data-stu-id="7df57-120">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="7df57-121">Viene quindi creata un'istanza della classe `AndAlsoModifier` e l'espressione viene passata al metodo `Modify` della classe.</span><span class="sxs-lookup"><span data-stu-id="7df57-121">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="7df57-122">Sia l'albero delle espressioni originale che quello modificato vengono inclusi nell'output per illustrare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="7df57-122">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6. <span data-ttu-id="7df57-123">Compilare l'applicazione ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="7df57-123">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df57-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7df57-124">See also</span></span>

- [<span data-ttu-id="7df57-125">Come eseguire gli alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="7df57-125">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="7df57-126">Alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="7df57-126">Expression Trees (C#)</span></span>](./index.md)
