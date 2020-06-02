---
title: Aggiunta di colonne a un oggetto DataTable
description: Una DataTable contiene oggetti DataColumn a cui fa riferimento la proprietà Columns della tabella. Usare questo codice di esempio per aggiungere colonne a una tabella in ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 9d6d21696acd7a6b63cfd6d2ea7e906ec2acd7c9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286947"
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="ee80e-104">Aggiunta di colonne a un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="ee80e-104">Adding Columns to a DataTable</span></span>
<span data-ttu-id="ee80e-105">Un oggetto <xref:System.Data.DataTable> contiene una raccolta di <xref:System.Data.DataColumn> oggetti a cui fa riferimento la proprietà **Columns** della tabella.</span><span class="sxs-lookup"><span data-stu-id="ee80e-105">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="ee80e-106">Tale raccolta di colonne, insieme a eventuali vincoli, consente di definire lo schema, o struttura, della tabella.</span><span class="sxs-lookup"><span data-stu-id="ee80e-106">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="ee80e-107">Per creare oggetti **DataColumn** all'interno di una tabella, è possibile usare il costruttore **DataColumn** oppure chiamare il metodo **Add** della proprietà **Columns** della tabella, che è un oggetto <xref:System.Data.DataColumnCollection> .</span><span class="sxs-lookup"><span data-stu-id="ee80e-107">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="ee80e-108">Il metodo **Add** accetta gli argomenti facoltativi **ColumnName**, **DataType**e **Expression** e crea un nuovo oggetto **DataColumn** come membro della raccolta.</span><span class="sxs-lookup"><span data-stu-id="ee80e-108">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="ee80e-109">Accetta inoltre un oggetto **DataColumn** esistente e lo aggiunge alla raccolta e restituisce un riferimento alla **DataColumn** aggiunta, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="ee80e-109">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="ee80e-110">Poiché gli oggetti **DataTable** non sono specifici di alcuna origine dati, i tipi di .NET Framework vengono usati quando si specifica il tipo di dati di un oggetto **DataColumn**.</span><span class="sxs-lookup"><span data-stu-id="ee80e-110">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="ee80e-111">Nell'esempio seguente vengono aggiunte quattro colonne a un **oggetto DataTable**.</span><span class="sxs-lookup"><span data-stu-id="ee80e-111">The following example adds four columns to a **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="ee80e-112">Nell'esempio si noti che le proprietà della colonna **CustID** sono impostate in modo da non consentire valori **DBNull** e vincolare i valori in modo che siano univoci.</span><span class="sxs-lookup"><span data-stu-id="ee80e-112">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="ee80e-113">Tuttavia, se si definisce la colonna **CustID** come colonna chiave primaria della tabella, la proprietà **AllowDBNull** verrà impostata automaticamente su **false** e la proprietà **Unique** verrà impostata automaticamente su **true**.</span><span class="sxs-lookup"><span data-stu-id="ee80e-113">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="ee80e-114">Per ulteriori informazioni, vedere [definizione delle chiavi primarie](defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="ee80e-114">For more information, see [Defining Primary Keys](defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="ee80e-115">Se per una colonna non viene specificato un nome di colonna, alla colonna viene assegnato il nome predefinito incrementale Column*N,* che inizia con "Column1", quando viene aggiunto a **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="ee80e-115">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="ee80e-116">Si consiglia di evitare la convenzione di denominazione "Column*N*" quando si fornisce un nome di colonna, perché il nome fornito potrebbe entrare in conflitto con un nome di colonna predefinito esistente in **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="ee80e-116">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="ee80e-117">Se il nome fornito è già presente, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ee80e-117">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="ee80e-118">Se si sta usando l'oggetto <xref:System.Xml.Linq.XElement> come proprietà <xref:System.Data.DataColumn.DataType%2A> di un oggetto <xref:System.Data.DataColumn> nell'oggetto <xref:System.Data.DataTable>, la serializzazione XML non funzionerà quando si legge nei dati.</span><span class="sxs-lookup"><span data-stu-id="ee80e-118">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="ee80e-119">Ad esempio, se si scrive un oggetto <xref:System.Xml.XmlDocument> usando il metodo `DataTable.WriteXml`, durante la serializzazione in XML è presente un nodo padre aggiuntivo nell'oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ee80e-119">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="ee80e-120">Per risolvere questo problema, usare il tipo <xref:System.Data.SqlTypes.SqlXml> invece dell'oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ee80e-120">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="ee80e-121">`ReadXml` e `WriteXml` funzionano correttamente con l'oggetto <xref:System.Data.SqlTypes.SqlXml>.</span><span class="sxs-lookup"><span data-stu-id="ee80e-121">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee80e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee80e-122">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="ee80e-123">Definizione dello schema DataTable</span><span class="sxs-lookup"><span data-stu-id="ee80e-123">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="ee80e-124">DataTable</span><span class="sxs-lookup"><span data-stu-id="ee80e-124">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="ee80e-125">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ee80e-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
