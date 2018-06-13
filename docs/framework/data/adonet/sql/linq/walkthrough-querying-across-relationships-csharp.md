---
title: 'Procedura dettagliata: eseguire query tra relazioni (C#)'
ms.date: 03/30/2017
ms.assetid: 552abeb1-18f2-4e93-a9c6-ef7b2db30c32
ms.openlocfilehash: a438b0ae83a223abfc35643915e6eedd5be068a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33364418"
---
# <a name="walkthrough-querying-across-relationships-c"></a><span data-ttu-id="ce5cf-102">Procedura dettagliata: eseguire query tra relazioni (C#)</span><span class="sxs-lookup"><span data-stu-id="ce5cf-102">Walkthrough: Querying Across Relationships (C#)</span></span>
<span data-ttu-id="ce5cf-103">Questa procedura dettagliata viene illustrato l'utilizzo di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *associazioni* per rappresentare relazioni di chiave esterna nel database.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-103">This walkthrough demonstrates the use of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *associations* to represent foreign-key relationships in the database.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="ce5cf-104">Questa procedura è stata scritta usando Impostazioni di sviluppo di Visual C#.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-104">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ce5cf-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ce5cf-105">Prerequisites</span></span>  
 <span data-ttu-id="ce5cf-106">È necessario avere completato [procedura dettagliata: oggetti modello e Query semplici (c#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md).</span><span class="sxs-lookup"><span data-stu-id="ce5cf-106">You must have completed [Walkthrough: Simple Object Model and Query (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md).</span></span> <span data-ttu-id="ce5cf-107">Questa procedura dettagliata si basa su tale procedura dettagliata, inclusa la presenza del file northwnd.mdf in c:\linqtest5.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-107">This walkthrough builds on that one, including the presence of the northwnd.mdf file in c:\linqtest5.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="ce5cf-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="ce5cf-108">Overview</span></span>  
 <span data-ttu-id="ce5cf-109">La procedura dettagliata è costituita da tre attività principali:</span><span class="sxs-lookup"><span data-stu-id="ce5cf-109">This walkthrough consists of three main tasks:</span></span>  
  
-   <span data-ttu-id="ce5cf-110">Aggiunta di una classe di entità per rappresentare la tabella Orders nel database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-110">Adding an entity class to represent the Orders table in the sample Northwind database.</span></span>  
  
-   <span data-ttu-id="ce5cf-111">Completamento delle annotazioni alla classe `Customer` per migliorare la relazione tra le classi `Customer` e `Order`.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-111">Supplementing annotations to the `Customer` class to enhance the relationship between the `Customer` and `Order` classes.</span></span>  
  
-   <span data-ttu-id="ce5cf-112">Creazione ed esecuzione di una query per testare la capacità di ottenere informazioni su `Order` usando la classe `Customer`.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-112">Creating and running a query to test obtaining `Order` information by using the `Customer` class.</span></span>  
  
## <a name="mapping-relationships-across-tables"></a><span data-ttu-id="ce5cf-113">Esecuzione del mapping delle relazioni tra tabelle</span><span class="sxs-lookup"><span data-stu-id="ce5cf-113">Mapping Relationships Across Tables</span></span>  
 <span data-ttu-id="ce5cf-114">Dopo la definizione della classe `Customer`, creare la definizione della classe di entità `Order` includendo il codice seguente per indicare che `Order.Customer` è correlata come chiave esterna a `Customer.CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-114">After the `Customer` class definition, create the `Order` entity class definition that includes the following code, which indicates that `Order.Customer` relates as a foreign key to `Customer.CustomerID`.</span></span>  
  
#### <a name="to-add-the-order-entity-class"></a><span data-ttu-id="ce5cf-115">Per aggiungere la classe di entità Order</span><span class="sxs-lookup"><span data-stu-id="ce5cf-115">To add the Order entity class</span></span>  
  
-   <span data-ttu-id="ce5cf-116">Digitare o incollare il codice seguente dopo la classe `Customer`:</span><span class="sxs-lookup"><span data-stu-id="ce5cf-116">Type or paste the following code after the `Customer` class:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#1)]  
  
## <a name="annotating-the-customer-class"></a><span data-ttu-id="ce5cf-117">Annotazione della classe Customer</span><span class="sxs-lookup"><span data-stu-id="ce5cf-117">Annotating the Customer Class</span></span>  
 <span data-ttu-id="ce5cf-118">In questo passaggio vengono aggiunte annotazioni alla classe `Customer` per indicare la relazione alla classe `Order`.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-118">In this step, you annotate the `Customer` class to indicate its relationship to the `Order` class.</span></span> <span data-ttu-id="ce5cf-119">Questa aggiunta non è strettamente necessaria, in quanto la definizione della relazione in una direzione è sufficiente per creare il collegamento.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-119">(This addition is not strictly necessary, because defining the relationship in either direction is sufficient to create the link.</span></span> <span data-ttu-id="ce5cf-120">Tuttavia aggiungendo l'annotazione sarà possibile spostarsi facilmente tra gli oggetti in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-120">But adding this annotation does enable you to easily navigate objects in either direction.)</span></span>  
  
#### <a name="to-annotate-the-customer-class"></a><span data-ttu-id="ce5cf-121">Per annotare la classe Customer</span><span class="sxs-lookup"><span data-stu-id="ce5cf-121">To annotate the Customer class</span></span>  
  
-   <span data-ttu-id="ce5cf-122">Digitare o incollare il codice seguente nella classe `Customer`:</span><span class="sxs-lookup"><span data-stu-id="ce5cf-122">Type or paste the following code into the `Customer` class:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a><span data-ttu-id="ce5cf-123">Creazione ed esecuzione di un query sulla relazione Customer-Order</span><span class="sxs-lookup"><span data-stu-id="ce5cf-123">Creating and Running a Query Across the Customer-Order Relationship</span></span>  
 <span data-ttu-id="ce5cf-124">A questo punto è possibile accedere direttamente agli oggetti `Order` dagli oggetti `Customer` o viceversa.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-124">You can now access `Order` objects directly from the `Customer` objects, or in the opposite order.</span></span> <span data-ttu-id="ce5cf-125">Non è necessaria l'esplicita *join* tra customers e orders.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-125">You do not need an explicit *join* between customers and orders.</span></span>  
  
#### <a name="to-access-order-objects-by-using-customer-objects"></a><span data-ttu-id="ce5cf-126">Per accedere agli oggetti Order usando oggetti Customer</span><span class="sxs-lookup"><span data-stu-id="ce5cf-126">To access Order objects by using Customer objects</span></span>  
  
1.  <span data-ttu-id="ce5cf-127">Modificare il metodo `Main` digitando o incollando il codice seguente nel metodo stesso:</span><span class="sxs-lookup"><span data-stu-id="ce5cf-127">Modify the `Main` method by typing or pasting the following code into the method:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#3)]  
  
2.  <span data-ttu-id="ce5cf-128">Premere F5 per eseguire il debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-128">Press F5 to debug your application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce5cf-129">È possibile eliminare il codice SQL nella finestra della console impostando come commento `db.Log = Console.Out;`.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-129">You can eliminate the SQL code in the Console window by commenting out `db.Log = Console.Out;`.</span></span>  
  
3.  <span data-ttu-id="ce5cf-130">Premere INVIO nella finestra della console per terminare il debug.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-130">Press Enter in the Console window to stop debugging.</span></span>  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a><span data-ttu-id="ce5cf-131">Creazione di una visualizzazione fortemente tipizzata del database</span><span class="sxs-lookup"><span data-stu-id="ce5cf-131">Creating a Strongly Typed View of Your Database</span></span>  
 <span data-ttu-id="ce5cf-132">È molto più facile iniziare con una visualizzazione fortemente tipizzata del database.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-132">It is much easier to start with a strongly typed view of your database.</span></span> <span data-ttu-id="ce5cf-133">Applicando la tipizzazione forte all'oggetto <xref:System.Data.Linq.DataContext>, si eviterà di eseguire chiamate a <xref:System.Data.Linq.DataContext.GetTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-133">By strongly typing the <xref:System.Data.Linq.DataContext> object, you do not need calls to <xref:System.Data.Linq.DataContext.GetTable%2A>.</span></span> <span data-ttu-id="ce5cf-134">Quando si usa l'oggetto fortemente tipizzato <xref:System.Data.Linq.DataContext>, è possibile usare tabelle fortemente tipizzate in tutte le query.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-134">You can use strongly typed tables in all your queries when you use the strongly typed <xref:System.Data.Linq.DataContext> object.</span></span>  
  
 <span data-ttu-id="ce5cf-135">Nei passaggi seguenti si creerà `Customers` come tabella fortemente tipizzata mappata alla tabella Customers nel database.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-135">In the following steps, you will create `Customers` as a strongly typed table that maps to the Customers table in the database.</span></span>  
  
#### <a name="to-strongly-type-the-datacontext-object"></a><span data-ttu-id="ce5cf-136">Per tipizzare fortemente l'oggetto DataContext</span><span class="sxs-lookup"><span data-stu-id="ce5cf-136">To strongly type the DataContext object</span></span>  
  
1.  <span data-ttu-id="ce5cf-137">Aggiungere il codice riportato di seguito sopra la dichiarazione della classe `Customer`.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-137">Add the following code above the `Customer` class declaration.</span></span>  
  
     [!code-csharp[DLinqWalk2CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#4)]  
  
2.  <span data-ttu-id="ce5cf-138">Per usare l'oggetto fortemente tipizzato `Main`, modificare il metodo <xref:System.Data.Linq.DataContext> come segue:</span><span class="sxs-lookup"><span data-stu-id="ce5cf-138">Modify the `Main` method to use the strongly typed <xref:System.Data.Linq.DataContext> as follows:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#5)]  
  
3.  <span data-ttu-id="ce5cf-139">Premere F5 per eseguire il debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-139">Press F5 to debug your application.</span></span>  
  
     <span data-ttu-id="ce5cf-140">L'output nella finestra della console sarà:</span><span class="sxs-lookup"><span data-stu-id="ce5cf-140">The Console window output is:</span></span>  
  
     `ID=WHITC`  
  
4.  <span data-ttu-id="ce5cf-141">Premere INVIO nella finestra della console per terminare il debug.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-141">Press Enter in the console window to stop debugging.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ce5cf-142">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ce5cf-142">Next Steps</span></span>  
 <span data-ttu-id="ce5cf-143">Nella procedura successiva ([procedura dettagliata: modifica di dati (c#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)) viene illustrato come modificare i dati.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-143">The next walkthrough ([Walkthrough: Manipulating Data (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)) demonstrates how to manipulate data.</span></span> <span data-ttu-id="ce5cf-144">Per tale procedura dettagliata non è necessario avere salvato le due procedure dettagliate di questa serie già completate.</span><span class="sxs-lookup"><span data-stu-id="ce5cf-144">That walkthrough does not require that you save the two walkthroughs in this series that you have already completed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce5cf-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce5cf-145">See Also</span></span>  
 [<span data-ttu-id="ce5cf-146">Apprendimento tramite procedure dettagliate</span><span class="sxs-lookup"><span data-stu-id="ce5cf-146">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
