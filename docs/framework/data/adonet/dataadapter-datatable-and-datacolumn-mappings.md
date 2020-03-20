---
title: Mapping di DataAdapter, DataTable e DataColumn
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 6380dd0512bd7834f50b87f90f445cb01b7a8b95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151559"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="17438-102">Mapping di DataAdapter, DataTable e DataColumn</span><span class="sxs-lookup"><span data-stu-id="17438-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="17438-103">Oggetto **DataAdapter** contiene una raccolta <xref:System.Data.Common.DataTableMapping> di zero o più oggetti nella relativa **TableMappings** proprietà.</span><span class="sxs-lookup"><span data-stu-id="17438-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="17438-104">Oggetto **DataTableMapping** fornisce un mapping master tra i dati restituiti <xref:System.Data.DataTable>da una query su un'origine dati e un oggetto .</span><span class="sxs-lookup"><span data-stu-id="17438-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="17438-105">Il **DataTableMapping** nome al posto del **DataTable** nome al **Fill** metodo il **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="17438-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="17438-106">Nell'esempio seguente viene creato un **oggetto DataTableMapping** denominato **AuthorsMapping** per la tabella **Authors.**</span><span class="sxs-lookup"><span data-stu-id="17438-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="17438-107">Oggetto **DataTableMapping** consente di utilizzare nomi di colonna in un **DataTable** diversi da quelli nel database.</span><span class="sxs-lookup"><span data-stu-id="17438-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="17438-108">Il **DataAdapter** utilizza il mapping in modo che corrisponda alle colonne quando la tabella viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="17438-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="17438-109">Se non si specifica un **TableName** o un nome **DataTableMapping** quando si chiama il metodo **Fill** o **Update** di **DataAdapter**, **DataAdapter** cerca un **DataTableMapping** denominato "Table".</span><span class="sxs-lookup"><span data-stu-id="17438-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="17438-110">Se tale **DataTableMapping** non esiste, il **TableName** del **DataTable** è "Table".</span><span class="sxs-lookup"><span data-stu-id="17438-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="17438-111">È possibile specificare un valore predefinito **DataTableMapping** creando un **DataTableMapping** con il nome "Table".</span><span class="sxs-lookup"><span data-stu-id="17438-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="17438-112">Esempio di codice seguente crea un <xref:System.Data.Common> **DataTableMapping** (dallo spazio dei nomi) e lo rende il mapping predefinito per il **DataAdapter** specificato denominandolo "Table".</span><span class="sxs-lookup"><span data-stu-id="17438-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="17438-113">Nell'esempio viene quindi eseguito il mapping delle colonne della prima tabella del risultato della query (la tabella <xref:System.Data.DataSet> **Customers** del database **Northwind)** a un set di nomi più descrittivi nella tabella Northwind **Customers** della sezione .</span><span class="sxs-lookup"><span data-stu-id="17438-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="17438-114">Per le colonne di cui non viene eseguito il mapping, viene usato il nome della colonna nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="17438-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
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
  
 <span data-ttu-id="17438-115">In situazioni più avanzate, è possibile decidere che si desidera che lo stesso **DataAdapter** supporti il caricamento di tabelle diverse con mapping diversi.</span><span class="sxs-lookup"><span data-stu-id="17438-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="17438-116">A tale scopo, è sufficiente aggiungere ulteriori **DataTableMapping** oggetti.</span><span class="sxs-lookup"><span data-stu-id="17438-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="17438-117">Quando il **Fill** metodo viene passata un'istanza di un **DataSet** e un **DataTableMapping** nome, se esiste un mapping con tale nome viene utilizzato; in caso contrario, viene utilizzato un **oggetto DataTable** con tale nome.</span><span class="sxs-lookup"><span data-stu-id="17438-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="17438-118">Negli esempi seguenti viene creato un **DataTableMapping** con un nome **Customers** e un nome **DataTable** **BizTalkSchema**.</span><span class="sxs-lookup"><span data-stu-id="17438-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="17438-119">Nell'esempio viene quindi eseguito il mapping delle righe restituite dall'istruzione SELECT a **BizTalkSchema** **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="17438-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
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
> <span data-ttu-id="17438-120">Se non viene indicato il nome della colonna di origine per il mapping di una colonna o il nome della tabella di origine per il mapping di una tabella, vengono generati automaticamente nomi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="17438-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="17438-121">Se non viene fornita alcuna colonna di origine per un mapping di colonna, al mapping di colonna viene assegnato un nome predefinito incrementale **di SourceColumn** *N,* a partire da **SourceColumn1**.</span><span class="sxs-lookup"><span data-stu-id="17438-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="17438-122">Se non viene fornito alcun nome di tabella di origine per un mapping di tabella, al mapping delle tabelle viene assegnato un nome predefinito incrementale **SourceTable** *N*, a partire da **SourceTable1**.</span><span class="sxs-lookup"><span data-stu-id="17438-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17438-123">È consigliabile evitare la convenzione di denominazione di **SourceColumn** *N* per un mapping di colonna o **SourceTable** *N* per un mapping di tabella, poiché il nome fornito potrebbe entrare in conflitto con un nome di mapping di colonna predefinito esistente in **ColumnMappingCollection** o nel nome del mapping di tabella in **DataTableMappingCollection**.</span><span class="sxs-lookup"><span data-stu-id="17438-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="17438-124">Se il nome specificato esiste già, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="17438-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="17438-125">Gestione di più set di risultati</span><span class="sxs-lookup"><span data-stu-id="17438-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="17438-126">Se **SelectCommand** restituisce più tabelle, **Fill** genera automaticamente nomi di tabella con valori incrementali per le tabelle nel **DataSet**, a partire dal nome della tabella specificata e continuando nel formato **NomeTabella** *N*, a partire da **NomeTabella1**.</span><span class="sxs-lookup"><span data-stu-id="17438-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="17438-127">È possibile utilizzare i mapping delle tabelle per eseguire il mapping del nome della tabella generata automaticamente a un nome che si desidera specificare per la tabella nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="17438-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="17438-128">Ad esempio, per un **SelectCommand** che restituisce due tabelle, **Customers** e **Orders**, eseguire la seguente chiamata a **Fill**.</span><span class="sxs-lookup"><span data-stu-id="17438-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 <span data-ttu-id="17438-129">Nel **DataSet**: **Customers** e **Customers1**vengono create due tabelle.</span><span class="sxs-lookup"><span data-stu-id="17438-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="17438-130">È possibile utilizzare i mapping di tabella per assicurarsi che la seconda tabella sia denominata **Orders** anziché **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="17438-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="17438-131">A tale scopo, eseguire il mapping della tabella di origine di **Customers1** alla tabella **DataSet** **Orders**, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="17438-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a><span data-ttu-id="17438-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17438-132">See also</span></span>

- [<span data-ttu-id="17438-133">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="17438-133">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="17438-134">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="17438-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="17438-135">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="17438-135">ADO.NET Overview</span></span>](ado-net-overview.md)
