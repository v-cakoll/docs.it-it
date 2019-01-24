---
title: Aggiunta di vincoli esistenti a un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 39b1e9945a1cf6cd847fbe82c0b29e50f23bf785
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714149"
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="f7ad7-102">Aggiunta di vincoli esistenti a un dataset</span><span class="sxs-lookup"><span data-stu-id="f7ad7-102">Adding Existing Constraints to a DataSet</span></span>
<span data-ttu-id="f7ad7-103">Il **riempire** metodo per il **DataAdapter** riempie un <xref:System.Data.DataSet> solo con le colonne della tabella e le righe da un'origine dati; tuttavia i vincoli vengano in genere impostati dall'origine dati, il **riempire** metodo non aggiunge queste informazioni sullo schema per il **set di dati** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="f7ad7-104">Per popolare una **set di dati** con informazioni di vincolo di chiave primaria esistente da un'origine dati, è possibile chiamare il **FillSchema** metodo per il **DataAdapter**, o impostare il **MissingSchemaAction** proprietà delle **DataAdapter** al **AddWithKey** prima di chiamare **riempire**.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="f7ad7-105">In tal modo, la chiave primaria vincoli nel **set di dati** riflettano quelli nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="f7ad7-106">Informazioni sul vincolo di chiave esterna non è inclusi e deve essere creati in modo esplicito, come illustrato nella [vincoli DataTable](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="f7ad7-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="f7ad7-107">Aggiunta di informazioni sullo schema da un **set di dati** prima di compilarlo con i dati assicura che i vincoli di chiave primari siano inclusi con il <xref:System.Data.DataTable> gli oggetti nel **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="f7ad7-108">Di conseguenza, quando ulteriori chiamate per compilare il **set di dati** vengono eseguite, il database primario informazioni della colonna chiave viene usate per associare nuove righe dall'origine dati con le righe correnti in ogni **DataTable**e i dati correnti in le tabelle viene sovrascritto con i dati dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="f7ad7-109">Senza le informazioni sullo schema, vengono aggiunte le nuove righe dall'origine dati per il **set di dati**, generando righe duplicate.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7ad7-110">Se una colonna in un'origine dati viene identificata come con incremento automatico, il **FillSchema** metodo, o il **riempimento** metodo con un **MissingSchemaAction** di  **AddWithKey**, viene creata una **DataColumn** con un **AutoIncrement** impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="f7ad7-111">Tuttavia, è necessario impostare il **AutoIncrementStep** e **AutoIncrementSeed** valori manualmente.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="f7ad7-112">Per altre informazioni sulle colonne con incremento automatico, vedere [creazione di colonne AutoIncrement](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span><span class="sxs-lookup"><span data-stu-id="f7ad7-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
 <span data-ttu-id="f7ad7-113">Usando **FillSchema** impostazione o il **MissingSchemaAction** al **AddWithKey** necessaria un'elaborazione aggiuntiva nell'origine dati per determinare le informazioni di colonna chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="f7ad7-114">Questa ulteriore elaborazione può ridurre le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="f7ad7-115">Se le informazioni sulla chiave primaria sono note in fase di progettazione, è consigliabile specificare la colonna o le colonne della chiave primaria in modo esplicito per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="f7ad7-116">Per informazioni sull'impostazione esplicita delle informazioni sulla chiave primarie per una tabella, vedere [definizione di chiavi primarie](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="f7ad7-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="f7ad7-117">Esempio di codice seguente viene illustrato come aggiungere informazioni sullo schema da un **set di dati** utilizzando **FillSchema**.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 <span data-ttu-id="f7ad7-118">Esempio di codice seguente viene illustrato come aggiungere informazioni sullo schema da un **set di dati** usando la **MissingSchemaAction. AddWithKey** proprietà del **riempire** (metodo).</span><span class="sxs-lookup"><span data-stu-id="f7ad7-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="f7ad7-119">Gestione di più set di risultati</span><span class="sxs-lookup"><span data-stu-id="f7ad7-119">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="f7ad7-120">Se il **DataAdapter** rileva più set di risultati restituito dalle **SelectCommand**, verrà create più tabelle nel **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="f7ad7-121">Le tabelle viene assegnato un nome predefinito incrementale in base zero **tabella** *N*, che inizia con **tabella** anziché con "Table0".</span><span class="sxs-lookup"><span data-stu-id="f7ad7-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="f7ad7-122">Se un nome di tabella viene passato come argomento per il **FillSchema** metodo, le tabelle viene assegnato un nome incrementale in base zero del **NomeTabella** *N*, che inizia con **NomeTabella** anziché con "TableName0".</span><span class="sxs-lookup"><span data-stu-id="f7ad7-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7ad7-123">Se il **FillSchema** metodo per il **OleDbDataAdapter** oggetto viene chiamato per un comando che restituisce più set di risultati, vengono restituite solo le informazioni dello schema dal primo set di risultati.</span><span class="sxs-lookup"><span data-stu-id="f7ad7-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="f7ad7-124">Quando la restituzione di informazioni sullo schema per il risultato di più set mediante il **OleDbDataAdapter**, si consiglia di specificare una **MissingSchemaAction** dei **AddWithKey** e ottenere le informazioni sullo schema quando si chiama il **riempire** (metodo).</span><span class="sxs-lookup"><span data-stu-id="f7ad7-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ad7-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7ad7-125">See also</span></span>
- [<span data-ttu-id="f7ad7-126">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="f7ad7-126">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="f7ad7-127">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="f7ad7-127">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="f7ad7-128">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f7ad7-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="f7ad7-129">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="f7ad7-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
