---
title: Attività dell'entità
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c04f7413-7fb8-40c6-819e-dc92b145b62e
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 81f8b1852b939d7ceb8b9afae4435ca12239b880
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="entity-activities"></a>Attività dell'entità
In questo esempio viene illustrato come utilizzare ADO.NET Entity Framework con Windows Workflow Foundation per semplificare l'accesso ai dati.  
  
 ADO.NET Entity Framework consente agli sviluppatori di usare dati nel formato oggetti, proprietà e relazioni specifici di dominio, quali Customers, Orders, Order Details e le relazioni tra queste entità. A tale scopo, ADO.NET Entity Framework dispone di un livello di astrazione che consente la programmazione in un modello di applicazione concettuale anziché programmando direttamente in uno schema di archiviazione relazionale. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] ADO.NET Entity Framework, vedere [ADO.NET Entity Framework](http://go.microsoft.com/fwlink/?LinkId=165549).  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 In questo esempio viene usato il database `Northwind` e sono inclusi script per la creazione e la rimozione di tale database `Northwind` (Setup.cmd e Cleanup.cmd). I progetti in questo esempio includono un modello Entity Data Model basato sul database `Northwind`. Il modello può essere trovato aprendo il file `Northwind.edmx` incluso nel progetto. Si tratta del modello che definisce la forma degli oggetti a cui è possibile accedere tramite ADO.NET Entity Framework.  
  
 In questo esempio sono incluse le attività seguenti:  
  
-   `EntitySQLQuery`: `EntitySQLQuery` questa attività consente di recuperare oggetti dal database in base a una stringa di query Entity SQL. Entity SQL è un linguaggio indipendente dall'archiviazione simile a SQL e consente di specificare query in base al modello concettuale e alle entità che sono parte del modello o del dominio. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] Linguaggio Entity SQL, vedere [linguaggio Entity SQL](http://go.microsoft.com/fwlink/?LinkId=165646).  
  
-   `EntityLinqQuery`: questa attività consente di recuperare oggetti dal database in base a un predicato o query LINQ.  
  
-   `EntityAdd`: `EntityAdd` questa attività consente di aggiungere un'entità o una raccolta di entità al database.  
  
-   `EntityDelete`: `EntityDelete` questa attività consente di eliminare un'entità o una raccolta di entità dal database.  
  
-   `ObjectContextScope`: le attività indicate in precedenza possono essere usate solo all'interno di un'istanza dell'attività `ObjectContextScope` contenitore. L'attività `ObjectContextScope` imposta la connessione sul database e richiede una stringa di connessione (passata o recuperata usando un'impostazione del file di configurazione). L'attività `ObjectContextScope` facilita l'esecuzione di un gruppo di operazioni correlate nelle entità. Poiché questo ambito gestisce una connessione attiva, si tratta di un ambito di non persistenza. Inoltre, quando l'attività `ObjectContextScope` viene chiusa, qualsiasi modifica apportata agli oggetti recuperati tramite le attività dell'entità all'interno di tale ambito viene resa persistente nel database, senza dover eseguire alcuna azione esplicita o successiva per un nuovo salvataggio degli oggetti nel database.  
  
## <a name="using-the-entity-activities"></a>Utilizzo delle attività dell'entità  
 Nei frammenti di codice seguenti viene illustrato come usare le attività dell'entità presentate in questo esempio.  
  
### <a name="entitysql"></a>EntitySql  
 Nel frammento di codice seguente viene illustrato come eseguire una query su tutti i clienti di Londra ordinati per nome e come scorrere l'elenco dei clienti.  
  
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
  
### <a name="entitylinqquery"></a>EntityLinqQuery  
 Nel frammento di codice seguente viene illustrato come eseguire una query su tutti i clienti di Londra e come scorrere l'elenco risultante dei clienti.  
  
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
  
### <a name="entityadd"></a>EntityAdd  
 Nel frammento di codice seguente viene illustrato come aggiungere un record OrderDetail a un ordine esistente.  
  
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
  
### <a name="entitydelete"></a>EntityDelete  
 Nel frammento di codice seguente viene illustrato come eliminare un record OrderDetail esistente in un ordine (se presente).  
  
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
  
## <a name="to-use-this-sample"></a>Per usare questo esempio  
 È necessario creare il database `Northwind` nell'istanza di SQL Server Express locale prima di eseguire questo esempio.  
  
#### <a name="to-set-up-the-northwind-database"></a>Per impostare il database Northwind  
  
1.  Aprire un prompt dei comandi.  
  
2.  Nella nuova finestra del prompt dei comandi passare alla cartella EntityActivities\CS.  
  
3.  Tipo `setup.cmd` e premere INVIO.  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  In [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] aprire il file della soluzione EntityActivities.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
 Dopo avere eseguito questo esempio, rimuovere il database `Northwind`.  
  
#### <a name="to-uninstall-the-northwind-database"></a>Per disinstallare il database Northwind  
  
1.  Aprire un prompt dei comandi.  
  
2.  Nella nuova finestra del prompt dei comandi passare alla cartella EntityActivities\CS.  
  
3.  Tipo `cleanup.cmd` e premere INVIO.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\EntityActivities`