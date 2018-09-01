---
title: Attività dell'entità
ms.date: 03/30/2017
ms.assetid: c04f7413-7fb8-40c6-819e-dc92b145b62e
ms.openlocfilehash: 03bd0e42c70f1226558d492bcb3b2cfa5c7010f2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385804"
---
# <a name="entity-activities"></a><span data-ttu-id="74ccc-102">Attività dell'entità</span><span class="sxs-lookup"><span data-stu-id="74ccc-102">Entity Activities</span></span>
<span data-ttu-id="74ccc-103">In questo esempio viene illustrato come utilizzare ADO.NET Entity Framework con Windows Workflow Foundation per semplificare l'accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="74ccc-103">This sample shows how to use the ADO.NET Entity Framework with Windows Workflow Foundation to simplify data access.</span></span>  
  
 <span data-ttu-id="74ccc-104">ADO.NET Entity Framework consente agli sviluppatori di usare dati nel formato oggetti, proprietà e relazioni specifici di dominio, quali Customers, Orders, Order Details e le relazioni tra queste entità.</span><span class="sxs-lookup"><span data-stu-id="74ccc-104">The ADO.NET Entity Framework enables developers to work with data in the form of domain-specific objects, properties and relationships such as Customers, Orders, Order Details and the relationships between these entities.</span></span> <span data-ttu-id="74ccc-105">A tale scopo, ADO.NET Entity Framework dispone di un livello di astrazione che consente la programmazione in un modello di applicazione concettuale anziché programmando direttamente in uno schema di archiviazione relazionale.</span><span class="sxs-lookup"><span data-stu-id="74ccc-105">The ADO.NET Entity Framework does this by providing a level of abstraction that enables programming against a conceptual application model instead of programming directly against a relational storage schema.</span></span> <span data-ttu-id="74ccc-106">Per altre informazioni su ADO.NET Entity Framework, vedere [ADO.NET Entity Framework](https://go.microsoft.com/fwlink/?LinkId=165549).</span><span class="sxs-lookup"><span data-stu-id="74ccc-106">For more information about the ADO.NET Entity Framework see [ADO.NET Entity Framework](https://go.microsoft.com/fwlink/?LinkId=165549).</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="74ccc-107">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="74ccc-107">Sample details</span></span>  
 <span data-ttu-id="74ccc-108">In questo esempio viene usato il database `Northwind` e sono inclusi script per la creazione e la rimozione di tale database `Northwind` (Setup.cmd e Cleanup.cmd).</span><span class="sxs-lookup"><span data-stu-id="74ccc-108">This sample uses the `Northwind` database and includes scripts for creating and removing the `Northwind` database (Setup.cmd and Cleanup.cmd).</span></span> <span data-ttu-id="74ccc-109">I progetti in questo esempio includono un modello Entity Data Model basato sul database `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="74ccc-109">The projects in this sample include an Entity Data Model based on the `Northwind` database.</span></span> <span data-ttu-id="74ccc-110">Il modello può essere trovato aprendo il file `Northwind.edmx` incluso nel progetto.</span><span class="sxs-lookup"><span data-stu-id="74ccc-110">You can find the model by opening the `Northwind.edmx` file that is included in the project.</span></span> <span data-ttu-id="74ccc-111">Si tratta del modello che definisce la forma degli oggetti a cui è possibile accedere tramite ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="74ccc-111">This is the model that defines the shape of the objects that can be accessed using the ADO.NET Entity Framework.</span></span>  
  
 <span data-ttu-id="74ccc-112">In questo esempio sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="74ccc-112">The following activities are included in this sample:</span></span>  
  
-   <span data-ttu-id="74ccc-113">`EntitySQLQuery`: `EntitySQLQuery` questa attività consente di recuperare oggetti dal database in base a una stringa di query Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="74ccc-113">`EntitySQLQuery`: The `EntitySQLQuery` activity allows you to retrieve objects from the database based on an Entity SQL query string.</span></span> <span data-ttu-id="74ccc-114">Entity SQL è un linguaggio indipendente dall'archiviazione simile a SQL e consente di specificare query in base al modello concettuale e alle entità che sono parte del modello o del dominio.</span><span class="sxs-lookup"><span data-stu-id="74ccc-114">Entity SQL is a store independent language that is similar to SQL and it allows you to specify queries based on the conceptual model and the entities that are a part of the model or domain.</span></span> <span data-ttu-id="74ccc-115">Per altre informazioni sul linguaggio Entity SQL, vedere [linguaggio Entity SQL](https://go.microsoft.com/fwlink/?LinkId=165646).</span><span class="sxs-lookup"><span data-stu-id="74ccc-115">For more information about Entity SQL Language, see [Entity SQL Language](https://go.microsoft.com/fwlink/?LinkId=165646).</span></span>  
  
-   <span data-ttu-id="74ccc-116">`EntityLinqQuery`: questa attività consente di recuperare oggetti dal database in base a un predicato o query LINQ.</span><span class="sxs-lookup"><span data-stu-id="74ccc-116">`EntityLinqQuery`: This activity allows you to retrieve objects from the database based on a LINQ query or predicate.</span></span>  
  
-   <span data-ttu-id="74ccc-117">`EntityAdd`: `EntityAdd` questa attività consente di aggiungere un'entità o una raccolta di entità al database.</span><span class="sxs-lookup"><span data-stu-id="74ccc-117">`EntityAdd`: The `EntityAdd` activity allows you to add an entity or a collection of entities to the database.</span></span>  
  
-   <span data-ttu-id="74ccc-118">`EntityDelete`: `EntityDelete` questa attività consente di eliminare un'entità o una raccolta di entità dal database.</span><span class="sxs-lookup"><span data-stu-id="74ccc-118">`EntityDelete`: The `EntityDelete` activity allows you to delete an entity or a collection of entities from the database.</span></span>  
  
-   <span data-ttu-id="74ccc-119">`ObjectContextScope`: le attività indicate in precedenza possono essere usate solo all'interno di un'istanza dell'attività `ObjectContextScope` contenitore.</span><span class="sxs-lookup"><span data-stu-id="74ccc-119">`ObjectContextScope`: The previously mentioned activities can only be used within a containing `ObjectContextScope` activity instance.</span></span> <span data-ttu-id="74ccc-120">L'attività `ObjectContextScope` imposta la connessione sul database</span><span class="sxs-lookup"><span data-stu-id="74ccc-120">The `ObjectContextScope` activity sets up the connection to the database.</span></span> <span data-ttu-id="74ccc-121">e richiede una stringa di connessione (passata o recuperata usando un'impostazione del file di configurazione).</span><span class="sxs-lookup"><span data-stu-id="74ccc-121">It requires a connection string (that is either passed in or retrieved using a configuration file setting).</span></span> <span data-ttu-id="74ccc-122">L'attività `ObjectContextScope` facilita l'esecuzione di un gruppo di operazioni correlate nelle entità.</span><span class="sxs-lookup"><span data-stu-id="74ccc-122">The `ObjectContextScope` activity makes it easy to perform a group of related operations on entities.</span></span> <span data-ttu-id="74ccc-123">Poiché questo ambito gestisce una connessione attiva, si tratta di un ambito di non persistenza.</span><span class="sxs-lookup"><span data-stu-id="74ccc-123">Because this scope maintains an active connection, it is a No Persist scope.</span></span> <span data-ttu-id="74ccc-124">Inoltre, quando l'attività `ObjectContextScope` viene chiusa, qualsiasi modifica apportata agli oggetti recuperati tramite le attività dell'entità all'interno di tale ambito viene resa persistente nel database, senza dover eseguire alcuna azione esplicita o successiva per un nuovo salvataggio degli oggetti nel database.</span><span class="sxs-lookup"><span data-stu-id="74ccc-124">In addition, when the `ObjectContextScope` activity exits, any changes that are made to objects retrieved using Entity Activities within that scope automatically get persisted back to the database, and no explicit or subsequent action is required to save objects back to the database.</span></span>  
  
## <a name="using-the-entity-activities"></a><span data-ttu-id="74ccc-125">Utilizzo delle attività dell'entità</span><span class="sxs-lookup"><span data-stu-id="74ccc-125">Using the entity activities</span></span>  
 <span data-ttu-id="74ccc-126">Nei frammenti di codice seguenti viene illustrato come usare le attività dell'entità presentate in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="74ccc-126">The following code snippets demonstrate how to use the entity activities presented in this sample.</span></span>  
  
### <a name="entitysql"></a><span data-ttu-id="74ccc-127">EntitySql</span><span class="sxs-lookup"><span data-stu-id="74ccc-127">EntitySql</span></span>  
 <span data-ttu-id="74ccc-128">Nel frammento di codice seguente viene illustrato come eseguire una query su tutti i clienti di Londra ordinati per nome e come scorrere l'elenco dei clienti.</span><span class="sxs-lookup"><span data-stu-id="74ccc-128">The code snippet below shows how to query all customers in London sorted by name and how to iterate through the list of customers.</span></span>  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>();  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>();  
  
// create and return the workflow  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
        {  
            Activities =   
                {               
                    new WriteLine { Text = "Executing query" },                            
                    // query for all customers that are in london   
                    new EntitySqlQuery<Customer>  
                    {  
                        EntitySql =  @"SELECT VALUE Customer   
                                        FROM NorthwindEntities.Customers AS Customer   
                                        WHERE Customer.City = 'London'   
                                        ORDER BY Customer.ContactName",  
                        Result = londonCustomers  
                    },  
  
                    // iterate through the list of customers and display them   
                    new ForEach<Customer>  
                    {                                      
                        Values = londonCustomers,  
                        Body = new ActivityAction<Customer>  
                        {  
                            Argument = iterationVariable,  
                            Handler = new WriteLine   
                            {   
                                  Text = new InArgument<String>(e =>    
                                              iterationVariable.Get(e).ContactName)   
                            }  
                        }  
                    }  
                }  
        }                 
};     
```  
  
### <a name="entitylinqquery"></a><span data-ttu-id="74ccc-129">EntityLinqQuery</span><span class="sxs-lookup"><span data-stu-id="74ccc-129">EntityLinqQuery</span></span>  
 <span data-ttu-id="74ccc-130">Nel frammento di codice seguente viene illustrato come eseguire una query su tutti i clienti di Londra e come scorrere l'elenco risultante dei clienti.</span><span class="sxs-lookup"><span data-stu-id="74ccc-130">The code snippet below shows how to query all customers in London and how to iterate through the resulting list of customers.</span></span>  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>() { Name = "LondonCustomers" };  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>() { Name = "iterationVariable" };  
  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // return all the customers that match with the provided Linq predicate  
            new EntityLinqQuery<Customer>  
            {   
                Predicate = new LambdaValue<Func<Customer, bool>>(  
                          ctx => new Func<Customer, bool>(c => c.City.Equals("London"))),                              
                Result = londonCustomers  
            },  
  
            // iterate through the list of customers and display in the console  
            new ForEach<Customer>  
            {                                      
                Values = londonCustomers,  
                Body = new ActivityAction<Customer>  
                {  
                    Argument = iterationVariable,  
                    Handler = new WriteLine   
                    {   
                        Text = new InArgument<String>(e =>   
                                      iterationVariable.Get(e).ContactName)   
                    }  
                }  
            }  
        }  
    }  
};  
```  
  
### <a name="entityadd"></a><span data-ttu-id="74ccc-131">EntityAdd</span><span class="sxs-lookup"><span data-stu-id="74ccc-131">EntityAdd</span></span>  
 <span data-ttu-id="74ccc-132">Nel frammento di codice seguente viene illustrato come aggiungere un record OrderDetail a un ordine esistente.</span><span class="sxs-lookup"><span data-stu-id="74ccc-132">The code snippet below shows how to add an OrderDetail record to an existing Order.</span></span>  
  
```  
Variable<IEnumerable<Order>> orders = new Variable<IEnumerable<Order>>();  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();  
Variable<Order> order = new Variable<Order>();  
Variable<OrderDetail> orderDetail = new Variable<OrderDetail>();              
  
return new ObjectContextScope  
{  
    Variables = { order, orders, orderDetail, orderDetails },  
    ContainerName = "NorthwindEntities",  
    ConnectionString = new InArgument<string>(connStr),                  
    Body = new Sequence  
    {                      
        Activities =   
        {                            
           // get the order where we want to add the detail  
           new EntitySqlQuery<Order>  
           {  
               EntitySql =    
                    @"SELECT VALUE [Order]  
                      FROM NorthwindEntities.Orders as [Order]  
                      WHERE Order.OrderID == 10249",  
               Result = orders  
           },  
  
           // store the order in a variable  
           new Assign<Order>   
           {  
               To = new OutArgument<Order>(order),  
               Value = new InArgument<Order>(c => orders.Get(c).First<Order>())  
           },  
  
           // add the detail to the order  
           new EntityAdd<OrderDetail>  
           {  
               Entity = new InArgument<OrderDetail>(c =>   
                                         new OrderDetail {   
                                                  OrderID=10249, ProductID=11,   
                                                  Quantity=1, UnitPrice = 15,   
                                                  Discount = 0, Order = order.Get(c) })  
           }  
        }  
    }  
};  
```  
  
### <a name="entitydelete"></a><span data-ttu-id="74ccc-133">EntityDelete</span><span class="sxs-lookup"><span data-stu-id="74ccc-133">EntityDelete</span></span>  
 <span data-ttu-id="74ccc-134">Nel frammento di codice seguente viene illustrato come eliminare un record OrderDetail esistente in un ordine (se presente).</span><span class="sxs-lookup"><span data-stu-id="74ccc-134">The code snippet below shows how to delete an existing OrderDetail record in an Order (if it exists).</span></span>  
  
```  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();              
  
return new ObjectContextScope  
{  
    Variables = { orderDetails },  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // find the entitiy to be deleted (order detail for product 11 in order 10249)  
            new EntitySqlQuery<OrderDetail>  
            {  
                EntitySql = @"SELECT VALUE OrderDetail  
                                FROM NorthwindEntities.OrderDetails as OrderDetail  
                               WHERE OrderDetail.OrderID == 10249   
                                 AND OrderDetail.ProductID == 11",  
                Result = orderDetails  
            },  
  
            // if the order detail is found, delete it, otherwise, display a message  
            new If  
            {  
                Condition = new InArgument<bool>(c=>orderDetails.Get(c).Count() > 0),  
                Then = new Sequence  
                {   
                    Activities =   
                    {                                      
                        new EntityDelete<OrderDetail>  
                        {  
                            Entity = new InArgument<OrderDetail>(c =>   
                                              orderDetails.Get(c).First<OrderDetail>())  
                        },  
                    }  
                },                              
                Else = new WriteLine { Text = "Order Detail for Deleting not found" }                              
            }                                                  
        }  
    }  
};  
```  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="74ccc-135">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="74ccc-135">To use this sample</span></span>  
 <span data-ttu-id="74ccc-136">È necessario creare il database `Northwind` nell'istanza di SQL Server Express locale prima di eseguire questo esempio.</span><span class="sxs-lookup"><span data-stu-id="74ccc-136">You must create the `Northwind` database in your local SQL server Express instance before running this sample.</span></span>  
  
#### <a name="to-set-up-the-northwind-database"></a><span data-ttu-id="74ccc-137">Per impostare il database Northwind</span><span class="sxs-lookup"><span data-stu-id="74ccc-137">To set up the Northwind database</span></span>  
  
1.  <span data-ttu-id="74ccc-138">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="74ccc-138">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="74ccc-139">Nella nuova finestra del prompt dei comandi passare alla cartella EntityActivities\CS.</span><span class="sxs-lookup"><span data-stu-id="74ccc-139">In the new command prompt window, navigate to the EntityActivities\CS folder.</span></span>  
  
3.  <span data-ttu-id="74ccc-140">Tipo `setup.cmd` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="74ccc-140">Type `setup.cmd` and press ENTER.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="74ccc-141">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="74ccc-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="74ccc-142">In [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] aprire il file della soluzione EntityActivities.sln.</span><span class="sxs-lookup"><span data-stu-id="74ccc-142">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EntityActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="74ccc-143">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="74ccc-143">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="74ccc-144">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="74ccc-144">To run the solution, press CTRL+F5.</span></span>  
  
 <span data-ttu-id="74ccc-145">Dopo avere eseguito questo esempio, rimuovere il database `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="74ccc-145">After running this sample, you may want to remove the `Northwind` database.</span></span>  
  
#### <a name="to-uninstall-the-northwind-database"></a><span data-ttu-id="74ccc-146">Per disinstallare il database Northwind</span><span class="sxs-lookup"><span data-stu-id="74ccc-146">To uninstall the Northwind database</span></span>  
  
1.  <span data-ttu-id="74ccc-147">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="74ccc-147">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="74ccc-148">Nella nuova finestra del prompt dei comandi passare alla cartella EntityActivities\CS.</span><span class="sxs-lookup"><span data-stu-id="74ccc-148">In the new command prompt window, navigate to the EntityActivities\CS folder.</span></span>  
  
3.  <span data-ttu-id="74ccc-149">Tipo `cleanup.cmd` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="74ccc-149">Type `cleanup.cmd` and press ENTER.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="74ccc-150">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="74ccc-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="74ccc-151">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="74ccc-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="74ccc-152">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="74ccc-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="74ccc-153">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="74ccc-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\EntityActivities`