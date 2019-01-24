---
title: Aggiunta di colonne a un oggetto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 892c0488588e9a5b59650f4a815ba9819493a610
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538268"
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="bb4e8-102">Aggiunta di colonne a un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="bb4e8-102">Adding Columns to a DataTable</span></span>
<span data-ttu-id="bb4e8-103">Oggetto <xref:System.Data.DataTable> contiene una raccolta di <xref:System.Data.DataColumn> gli oggetti a cui fanno riferimento le **colonne** proprietà della tabella.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-103">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="bb4e8-104">Tale raccolta di colonne, insieme a eventuali vincoli, consente di definire lo schema, o struttura, della tabella.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-104">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="bb4e8-105">Crei **DataColumn** oggetti all'interno di una tabella utilizzando il **DataColumn** costruttore, oppure chiamando il **Aggiungi** metodo del **colonne**proprietà della tabella, ovvero un <xref:System.Data.DataColumnCollection>.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-105">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="bb4e8-106">Il **Add** metodo accetta facoltativo **nomecolonna**, **DataType**, e **espressione** argomenti e crea un nuovo  **DataColumn** come membro della raccolta.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-106">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="bb4e8-107">L'attività accetta inoltre un oggetto esistente **DataColumn** dell'oggetto e lo aggiunge alla raccolta e restituisce un riferimento all'oggetto aggiunto **DataColumn** se richiesto.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-107">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="bb4e8-108">In quanto **DataTable** gli oggetti non sono specifici di qualsiasi origine dati, i tipi di .NET Framework vengono usati quando si specifica il tipo di dati di un **DataColumn**.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-108">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="bb4e8-109">L'esempio seguente aggiunge quattro colonne a un **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-109">The following example adds four columns to a **DataTable**.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 <span data-ttu-id="bb4e8-110">Nell'esempio, si noti che le proprietà per il **CustID** colonna sono impostate per non consentire **DBNull** valori e per vincolare i valori siano univoci.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-110">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="bb4e8-111">Tuttavia, se si definisce la **CustID** colonna come colonna chiave primaria della tabella, il **AllowDBNull** verrà automaticamente impostata su **false** e il **Unique** verrà automaticamente impostata su **true**.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-111">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="bb4e8-112">Per altre informazioni, vedere [definizione di chiavi primarie](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="bb4e8-112">For more information, see [Defining Primary Keys](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="bb4e8-113">Se non viene fornito un nome di colonna per una colonna, la colonna viene assegnata il nome predefinito incrementale della colonna*N,* a partire da "Column1", quando viene aggiunto per il **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-113">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="bb4e8-114">Si consiglia di evitare la convenzione di denominazione "colonna*N*" quando si fornisce un nome di colonna, perché il nome fornito sia in conflitto con un nome di colonna predefinito esistente nel **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-114">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="bb4e8-115">Se il nome fornito è già presente, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="bb4e8-116">Se si sta usando l'oggetto <xref:System.Xml.Linq.XElement> come proprietà <xref:System.Data.DataColumn.DataType%2A> di un oggetto <xref:System.Data.DataColumn> nell'oggetto <xref:System.Data.DataTable>, la serializzazione XML non funzionerà quando si legge nei dati.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-116">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="bb4e8-117">Ad esempio, se si scrive un oggetto <xref:System.Xml.XmlDocument> usando il metodo `DataTable.WriteXml`, durante la serializzazione in XML è presente un nodo padre aggiuntivo nell'oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-117">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="bb4e8-118">Per risolvere questo problema, usare il tipo <xref:System.Data.SqlTypes.SqlXml> invece dell'oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-118">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="bb4e8-119">`ReadXml` e `WriteXml` funzionano correttamente con l'oggetto <xref:System.Data.SqlTypes.SqlXml>.</span><span class="sxs-lookup"><span data-stu-id="bb4e8-119">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb4e8-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb4e8-120">See also</span></span>
- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="bb4e8-121">Definizione dello schema DataTable</span><span class="sxs-lookup"><span data-stu-id="bb4e8-121">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="bb4e8-122">DataTable</span><span class="sxs-lookup"><span data-stu-id="bb4e8-122">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="bb4e8-123">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="bb4e8-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
