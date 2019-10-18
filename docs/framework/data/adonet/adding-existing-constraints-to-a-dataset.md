---
title: Aggiunta di vincoli esistenti a un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 267d6489d39f86fc06b35de8cf30dad74f501b0b
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523231"
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="88647-102">Aggiunta di vincoli esistenti a un dataset</span><span class="sxs-lookup"><span data-stu-id="88647-102">Adding Existing Constraints to a DataSet</span></span>

<span data-ttu-id="88647-103">Il metodo **Fill** di **DataAdapter** compila un <xref:System.Data.DataSet> solo con le colonne e le righe della tabella di un'origine dati. Sebbene i vincoli siano comunemente impostati dall'origine dati, il metodo **Fill** non aggiunge le informazioni sullo schema al **set** di dati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="88647-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="88647-104">Per popolare un **set** di dati con informazioni sui vincoli PRIMARY KEY esistenti da un'origine dati, è possibile chiamare il metodo **FillSchema** di **DataAdapter**oppure impostare la proprietà **MissingSchemaAction** di **DataAdapter** . per **AddWithKey** prima di chiamare **Fill**.</span><span class="sxs-lookup"><span data-stu-id="88647-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="88647-105">In questo modo si garantisce che i vincoli PRIMARY KEY nel **set** di dati corrispondano a quelli dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="88647-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="88647-106">Le informazioni sui vincoli di chiave esterna non sono incluse e devono essere create in modo esplicito, come illustrato nei [vincoli DataTable](./dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="88647-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](./dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
<span data-ttu-id="88647-107">L'aggiunta di informazioni sullo schema a un **set** di dati prima di compilarlo con i dati garantisce che i vincoli PRIMARY KEY siano inclusi con gli oggetti <xref:System.Data.DataTable> nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="88647-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="88647-108">Di conseguenza, quando vengono effettuate chiamate aggiuntive per il riempimento del **set** di dati, le informazioni sulla colonna chiave primaria vengono usate per trovare una corrispondenza tra le nuove righe dell'origine dati e le righe correnti in ogni **DataTable**e i dati correnti delle tabelle vengono sovrascritti con i dati del origine dati.</span><span class="sxs-lookup"><span data-stu-id="88647-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="88647-109">Senza le informazioni sullo schema, le nuove righe dall'origine dati vengono accodate al **DataSet**, ottenendo righe duplicate.</span><span class="sxs-lookup"><span data-stu-id="88647-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88647-110">Se una colonna in un'origine dati viene identificata come incremento automatico, il metodo **FillSchema** o il metodo **Fill** con un oggetto **MissingSchemaAction** di **AddWithKey**, crea una **DataColumn** con una proprietà **AutoIncrement** impostare su `true`.</span><span class="sxs-lookup"><span data-stu-id="88647-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="88647-111">Tuttavia, sarà necessario impostare manualmente i valori **AutoIncrementStep** e **AutoIncrementSeed** .</span><span class="sxs-lookup"><span data-stu-id="88647-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="88647-112">Per altre informazioni sulle colonne a incremento automatico, vedere [creazione di colonne AutoIncrement](./dataset-datatable-dataview/creating-autoincrement-columns.md).</span><span class="sxs-lookup"><span data-stu-id="88647-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](./dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
<span data-ttu-id="88647-113">L'uso di **FillSchema** o dell'impostazione di **MissingSchemaAction** su **AddWithKey** richiede un'elaborazione aggiuntiva nell'origine dati per determinare le informazioni sulla colonna chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="88647-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="88647-114">Questa ulteriore elaborazione può ridurre le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="88647-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="88647-115">Se le informazioni sulla chiave primaria sono note in fase di progettazione, è consigliabile specificare la colonna o le colonne della chiave primaria in modo esplicito per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="88647-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="88647-116">Per informazioni sull'impostazione esplicita delle informazioni sulla chiave primaria per una tabella, vedere [definizione di chiavi primarie](./dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="88647-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](./dataset-datatable-dataview/defining-primary-keys.md).</span></span>
  
<span data-ttu-id="88647-117">Nell'esempio di codice seguente viene illustrato come aggiungere informazioni sullo schema a un **DataSet** utilizzando **FillSchema**:</span><span class="sxs-lookup"><span data-stu-id="88647-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**:</span></span>
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
<span data-ttu-id="88647-118">Nell'esempio di codice seguente viene illustrato come aggiungere informazioni sullo schema a un **DataSet** utilizzando la proprietà **MissingSchemaAction. AddWithKey** del metodo **Fill** :</span><span class="sxs-lookup"><span data-stu-id="88647-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method:</span></span>
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="88647-119">Gestione di più set di risultati</span><span class="sxs-lookup"><span data-stu-id="88647-119">Handling multiple result sets</span></span>  

<span data-ttu-id="88647-120">Se **DataAdapter** rileva più set di risultati restituiti da **SelectCommand**, creerà più tabelle nel **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="88647-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="88647-121">Alle tabelle verrà assegnato un nome predefinito incrementale in base zero della **tabella** *N*, a partire dalla **tabella** anziché da "Table0".</span><span class="sxs-lookup"><span data-stu-id="88647-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="88647-122">Se un nome di tabella viene passato come argomento al metodo **FillSchema** , alle tabelle verrà assegnato un nome incrementale in base zero di **TableName** *N*, a partire da **TableName** anziché da "TableName0".</span><span class="sxs-lookup"><span data-stu-id="88647-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88647-123">Se viene chiamato il metodo **FillSchema** dell'oggetto **OleDbDataAdapter** per un comando che restituisce più set di risultati, vengono restituite solo le informazioni sullo schema del primo set di risultati.</span><span class="sxs-lookup"><span data-stu-id="88647-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="88647-124">Quando si restituiscono informazioni sullo schema per più set di risultati utilizzando **OleDbDataAdapter**, è consigliabile specificare un **MissingSchemaAction** di **AddWithKey** e ottenere le informazioni sullo schema durante la chiamata al **riempimento** Metodo.</span><span class="sxs-lookup"><span data-stu-id="88647-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88647-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88647-125">See also</span></span>

- [<span data-ttu-id="88647-126">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="88647-126">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="88647-127">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="88647-127">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="88647-128">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="88647-128">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="88647-129">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="88647-129">ADO.NET Overview</span></span>](ado-net-overview.md)
