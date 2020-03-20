---
title: Recupero di dati e operazioni CUD in applicazioni a più livelli (LINQ to SQL)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c3133d53-83ed-4a4d-af8b-82edcf3831db
ms.openlocfilehash: 5ab829993b8f8faa6dcb91d3f23e8442b8aa95bd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148413"
---
# <a name="data-retrieval-and-cud-operations-in-n-tier-applications-linq-to-sql"></a><span data-ttu-id="fc658-102">Recupero di dati e operazioni CUD in applicazioni a più livelli (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="fc658-102">Data Retrieval and CUD Operations in N-Tier Applications (LINQ to SQL)</span></span>
<span data-ttu-id="fc658-103">Quando si serializzano oggetti entità, ad esempio Customers o Orders, in un client di una rete, tali entità vengono disconnesse dal relativo contesto dati.</span><span class="sxs-lookup"><span data-stu-id="fc658-103">When you serialize entity objects such as Customers or Orders to a client over a network, those entities are detached from their data context.</span></span> <span data-ttu-id="fc658-104">Il contesto dati non rileva più le modifiche o le associazioni con gli altri oggetti,</span><span class="sxs-lookup"><span data-stu-id="fc658-104">The data context no longer tracks their changes or their associations with other objects.</span></span> <span data-ttu-id="fc658-105">il che non rappresenta un problema se i client leggono solo i dati.</span><span class="sxs-lookup"><span data-stu-id="fc658-105">This is not an issue as long as the clients are only reading the data.</span></span> <span data-ttu-id="fc658-106">È inoltre relativamente semplice consentire ai client di aggiungere nuove righe in un database.</span><span class="sxs-lookup"><span data-stu-id="fc658-106">It is also relatively simple to enable clients to add new rows to a database.</span></span> <span data-ttu-id="fc658-107">Tuttavia, se l'applicazione richiede che i client siano in grado di aggiornare o eliminare i dati, sarà necessario associare le entità a un nuovo contesto dati prima di chiamare <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fc658-107">However, if your application requires that clients be able to update or delete data, then you must attach the entities to a new data context before you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fc658-108">Inoltre, se si usa un controllo della concorrenza ottimistica con i valori originali, sarà necessario anche un modo per fornire al database l'entità originale e l'entità come modificata.</span><span class="sxs-lookup"><span data-stu-id="fc658-108">In addition, if you are using an optimistic concurrency check with original values, then you will also need a way to provide the database both the original entity and the entity as modified.</span></span> <span data-ttu-id="fc658-109">I metodi `Attach` vengono forniti per consentire l'inserimento delle entità in un nuovo contesto dati dopo essere stati disconnessi.</span><span class="sxs-lookup"><span data-stu-id="fc658-109">The `Attach` methods are provided to enable you to put entities into a new data context after they have been detached.</span></span>  
  
 <span data-ttu-id="fc658-110">Anche se si serializzano oggetti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proxy al posto delle entità, è comunque necessario creare un'entità <xref:System.Data.Linq.DataContext?displayProperty=nameWithType>sul livello di accesso ai dati (DAL) e collegarla a un nuovo oggetto , per inviare i dati al database.</span><span class="sxs-lookup"><span data-stu-id="fc658-110">Even if you are serializing proxy objects in place of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] entities, you still have to construct an entity on the data access layer (DAL), and attach it to a new <xref:System.Data.Linq.DataContext?displayProperty=nameWithType>, in order to submit the data to the database.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="fc658-111">è completamente indifferente sul modo in cui le entità vengono serializzate.</span><span class="sxs-lookup"><span data-stu-id="fc658-111">is completely indifferent about how entities are serialized.</span></span> <span data-ttu-id="fc658-112">Per ulteriori informazioni su come utilizzare gli strumenti Object Relational Designer e SQLMetal per generare classi serializzabili tramite Windows Communication Foundation (WCF), vedere [Procedura: rendere serializzabili le entità.](how-to-make-entities-serializable.md)</span><span class="sxs-lookup"><span data-stu-id="fc658-112">For more information about how to use the Object Relational Designer and SQLMetal tools to generate classes that are serializable by using Windows Communication Foundation (WCF), see [How to: Make Entities Serializable](how-to-make-entities-serializable.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc658-113">Chiamare i metodi `Attach` solo sulle entità nuove o deserializzate.</span><span class="sxs-lookup"><span data-stu-id="fc658-113">Only call the `Attach` methods on new or deserialized entities.</span></span> <span data-ttu-id="fc658-114">L'unico modo per disconnettere un'entità dal contesto dati originali è serializzarla.</span><span class="sxs-lookup"><span data-stu-id="fc658-114">The only way for an entity to be detached from its original data context is for it to be serialized.</span></span> <span data-ttu-id="fc658-115">Se si tenta di associare un'entità disconnessa a un nuovo contesto dati e tale entità dispone ancora di caricatori posticipati dal contesto dati precedente, in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="fc658-115">If you try to attach an undetached entity to a new data context, and that entity still has deferred loaders from its previous data context, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] will thrown an exception.</span></span> <span data-ttu-id="fc658-116">Un'entità con caricatori posticipati da due contesti dati diversi può causare risultati imprevisti quando si eseguono le operazioni di inserimento, aggiornamento ed eliminazione su tale entità.</span><span class="sxs-lookup"><span data-stu-id="fc658-116">An entity with deferred loaders from two different data contexts could cause unwanted results when you perform insert, update, and delete operations on that entity.</span></span> <span data-ttu-id="fc658-117">Per ulteriori informazioni sui caricatori posticipati, vedere [Caricamento posticipato e caricamento immediato](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="fc658-117">For more information about deferred loaders, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="retrieving-data"></a><span data-ttu-id="fc658-118">Recupero di dati</span><span class="sxs-lookup"><span data-stu-id="fc658-118">Retrieving Data</span></span>  
  
### <a name="client-method-call"></a><span data-ttu-id="fc658-119">Chiamata al metodo client</span><span class="sxs-lookup"><span data-stu-id="fc658-119">Client Method Call</span></span>  
 <span data-ttu-id="fc658-120">Negli esempi seguenti viene illustrata una chiamata al metodo di esempio nel DAL da un client Windows Form.</span><span class="sxs-lookup"><span data-stu-id="fc658-120">The following examples show a sample method call to the DAL from a Windows Forms client.</span></span> <span data-ttu-id="fc658-121">In questo esempio il DAL viene implementato come libreria dei servizi Windows:</span><span class="sxs-lookup"><span data-stu-id="fc658-121">In this example, the DAL is implemented as a Windows Service Library:</span></span>  
  
```vb  
Private Function GetProdsByCat_Click(ByVal sender As Object, ByVal e _  
    As EventArgs)  
  
    ' Create the WCF client proxy.  
    Dim proxy As New NorthwindServiceReference.Service1Client  
  
    ' Call the method on the service.  
    Dim products As NorthwindServiceReference.Product() = _  
        proxy.GetProductsByCategory(1)  
  
    ' If the database uses original values for concurrency checks,  
    ' the client needs to store them and pass them back to the  
    ' middle tier along with the new values when updating data.  
  
    For Each v As NorthwindClient1.NorthwindServiceReference.Product _  
        In products  
        ' Persist to a List(Of Product) declared at class scope.  
        ' Additional change-tracking logic is the responsibility  
        ' of the presentation tier and/or middle tier.  
        originalProducts.Add(v)  
    Next  
  
    ' (Not shown) Bind the products list to a control  
    ' and/or perform whatever processing is necessary.  
End Function  
```  
  
```csharp  
private void GetProdsByCat_Click(object sender, EventArgs e)  
{  
    // Create the WCF client proxy.  
    NorthwindServiceReference.Service1Client proxy =
    new NorthwindClient.NorthwindServiceReference.Service1Client();  
  
    // Call the method on the service.  
    NorthwindServiceReference.Product[] products =
    proxy.GetProductsByCategory(1);  
  
    // If the database uses original values for concurrency checks,
    // the client needs to store them and pass them back to the
    // middle tier along with the new values when updating data.  
    foreach (var v in products)  
    {  
        // Persist to a list<Product> declared at class scope.  
        // Additional change-tracking logic is the responsibility  
        // of the presentation tier and/or middle tier.  
        originalProducts.Add(v);  
    }  
  
    // (Not shown) Bind the products list to a control  
    // and/or perform whatever processing is necessary.  
    }  
```  
  
### <a name="middle-tier-implementation"></a><span data-ttu-id="fc658-122">Implementazione del livello intermedio</span><span class="sxs-lookup"><span data-stu-id="fc658-122">Middle Tier Implementation</span></span>  
 <span data-ttu-id="fc658-123">Nell'esempio seguente viene illustrata un'implementazione del metodo di interfaccia nel livello intermedio.</span><span class="sxs-lookup"><span data-stu-id="fc658-123">The following example shows an implementation of the interface method on the middle tier.</span></span> <span data-ttu-id="fc658-124">Di seguito sono riportati i due punti principali da tenere presente:</span><span class="sxs-lookup"><span data-stu-id="fc658-124">The following are the two main points to note:</span></span>  
  
- <span data-ttu-id="fc658-125">L'oggetto <xref:System.Data.Linq.DataContext> viene dichiarato nell'ambito del metodo.</span><span class="sxs-lookup"><span data-stu-id="fc658-125">The <xref:System.Data.Linq.DataContext> is declared at method scope.</span></span>  
  
- <span data-ttu-id="fc658-126">Il metodo restituisce una raccolta <xref:System.Collections.IEnumerable> dei risultati effettivi.</span><span class="sxs-lookup"><span data-stu-id="fc658-126">The method returns an <xref:System.Collections.IEnumerable> collection of the actual results.</span></span> <span data-ttu-id="fc658-127">Il serializzatore eseguirà la query per restituire i risultati a livello di client/presentazione.</span><span class="sxs-lookup"><span data-stu-id="fc658-127">The serializer will execute the query to send the results back to the client/presentation tier.</span></span> <span data-ttu-id="fc658-128">Per accedere localmente ai risultati della query nel livello intermedio, è possibile forzare l'esecuzione chiamando `ToList` o `ToArray` sulla variabile della query.</span><span class="sxs-lookup"><span data-stu-id="fc658-128">To access the query results locally on the middle tier, you can force execution by calling `ToList` or `ToArray` on the query variable.</span></span> <span data-ttu-id="fc658-129">È quindi possibile restituire tale elenco o matrice come oggetto `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="fc658-129">You can then return that list or array as an `IEnumerable`.</span></span>  
  
```vb  
Public Function GetProductsByCategory(ByVal categoryID As Integer) _  
    As IEnumerable(Of Product)  
  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
    Dim productQuery = _  
    From prod In db.Products _  
    Where prod.CategoryID = categoryID _  
    Select prod  
  
    Return productQuery.AsEnumerable()  
  
End Function  
```  
  
```csharp  
public IEnumerable<Product> GetProductsByCategory(int categoryID)  
{  
    NorthwindClasses1DataContext db =
    new NorthwindClasses1DataContext(connectionString);  
  
    IEnumerable<Product> productQuery =  
    from prod in db.Products  
    where prod.CategoryID == categoryID  
    select prod;  
  
    return productQuery.AsEnumerable();
}  
```  
  
 <span data-ttu-id="fc658-130">Un'istanza di un contesto dati deve avere una durata di una "unità di lavoro."</span><span class="sxs-lookup"><span data-stu-id="fc658-130">An instance of a data context should have a lifetime of one "unit of work."</span></span> <span data-ttu-id="fc658-131">In un ambiente a regime di controllo libero ("loosely-coupled") un'unità di lavoro è tipicamente piccola, forse una transazione ottimistica, inclusa una singola chiamata a `SubmitChanges`.</span><span class="sxs-lookup"><span data-stu-id="fc658-131">In a loosely-coupled environment, a unit of work is typically small, perhaps one optimistic transaction, including a single call to `SubmitChanges`.</span></span> <span data-ttu-id="fc658-132">Pertanto, il contesto dati viene creato ed eliminato nell'ambito del metodo.</span><span class="sxs-lookup"><span data-stu-id="fc658-132">Therefore, the data context is created and disposed at method scope.</span></span> <span data-ttu-id="fc658-133">Se l'unità di lavoro include chiamate alla logica delle regole business, è preferibile in genere mantenere l'istanza `DataContext` per l'intera operazione.</span><span class="sxs-lookup"><span data-stu-id="fc658-133">If the unit of work includes calls to business rules logic, then generally you will want to keep the `DataContext` instance for that whole operation.</span></span> <span data-ttu-id="fc658-134">In ogni caso, le istanze `DataContext` non devono essere conservate per lunghi periodi di tempo con un numero arbitrario di transazioni.</span><span class="sxs-lookup"><span data-stu-id="fc658-134">In any case, `DataContext` instances are not intended to be kept alive for long periods of time across arbitrary numbers of transactions.</span></span>  
  
 <span data-ttu-id="fc658-135">Questo metodo restituirà oggetti Product ma non la raccolta di oggetti Order_Detail associati a ogni oggetto Product.</span><span class="sxs-lookup"><span data-stu-id="fc658-135">This method will return Product objects but not the collection of Order_Detail objects that are associated with each Product.</span></span> <span data-ttu-id="fc658-136">Usare l'oggetto <xref:System.Data.Linq.DataLoadOptions> per modificare questo comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="fc658-136">Use the <xref:System.Data.Linq.DataLoadOptions> object to change this default behavior.</span></span> <span data-ttu-id="fc658-137">Per ulteriori informazioni, vedere [Procedura: controllare la quantità](how-to-control-how-much-related-data-is-retrieved.md)di dati correlati recuperati .</span><span class="sxs-lookup"><span data-stu-id="fc658-137">For more information, see [How to: Control How Much Related Data Is Retrieved](how-to-control-how-much-related-data-is-retrieved.md).</span></span>  
  
## <a name="inserting-data"></a><span data-ttu-id="fc658-138">Inserimento di dati</span><span class="sxs-lookup"><span data-stu-id="fc658-138">Inserting Data</span></span>  
 <span data-ttu-id="fc658-139">Per inserire un nuovo oggetto, il livello di presentazione chiama il metodo desiderato sull'interfaccia del livello intermedio e passa il nuovo oggetto da inserire.</span><span class="sxs-lookup"><span data-stu-id="fc658-139">To insert a new object, the presentation tier just calls the relevant method on the middle tier interface, and passes in the new object to insert.</span></span> <span data-ttu-id="fc658-140">In alcuni casi, può essere più efficiente per il client passare solo alcuni valori e far costruire al livello intermedio l'oggetto completo.</span><span class="sxs-lookup"><span data-stu-id="fc658-140">In some cases, it may be more efficient for the client to pass in only some values and have the middle tier construct the full object.</span></span>  
  
### <a name="middle-tier-implementation"></a><span data-ttu-id="fc658-141">Implementazione del livello intermedio</span><span class="sxs-lookup"><span data-stu-id="fc658-141">Middle Tier Implementation</span></span>  
 <span data-ttu-id="fc658-142">Nel livello intermedio viene creato un nuovo oggetto <xref:System.Data.Linq.DataContext>, l'oggetto viene associato all'oggetto <xref:System.Data.Linq.DataContext> usando il metodo <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> e l'oggetto viene inserito quando viene chiamato il metodo <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc658-142">On the middle tier, a new <xref:System.Data.Linq.DataContext> is created, the object is attached to the <xref:System.Data.Linq.DataContext> by using the <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> method, and the object is inserted when <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called.</span></span> <span data-ttu-id="fc658-143">Le eccezioni, i callback e le condizioni di errore possono essere gestiti analogamente a qualsiasi altro scenario del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="fc658-143">Exceptions, callbacks, and error conditions can be handled just as in any other Web service scenario.</span></span>  
  
```vb  
' No call to Attach is necessary for inserts.  
Public Sub InsertOrder(ByVal o As Order)  
  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
    db.Orders.InsertOnSubmit(o)  
  
    ' Exception handling not shown.  
    db.SubmitChanges()  
  
End Sub  
```  
  
```csharp  
// No call to Attach is necessary for inserts.  
    public void InsertOrder(Order o)  
    {  
        NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString);  
        db.Orders.InsertOnSubmit(o);  
  
        // Exception handling not shown.  
        db.SubmitChanges();  
    }  
```  
  
## <a name="deleting-data"></a><span data-ttu-id="fc658-144">Eliminazione di dati</span><span class="sxs-lookup"><span data-stu-id="fc658-144">Deleting Data</span></span>  
 <span data-ttu-id="fc658-145">Per eliminare un oggetto esistente dal database, il livello di presentazione chiama il metodo desiderato sull'interfaccia del livello intermedio e passa la copia che include i valori originali dell'oggetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="fc658-145">To delete an existing object from the database, the presentation tier calls the relevant method on the middle tier interface, and passes in its copy that includes original values of the object to be deleted.</span></span>  
  
 <span data-ttu-id="fc658-146">Le operazioni di eliminazione implicano i controlli di concorrenza ottimistica e l'oggetto da eliminare deve prima essere associato al nuovo contesto dati.</span><span class="sxs-lookup"><span data-stu-id="fc658-146">Delete operations involve optimistic concurrency checks, and the object to be deleted must first be attached to the new data context.</span></span> <span data-ttu-id="fc658-147">In questo esempio il parametro `Boolean` è impostato su `false` per indicare che l'oggetto non ha un timestamp (RowVersion).</span><span class="sxs-lookup"><span data-stu-id="fc658-147">In this example, the `Boolean` parameter is set to `false` to indicate that the object does not have a timestamp (RowVersion).</span></span> <span data-ttu-id="fc658-148">Se la tabella di database genera timestamp per ogni record, i controlli di concorrenza sono molto più semplici, sopratutto per il client.</span><span class="sxs-lookup"><span data-stu-id="fc658-148">If your database table does generate timestamps for each record, then concurrency checks are much simpler, especially for the client.</span></span> <span data-ttu-id="fc658-149">È necessario solo passare l'oggetto originale o modificato e impostare il parametro `Boolean` su `true`.</span><span class="sxs-lookup"><span data-stu-id="fc658-149">Just pass in either the original or modified object and set the `Boolean` parameter to `true`.</span></span> <span data-ttu-id="fc658-150">In ogni caso, nel livello intermedio è in genere necessario rilevare l'eccezione <xref:System.Data.Linq.ChangeConflictException>.</span><span class="sxs-lookup"><span data-stu-id="fc658-150">In any case, on the middle tier it is typically necessary to catch the <xref:System.Data.Linq.ChangeConflictException>.</span></span> <span data-ttu-id="fc658-151">Per ulteriori informazioni su come gestire i conflitti di concorrenza ottimistica, vedere [Concorrenza ottimistica: panoramica](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fc658-151">For more information about how to handle optimistic concurrency conflicts, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
 <span data-ttu-id="fc658-152">Quando si eliminano le entità che hanno vincoli di chiave esterna nelle tabelle associate, è necessario prima eliminare tutti gli oggetti nelle raccolte <xref:System.Data.Linq.EntitySet%601>.</span><span class="sxs-lookup"><span data-stu-id="fc658-152">When deleting entities that have foreign key constraints on associated tables, you must first delete all the objects in its <xref:System.Data.Linq.EntitySet%601> collections.</span></span>  
  
```vb  
' Attach is necessary for deletes.  
Public Sub DeleteOrder(ByVal order As Order)  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
  
    db.Orders.Attach(order, False)  
    ' This will throw an exception if the order has order details.  
    db.Orders.DeleteOnSubmit(order)  
  
    Try  
        ' ConflictMode is an optional parameter.  
        db.SubmitChanges(ConflictMode.ContinueOnConflict)  
  
    Catch ex As ChangeConflictException  
        ' Get conflict information, and take actions  
        ' that are appropriate for your application.  
        ' See MSDN Article "How to: Manage Change  
        ' Conflicts (LINQ to SQL).  
  
    End Try  
End Sub  
```  
  
```csharp  
// Attach is necessary for deletes.  
public void DeleteOrder(Order order)  
{  
    NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString);  
  
    db.Orders.Attach(order, false);  
    // This will throw an exception if the order has order details.  
    db.Orders.DeleteOnSubmit(order);  
    try  
    {  
        // ConflictMode is an optional parameter.  
        db.SubmitChanges(ConflictMode.ContinueOnConflict);  
    }  
    catch (ChangeConflictException e)  
    {  
       // Get conflict information, and take actions  
       // that are appropriate for your application.  
       // See MSDN Article How to: Manage Change Conflicts (LINQ to SQL).  
    }  
}  
```  
  
## <a name="updating-data"></a><span data-ttu-id="fc658-153">Aggiornamento dei dati</span><span class="sxs-lookup"><span data-stu-id="fc658-153">Updating Data</span></span>  
 <span data-ttu-id="fc658-154">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono supportati gli aggiornamenti di questi scenari relativi alla concorrenza ottimistica:</span><span class="sxs-lookup"><span data-stu-id="fc658-154">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports updates in these scenarios involving optimistic concurrency:</span></span>  
  
- <span data-ttu-id="fc658-155">Concorrenza ottimistica basata sui timestamp o i numeri RowVersion.</span><span class="sxs-lookup"><span data-stu-id="fc658-155">Optimistic concurrency based on timestamps or RowVersion numbers.</span></span>  
  
- <span data-ttu-id="fc658-156">Concorrenza ottimistica basata sui valori originali di un subset di proprietà dell'entità.</span><span class="sxs-lookup"><span data-stu-id="fc658-156">Optimistic concurrency based on original values of a subset of entity properties.</span></span>  
  
- <span data-ttu-id="fc658-157">Concorrenza ottimistica basata sulle entità complete originali o modificate.</span><span class="sxs-lookup"><span data-stu-id="fc658-157">Optimistic concurrency based on the complete original and modified entities.</span></span>  
  
 <span data-ttu-id="fc658-158">È inoltre possibile eseguire aggiornamenti o eliminazioni su un'entità con le relative relazioni, ad esempio un oggetto Customer e una raccolta degli oggetti Order associati.</span><span class="sxs-lookup"><span data-stu-id="fc658-158">You can also perform updates or deletes on an entity together with its relations, for example a Customer and a collection of its associated Order objects.</span></span> <span data-ttu-id="fc658-159">Quando nel client si effettuano modifiche a un grafico di oggetti entità e alle relative raccolte figlio (`EntitySet`) e i controlli di concorrenza ottimistica richiedono i valori originali, il client deve fornire tali valori originali per ogni entità e oggetto <xref:System.Data.Linq.EntitySet%601>.</span><span class="sxs-lookup"><span data-stu-id="fc658-159">When you make modifications on the client to a graph of entity objects and their child (`EntitySet`) collections, and the optimistic concurrency checks require original values, the client must provide those original values for each entity and <xref:System.Data.Linq.EntitySet%601> object.</span></span> <span data-ttu-id="fc658-160">Per consentire ai client di effettuare un set di aggiornamenti, eliminazioni e inserimenti correlati in una sola chiamata al metodo, è necessario fornire al client un modo per indicare il tipo di operazione da eseguire su ogni entità.</span><span class="sxs-lookup"><span data-stu-id="fc658-160">If you want to enable clients to make a set of related updates, deletes, and insertions in a single method call, you must provide the client a way to indicate what type of operation to perform on each entity.</span></span> <span data-ttu-id="fc658-161">Nel livello intermedio chiamare quindi il metodo <xref:System.Data.Linq.ITable.Attach%2A> adatto e quindi <xref:System.Data.Linq.ITable.InsertOnSubmit%2A>, <xref:System.Data.Linq.ITable.DeleteAllOnSubmit%2A> o <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> (senza `Attach` per gli inserimenti) per ogni entità prima di chiamare <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc658-161">On the middle tier, you then must call the appropriate <xref:System.Data.Linq.ITable.Attach%2A> method and then <xref:System.Data.Linq.ITable.InsertOnSubmit%2A>, <xref:System.Data.Linq.ITable.DeleteAllOnSubmit%2A>, or <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> (without `Attach`, for insertions) for each entity before you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="fc658-162">Non recuperare i dati dal database per ottenere i valori originali prima dell'esecuzione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="fc658-162">Do not retrieve data from the database as a way to obtain original values before you try updates.</span></span>  
  
 <span data-ttu-id="fc658-163">Per ulteriori informazioni sulla concorrenza ottimistica, vedere [Concorrenza ottimistica: panoramica](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fc658-163">For more information about optimistic concurrency, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span> <span data-ttu-id="fc658-164">Per informazioni dettagliate sulla risoluzione dei conflitti di modifica della concorrenza ottimistica, vedere [Procedura: gestire](how-to-manage-change-conflicts.md)i conflitti di modifica .</span><span class="sxs-lookup"><span data-stu-id="fc658-164">For detailed information about resolving optimistic concurrency change conflicts, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>  
  
 <span data-ttu-id="fc658-165">Negli esempi seguenti vengono illustrati tutti gli scenari:</span><span class="sxs-lookup"><span data-stu-id="fc658-165">The following examples demonstrate each scenario:</span></span>  
  
### <a name="optimistic-concurrency-with-timestamps"></a><span data-ttu-id="fc658-166">Concorrenza ottimistica con timestamp</span><span class="sxs-lookup"><span data-stu-id="fc658-166">Optimistic concurrency with timestamps</span></span>  
  
```vb  
' Assume that "customer" has been sent by client.  
' Attach with "true" to say this is a modified entity  
' and it can be checked for optimistic concurrency  
' because it has a column that is marked with the  
' "RowVersion" attribute.  
  
db.Customers.Attach(customer, True)  
  
Try  
    ' Optional: Specify a ConflictMode value  
    ' in call to SubmitChanges.  
    db.SubmitChanges()  
Catch ex As ChangeConflictException  
    ' Handle conflict based on options provided.  
    ' See MSDN article "How to: Manage Change  
    ' Conflicts (LINQ to SQL)".  
End Try  
```  
  
```csharp  
// Assume that "customer" has been sent by client.  
// Attach with "true" to say this is a modified entity  
// and it can be checked for optimistic concurrency because  
//  it has a column that is marked with "RowVersion" attribute  
db.Customers.Attach(customer, true)  
try  
{  
    // Optional: Specify a ConflictMode value  
    // in call to SubmitChanges.  
    db.SubmitChanges();  
}  
catch(ChangeConflictException e)  
{  
    // Handle conflict based on options provided  
    // See MSDN article How to: Manage Change Conflicts (LINQ to SQL).  
}  
```  
  
### <a name="with-subset-of-original-values"></a><span data-ttu-id="fc658-167">Con un subset di valori originali</span><span class="sxs-lookup"><span data-stu-id="fc658-167">With Subset of Original Values</span></span>  
 <span data-ttu-id="fc658-168">In questo approccio il client restituisce l'oggetto serializzato completo, insieme ai valori da modificare.</span><span class="sxs-lookup"><span data-stu-id="fc658-168">In this approach, the client returns the complete serialized object, together with the values to be modified.</span></span>  
  
```vb  
Public Sub UpdateProductInventory(ByVal p As Product, ByVal _  
    unitsInStock As Short?, ByVal unitsOnOrder As Short?)  
  
    Using db As New NorthwindClasses1DataContext(connectionString)  
        ' p is the original unmodified product  
        ' that was obtained from the database.  
        ' The client kept a copy and returns it now.  
        db.Products.Attach(p, False)  
  
        ' Now that the original values are in the data context,  
        ' apply the changes.  
        p.UnitsInStock = unitsInStock  
        p.UnitsOnOrder = unitsOnOrder  
  
        Try  
            ' Optional: Specify a ConflictMode value  
            ' in call to SubmitChanges.  
            db.SubmitChanges()  
  
        Catch ex As Exception  
            ' Handle conflict based on options provided.  
            ' See MSDN article "How to: Manage Change Conflicts  
            ' (LINQ to SQL)".  
        End Try  
    End Using  
End Sub  
```  
  
```csharp  
public void UpdateProductInventory(Product p, short? unitsInStock, short? unitsOnOrder)  
{  
    using (NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString))  
    {  
        // p is the original unmodified product  
        // that was obtained from the database.  
        // The client kept a copy and returns it now.  
        db.Products.Attach(p, false);  
  
        // Now that the original values are in the data context, apply the changes.  
        p.UnitsInStock = unitsInStock;  
        p.UnitsOnOrder = unitsOnOrder;  
        try  
        {  
             // Optional: Specify a ConflictMode value  
             // in call to SubmitChanges.  
             db.SubmitChanges();  
        }  
        catch (ChangeConflictException e)  
        {  
            // Handle conflict based on provided options.  
            // See MSDN article How to: Manage Change Conflicts  
            // (LINQ to SQL).  
        }  
    }  
}  
```  
  
### <a name="with-complete-entities"></a><span data-ttu-id="fc658-169">Con entità complete</span><span class="sxs-lookup"><span data-stu-id="fc658-169">With Complete Entities</span></span>  
  
```vb  
Public Sub UpdateProductInfo(ByVal newProd As Product, ByVal _  
    originalProd As Product)  
  
    Using db As New NorthwindClasses1DataContext(connectionString)  
        db.Products.Attach(newProd, originalProd)  
  
        Try  
            ' Optional: Specify a ConflictMode value  
            ' in call to SubmitChanges.  
            db.SubmitChanges()  
  
        Catch ex As Exception  
            ' Handle potential change conflicgt in whatever way  
            ' is appropriate for your application.  
            ' For more information, see the MSDN article  
            ' "How to: Manage Change Conflicts (LINQ to  
            ' SQL)".  
        End Try  
  
    End Using  
End Sub  
```  
  
```csharp  
public void UpdateProductInfo(Product newProd, Product originalProd)  
{  
     using (NorthwindClasses1DataContext db = new  
        NorthwindClasses1DataContext(connectionString))  
     {  
         db.Products.Attach(newProd, originalProd);  
         try  
         {  
               // Optional: Specify a ConflictMode value  
               // in call to SubmitChanges.  
               db.SubmitChanges();  
         }  
        catch (ChangeConflictException e)  
        {  
            // Handle potential change conflict in whatever way  
            // is appropriate for your application.  
            // For more information, see the MSDN article  
            // How to: Manage Change Conflicts (LINQ to SQL)/  
        }
    }  
}  
```  
  
 <span data-ttu-id="fc658-170">Per aggiornare una raccolta, chiamare <xref:System.Data.Linq.ITable.AttachAll%2A> anziché `Attach`.</span><span class="sxs-lookup"><span data-stu-id="fc658-170">To update a collection, call <xref:System.Data.Linq.ITable.AttachAll%2A> instead of `Attach`.</span></span>  
  
### <a name="expected-entity-members"></a><span data-ttu-id="fc658-171">Membri dell'entità previsti</span><span class="sxs-lookup"><span data-stu-id="fc658-171">Expected Entity Members</span></span>  
 <span data-ttu-id="fc658-172">Come indicato in precedenza, è necessario impostare solo alcuni membri dell'oggetto entità prima di chiamare i metodi `Attach`.</span><span class="sxs-lookup"><span data-stu-id="fc658-172">As stated previously, only certain members of the entity object are required to be set before you call the `Attach` methods.</span></span> <span data-ttu-id="fc658-173">I membri dell'entità da impostare devono soddisfare i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc658-173">Entity members that are required to be set must fulfill the following criteria:</span></span>  
  
- <span data-ttu-id="fc658-174">Devono essere parte dell'identità dell'entità.</span><span class="sxs-lookup"><span data-stu-id="fc658-174">Be part of the entity’s identity.</span></span>  
  
- <span data-ttu-id="fc658-175">Devono poter essere modificati.</span><span class="sxs-lookup"><span data-stu-id="fc658-175">Be expected to be modified.</span></span>  
  
- <span data-ttu-id="fc658-176">Devono essere un timestamp o avere l'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> impostato su un valore diverso da `Never`.</span><span class="sxs-lookup"><span data-stu-id="fc658-176">Be a timestamp or have its <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> attribute set to something besides `Never`.</span></span>  
  
 <span data-ttu-id="fc658-177">Se una tabella usa un timestamp o un numero di versione per un controllo della concorrenza ottimistica, è necessario impostare tali membri prima di chiamare <xref:System.Data.Linq.ITable.Attach%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc658-177">If a table uses a timestamp or version number for an optimistic concurrency check, you must set those members before you call <xref:System.Data.Linq.ITable.Attach%2A>.</span></span> <span data-ttu-id="fc658-178">Un membro è dedicato al controllo della concorrenza ottimistica quando la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> è impostata su true nell'attributo Column.</span><span class="sxs-lookup"><span data-stu-id="fc658-178">A member is dedicated for optimistic concurrency checking when the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property is set to true on that Column attribute.</span></span> <span data-ttu-id="fc658-179">Tutti gli aggiornamenti necessari vengono inviati solo se i valori del numero di versione o del timestamp sono gli stessi di quelli presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="fc658-179">Any requested updates will be submitted only if the version number or timestamp values are the same on the database.</span></span>  
  
 <span data-ttu-id="fc658-180">Un membro viene usato anche nel controllo della concorrenza ottimistica purché la proprietà del membro <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> non sia impostata su `Never`.</span><span class="sxs-lookup"><span data-stu-id="fc658-180">A member is also used in the optimistic concurrency check as long as the member does not have <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> set to `Never`.</span></span> <span data-ttu-id="fc658-181">Il valore predefinito è `Always` se non viene specificato un altro valore.</span><span class="sxs-lookup"><span data-stu-id="fc658-181">The default value is `Always` if no other value is specified.</span></span>  
  
 <span data-ttu-id="fc658-182">Se uno di questi membri necessari risulta mancante, viene generata un'eccezione <xref:System.Data.Linq.ChangeConflictException> durante l'operazione <xref:System.Data.Linq.DataContext.SubmitChanges%2A> ("Riga non trovata o modificata").</span><span class="sxs-lookup"><span data-stu-id="fc658-182">If any one of these required members is missing, a <xref:System.Data.Linq.ChangeConflictException> is thrown during <xref:System.Data.Linq.DataContext.SubmitChanges%2A> ("Row not found or changed").</span></span>  
  
### <a name="state"></a><span data-ttu-id="fc658-183">State</span><span class="sxs-lookup"><span data-stu-id="fc658-183">State</span></span>  
 <span data-ttu-id="fc658-184">Dopo aver associato un oggetto entità all'istanza <xref:System.Data.Linq.DataContext>, lo stato dell'oggetto diventa `PossiblyModified`.</span><span class="sxs-lookup"><span data-stu-id="fc658-184">After an entity object is attached to the <xref:System.Data.Linq.DataContext> instance, the object is considered to be in the `PossiblyModified` state.</span></span> <span data-ttu-id="fc658-185">Sono disponibili tre modalità per forzare un oggetto associato in modo da essere considerato `Modified`.</span><span class="sxs-lookup"><span data-stu-id="fc658-185">There are three ways to force an attached object to be considered `Modified`.</span></span>  
  
1. <span data-ttu-id="fc658-186">Associarlo come non modificato e quindi modificare direttamente i campi.</span><span class="sxs-lookup"><span data-stu-id="fc658-186">Attach it as unmodified, and then directly modify the fields.</span></span>  
  
2. <span data-ttu-id="fc658-187">Associarlo con l'overload <xref:System.Data.Linq.Table%601.Attach%2A> che accetta le istanze dell'oggetto originale e corrente.</span><span class="sxs-lookup"><span data-stu-id="fc658-187">Attach it with the <xref:System.Data.Linq.Table%601.Attach%2A> overload that takes current and original object instances.</span></span> <span data-ttu-id="fc658-188">In questo modo alla funzionalità di ricerca delle modifiche vengono forniti i valori vecchi e nuovi per rilevare automaticamente i campi modificati.</span><span class="sxs-lookup"><span data-stu-id="fc658-188">This supplies the change tracker with old and new values so that it will automatically know which fields have changed.</span></span>  
  
3. <span data-ttu-id="fc658-189">Associarlo con l'overload <xref:System.Data.Linq.Table%601.Attach%2A> che accetta un secondo parametro booleano (impostato su true).</span><span class="sxs-lookup"><span data-stu-id="fc658-189">Attach it with the <xref:System.Data.Linq.Table%601.Attach%2A> overload that takes a second Boolean parameter (set to true).</span></span> <span data-ttu-id="fc658-190">In questo modo la funzionalità di ricerca delle modifiche considererà l'oggetto modificato senza dover richiedere i valori originali.</span><span class="sxs-lookup"><span data-stu-id="fc658-190">This will tell the change tracker to consider the object modified without having to supply any original values.</span></span> <span data-ttu-id="fc658-191">In questo approccio l'oggetto deve avere un campo di versione/timestamp.</span><span class="sxs-lookup"><span data-stu-id="fc658-191">In this approach, the object must have a version/timestamp field.</span></span>  
  
 <span data-ttu-id="fc658-192">Per ulteriori informazioni, vedere [Stati oggetto e Rilevamento modifiche](object-states-and-change-tracking.md).</span><span class="sxs-lookup"><span data-stu-id="fc658-192">For more information, see [Object States and Change-Tracking](object-states-and-change-tracking.md).</span></span>  
  
 <span data-ttu-id="fc658-193">Se un oggetto entità è già presente nella Cache ID con la stessa identità dell'oggetto associato, viene generata un'eccezione <xref:System.Data.Linq.DuplicateKeyException>.</span><span class="sxs-lookup"><span data-stu-id="fc658-193">If an entity object already occurs in the ID Cache with the same identity as the object being attached, a <xref:System.Data.Linq.DuplicateKeyException> is thrown.</span></span>  
  
 <span data-ttu-id="fc658-194">Quando si associa un set di oggetti `IEnumerable`, viene generata un'eccezione <xref:System.Data.Linq.DuplicateKeyException> se è presente una chiave già esistente.</span><span class="sxs-lookup"><span data-stu-id="fc658-194">When you attach with an `IEnumerable` set of objects, a <xref:System.Data.Linq.DuplicateKeyException> is thrown when an already existing key is present.</span></span> <span data-ttu-id="fc658-195">Gli oggetti rimanenti non verranno associati.</span><span class="sxs-lookup"><span data-stu-id="fc658-195">Remaining objects are not attached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc658-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc658-196">See also</span></span>

- [<span data-ttu-id="fc658-197">Applicazioni a più livelli e remote con LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fc658-197">N-Tier and Remote Applications with LINQ to SQL</span></span>](n-tier-and-remote-applications-with-linq-to-sql.md)
- [<span data-ttu-id="fc658-198">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="fc658-198">Background Information</span></span>](background-information.md)
