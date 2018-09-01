---
title: Creazione di un oggetto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: ad3f8bc6b42c5a54b42100a5d010e097ba80adc2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43386913"
---
# <a name="creating-a-datatable"></a><span data-ttu-id="e07cb-102">Creazione di un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="e07cb-102">Creating a DataTable</span></span>
<span data-ttu-id="e07cb-103">È possibile creare una <xref:System.Data.DataTable>, che rappresenta una tabella di dati relazionali in memoria, e usarla in modo indipendente oppure usarla tramite altri oggetti di .NET Framework, in genere come membro di un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="e07cb-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="e07cb-104">È possibile creare un **DataTable** oggetto utilizzando l'oggetto appropriato **DataTable** costruttore.</span><span class="sxs-lookup"><span data-stu-id="e07cb-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="e07cb-105">È possibile aggiungerlo al **set di dati** tramite il **Add** metodo deve essere aggiunto il **DataTable** dell'oggetto **tabelle** raccolta.</span><span class="sxs-lookup"><span data-stu-id="e07cb-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="e07cb-106">È anche possibile creare **DataTable** oggetti all'interno di un **set di dati** utilizzando il **riempire** o **FillSchema** metodi del  **DataAdapter** oggetto, o da una predefinito o inferito XML schema usando il **ReadXml**, **ReadXmlSchema**, oppure **InferXmlSchema** i metodi del **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="e07cb-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="e07cb-107">Si noti che dopo aver aggiunto un **DataTable** come membro delle **tabelle** raccolta di uno **set di dati**, non è possibile aggiungere alla raccolta di tabelle di qualsiasi altro **Set di dati**.</span><span class="sxs-lookup"><span data-stu-id="e07cb-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="e07cb-108">Quando si crea prima di tutto una **DataTable**, che non è uno schema (vale a dire una struttura).</span><span class="sxs-lookup"><span data-stu-id="e07cb-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="e07cb-109">Per definire lo schema della tabella, è necessario creare e aggiungere <xref:System.Data.DataColumn> gli oggetti per il **colonne** insieme della tabella.</span><span class="sxs-lookup"><span data-stu-id="e07cb-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="e07cb-110">È anche possibile definire una colonna chiave primaria per la tabella e creare e aggiungere **vincolo** gli oggetti per il **vincoli** insieme della tabella.</span><span class="sxs-lookup"><span data-stu-id="e07cb-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="e07cb-111">Dopo aver definito lo schema per un **DataTable**, è possibile aggiungere le righe di dati alla tabella tramite l'aggiunta **DataRow** oggetti per il **righe** insieme della tabella.</span><span class="sxs-lookup"><span data-stu-id="e07cb-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="e07cb-112">Non è necessario fornire un valore per il <xref:System.Data.DataTable.TableName%2A> proprietà quando si crea un' **DataTable**; è possibile specificare la proprietà in un secondo momento, oppure è possibile lasciarla vuota.</span><span class="sxs-lookup"><span data-stu-id="e07cb-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="e07cb-113">Tuttavia, quando si aggiunge una tabella senza un **TableName** valore a un **set di dati**, la tabella verrà assegnato un nome predefinito incrementale Table*N*, che inizia con "Table" per Table0.</span><span class="sxs-lookup"><span data-stu-id="e07cb-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e07cb-114">È consigliabile evitare il "tabella*N*" convenzione di denominazione quando si fornisce un **TableName** valore, poiché il nome immesso sia in conflitto con un nome di tabella predefinito esistente nel **set di dati** .</span><span class="sxs-lookup"><span data-stu-id="e07cb-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="e07cb-115">Se il nome fornito è già presente, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e07cb-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="e07cb-116">L'esempio seguente crea un'istanza di un **DataTable** dell'oggetto e le assegna il nome "Customers".</span><span class="sxs-lookup"><span data-stu-id="e07cb-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="e07cb-117">L'esempio seguente crea un'istanza di un **DataTable** aggiungendola alle **tabelle** raccolta di un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="e07cb-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="e07cb-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e07cb-118">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [<span data-ttu-id="e07cb-119">DataTable</span><span class="sxs-lookup"><span data-stu-id="e07cb-119">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="e07cb-120">Popolamento di un set di dati da un oggetto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="e07cb-120">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [<span data-ttu-id="e07cb-121">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="e07cb-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="e07cb-122">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="e07cb-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="e07cb-123">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="e07cb-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
