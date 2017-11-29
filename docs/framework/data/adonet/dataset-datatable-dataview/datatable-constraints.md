---
title: Vincoli DataTable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fb1fd2c7aa057fcc83c82ab9d72129db2cac680e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="datatable-constraints"></a><span data-ttu-id="25dc5-102">Vincoli DataTable</span><span class="sxs-lookup"><span data-stu-id="25dc5-102">DataTable Constraints</span></span>
<span data-ttu-id="25dc5-103">I vincoli consentono di applicare restrizioni ai dati di una <xref:System.Data.DataTable>, in modo da garantire l'integrità di tali dati.</span><span class="sxs-lookup"><span data-stu-id="25dc5-103">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="25dc5-104">Un vincolo è una regola automatica applicata a una colonna, o a colonne correlate, che consente di determinare le operazioni da eseguire in caso di modifica del valore di una riga.</span><span class="sxs-lookup"><span data-stu-id="25dc5-104">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="25dc5-105">I vincoli vengono applicati quando la `System.Data.DataSet.EnforceConstraints` proprietà del <xref:System.Data.DataSet> è **true**.</span><span class="sxs-lookup"><span data-stu-id="25dc5-105">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="25dc5-106">Per un esempio di codice che illustra come impostare la proprietà `EnforceConstraints`, vedere l'argomento relativo a <xref:System.Data.DataSet.EnforceConstraints%2A>.</span><span class="sxs-lookup"><span data-stu-id="25dc5-106">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="25dc5-107">In ADO.NET sono disponibili due tipi di vincoli: <xref:System.Data.ForeignKeyConstraint> e <xref:System.Data.UniqueConstraint>.</span><span class="sxs-lookup"><span data-stu-id="25dc5-107">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="25dc5-108">Per impostazione predefinita, entrambi i vincoli vengono creati automaticamente quando si crea una relazione tra due o più tabelle aggiungendo un <xref:System.Data.DataRelation> per il **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="25dc5-108">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="25dc5-109">Tuttavia, è possibile disabilitare questo comportamento specificando **createConstraints** = **false** durante la creazione della relazione.</span><span class="sxs-lookup"><span data-stu-id="25dc5-109">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="25dc5-110">ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="25dc5-110">ForeignKeyConstraint</span></span>  
 <span data-ttu-id="25dc5-111">Oggetto **ForeignKeyConstraint** applica le regole sulla modalità di propagazione degli aggiornamenti ed eliminazioni alle tabelle correlate.</span><span class="sxs-lookup"><span data-stu-id="25dc5-111">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="25dc5-112">Se un valore in una riga di una tabella viene aggiornato o eliminato e tale valore è utilizzato anche in uno o più tabelle correlate, ad esempio un **ForeignKeyConstraint** determina cosa accade nelle tabelle correlate.</span><span class="sxs-lookup"><span data-stu-id="25dc5-112">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="25dc5-113">Il <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> e <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> le proprietà del **ForeignKeyConstraint** definire l'azione da intraprendere quando l'utente tenta di eliminare o aggiornare una riga in una tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="25dc5-113">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="25dc5-114">Nella tabella seguente vengono descritte le diverse impostazioni disponibili per il **DeleteRule** e **UpdateRule** le proprietà del **ForeignKeyConstraint**.</span><span class="sxs-lookup"><span data-stu-id="25dc5-114">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="25dc5-115">Impostazione della regola</span><span class="sxs-lookup"><span data-stu-id="25dc5-115">Rule setting</span></span>|<span data-ttu-id="25dc5-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25dc5-116">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="25dc5-117">**CASCADE**</span><span class="sxs-lookup"><span data-stu-id="25dc5-117">**Cascade**</span></span>|<span data-ttu-id="25dc5-118">Elimina o aggiorna righe correlate.</span><span class="sxs-lookup"><span data-stu-id="25dc5-118">Delete or update related rows.</span></span>|  
|<span data-ttu-id="25dc5-119">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="25dc5-119">**SetNull**</span></span>|<span data-ttu-id="25dc5-120">Impostare i valori nelle righe correlate **DBNull**.</span><span class="sxs-lookup"><span data-stu-id="25dc5-120">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="25dc5-121">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="25dc5-121">**SetDefault**</span></span>|<span data-ttu-id="25dc5-122">Imposta i valori delle righe correlate sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="25dc5-122">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="25dc5-123">**None**</span><span class="sxs-lookup"><span data-stu-id="25dc5-123">**None**</span></span>|<span data-ttu-id="25dc5-124">Non viene eseguita alcuna operazione sulle righe correlate.</span><span class="sxs-lookup"><span data-stu-id="25dc5-124">Take no action on related rows.</span></span> <span data-ttu-id="25dc5-125">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="25dc5-125">This is the default.</span></span>|  
  
 <span data-ttu-id="25dc5-126">Oggetto **ForeignKeyConstraint** consente di limitare, oltre che propagare, modifiche alle relative colonne.</span><span class="sxs-lookup"><span data-stu-id="25dc5-126">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="25dc5-127">In base alle proprietà impostate per il **ForeignKeyConstraint** di una colonna, se il **EnforceConstraints** proprietà del **DataSet** è **true**, eseguire determinate operazioni sulla riga padre provocherà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="25dc5-127">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="25dc5-128">Ad esempio, se il **DeleteRule** proprietà del **ForeignKeyConstraint** è **Nessuno**, Impossibile eliminare una riga padre se dispone di tutte le righe figlio.</span><span class="sxs-lookup"><span data-stu-id="25dc5-128">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="25dc5-129">È possibile creare un vincolo di chiave esterna tra singole colonne o tra una matrice di colonne usando la **ForeignKeyConstraint** costruttore.</span><span class="sxs-lookup"><span data-stu-id="25dc5-129">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="25dc5-130">Passare il valore risultante **ForeignKeyConstraint** dell'oggetto per il **Aggiungi** metodo per la tabella **vincoli** proprietà, ovvero un **ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="25dc5-130">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="25dc5-131">È anche possibile passare gli argomenti del costruttore a diversi overload di **Aggiungi** metodo di un **ConstraintCollection** per creare un **ForeignKeyConstraint**.</span><span class="sxs-lookup"><span data-stu-id="25dc5-131">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="25dc5-132">Durante la creazione di un **ForeignKeyConstraint**, è possibile passare il **DeleteRule** e **UpdateRule** valori al costruttore come argomenti o impostare tali valori come proprietà come il Dopo l'esempio (dove il **DeleteRule** è impostato su **Nessuno**).</span><span class="sxs-lookup"><span data-stu-id="25dc5-132">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None    
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],   
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;    
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a><span data-ttu-id="25dc5-133">AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="25dc5-133">AcceptRejectRule</span></span>  
 <span data-ttu-id="25dc5-134">Le modifiche alle righe possono essere accettate utilizzando il **AcceptChanges** metodo o annullato utilizzando il **RejectChanges** metodo il **set di dati**, **DataTable**, o **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="25dc5-134">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="25dc5-135">Quando un **DataSet** contiene **ForeignKeyConstraints**, la chiamata di **AcceptChanges** o **RejectChanges** metodi impone il  **AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="25dc5-135">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="25dc5-136">Il **AcceptRejectRule** proprietà del **ForeignKeyConstraint** determina quali azioni saranno eseguite sull'elemento figlio delle righe quando **AcceptChanges** o  **RejectChanges** viene chiamato nella riga padre.</span><span class="sxs-lookup"><span data-stu-id="25dc5-136">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="25dc5-137">La tabella seguente elenca le impostazioni disponibili per il **AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="25dc5-137">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="25dc5-138">Impostazione della regola</span><span class="sxs-lookup"><span data-stu-id="25dc5-138">Rule setting</span></span>|<span data-ttu-id="25dc5-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25dc5-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="25dc5-140">**CASCADE**</span><span class="sxs-lookup"><span data-stu-id="25dc5-140">**Cascade**</span></span>|<span data-ttu-id="25dc5-141">Consente di accettare o rifiutare le modifiche alle righe figlio.</span><span class="sxs-lookup"><span data-stu-id="25dc5-141">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="25dc5-142">**None**</span><span class="sxs-lookup"><span data-stu-id="25dc5-142">**None**</span></span>|<span data-ttu-id="25dc5-143">Non viene eseguita alcuna operazione sulle righe figlio.</span><span class="sxs-lookup"><span data-stu-id="25dc5-143">Take no action on child rows.</span></span> <span data-ttu-id="25dc5-144">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="25dc5-144">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="25dc5-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="25dc5-145">Example</span></span>  
 <span data-ttu-id="25dc5-146">Nell'esempio seguente viene creato un oggetto <xref:System.Data.ForeignKeyConstraint>, ne vengono impostate alcune proprietà, tra cui <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, nonché viene aggiunto all'oggetto <xref:System.Data.ConstraintCollection> di un oggetto <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="25dc5-146">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="25dc5-147">UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="25dc5-147">UniqueConstraint</span></span>  
 <span data-ttu-id="25dc5-148">Il **UniqueConstraint** oggetto, che può essere assegnato a una singola colonna o a una matrice di colonne in un **DataTable**, assicura che tutti i dati della colonna specificata o delle colonne sia univoco per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="25dc5-148">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="25dc5-149">È possibile creare un vincolo univoco per una colonna o una matrice di colonne tramite il **UniqueConstraint** costruttore.</span><span class="sxs-lookup"><span data-stu-id="25dc5-149">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="25dc5-150">Passare il valore risultante **UniqueConstraint** dell'oggetto per il **Aggiungi** metodo per la tabella **vincoli** proprietà, ovvero un **ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="25dc5-150">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="25dc5-151">È anche possibile passare gli argomenti del costruttore a diversi overload di **Aggiungi** metodo di un **ConstraintCollection** per creare un **UniqueConstraint**.</span><span class="sxs-lookup"><span data-stu-id="25dc5-151">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="25dc5-152">Quando si crea un **UniqueConstraint** per una o più colonne, è possibile, facoltativamente, specificare se le colonne sono una chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="25dc5-152">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="25dc5-153">È anche possibile creare un vincolo univoco per una colonna impostando il **Unique** proprietà della colonna **true**.</span><span class="sxs-lookup"><span data-stu-id="25dc5-153">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="25dc5-154">In alternativa, l'impostazione di **Unique** proprietà di una singola colonna per **false** rimuove qualsiasi vincolo unique che potrebbe esistere.</span><span class="sxs-lookup"><span data-stu-id="25dc5-154">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="25dc5-155">La definizione di una o più colonne come chiave primaria per una tabella consentirà di creare automaticamente un vincolo univoco per la colonna o le colonne specificate.</span><span class="sxs-lookup"><span data-stu-id="25dc5-155">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="25dc5-156">Se si rimuove una colonna dal **PrimaryKey** proprietà di un **DataTable**, **UniqueConstraint** viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="25dc5-156">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="25dc5-157">Nell'esempio seguente viene creato un **UniqueConstraint** per due colonne di una **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="25dc5-157">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]   
    {custTable.Columns["CustomerID"],   
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a><span data-ttu-id="25dc5-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25dc5-158">See Also</span></span>  
 <xref:System.Data.DataRelation>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.ForeignKeyConstraint>  
 <xref:System.Data.UniqueConstraint>  
 [<span data-ttu-id="25dc5-159">Definizione dello Schema di DataTable</span><span class="sxs-lookup"><span data-stu-id="25dc5-159">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="25dc5-160">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="25dc5-160">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="25dc5-161">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="25dc5-161">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
