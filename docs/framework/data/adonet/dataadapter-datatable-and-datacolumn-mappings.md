---
title: Mapping di DataAdapter, DataTable e DataColumn
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 1b426dbcdc78ecfddeac003616993849ce60b89c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759023"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="c8bed-102">Mapping di DataAdapter, DataTable e DataColumn</span><span class="sxs-lookup"><span data-stu-id="c8bed-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="c8bed-103">Oggetto **DataAdapter** contiene una raccolta di zero o più <xref:System.Data.Common.DataTableMapping> gli oggetti relativi **TableMappings** proprietà.</span><span class="sxs-lookup"><span data-stu-id="c8bed-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="c8bed-104">Oggetto **DataTableMapping** fornisce un mapping master tra i dati restituiti da una query su un'origine dati e un <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="c8bed-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="c8bed-105">Il **DataTableMapping** nome può essere passato al posto del **DataTable** nome per il **riempimento** metodo il **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="c8bed-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="c8bed-106">Nell'esempio seguente viene creato un **DataTableMapping** denominato **AuthorsMapping** per il **autori** tabella.</span><span class="sxs-lookup"><span data-stu-id="c8bed-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="c8bed-107">Oggetto **DataTableMapping** consente di utilizzare nomi di colonna in un **DataTable** diversi da quelli presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="c8bed-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="c8bed-108">Il **DataAdapter** utilizza il mapping per la corrispondenza delle colonne quando viene aggiornata la tabella.</span><span class="sxs-lookup"><span data-stu-id="c8bed-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="c8bed-109">Se non si specifica un **TableName** o un **DataTableMapping** nome quando si chiama il **riempimento** o **aggiornamento** metodo il  **DataAdapter**, **DataAdapter** Cerca un **DataTableMapping** denominato "Table".</span><span class="sxs-lookup"><span data-stu-id="c8bed-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="c8bed-110">Se tale **DataTableMapping** non esiste, il **TableName** del **DataTable** sarà "Table".</span><span class="sxs-lookup"><span data-stu-id="c8bed-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="c8bed-111">È possibile specificare un valore predefinito **DataTableMapping** creando un **DataTableMapping** con il nome "Table".</span><span class="sxs-lookup"><span data-stu-id="c8bed-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="c8bed-112">L'esempio di codice seguente crea un **DataTableMapping** (dal <xref:System.Data.Common> dello spazio dei nomi) e lo rende il mapping predefinito per l'oggetto specificato **DataAdapter** denominandolo "Table".</span><span class="sxs-lookup"><span data-stu-id="c8bed-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="c8bed-113">Viene quindi eseguito il mapping di colonne della prima tabella nel risultato della query (il **clienti** tabella il **Northwind** database) a un set di nomi più descrittivi nel **Customers di Northwind**  tabella il <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c8bed-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="c8bed-114">Per le colonne di cui non viene eseguito il mapping, viene usato il nome della colonna nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c8bed-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =   
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 <span data-ttu-id="c8bed-115">In situazioni più avanzate, è possibile che si desidera che lo stesso **DataAdapter** per supportare il caricamento di diverse tabelle con mapping diversi.</span><span class="sxs-lookup"><span data-stu-id="c8bed-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="c8bed-116">A tale scopo, è sufficiente aggiungere altri **DataTableMapping** oggetti.</span><span class="sxs-lookup"><span data-stu-id="c8bed-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="c8bed-117">Quando il **riempimento** metodo verrà passato un'istanza di un **set di dati** e **DataTableMapping** nome, se esiste un mapping con quel nome è utilizzato in caso contrario, un  **DataTable** nome che viene usato.</span><span class="sxs-lookup"><span data-stu-id="c8bed-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="c8bed-118">Gli esempi seguenti creano un **DataTableMapping** con un nome di **clienti** e **DataTable** nome di **BizTalkSchema**.</span><span class="sxs-lookup"><span data-stu-id="c8bed-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="c8bed-119">Nell'esempio viene quindi eseguito il mapping le righe restituite dall'istruzione SELECT per la **BizTalkSchema** **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="c8bed-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =   
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
>  <span data-ttu-id="c8bed-120">Se non viene indicato il nome della colonna di origine per il mapping di una colonna o il nome della tabella di origine per il mapping di una tabella, vengono generati automaticamente nomi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c8bed-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="c8bed-121">Se nessuna colonna di origine viene fornita per il mapping di una colonna, il mapping della colonna viene assegnato il nome predefinito incrementale **SourceColumn** *N,* a partire da **SourceColumn1**.</span><span class="sxs-lookup"><span data-stu-id="c8bed-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="c8bed-122">Se viene specificato alcun nome di tabella di origine per il mapping di una tabella, il mapping di tabella viene assegnato il nome predefinito incrementale **SourceTable** *N*, a partire da **SourceTable1**.</span><span class="sxs-lookup"><span data-stu-id="c8bed-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8bed-123">Si consiglia di evitare la convenzione di denominazione **SourceColumn** *N* per il mapping di una colonna, o **SourceTable** *N* per una tabella mapping, poiché il nome sia in conflitto con un nome di mapping di colonna predefinito esistente nel **ColumnMappingCollection** o nome della tabella mapping nel **DataTableMappingCollection** .</span><span class="sxs-lookup"><span data-stu-id="c8bed-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="c8bed-124">Se il nome specificato esiste già, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c8bed-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="c8bed-125">Gestione di più set di risultati</span><span class="sxs-lookup"><span data-stu-id="c8bed-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="c8bed-126">Se il **SelectCommand** restituisce più tabelle, **riempimento** genera automaticamente i nomi di tabella con valori incrementali per le tabelle il **set di dati**, che inizia con il specificato nome di tabella e continuando nel formato **TableName** *N*, a partire da **TableName1**.</span><span class="sxs-lookup"><span data-stu-id="c8bed-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="c8bed-127">È possibile utilizzare i mapping di tabella per il mapping del nome della tabella generato automaticamente in un nome che si desidera specificare per la tabella di **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="c8bed-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="c8bed-128">Ad esempio, per un **SelectCommand** che restituisce due tabelle, **clienti** e **ordini**, eseguire la chiamata seguente a **riempimento**.</span><span class="sxs-lookup"><span data-stu-id="c8bed-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 <span data-ttu-id="c8bed-129">Cui vengono create due tabelle di **DataSet**: **clienti** e **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="c8bed-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="c8bed-130">È possibile utilizzare i mapping di tabella per assicurarsi che la seconda tabella è denominata **ordini** anziché **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="c8bed-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="c8bed-131">A tale scopo, eseguire il mapping di tabella di origine della **Customers1** per il **DataSet** tabella **ordini**, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c8bed-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8bed-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8bed-132">See Also</span></span>  
 [<span data-ttu-id="c8bed-133">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="c8bed-133">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="c8bed-134">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c8bed-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="c8bed-135">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="c8bed-135">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
