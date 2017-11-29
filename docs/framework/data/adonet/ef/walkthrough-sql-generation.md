---
title: 'Procedura dettagliata: generazione SQL'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16c38aaa-9927-4f3c-ab0f-81636cce57a3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8c19c459bf3b62b7e1d7e2917e09717c246e728c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-sql-generation"></a><span data-ttu-id="74d8c-102">Procedura dettagliata: generazione SQL</span><span class="sxs-lookup"><span data-stu-id="74d8c-102">Walkthrough: SQL Generation</span></span>
<span data-ttu-id="74d8c-103">In questo argomento viene illustrato come modalità di generazione SQL nel [Provider di esempio](http://go.microsoft.com/fwlink/?LinkId=180616).</span><span class="sxs-lookup"><span data-stu-id="74d8c-103">This topic illustrates how SQL generation occurs in the [Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616).</span></span> <span data-ttu-id="74d8c-104">Nella query Entity SQL seguente viene usato il modello incluso nel provider di esempio:</span><span class="sxs-lookup"><span data-stu-id="74d8c-104">The following Entity SQL query uses the model that is included with the sample provider:</span></span>  
  
```  
SELECT  j1.ProductId, j1.ProductName, j1.CategoryName, j2.ShipCountry, j2.ProductId  
FROM (  SELECT P.ProductName, P.ProductId, P.Category.CategoryName  
        FROM NorthwindEntities.Products AS P) as j1  
INNER JOIN (SELECT OD.ProductId, OD.Order.ShipCountry as ShipCountry  
            FROM NorthwindEntities.OrderDetails AS OD) as j2  
            ON j1.ProductId == j2.ProductId   
```  
  
 <span data-ttu-id="74d8c-105">La query produce il seguente albero dei comandi di output passato al provider:</span><span class="sxs-lookup"><span data-stu-id="74d8c-105">The query produces the following output command tree that is passed to the provider:</span></span>  
  
```  
DbQueryCommandTree  
|_Parameters  
|_Query : Collection{Record['C1'=Edm.Int32, 'ProductID'=Edm.Int32, 'ProductName'=Edm.String, 'CategoryName'=Edm.String, 'ShipCountry'=Edm.String, 'ProductID1'=Edm.Int32]}  
  |_Project  
    |_Input : 'Join4'  
    | |_InnerJoin  
    |   |_Left : 'Join1'  
    |   | |_LeftOuterJoin  
    |   |   |_Left : 'Extent1'  
    |   |   | |_Scan : dbo.Products  
    |   |   |_Right : 'Extent2'  
    |   |   | |_Scan : dbo.Categories  
    |   |   |_JoinCondition  
    |   |     |_  
    |   |       |_Var(Extent1).CategoryID  
    |   |       |_=  
    |   |       |_Var(Extent2).CategoryID  
    |   |_Right : 'Join3'  
    |   | |_LeftOuterJoin  
    |   |   |_Left : 'Extent3'  
    |   |   | |_Scan : dbo.OrderDetails  
    |   |   |_Right : 'Join2'  
    |   |   | |_LeftOuterJoin  
    |   |   |   |_Left : 'Extent4'  
    |   |   |   | |_Scan : dbo.Orders  
    |   |   |   |_Right : 'Extent5'  
    |   |   |   | |_Scan : dbo.InternationalOrders  
    |   |   |   |_JoinCondition  
    |   |   |     |_  
    |   |   |       |_Var(Extent4).OrderID  
    |   |   |       |_=  
    |   |   |       |_Var(Extent5).OrderID  
    |   |   |_JoinCondition  
    |   |     |_  
    |   |       |_Var(Extent3).OrderID  
    |   |       |_=  
    |   |       |_Var(Join2).Extent4.OrderID  
    |   |_JoinCondition  
    |     |_  
    |       |_Var(Join1).Extent1.ProductID  
    |       |_=  
    |       |_Var(Join3).Extent3.ProductID  
    |_Projection  
      |_NewInstance : Record['C1'=Edm.Int32, 'ProductID'=Edm.Int32, 'ProductName'=Edm.String, 'CategoryName'=Edm.String, 'ShipCountry'=Edm.String, 'ProductID1'=Edm.Int32]  
        |_Column : 'C1'  
        | |_1  
        |_Column : 'ProductID'  
        | |_Var(Join4).Join1.Extent1.ProductID  
        |_Column : 'ProductName'  
        | |_Var(Join4).Join1.Extent1.ProductName  
        |_Column : 'CategoryName'  
        | |_Var(Join4).Join1.Extent2.CategoryName  
        |_Column : 'ShipCountry'  
        | |_Var(Join4).Join3.Join2.Extent4.ShipCountry  
        |_Column : 'ProductID1'  
          |_Var(Join4).Join3.Extent3.ProductID  
```  
  
 <span data-ttu-id="74d8c-106">In questo argomento viene descritto come convertire l'albero dei comandi di output nelle istruzioni SQL riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="74d8c-106">This topic describes how to translate this output command tree into the following SQL statements.</span></span>  
  
```  
SELECT   
1 AS [C1],   
[Extent1].[ProductID] AS [ProductID],   
[Extent1].[ProductName] AS [ProductName],   
[Extent2].[CategoryName] AS [CategoryName],   
[Join3].[ShipCountry] AS [ShipCountry],   
[Join3].[ProductID] AS [ProductID1]  
FROM   [dbo].[Products] AS [Extent1]  
LEFT OUTER JOIN [dbo].[Categories] AS [Extent2] ON [Extent1].[CategoryID] = [Extent2].[CategoryID]  
INNER JOIN    
(SELECT [Extent3].[OrderID] AS [OrderID1], [Extent3].[ProductID] AS [ProductID], [Extent3].[UnitPrice] AS [UnitPrice], [Extent3].[Quantity] AS [Quantity], [Extent3].[Discount] AS [Discount], [Join2].[OrderID2], [Join2].[CustomerID], [Join2].[EmployeeID], [Join2].[OrderDate], [Join2].[RequiredDate], [Join2].[ShippedDate], [Join2].[Freight], [Join2].[ShipName], [Join2].[ShipAddress], [Join2].[ShipCity], [Join2].[ShipRegion], [Join2].[ShipPostalCode], [Join2].[ShipCountry], [Join2].[OrderID3], [Join2].[CustomsDescription], [Join2].[ExciseTax]  
FROM  [dbo].[OrderDetails] AS [Extent3]  
LEFT OUTER JOIN    
      (SELECT [Extent4].[OrderID] AS [OrderID2], [Extent4].[CustomerID] AS [CustomerID], [Extent4].[EmployeeID] AS [EmployeeID], [Extent4].[OrderDate] AS [OrderDate], [Extent4].[RequiredDate] AS [RequiredDate], [Extent4].[ShippedDate] AS [ShippedDate], [Extent4].[Freight] AS [Freight], [Extent4].[ShipName] AS [ShipName], [Extent4].[ShipAddress] AS [ShipAddress], [Extent4].[ShipCity] AS [ShipCity], [Extent4].[ShipRegion] AS [ShipRegion], [Extent4].[ShipPostalCode] AS [ShipPostalCode], [Extent4].[ShipCountry] AS [ShipCountry], [Extent5].[OrderID] AS [OrderID3], [Extent5].[CustomsDescription] AS [CustomsDescription], [Extent5].[ExciseTax] AS [ExciseTax]  
FROM  [dbo].[Orders] AS [Extent4]  
LEFT OUTER JOIN [dbo].[InternationalOrders] AS [Extent5] ON [Extent4].[OrderID] = [Extent5].[OrderID]   
      ) AS [Join2] ON [Extent3].[OrderID] = [Join2].[OrderID2]   
   ) AS [Join3] ON [Extent1].[ProductID] = [Join3].[ProductID]  
```  
  
## <a name="first-phase-of-sql-generation-visiting-the-expression-tree"></a><span data-ttu-id="74d8c-107">Prima fase della generazione SQL: visita dell'albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="74d8c-107">First Phase of SQL Generation: Visiting the Expression Tree</span></span>  
 <span data-ttu-id="74d8c-108">Nella figura seguente viene illustrato lo stato vuoto iniziale del visitatore.</span><span class="sxs-lookup"><span data-stu-id="74d8c-108">The following figure illustrates the initial empty state of the visitor.</span></span>  <span data-ttu-id="74d8c-109">Nell'argomento vengono illustrate solo le proprietà che si riferiscono alla descrizione della procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="74d8c-109">Throughout this topic, only the properties relevant to the walkthrough explanation are shown.</span></span>  
  
 <span data-ttu-id="74d8c-110">![Diagramma](../../../../../docs/framework/data/adonet/ef/media/430180f5-4fb9-4bc3-8589-d566512d9703.gif "430180f5-4fb9-4bc3-8589-d566512d9703")</span><span class="sxs-lookup"><span data-stu-id="74d8c-110">![Diagram](../../../../../docs/framework/data/adonet/ef/media/430180f5-4fb9-4bc3-8589-d566512d9703.gif "430180f5-4fb9-4bc3-8589-d566512d9703")</span></span>  
  
 <span data-ttu-id="74d8c-111">Quando si visita il nodo Project, viene effettuata la chiamata a VisitInputExpression sul relativo input (Join4), che attiva la visita di Join4 mediante il metodo VisitJoinExpression.</span><span class="sxs-lookup"><span data-stu-id="74d8c-111">When the Project  node is visited, VisitInputExpression is called over its input (Join4), which triggers the visit of Join4 by the method VisitJoinExpression.</span></span> <span data-ttu-id="74d8c-112">Poiché si tratta di un join di livello superiore, IsParentAJoin restituisce false e un nuovo oggetto SqlSelectStatement (SelectStatement0) viene creato e inserito nello stack di istruzioni SELECT.</span><span class="sxs-lookup"><span data-stu-id="74d8c-112">Because this is a topmost join, IsParentAJoin returns false and a new SqlSelectStatement (SelectStatement0) is created and pushed on the SELECT statement stack.</span></span> <span data-ttu-id="74d8c-113">Viene inoltre inserito un nuovo ambito (scope0) nella tabella dei simboli.</span><span class="sxs-lookup"><span data-stu-id="74d8c-113">Also, a new scope (scope0) is entered in the symbol table.</span></span> <span data-ttu-id="74d8c-114">Prima della visita del primo input di sinistra (Left) del join, nello stack IsParentAJoin viene inserito "true".</span><span class="sxs-lookup"><span data-stu-id="74d8c-114">Before the first (left) input of the join is visited, 'true' is pushed on the IsParentAJoin stack.</span></span> <span data-ttu-id="74d8c-115">Prima della visita di Join1, ovvero l'input di sinistra di Join4, lo stato del visitatore corrisponde a quello illustrato nella figura che segue.</span><span class="sxs-lookup"><span data-stu-id="74d8c-115">Right before Join1, which is the left input of Join4, is visited, the state of the visitor is as shown in the next figure.</span></span>  
  
 <span data-ttu-id="74d8c-116">![Diagramma](../../../../../docs/framework/data/adonet/ef/media/406d4f5f-6166-44ea-8e74-c5001d5d5d79.gif "406d4f5f-6166-44ea-8e74-c5001d5d5d79")</span><span class="sxs-lookup"><span data-stu-id="74d8c-116">![Diagram](../../../../../docs/framework/data/adonet/ef/media/406d4f5f-6166-44ea-8e74-c5001d5d5d79.gif "406d4f5f-6166-44ea-8e74-c5001d5d5d79")</span></span>  
  
 <span data-ttu-id="74d8c-117">Quando il metodo di visita del join viene richiamato su Join4, IsParentAJoin è true e pertanto riusa l'istruzione Select corrente SelectStatement0.</span><span class="sxs-lookup"><span data-stu-id="74d8c-117">When the join visit method is invoked over Join4, IsParentAJoin is true, thus it reuses the current select statement SelectStatement0.</span></span> <span data-ttu-id="74d8c-118">Viene immesso un nuovo ambito (scope1).</span><span class="sxs-lookup"><span data-stu-id="74d8c-118">A new scope is entered (scope1).</span></span> <span data-ttu-id="74d8c-119">Prima di visitare l'elemento figlio di sinistra, Extent1, nello stack IsParentAJoin viene inserito un altro valore true.</span><span class="sxs-lookup"><span data-stu-id="74d8c-119">Before visiting its left child, Extent1, another true is pushed on the IsParentAJoin stack.</span></span>  
  
 <span data-ttu-id="74d8c-120">Poiché IsParentAJoin restituisce true, quando viene visitato Extent1 restituisce un oggetto SqlBuilder contenente "[dbo].[Products]".</span><span class="sxs-lookup"><span data-stu-id="74d8c-120">When Extent1 is visited, because IsParentAJoin returns true, it returns a SqlBuilder containing "[dbo].[Products]".</span></span> <span data-ttu-id="74d8c-121">Il controllo viene restituito al metodo che visita Join4.</span><span class="sxs-lookup"><span data-stu-id="74d8c-121">The control returns to the method visiting Join4.</span></span> <span data-ttu-id="74d8c-122">Viene estratta una voce da IsParentAJoin e viene chiamato l'oggetto ProcessJoinInputResult, con la conseguente aggiunta del risultato della visita di Extent1 alla clausola From di SelectStatement0.</span><span class="sxs-lookup"><span data-stu-id="74d8c-122">An entry is popped from IsParentAJoin, and ProcessJoinInputResult is called, which appends the result of visiting Extent1 to the From clause of SelectStatement0.</span></span> <span data-ttu-id="74d8c-123">Un nuovo simbolo from, symbol_Extent1, per il nome dell'associazione di input "Extent1" viene creato e aggiunto all'oggetto FromExtents di SelectStatement0. "As" e symbol_Extent1 vengono inoltre aggiunti alla clausola from.</span><span class="sxs-lookup"><span data-stu-id="74d8c-123">A new from symbol, symbol_Extent1, for the input binding name "Extent1" is created, added to the FromExtents of SelectStatement0, and also "As" and  symbol_Extent1 are appended to the from clause.</span></span> <span data-ttu-id="74d8c-124">Una nuova voce viene aggiunta a AllExtentNames per "Extent1" con il valore 0.</span><span class="sxs-lookup"><span data-stu-id="74d8c-124">A new entry is added to AllExtentNames for "Extent1" with the value of 0.</span></span> <span data-ttu-id="74d8c-125">Una nuova voce viene aggiunta all'ambito corrente nella tabella dei simboli per associare "Extent1" al relativo simbolo symbol_Extent1.</span><span class="sxs-lookup"><span data-stu-id="74d8c-125">A new entry is added to the current scope in the symbol table to associate "Extent1" with its symbol symbol_Extent1.</span></span> <span data-ttu-id="74d8c-126">Symbol_Extent1 viene inoltre aggiunto all'oggetto AllJoinExtents di SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="74d8c-126">Symbol_Extent1 is also added to the AllJoinExtents of the SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="74d8c-127">Prima della visita dell'input di destra (Right) di Join1, "LEFT OUTER JOIN" viene aggiunto alla clausola From di SelectStatement0.</span><span class="sxs-lookup"><span data-stu-id="74d8c-127">Before the right input of Join1 is visited, "LEFT OUTER JOIN" is added to the From clause of SelectStatement0.</span></span> <span data-ttu-id="74d8c-128">Poiché l'input di destra è un'espressione Scan, nello stack IsParentAJoin viene nuovamente inserito il valore true.</span><span class="sxs-lookup"><span data-stu-id="74d8c-128">Because the right input is a Scan expression, true is again pushed to the IsParentAJoin stack.</span></span> <span data-ttu-id="74d8c-129">Lo stato prima della visita dell'input di destra viene illustrato nella figura che segue.</span><span class="sxs-lookup"><span data-stu-id="74d8c-129">The state before visiting the right input as shown in the next figure.</span></span>  
  
 <span data-ttu-id="74d8c-130">![Diagramma](../../../../../docs/framework/data/adonet/ef/media/ca62c31b-7ff6-4836-b209-e16166304fdc.gif "ca62c31b-7ff6-4836-b209-e16166304fdc")</span><span class="sxs-lookup"><span data-stu-id="74d8c-130">![Diagram](../../../../../docs/framework/data/adonet/ef/media/ca62c31b-7ff6-4836-b209-e16166304fdc.gif "ca62c31b-7ff6-4836-b209-e16166304fdc")</span></span>  
  
 <span data-ttu-id="74d8c-131">L'input di destra viene elaborato esattamente come l'input di sinistra.</span><span class="sxs-lookup"><span data-stu-id="74d8c-131">The right input is processed in the same way as the left input.</span></span> <span data-ttu-id="74d8c-132">Lo stato dopo la visita dell'input di destra viene illustrato nella figura che segue.</span><span class="sxs-lookup"><span data-stu-id="74d8c-132">The state after visiting the right input is shown in the next figure.</span></span>  
  
 <span data-ttu-id="74d8c-133">![Diagramma](../../../../../docs/framework/data/adonet/ef/media/cd2afa99-7256-4c63-aaa9-c2d13f18a3d8.gif "cd2afa99-7256-4c63-aaa9-c2d13f18a3d8")</span><span class="sxs-lookup"><span data-stu-id="74d8c-133">![Diagram](../../../../../docs/framework/data/adonet/ef/media/cd2afa99-7256-4c63-aaa9-c2d13f18a3d8.gif "cd2afa99-7256-4c63-aaa9-c2d13f18a3d8")</span></span>  
  
 <span data-ttu-id="74d8c-134">Il valore "false" successivo viene inserito nello stack IsParentAJoin e la condizione di join Var(Extent1).CategoryID == Var(Extent2).CategoryID viene elaborata.</span><span class="sxs-lookup"><span data-stu-id="74d8c-134">Next "false" is pushed on the IsParentAJoin stack and the join condition Var(Extent1).CategoryID == Var(Extent2).CategoryID is processed.</span></span> <span data-ttu-id="74d8c-135">Var(Extenent1) viene risolto in <symbol_Extent1> dopo una ricerca nella tabella dei simboli.</span><span class="sxs-lookup"><span data-stu-id="74d8c-135">Var(Extenent1) is resolved to <symbol_Extent1> after a look up in the symbol table.</span></span> <span data-ttu-id="74d8c-136">Poiché l'istanza viene risolto in un simbolo semplice, in seguito all'elaborazione Var(Extent1). CategoryID, un oggetto SqlBuilder con \<symbol1 >. " Viene restituito CategoryID".</span><span class="sxs-lookup"><span data-stu-id="74d8c-136">Because the instance is resolved to a simple Symbol, as a result of processing Var(Extent1).CategoryID, a SqlBuilder with \<symbol1>."CategoryID" is returned.</span></span> <span data-ttu-id="74d8c-137">Analogamente, viene elaborato l'altro lato del confronto e il risultato della visita della condizione di join viene aggiunto alla clausola FROM di SelectStatement1 e il valore "false" viene estratto dallo stack IsParentAJoin.</span><span class="sxs-lookup"><span data-stu-id="74d8c-137">Similarly the other side of the comparison is processed, and the result of visiting the join condition is appended to the FROM clause of SelectStatement1 and the value "false" is popped from the IsParentAJoin stack.</span></span>  
  
 <span data-ttu-id="74d8c-138">A questo punto, l'elaborazione di Join1 è completa e viene estratto un ambito dalla tabella dei simboli.</span><span class="sxs-lookup"><span data-stu-id="74d8c-138">With this, Join1 has completely been processed, and a scope is popped from the symbol table.</span></span>  
  
 <span data-ttu-id="74d8c-139">Il controllo viene restituito all'elaborazione di Join4, ovvero l'elemento padre di Join1.</span><span class="sxs-lookup"><span data-stu-id="74d8c-139">Control returns to processing Join4, the parent of Join1.</span></span> <span data-ttu-id="74d8c-140">Poiché l'elemento figlio ha riutilizzato l'istruzione Select, gli extent di Join1 vengono sostituiti con un singolo simbolo di Join <joinSymbol_Join1>.</span><span class="sxs-lookup"><span data-stu-id="74d8c-140">Because the child reused the Select statement, the Join1 extents are replaced with a single Join symbol <joinSymbol_Join1>.</span></span> <span data-ttu-id="74d8c-141">Viene inoltre aggiunta una nuova voce alla tabella dei simboli per associare Join1 con <joinSymbol_Join1>.</span><span class="sxs-lookup"><span data-stu-id="74d8c-141">Also a new entry is added to the symbol table to associate Join1 with <joinSymbol_Join1>.</span></span>  
  
 <span data-ttu-id="74d8c-142">Il successivo nodo da elaborare è Join3, il secondo elemento figlio di Join4.</span><span class="sxs-lookup"><span data-stu-id="74d8c-142">The next node to be processed is Join3, the second child of Join4.</span></span> <span data-ttu-id="74d8c-143">Poiché è un elemento figlio di destra, viene inserito il valore "false" nello stack IsParentAJoin.</span><span class="sxs-lookup"><span data-stu-id="74d8c-143">As it is a right child, "false" is pushed to the IsParentAJoin stack.</span></span> <span data-ttu-id="74d8c-144">Lo stato del visitatore in questa fase viene illustrato nella figura che segue.</span><span class="sxs-lookup"><span data-stu-id="74d8c-144">The state of the visitor at this point is illustrated in the next figure.</span></span>  
  
 <span data-ttu-id="74d8c-145">![Diagramma](../../../../../docs/framework/data/adonet/ef/media/1ec61ed3-fcdd-4649-9089-24385be7e423.gif "1ec61ed3-fcdd-4649-9089-24385be7e423")</span><span class="sxs-lookup"><span data-stu-id="74d8c-145">![Diagram](../../../../../docs/framework/data/adonet/ef/media/1ec61ed3-fcdd-4649-9089-24385be7e423.gif "1ec61ed3-fcdd-4649-9089-24385be7e423")</span></span>  
  
 <span data-ttu-id="74d8c-146">Per Join3, IsParentAJoin restituisce false e deve avviare un nuovo oggetto SqlSelectStatement (SelectStatement1) e inserirlo nello stack.</span><span class="sxs-lookup"><span data-stu-id="74d8c-146">For Join3, IsParentAJoin returns false and needs to start a new SqlSelectStatement (SelectStatement1) and push it on the stack.</span></span> <span data-ttu-id="74d8c-147">L'elaborazione continua come per i join precedenti, viene inserito un nuovo ambito nello stack e gli elementi figlio vengono elaborati.</span><span class="sxs-lookup"><span data-stu-id="74d8c-147">Processing continues as it did with the previous the previous joins, a new scope is pushed on the stack and the children are processed.</span></span> <span data-ttu-id="74d8c-148">L'elemento figlio di sinistra è un extent (Extent3) mentre l'elemento figlio di destra è un join (Join2) che deve inoltre avviare un nuovo oggetto SqlSelectStatement: SelectStatement2.</span><span class="sxs-lookup"><span data-stu-id="74d8c-148">The left child is an Extent (Extent3) and the right child is a join (Join2) which also needs to start a new SqlSelectStatement: SelectStatement2.</span></span> <span data-ttu-id="74d8c-149">Anche gli elementi figlio di Join2 sono extent e vengono aggregati in SelectStatement2.</span><span class="sxs-lookup"><span data-stu-id="74d8c-149">The children on Join2 are Extents as well and are aggregated into SelectStatement2.</span></span>  
  
 <span data-ttu-id="74d8c-150">Lo stato del visitatore subito dopo la visita di Join2, ma prima che ne venga eseguita la post-elaborazione (ProcessJoinInputResult), viene illustrato nella figura che segue:</span><span class="sxs-lookup"><span data-stu-id="74d8c-150">The state of the visitor right after Join2 is visited, but before its post-processing (ProcessJoinInputResult) is done is shown in the next figure:</span></span>  
  
 <span data-ttu-id="74d8c-151">![Diagramma](../../../../../docs/framework/data/adonet/ef/media/7510346f-8b09-4c99-b411-40af239c3c4d.gif "7510346f-8b09-4c99-b411-40af239c3c4d")</span><span class="sxs-lookup"><span data-stu-id="74d8c-151">![Diagram](../../../../../docs/framework/data/adonet/ef/media/7510346f-8b09-4c99-b411-40af239c3c4d.gif "7510346f-8b09-4c99-b411-40af239c3c4d")</span></span>  
  
 <span data-ttu-id="74d8c-152">Nella figura precedente SelectStatement2 viene illustrato come oggetto mobile in quanto è stato estratto dallo stack, ma non ancora sottoposto alla post-elaborazione da parte dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="74d8c-152">In the previous figure, SelectStatement2 is shown as free floating because it was popped out of the stack, but not yet post processed by the parent.</span></span> <span data-ttu-id="74d8c-153">Deve essere aggiunto alla parte FROM dell'elemento padre, ma non è un'istruzione SQL completa se non include una clausola SELECT.</span><span class="sxs-lookup"><span data-stu-id="74d8c-153">It needs to be added to the FROM part of the parent, but it is not a complete SQL statement without a SELECT clause.</span></span> <span data-ttu-id="74d8c-154">A questo punto le colonne predefinite, ovvero tutte le colonne prodotte dai relativi input, vengono aggiunte all'elenco di selezione mediante il metodo AddDefaultColumns.</span><span class="sxs-lookup"><span data-stu-id="74d8c-154">So, at this point, the default columns (all the columns produced by its inputs) are added to the select list by the method AddDefaultColumns.</span></span> <span data-ttu-id="74d8c-155">AddDefaultColumns scorre i simboli in FromExtents e per ogni simbolo aggiunge tutte le colonne incluse nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="74d8c-155">AddDefaultColumns iterates over the symbols in FromExtents and for each symbol adds all the columns brought in scope.</span></span> <span data-ttu-id="74d8c-156">Per un simbolo semplice, analizza il tipo di simbolo per recuperarne tutte le proprietà da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="74d8c-156">For a simple symbol, it looks at the symbol type to retrieve all its properties to be added.</span></span> <span data-ttu-id="74d8c-157">Popola inoltre il dizionario AllColumnNames con i nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="74d8c-157">It also populates the AllColumnNames dictionary with the column names.</span></span> <span data-ttu-id="74d8c-158">L'oggetto SelectStatement2 completo viene aggiunto alla clausola FROM di SelectStatement1.</span><span class="sxs-lookup"><span data-stu-id="74d8c-158">The completed SelectStatement2 is appended to the FROM clause of SelectStatement1.</span></span>  
  
 <span data-ttu-id="74d8c-159">Successivamente, viene creato un nuovo simbolo di join per rappresentare Join2. Tale simbolo viene contrassegnato come join annidato, aggiunto all'oggetto AllJoinExtents di SelectStatement1 e infine alla tabella dei simboli.</span><span class="sxs-lookup"><span data-stu-id="74d8c-159">Next, a new join symbol is created to represent Join2, it is marked as a nested join and added to the AllJoinExtents of SelectStatement1 and added to the symbol table.</span></span>  <span data-ttu-id="74d8c-160">È ora necessario elaborare la condizione di join di Join3, Var(Extent3).OrderID = Var(Join2).Extent4.OrderID.</span><span class="sxs-lookup"><span data-stu-id="74d8c-160">Now the join condition of Join3, Var(Extent3).OrderID =  Var(Join2).Extent4.OrderID, needs to be processed.</span></span> <span data-ttu-id="74d8c-161">L'elaborazione del lato sinistro è simile alla condizione di join di Join1.</span><span class="sxs-lookup"><span data-stu-id="74d8c-161">Processing of the left hand side is similar to the join condition of Join1.</span></span> <span data-ttu-id="74d8c-162">L'elaborazione del lato destro "Var(Join2).Extent4.OrderID" è tuttavia diversa in quanto è richiesta la bidimensionalità del join.</span><span class="sxs-lookup"><span data-stu-id="74d8c-162">However, the processing of the right and side "Var(Join2).Extent4.OrderID" is different because join flattening is required.</span></span>  
  
 <span data-ttu-id="74d8c-163">Nella figura che segue viene illustrato lo stato del visitatore prima dell'elaborazione dell'oggetto DbPropertyExpression "Var(Join2).Extent4.OrderID".</span><span class="sxs-lookup"><span data-stu-id="74d8c-163">The next figure shows the state of the visitor right before the DbPropertyExpression "Var(Join2).Extent4.OrderID" is processed.</span></span>  
  
 <span data-ttu-id="74d8c-164">Si consideri il modo in cui viene visitato "Var(Join2).Extent4.OrderID".</span><span class="sxs-lookup"><span data-stu-id="74d8c-164">Consider how "Var(Join2).Extent4.OrderID" is visited.</span></span> <span data-ttu-id="74d8c-165">Viene innanzitutto visitata la proprietà dell'istanza "Var(Join2).Extent4", che rappresenta un altro oggetto DbPropertyExpression che visita prima la propria istanza "Var(Join2)".</span><span class="sxs-lookup"><span data-stu-id="74d8c-165">First, the instance property "Var(Join2).Extent4" is visited, which is another DbPropertyExpression and first visits its instance "Var(Join2)".</span></span> <span data-ttu-id="74d8c-166">Nell'ambito superiore della tabella dei simboli "Join2" viene risolto in <joinSymbol_join2>.</span><span class="sxs-lookup"><span data-stu-id="74d8c-166">In the top most scope in the symbol table, "Join2" resolves to <joinSymbol_join2>.</span></span> <span data-ttu-id="74d8c-167">Nel metodo di visita per l'oggetto DbPropertyExpression che elabora "Var(Join2).Extent4" si noterà che è stato restituito un simbolo di join durante la visita dell'istanza e che è necessaria la bidimensionalità.</span><span class="sxs-lookup"><span data-stu-id="74d8c-167">In the visit method for DbPropertyExpression processing "Var(Join2).Extent4" notice that a join symbol was returned when visiting the instance and flattening is required.</span></span>  
  
 <span data-ttu-id="74d8c-168">Poiché si tratta di un join annidato, viene cercata la proprietà "Extent4" nel dizionario NameToExtent del simbolo di join, che viene risolta in <symbol_Extent4>, e viene restituito un nuovo oggetto SymbolPair(<joinSymbol_join2>, <symbol_Extent4>).</span><span class="sxs-lookup"><span data-stu-id="74d8c-168">Since it is a nested join, we look up the property "Extent4" in the NameToExtent dictionary of the join symbol, resolve it to <symbol_Extent4> and return a new SymbolPair(<joinSymbol_join2>, <symbol_Extent4>).</span></span> <span data-ttu-id="74d8c-169">Poiché viene restituita una coppia di simboli dall'elaborazione dell'istanza di "Var(Join2).Extent4.OrderID", la proprietà "OrderID" viene risolta dall'oggetto ColumnPart di tale coppia di simboli (<symbol_Extent4>), che include un elenco di colonne dell'extent che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="74d8c-169">Since a symbol pair is returned from the processing of the instance of "Var(Join2).Extent4.OrderID",  the property "OrderID" is resolved from the ColumnPart of that symbol pair (<symbol_Extent4>), which has a list of the columns of the extent it represents.</span></span> <span data-ttu-id="74d8c-170">"Var(Join2).Extent4.OrderID" viene pertanto risolto in { <joinSymbol_Join2>, ".", <symbol_OrderID>}.</span><span class="sxs-lookup"><span data-stu-id="74d8c-170">So, "Var(Join2).Extent4.OrderID" is resolved to { <joinSymbol_Join2>, ".", <symbol_OrderID>}.</span></span>  
  
 <span data-ttu-id="74d8c-171">La condizione di join di Join4 viene elaborata in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="74d8c-171">The join condition of Join4 is similarly processed.</span></span> <span data-ttu-id="74d8c-172">Il controllo viene restituito al metodo VisitInputExpression che ha elaborato il progetto di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="74d8c-172">The control returns to the VisitInputExpression method that processed the top most project.</span></span> <span data-ttu-id="74d8c-173">Analizzando FromExtents dell'oggetto SelectStatement0 restituito, si noterà che l'input viene identificato come un join e rimuove gli extent originali sostituendoli con un nuovo extent che include solo il simbolo di join.</span><span class="sxs-lookup"><span data-stu-id="74d8c-173">Looking at the FromExtents of the returned SelectStatement0, the input is identified as a join, and removes the original extents and replaces them with a new extent with just the Join symbol.</span></span> <span data-ttu-id="74d8c-174">Viene aggiornata anche la tabella dei simboli e viene quindi elaborata la parte relativa alla proiezione del progetto.</span><span class="sxs-lookup"><span data-stu-id="74d8c-174">The symbol table is also updated and next the projection part of the Project is processed.</span></span> <span data-ttu-id="74d8c-175">La risoluzione delle proprietà e la bidimensionalità degli extent del join corrispondono a quanto descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="74d8c-175">The resolving of the properties and the flattening of the join extents is as described earlier.</span></span>  
  
 <span data-ttu-id="74d8c-176">![Diagramma](../../../../../docs/framework/data/adonet/ef/media/9456d6a9-ea2e-40ae-accc-a10e18e28b81.gif "9456d6a9-ea2e-40ae-accc-a10e18e28b81")</span><span class="sxs-lookup"><span data-stu-id="74d8c-176">![Diagram](../../../../../docs/framework/data/adonet/ef/media/9456d6a9-ea2e-40ae-accc-a10e18e28b81.gif "9456d6a9-ea2e-40ae-accc-a10e18e28b81")</span></span>  
  
 <span data-ttu-id="74d8c-177">Viene infine prodotto l'oggetto SqlSelectStatement seguente:</span><span class="sxs-lookup"><span data-stu-id="74d8c-177">Finally, the following SqlSelectStatement is produced:</span></span>  
  
```  
SELECT:   
  "1", " AS ", "[C1]",  
  <symbol_Extent1>, ".", "[ProductID]", " AS ", "[ProductID]",   
  <symbol_Extent1>, ".", "[ProductName]", " AS ", "[ProductName]",  
  <symbol_Extent2>, ".", "[CategoryName]", " AS ", "[CategoryName]",  
  <joinSymbol_Join3>, ".", <symbol_ShipCountry>, " AS ", "[ShipCountry]",   
  <joinSymbol_Join3>, ".", <symbol_ProductID>, " AS ", "[ProductID1]"  
FROM: "[dbo].[Products]", " AS ", <symbol_Extent1>,   
        "LEFT OUTER JOIN ""[dbo].[Categories]", " AS ", <symbol_Extent2>, " ON ", <symbol_Extent1>, ".", "[CategoryID]", " = ", <symbol_Extent2>, ".", "[CategoryID]",   
        "INNER JOIN ",   
        " (", SELECT:   
           <symbol_Extent3>, ".", "[OrderID]", " AS ", <symbol_OrderID>, ",   
              <symbol_Extent3>, ".", "[ProductID]", " AS ", <symbol_ProductID>, ...,  
         <joinSymbol_Join2>, ".", <symbol_OrderID_2>, ", ",   
           <joinSymbol_Join2>, ".", <symbol_CustomerID>, ....,    
        <joinSymbol_Join2>, ".", <symbol_OrderID_3>,   
<joinSymbol_Join2>, ".", <symbol_CustomsDescription>,   
<joinSymbol_Join2>, ".", <symbol_ExciseTax>  
FROM: "[dbo].[OrderDetails]", " AS ", <symbol_Extent3>,   
"LEFT OUTER JOIN ",   
" (", SELECT:   
<symbol_Extent4>, ".", "[OrderID]", " AS ", <symbol_OrderID_2>,   
<symbol_Extent4>, ".", "[CustomerID]", " AS ", <symbol_CustomerID>, ...  
<symbol_Extent5>, ".", "[OrderID]", " AS ", <symbol_OrderID_3>,  
<symbol_Extent5>, ".", "[CustomsDescription]", " AS ", <symbol_CustomsDescription>,  
<symbol_Extent5>, ".", "[ExciseTax]", " AS ", <symbol_ExciseTax>  
FROM: "[dbo].[Orders]", " AS ", <symbol_Extent4>,  
"LEFT OUTER JOIN ", , "[dbo].[InternationalOrders]", " AS ", <symbol_Extent5>,   
" ON ", <symbol_Extent4>, ".", "[OrderID]", " = ", , <symbol_Extent5>, ".", "[OrderID]"  
" )", " AS ", <joinSymbol_Join2>, " ON ", , , <symbol_Extent3>, ".", "[OrderID]", " = ", , <joinSymbol_Join2>, ".", <symbol_OrderID_2>  
" )", " AS ", <joinSymbol_Join3>, " ON ", , , <symbol_Extent1>, ".", "[ProductID]", " = ", , <joinSymbol_Join3>, ".", <symbol_ProductID>  
```  
  
### <a name="second-phase-of-sql-generation-generating-the-string-command"></a><span data-ttu-id="74d8c-178">Seconda fase della generazione SQL: generazione della stringa di comando</span><span class="sxs-lookup"><span data-stu-id="74d8c-178">Second Phase of SQL Generation: Generating the String Command</span></span>  
 <span data-ttu-id="74d8c-179">Nella seconda fase vengono prodotti i nomi effettivi dei simboli e vengono descritti solo i simboli che rappresentano le colonne denominate "OrderID", in quanto in questo caso è necessario risolvere un conflitto.</span><span class="sxs-lookup"><span data-stu-id="74d8c-179">The second phase produces actual names for the symbols, and we only focus on the symbols representing columns named "OrderID", as in this case a conflict needs to be resolved.</span></span> <span data-ttu-id="74d8c-180">Tali nomi sono evidenziati in SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="74d8c-180">These are highlighted in the SqlSelectStatement.</span></span> <span data-ttu-id="74d8c-181">Si noti che i suffissi usati nella figura servono solo a indicare che si tratta di istanze differenti e non per rappresentare nuovi nomi, poiché in questa fase i nomi finali (probabilmente diversi da quelli originali) non sono stati ancora assegnati.</span><span class="sxs-lookup"><span data-stu-id="74d8c-181">Note that the suffixes used in the figure are only to emphasize that these are different instances, not to represent any new names, as at this stage their final names (possibly different form the original names) have not been assigned yet.</span></span>  
  
 <span data-ttu-id="74d8c-182">Il primo simbolo da rinominare è <symbol_OrderID>.</span><span class="sxs-lookup"><span data-stu-id="74d8c-182">The first symbol found that needs to be renamed is <symbol_OrderID>.</span></span> <span data-ttu-id="74d8c-183">Il nuovo nome assegnato è "OrderID1", dove 1 è contrassegnato come ultimo suffisso usato per "OrderID" e il simbolo è contrassegnato come da non rinominare.</span><span class="sxs-lookup"><span data-stu-id="74d8c-183">Its new name is assigned as "OrderID1", 1 is marked as the last used suffix for "OrderID" and the symbol is marked as not needing renaming.</span></span> <span data-ttu-id="74d8c-184">Viene quindi individuato il primo utilizzo di <symbol_OrderID_2>.</span><span class="sxs-lookup"><span data-stu-id="74d8c-184">Next, the first usage of <symbol_OrderID_2> is found.</span></span> <span data-ttu-id="74d8c-185">Quest'ultimo viene rinominato in modo da usare il successivo suffisso disponibile ("OrderID2") e nuovamente contrassegnato come da non rinominare, in modo che non venga rinominato al successivo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="74d8c-185">It is renamed to use the next available suffix ("OrderID2") and again marked as not needing renaming, so that next time it is used it does not get renamed.</span></span> <span data-ttu-id="74d8c-186">Questa stessa procedura viene eseguita anche per <symbol_OrderID_3>.</span><span class="sxs-lookup"><span data-stu-id="74d8c-186">This is done for <symbol_OrderID_3> too.</span></span>  
  
 <span data-ttu-id="74d8c-187">Alla fine della seconda fase viene generata l'istruzione SQL finale.</span><span class="sxs-lookup"><span data-stu-id="74d8c-187">At the end of the second phase, the final SQL statement is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74d8c-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74d8c-188">See Also</span></span>  
 [<span data-ttu-id="74d8c-189">Generazione SQL nel Provider di esempio</span><span class="sxs-lookup"><span data-stu-id="74d8c-189">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)
