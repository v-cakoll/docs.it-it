---
title: Deduzione di relazioni
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 7dc3fb0c6098d636e640aaf52b72a404c1486492
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47080039"
---
# <a name="inferring-relationships"></a><span data-ttu-id="38786-102">Deduzione di relazioni</span><span class="sxs-lookup"><span data-stu-id="38786-102">Inferring Relationships</span></span>
<span data-ttu-id="38786-103">Se a un elemento inferito come tabella è associato un elemento figlio a sua volta inferito come tabella, tra le due tabelle verrà creato un tipo <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="38786-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="38786-104">Una nuova colonna con il nome **ParentTableName_Id** verranno aggiunti alla tabella creata per l'elemento padre sia la tabella creata per l'elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="38786-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="38786-105">Il **ColumnMapping** della colonna identity verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="38786-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="38786-106">La colonna sarà una chiave primaria con incremento automatico per la tabella padre e verrà usata per il **DataRelation** tra le due tabelle.</span><span class="sxs-lookup"><span data-stu-id="38786-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="38786-107">Il tipo di dati della colonna identity aggiunta sarà **System.Int32**, a differenza del tipo di dati di tutte le altre colonne inferite, ovvero **System. String**.</span><span class="sxs-lookup"><span data-stu-id="38786-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="38786-108">Oggetto <xref:System.Data.ForeignKeyConstraint> con **DeleteRule** = **Cascade** verrà inoltre creato usando la nuova colonna nelle tabelle padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="38786-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="38786-109">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="38786-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="38786-110">Il processo di inferenza verrà prodotte due tabelle: **Element1** e **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="38786-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="38786-111">Il **Element1** tabella sarà presenti due colonne: **Element1_Id** e **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="38786-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="38786-112">Il **ColumnMapping** proprietà delle **Element1_Id** colonna verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="38786-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="38786-113">Il **ColumnMapping** proprietà delle **ChildElement2** colonna verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="38786-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="38786-114">Il **Element1_Id** verrà impostata come chiave primaria della colonna la **Element1** tabella.</span><span class="sxs-lookup"><span data-stu-id="38786-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="38786-115">Il **ChildElement1** tabella sarà presenti tre colonne: **attr1**, **attr2** e **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="38786-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="38786-116">Il **ColumnMapping** proprietà per il **attr1** e **attr2** colonne verranno impostate su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="38786-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="38786-117">Il **ColumnMapping** proprietà delle **Element1_Id** colonna verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="38786-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="38786-118">Oggetto **DataRelation** e **ForeignKeyConstraint** verrà creato utilizzando il **Element1_Id** colonne di entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="38786-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="38786-119">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="38786-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="38786-120">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="38786-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="38786-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="38786-121">Element1_Id</span></span>|<span data-ttu-id="38786-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="38786-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="38786-123">0</span><span class="sxs-lookup"><span data-stu-id="38786-123">0</span></span>|<span data-ttu-id="38786-124">Text2</span><span class="sxs-lookup"><span data-stu-id="38786-124">Text2</span></span>|  
  
 <span data-ttu-id="38786-125">**Tabella:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="38786-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="38786-126">attr1</span><span class="sxs-lookup"><span data-stu-id="38786-126">attr1</span></span>|<span data-ttu-id="38786-127">attr2</span><span class="sxs-lookup"><span data-stu-id="38786-127">attr2</span></span>|<span data-ttu-id="38786-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="38786-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="38786-129">value1</span><span class="sxs-lookup"><span data-stu-id="38786-129">value1</span></span>|<span data-ttu-id="38786-130">value2</span><span class="sxs-lookup"><span data-stu-id="38786-130">value2</span></span>|<span data-ttu-id="38786-131">0</span><span class="sxs-lookup"><span data-stu-id="38786-131">0</span></span>|  
  
 <span data-ttu-id="38786-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="38786-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="38786-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="38786-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="38786-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="38786-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="38786-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="38786-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="38786-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="38786-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="38786-137">**Annidati:** True</span><span class="sxs-lookup"><span data-stu-id="38786-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="38786-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="38786-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="38786-139">**Colonna:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="38786-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="38786-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="38786-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="38786-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="38786-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="38786-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="38786-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="38786-143">**AcceptRejectRule:** None</span><span class="sxs-lookup"><span data-stu-id="38786-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38786-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38786-144">See Also</span></span>  
 [<span data-ttu-id="38786-145">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="38786-145">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="38786-146">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="38786-146">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="38786-147">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="38786-147">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="38786-148">Annidamento di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="38786-148">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [<span data-ttu-id="38786-149">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="38786-149">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="38786-150">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="38786-150">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="38786-151">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="38786-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
