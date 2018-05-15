---
title: Gestione di eventi dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: 486f38e2900eb85dbffbb4f9a9d0e6753267e32b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="handling-dataset-events"></a><span data-ttu-id="df5e7-102">Gestione di eventi dataset</span><span class="sxs-lookup"><span data-stu-id="df5e7-102">Handling DataSet Events</span></span>
<span data-ttu-id="df5e7-103">L'oggetto <xref:System.Data.DataSet> fornisce tre eventi: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>e <xref:System.Data.DataSet.MergeFailed>.</span><span class="sxs-lookup"><span data-stu-id="df5e7-103">The <xref:System.Data.DataSet> object provides three events: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>, and <xref:System.Data.DataSet.MergeFailed>.</span></span>  
  
## <a name="the-mergefailed-event"></a><span data-ttu-id="df5e7-104">Evento MergeFailed</span><span class="sxs-lookup"><span data-stu-id="df5e7-104">The MergeFailed Event</span></span>  
 <span data-ttu-id="df5e7-105">L'evento dell'oggetto `DataSet` usato più di frequente è `MergeFailed`, che viene generato quando gli schemi degli oggetti `DataSet` sono in conflitto.</span><span class="sxs-lookup"><span data-stu-id="df5e7-105">The most commonly used event of the `DataSet` object is `MergeFailed`, which is raised when the schema of the `DataSet` objects being merged are in conflict.</span></span> <span data-ttu-id="df5e7-106">Questo problema si verifica quando gli oggetti <xref:System.Data.DataRow> di origine e di destinazione presentano lo stesso valore di chiave primaria e la proprietà <xref:System.Data.DataSet.EnforceConstraints%2A> è impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="df5e7-106">This occurs when a target and source <xref:System.Data.DataRow> have the same primary key value, and the <xref:System.Data.DataSet.EnforceConstraints%2A> property is set to `true`.</span></span> <span data-ttu-id="df5e7-107">Se ad esempio le colonne relative alla chiave primaria di una tabella da unire sono uguali tra le tabelle dei due oggetti `DataSet` , si verifica un'eccezione e viene generato un evento `MergeFailed` .</span><span class="sxs-lookup"><span data-stu-id="df5e7-107">For example, if the primary key columns of a table being merged are the same between the tables in the two `DataSet` objects, an exception is thrown and the `MergeFailed` event is raised.</span></span> <span data-ttu-id="df5e7-108">L'oggetto <xref:System.Data.MergeFailedEventArgs> passato all'evento `MergeFailed` include una proprietà <xref:System.Data.MergeFailedEventArgs.Conflict%2A> che identifica il conflitto di schema tra i due oggetti `DataSet` e una proprietà <xref:System.Data.MergeFailedEventArgs.Table%2A> che identifica il nome della tabella in conflitto.</span><span class="sxs-lookup"><span data-stu-id="df5e7-108">The <xref:System.Data.MergeFailedEventArgs> object passed to the `MergeFailed` event have a <xref:System.Data.MergeFailedEventArgs.Conflict%2A> property that identifies the conflict in schema between the two `DataSet` objects, and a <xref:System.Data.MergeFailedEventArgs.Table%2A> property that identifies the name of the table in conflict.</span></span>  
  
 <span data-ttu-id="df5e7-109">Nel frammento di codice riportato di seguito viene illustrato come aggiungere un gestore per l'evento `MergeFailed`.</span><span class="sxs-lookup"><span data-stu-id="df5e7-109">The following code fragment demonstrates how to add an event handler for the `MergeFailed` event.</span></span>  
  
```vb  
AddHandler workDS.MergeFailed, New MergeFailedEventHandler( _  
  AddressOf DataSetMergeFailed)  
  
Private Shared Sub DataSetMergeFailed(  _  
  sender As Object,args As MergeFailedEventArgs)  
  Console.WriteLine("Merge failed for table " & args.Table.TableName)  
  Console.WriteLine("Conflict = " & args.Conflict)  
End Sub  
```  
  
```csharp  
workDS.MergeFailed += new MergeFailedEventHandler(DataSetMergeFailed);  
  
private static void DataSetMergeFailed(  
  object sender, MergeFailedEventArgs args)  
{  
  Console.WriteLine("Merge failed for table " + args.Table.TableName);  
  Console.WriteLine("Conflict = " + args.Conflict);  
}  
```  
  
## <a name="the-initialized-event"></a><span data-ttu-id="df5e7-110">Evento Initialized</span><span class="sxs-lookup"><span data-stu-id="df5e7-110">The Initialized Event</span></span>  
 <span data-ttu-id="df5e7-111">L'evento <xref:System.Data.DataSet.Initialized> viene generato dopo che il costruttore di `DataSet` inizializza una nuova istanza del `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="df5e7-111">The <xref:System.Data.DataSet.Initialized> event occurs after the `DataSet` constructor initializes a new instance of the `DataSet`.</span></span>  
  
 <span data-ttu-id="df5e7-112">La proprietà <xref:System.Data.DataSet.IsInitialized%2A> restituisce `true` se l'inizializzazione del `DataSet` è stata completata; in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="df5e7-112">The <xref:System.Data.DataSet.IsInitialized%2A> property returns `true` if the `DataSet` has completed initialization; otherwise it returns `false`.</span></span> <span data-ttu-id="df5e7-113">Il metodo <xref:System.Data.DataSet.BeginInit%2A> , che avvia l'inizializzazione di un `DataSet`, imposta <xref:System.Data.DataSet.IsInitialized%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="df5e7-113">The <xref:System.Data.DataSet.BeginInit%2A> method, which begins the initialization of a `DataSet`, sets <xref:System.Data.DataSet.IsInitialized%2A> to `false`.</span></span> <span data-ttu-id="df5e7-114">Il metodo <xref:System.Data.DataSet.EndInit%2A> , che termina l'inizializzazione del `DataSet`, lo imposta su `true`.</span><span class="sxs-lookup"><span data-stu-id="df5e7-114">The <xref:System.Data.DataSet.EndInit%2A> method, which ends the initialization of the `DataSet`, sets it to `true`.</span></span> <span data-ttu-id="df5e7-115">Questi metodi vengono usati dall'ambiente di progettazione di Visual Studio per inizializzare un `DataSet` che viene utilizzato da un altro componente.</span><span class="sxs-lookup"><span data-stu-id="df5e7-115">These methods are used by the Visual Studio design environment to initialize a `DataSet` that is being used by another component.</span></span> <span data-ttu-id="df5e7-116">Non vengono comunemente usati nel codice.</span><span class="sxs-lookup"><span data-stu-id="df5e7-116">You will not commonly use them in your code.</span></span>  
  
## <a name="the-disposed-event"></a><span data-ttu-id="df5e7-117">Evento Disposed</span><span class="sxs-lookup"><span data-stu-id="df5e7-117">The Disposed Event</span></span>  
 <span data-ttu-id="df5e7-118">`DataSet` è derivato dalla classe <xref:System.ComponentModel.MarshalByValueComponent> , che espone il metodo <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> e l'evento <xref:System.ComponentModel.MarshalByValueComponent.Disposed> .</span><span class="sxs-lookup"><span data-stu-id="df5e7-118">`DataSet` is derived from the <xref:System.ComponentModel.MarshalByValueComponent> class, which exposes both the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method and the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event.</span></span> <span data-ttu-id="df5e7-119">Il <xref:System.ComponentModel.MarshalByValueComponent.Disposed> eventi aggiunge un gestore eventi per restare in attesa per l'evento disposed sul componente.</span><span class="sxs-lookup"><span data-stu-id="df5e7-119">The <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event adds an event handler to listen to the disposed event on the component.</span></span> <span data-ttu-id="df5e7-120">È possibile utilizzare il <xref:System.ComponentModel.MarshalByValueComponent.Disposed> evento di un `DataSet` se si desidera eseguire il codice quando il <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="df5e7-120">You can use the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event of a `DataSet` if you want to execute code when the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method is called.</span></span> <span data-ttu-id="df5e7-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> Rilascia le risorse usate dal <xref:System.ComponentModel.MarshalByValueComponent>.</span><span class="sxs-lookup"><span data-stu-id="df5e7-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> releases the resources used by the <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df5e7-122">Il `DataSet` e `DataTable` oggetti ereditano <xref:System.ComponentModel.MarshalByValueComponent> e supportano il <xref:System.Runtime.Serialization.ISerializable> interfaccia per la comunicazione remota.</span><span class="sxs-lookup"><span data-stu-id="df5e7-122">The `DataSet` and `DataTable` objects inherit from <xref:System.ComponentModel.MarshalByValueComponent> and support the <xref:System.Runtime.Serialization.ISerializable> interface for remoting.</span></span> <span data-ttu-id="df5e7-123">Si tratta degli unici oggetti ADO.NET che è possibile eseguire in remoto.</span><span class="sxs-lookup"><span data-stu-id="df5e7-123">These are the only ADO.NET objects that can be remoted.</span></span> <span data-ttu-id="df5e7-124">Per ulteriori informazioni, vedere [oggetti remoti](http://msdn.microsoft.com/library/515686e6-0a8d-42f7-8188-73abede57c58).</span><span class="sxs-lookup"><span data-stu-id="df5e7-124">For more information, see [Remote Objects](http://msdn.microsoft.com/library/515686e6-0a8d-42f7-8188-73abede57c58).</span></span>  
  
 <span data-ttu-id="df5e7-125">Per informazioni su altri eventi disponibili quando si lavora con un `DataSet`, vedere [gestione di eventi DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) e [gestione di eventi DataAdapter](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="df5e7-125">For information about other events available when working with a `DataSet`, see [Handling DataTable Events](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) and [Handling DataAdapter Events](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df5e7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df5e7-126">See Also</span></span>  
 [<span data-ttu-id="df5e7-127">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="df5e7-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="df5e7-128">Convalida dei dati</span><span class="sxs-lookup"><span data-stu-id="df5e7-128">Validating Data</span></span>](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)  
 [<span data-ttu-id="df5e7-129">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="df5e7-129">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="df5e7-130">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="df5e7-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
