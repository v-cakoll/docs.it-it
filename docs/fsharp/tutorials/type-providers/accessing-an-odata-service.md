---
title: 'Procedura dettagliata: Accesso a un servizio OData tramite provider di tipi (F#)'
description: 'Informazioni su come utilizzare il provider di tipi ODataService F # in F # 3.0 per generare i tipi di client per un servizio OData e fornisce query feed di dati che il servizio.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0adae84c-b0fa-455f-994b-274ecdc6df30
ms.openlocfilehash: 750407c36a989cece30c0c0654ff905c8eee3b33
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-an-odata-service-by-using-type-providers"></a>Procedura dettagliata: Accesso a un servizio OData tramite provider di tipi

> [!NOTE]
Questa guida è stata scritta per F # 3.0 e verrà aggiornata.  Per provider di tipo multipiattaforma aggiornati, vedere [FSharp.Data](https://fsharp.github.io/FSharp.Data/).

> [!NOTE]
I collegamenti di riferimento API richiederà a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

OData, vale a dire Open Data Protocol, è un protocollo per il trasferimento dei dati tramite Internet. Molti provider di dati espone l'accesso ai dati tramite la pubblicazione di un servizio web OData. È possibile accedere ai dati provenienti da un'origine OData in F # 3.0 utilizzando tipi di dati che vengono generati automaticamente mediante il `ODataService` provider di tipi. Per ulteriori informazioni su OData, vedere https://msdn.microsoft.com/library/da3380cc-f6da-4c6c-bdb2-bb86afa59d62.

Questa procedura dettagliata viene illustrato come utilizzare il provider di tipi F # ODataService per generare tipi di client per un servizio OData e fornisce query feed di dati che il servizio.

In questa procedura dettagliata vengono illustrate le seguenti attività, che è consigliabile eseguire in quest'ordine perché la procedura abbia esito positivo:


- Configurazione di un progetto client per un servizio OData
<br />

- L'accesso a tipi di OData
<br />

- Esecuzione di query su un servizio OData
<br />

- Verifica delle richieste OData
<br />


## <a name="configuring-a-client-project-for-an-odata-service"></a>Configurazione di un progetto client per un servizio OData
In questo passaggio è configurare un progetto per utilizzare un provider di tipi OData.


#### <a name="to-configure-a-client-project-for-an-odata-service"></a>Per configurare un progetto client per un servizio OData

- Aprire un progetto di applicazione Console F # e quindi aggiungere un riferimento di `System.Data.Services.Client` assembly Framework.
<br />

- In `Extensions`, aggiungere un riferimento di `FSharp.Data.TypeProviders` assembly.
<br />

## <a name="accessing-odata-types"></a>L'accesso a tipi di OData
In questo passaggio creare un provider di tipo che fornisce l'accesso per i tipi e i dati per un servizio OData.


#### <a name="to-access-odata-types"></a>Per accedere a tipi di OData

- Nell'Editor di codice, aprire un file di origine F # e immettere il codice seguente.
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type Northwind = ODataService<"https://services.odata.org/Northwind/Northwind.svc/">

let db = Northwind.GetDataContext()
let fullContext = Northwind.ServiceTypes.NorthwindEntities()
```

In questo esempio, ha richiamato il provider di tipi F # e ha richiesto la creazione di un set di tipi basati su URI OData specificato. Sono disponibili due oggetti che contengono informazioni sui dati; uno è un contesto dati semplificato, `db` nell'esempio. Questo oggetto contiene solo i tipi di dati che sono associati a database, che includono i tipi di tabelle o feed. L'oggetto, `fullContext` in questo esempio è un'istanza di `System.Data.Linq.DataContext` e contiene molte altre proprietà, metodi ed eventi.
<br />


## <a name="querying-an-odata-service"></a>Esecuzione di query su un servizio OData
In questo passaggio, utilizzare le espressioni di query F # per eseguire query sul servizio OData.


#### <a name="to-query-an-odata-service"></a>Eseguire una query di un servizio OData

1. Ora che è stato configurato il provider di tipi, è possibile eseguire la query di un servizio OData.
<br />  OData supporta solo un subset delle operazioni di query disponibili. Sono supportate le seguenti operazioni e le parole chiave corrispondenti:
<br />
  - proiezione (`select`)
<br />

  - applicazione di filtri (`where`, utilizzando una stringa e le operazioni di data)
<br />

  - paging (`skip`, `take`)
<br />

  - ordinamento (`orderBy`, `thenBy`)
<br />

  - `AddQueryOption` e `Expand`, che sono operazioni specifiche di OData
<br />

  Per ulteriori informazioni, vedere [considerazioni su LINQ &#40; WCF Data Services &#41; ](https://msdn.microsoft.com/library/ee622463.aspx).
<br />  Se si desidera, tutte le voci in un feed o una tabella, utilizzare la forma più semplice dell'espressione di query, come illustrato nel codice seguente:
<br />

```fsharp
query {
  for customer in db.Customers do
  select customer
} |> Seq.iter (fun customer ->
                  printfn "ID: %s\nCompany: %s" customer.CustomerID customer.CompanyName
                  printfn "Contact: %s\nAddress: %s" customer.ContactName customer.Address
                  printfn "         %s, %s %s" customer.City customer.Region customer.PostalCode
                  printfn "%s\n" customer.Phone)
```

2. Specificare i campi o le colonne che desidera utilizzare una tupla dopo la parola chiave select.
<br />

```fsharp
  query { 
    for cat in db.Categories do
    select (cat.CategoryID, cat.CategoryName, cat.Description)
  } |> Seq.iter (fun (id, name, description) ->
                    printfn "ID: %d\nCategory: %s\nDescription: %s\n" id name description)
```

3. Specificare le condizioni usando un `where` clausola.
<br />

```fsharp
query {
  for employee in db.Employees do
  where (employee.EmployeeID = 9)
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

4. Specificare una condizione di sottostringa per la query utilizzando il `System.String.Contains(System.String)` metodo. La query seguente restituisce tutti i prodotti che contengono "Chef" nel nome. Si noti inoltre l'utilizzo di `System.Nullable<'T>.GetValueOrDefault()`. Il `UnitPrice` è un valore che ammette valori null, ovvero, è necessario ottenere il valore utilizzando il `Value` proprietà oppure è necessario chiamare `System.Nullable<'T>.GetValueOrDefault()`.
<br />

```fsharp
query { 
  for product in db.Products do
  where (product.ProductName.Contains("Chef"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

5. Utilizzare il `System.String.EndsWith(System.String)` per specificare che una stringa termina con una specifica sottostringa.
<br />

```fsharp
query {
  for product in db.Products do
  where (product.ProductName.EndsWith("u"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

6. Combinare le condizioni in una clausola utilizzando il `&&` operatore.
<br />

```fsharp
// Open this module to use the nullable operators ?> and ?<.
open Microsoft.FSharp.Linq.NullableOperators

let salesIn1997 = query { 
  for sales in db.Category_Sales_for_1997 do
  where (sales.CategorySales ?> 50000.00M && sales.CategorySales ?< 60000.0M)
  select sales }

salesIn1997
|> Seq.iter (fun sales ->
                printfn "Category: %s Sales: %M" sales.CategoryName (sales.CategorySales.GetValueOrDefault()))
```

Gli operatori `?>` e `?<` sono operatori ammette valori null. È possibile utilizzare un set completo di operatori di uguaglianza e confronto nullable. Per ulteriori informazioni, vedere [modulo Linq. nullableoperators](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).
<br />

7. Utilizzare il `sortBy` operatore per specificare l'ordinamento di query e utilizzare `thenBy` per specificare un altro livello di ordinamento. Si noti inoltre l'utilizzo di una tupla nella sezione select della query. Pertanto, la query ha una tupla come tipo di elemento.
<br />

```fsharp
printfn "Freight for some orders: "

query { 
  for order in db.Orders do
  sortBy (order.OrderDate.Value)
  thenBy (order.OrderID)
  select (order.OrderDate, order.OrderID, order.Customer.CompanyName)
} |> Seq.iter (fun (orderDate, orderID, company) ->
                  printfn "OrderDate: %s" (orderDate.GetValueOrDefault().ToString())
                  printfn "OrderID: %d Company: %s\n" orderID company)
```

8. Ignora un numero di record specificato utilizzando l'operatore skip e usare l'operatore take per specificare un numero di record da restituire. In questo modo, è possibile implementare il paging nel feed di dati.
<br />

```fsharp
printfn "Get the first page of 2 employees."

query { 
  for employee in db.Employees do
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID)) 

printfn "Get the next 2 employees."

query { 
  for employee in db.Employees do
  skip 2
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

## <a name="verifying-the-odata-request"></a>Verifica per determinare se la richiesta di OData
Ogni query OData viene convertito in un determinato URI di richiesta di OData. È possibile verificare che URI, ad esempio il debug a scopo di, aggiungendo un gestore eventi per il `SendingRequest` eventi dell'oggetto di contesto dati completo.


#### <a name="to-verify-the-odata-request"></a>Per verificare la richiesta di OData

- Per verificare l'URI della richiesta di OData, utilizzare il codice seguente:
<br />

```fsharp
// The DataContext property returns the full data context.
db.DataContext.SendingRequest.Add (fun eventArgs -> printfn "Requesting %A" eventArgs.Request.RequestUri)
```

L'output del codice precedente è:
<br />`requesting https://services.odata.org/Northwind/Northwind.svc/Orders()?$orderby=ShippedDate&amp;$select=OrderID,ShippedDate`


## <a name="see-also"></a>Vedere anche
[Espressioni di query](../../language-reference/query-expressions.md)

[Considerazioni su LINQ (WCF Data Services)](https://msdn.microsoft.com/library/ee622463.aspx)

[Provider di tipi ODataService (F #)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/odataservice-type-provider-%5bfsharp%5d)
