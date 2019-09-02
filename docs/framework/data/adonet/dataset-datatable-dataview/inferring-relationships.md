---
title: Deduzione di relazioni
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 92a4953dc7f5119ffbf171ff2a7bf5b58e896638
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204765"
---
# <a name="inferring-relationships"></a><span data-ttu-id="eab63-102">Deduzione di relazioni</span><span class="sxs-lookup"><span data-stu-id="eab63-102">Inferring Relationships</span></span>
<span data-ttu-id="eab63-103">Se a un elemento inferito come tabella è associato un elemento figlio a sua volta inferito come tabella, tra le due tabelle verrà creato un tipo <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="eab63-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="eab63-104">Una nuova colonna con nome **ParentTableName_Id** verrà aggiunta sia alla tabella creata per l'elemento padre che alla tabella creata per l'elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="eab63-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="eab63-105">La proprietà **ColumnMapping** della colonna Identity verrà impostata su **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="eab63-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="eab63-106">La colonna sarà una chiave primaria a incremento automatico per la tabella padre e verrà utilizzata per la DataRelation tra le due tabelle.</span><span class="sxs-lookup"><span data-stu-id="eab63-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="eab63-107">Il tipo di dati della colonna Identity aggiunta sarà **System. Int32**, a differenza del tipo di dati di tutte le altre colonne inferite, ovvero **System. String**.</span><span class="sxs-lookup"><span data-stu-id="eab63-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="eab63-108">Verrà <xref:System.Data.ForeignKeyConstraint> creato anche un oggetto con **DeleteRule** = **Cascade** usando la nuova colonna in entrambe le tabelle padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="eab63-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="eab63-109">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="eab63-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="eab63-110">Dal processo di inferenza verranno prodotte due tabelle: **Element1** e **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="eab63-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="eab63-111">La tabella **Element1** includerà due colonne: **Element1_Id** e **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="eab63-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="eab63-112">La proprietà **ColumnMapping** della colonna **Element1_Id** verrà impostata su **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="eab63-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="eab63-113">La proprietà **ColumnMapping** della colonna **ChildElement2** verrà impostata su **MappingType. Element**.</span><span class="sxs-lookup"><span data-stu-id="eab63-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="eab63-114">La colonna **Element1_Id** verrà impostata come chiave primaria della tabella **Element1** .</span><span class="sxs-lookup"><span data-stu-id="eab63-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="eab63-115">La tabella **ChildElement1** includerà tre colonne: **attr1**, **attr2** e **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="eab63-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="eab63-116">La proprietà **ColumnMapping** per le colonne **attr1** e **attr2** verrà impostata su **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="eab63-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="eab63-117">La proprietà **ColumnMapping** della colonna **Element1_Id** verrà impostata su **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="eab63-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="eab63-118">Verranno creati un oggetto DataRelation e **ForeignKeyConstraint** usando le colonne **Element1_Id** di entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="eab63-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="eab63-119">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="eab63-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="eab63-120">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="eab63-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="eab63-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="eab63-121">Element1_Id</span></span>|<span data-ttu-id="eab63-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="eab63-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="eab63-123">0</span><span class="sxs-lookup"><span data-stu-id="eab63-123">0</span></span>|<span data-ttu-id="eab63-124">Text2</span><span class="sxs-lookup"><span data-stu-id="eab63-124">Text2</span></span>|  
  
 <span data-ttu-id="eab63-125">**tavolo:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="eab63-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="eab63-126">attr1</span><span class="sxs-lookup"><span data-stu-id="eab63-126">attr1</span></span>|<span data-ttu-id="eab63-127">attr2</span><span class="sxs-lookup"><span data-stu-id="eab63-127">attr2</span></span>|<span data-ttu-id="eab63-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="eab63-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="eab63-129">value1</span><span class="sxs-lookup"><span data-stu-id="eab63-129">value1</span></span>|<span data-ttu-id="eab63-130">value2</span><span class="sxs-lookup"><span data-stu-id="eab63-130">value2</span></span>|<span data-ttu-id="eab63-131">0</span><span class="sxs-lookup"><span data-stu-id="eab63-131">0</span></span>|  
  
 <span data-ttu-id="eab63-132">**DataRelation** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="eab63-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="eab63-133">**ParentTable** Element1</span><span class="sxs-lookup"><span data-stu-id="eab63-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="eab63-134">**ParentColumn** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="eab63-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="eab63-135">**ChildTable** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="eab63-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="eab63-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="eab63-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="eab63-137">**Annidati** True</span><span class="sxs-lookup"><span data-stu-id="eab63-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="eab63-138">**ForeignKeyConstraint** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="eab63-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="eab63-139">**Colonna** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="eab63-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="eab63-140">**ParentTable** Element1</span><span class="sxs-lookup"><span data-stu-id="eab63-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="eab63-141">**ChildTable** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="eab63-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="eab63-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="eab63-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="eab63-143">**AcceptRejectRule:** Nessuna</span><span class="sxs-lookup"><span data-stu-id="eab63-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eab63-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eab63-144">See also</span></span>

- [<span data-ttu-id="eab63-145">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="eab63-145">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="eab63-146">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="eab63-146">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="eab63-147">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="eab63-147">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="eab63-148">Annidamento di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="eab63-148">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="eab63-149">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="eab63-149">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="eab63-150">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="eab63-150">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="eab63-151">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="eab63-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
