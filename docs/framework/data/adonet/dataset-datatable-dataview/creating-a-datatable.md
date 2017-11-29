---
title: Creazione di un oggetto DataTable
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
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 923d19e9539c6d93f3714efcdaa6fe7a5da843ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="creating-a-datatable"></a><span data-ttu-id="fb955-102">Creazione di un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="fb955-102">Creating a DataTable</span></span>
<span data-ttu-id="fb955-103">È possibile creare una <xref:System.Data.DataTable>, che rappresenta una tabella di dati relazionali in memoria, e usarla in modo indipendente oppure usarla tramite altri oggetti di .NET Framework, in genere come membro di un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="fb955-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="fb955-104">È possibile creare un **DataTable** oggetto, utilizzando i **DataTable** costruttore.</span><span class="sxs-lookup"><span data-stu-id="fb955-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="fb955-105">È possibile aggiungerlo al **DataSet** utilizzando il **Aggiungi** metodo per aggiungerlo al **DataTable** dell'oggetto **tabelle** insieme.</span><span class="sxs-lookup"><span data-stu-id="fb955-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="fb955-106">È inoltre possibile creare **DataTable** oggetti all'interno di un **set di dati** utilizzando il **riempimento** o **FillSchema** metodi del  **DataAdapter** oggetto, o da un predefinito o inferito uno schema XML utilizzando il **ReadXml**, **ReadXmlSchema**, o **InferXmlSchema** metodi di **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="fb955-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="fb955-107">Si noti che dopo aver aggiunto un **DataTable** come membro del **tabelle** raccolta costituita da un **DataSet**, non è possibile aggiungere alla raccolta di tabelle di qualsiasi altro **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="fb955-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="fb955-108">Quando si crea innanzitutto un **DataTable**, non è uno schema (ovvero, una struttura).</span><span class="sxs-lookup"><span data-stu-id="fb955-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="fb955-109">Per definire lo schema della tabella, è necessario creare e aggiungere <xref:System.Data.DataColumn> oggetti per il **colonne** insieme della tabella.</span><span class="sxs-lookup"><span data-stu-id="fb955-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="fb955-110">È inoltre possibile definire una colonna chiave primaria per la tabella e creare e aggiungere **vincolo** oggetti per il **vincoli** insieme della tabella.</span><span class="sxs-lookup"><span data-stu-id="fb955-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="fb955-111">Dopo aver definito lo schema per un **DataTable**, è possibile aggiungere righe di dati alla tabella aggiungendo **DataRow** oggetti per il **righe** insieme della tabella.</span><span class="sxs-lookup"><span data-stu-id="fb955-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="fb955-112">Non è necessario fornire un valore per il <xref:System.Data.DataTable.TableName%2A> proprietà quando si crea un **DataTable**; è possibile specificare la proprietà in un secondo momento, oppure è possibile lasciare vuoto.</span><span class="sxs-lookup"><span data-stu-id="fb955-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="fb955-113">Tuttavia, quando si aggiunge una tabella senza un **TableName** valore un **DataSet**, la tabella verrà assegnato un nome predefinito incrementale Table*N*, che inizia con "Table" per Table0.</span><span class="sxs-lookup"><span data-stu-id="fb955-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb955-114">È consigliabile evitare di "tabella*N*" convenzione di denominazione quando si fornisce un **TableName** valore, poiché il nome sia in conflitto con un nome di tabella predefinito esistente nel **set di dati** .</span><span class="sxs-lookup"><span data-stu-id="fb955-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="fb955-115">Se il nome fornito è già presente, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="fb955-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="fb955-116">L'esempio seguente crea un'istanza di un **DataTable** dell'oggetto e viene assegnato il nome "Customers".</span><span class="sxs-lookup"><span data-stu-id="fb955-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="fb955-117">L'esempio seguente crea un'istanza di un **DataTable** aggiungendolo al **tabelle** raccolta di un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="fb955-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb955-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb955-118">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [<span data-ttu-id="fb955-119">DataTable</span><span class="sxs-lookup"><span data-stu-id="fb955-119">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="fb955-120">Popolamento di un set di dati da un oggetto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="fb955-120">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [<span data-ttu-id="fb955-121">Caricamento di un DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="fb955-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="fb955-122">Il caricamento delle informazioni dello Schema di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="fb955-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="fb955-123">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="fb955-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
