---
title: Deduzione di relazioni
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 4c9c13453e4a830fcda337e8163649ba6491a995
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785367"
---
# <a name="inferring-relationships"></a><span data-ttu-id="4c89a-102">Deduzione di relazioni</span><span class="sxs-lookup"><span data-stu-id="4c89a-102">Inferring Relationships</span></span>
<span data-ttu-id="4c89a-103">Se a un elemento inferito come tabella è associato un elemento figlio a sua volta inferito come tabella, tra le due tabelle verrà creato un tipo <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="4c89a-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="4c89a-104">Una nuova colonna con nome **ParentTableName_Id** verrà aggiunta sia alla tabella creata per l'elemento padre che alla tabella creata per l'elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="4c89a-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="4c89a-105">La proprietà **ColumnMapping** della colonna Identity verrà impostata su **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="4c89a-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="4c89a-106">La colonna sarà una chiave primaria a incremento automatico per la tabella padre e verrà utilizzata per la **DataRelation** tra le due tabelle.</span><span class="sxs-lookup"><span data-stu-id="4c89a-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="4c89a-107">Il tipo di dati della colonna Identity aggiunta sarà **System. Int32**, a differenza del tipo di dati di tutte le altre colonne inferite, ovvero **System. String**.</span><span class="sxs-lookup"><span data-stu-id="4c89a-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="4c89a-108">Verrà <xref:System.Data.ForeignKeyConstraint> creato anche un oggetto con **DeleteRule** = **Cascade** usando la nuova colonna in entrambe le tabelle padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="4c89a-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="4c89a-109">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="4c89a-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="4c89a-110">Dal processo di inferenza verranno prodotte due tabelle: **Element1** e **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="4c89a-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="4c89a-111">La tabella **Element1** includerà due colonne: **Element1_Id** e **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="4c89a-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="4c89a-112">La proprietà **ColumnMapping** della colonna **Element1_Id** verrà impostata su **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="4c89a-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="4c89a-113">La proprietà **ColumnMapping** della colonna **ChildElement2** verrà impostata su **MappingType. Element**.</span><span class="sxs-lookup"><span data-stu-id="4c89a-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="4c89a-114">La colonna **Element1_Id** verrà impostata come chiave primaria della tabella **Element1** .</span><span class="sxs-lookup"><span data-stu-id="4c89a-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="4c89a-115">La tabella **ChildElement1** includerà tre colonne: **attr1**, **attr2** e **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="4c89a-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="4c89a-116">La proprietà **ColumnMapping** per le colonne **attr1** e **attr2** verrà impostata su **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="4c89a-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="4c89a-117">La proprietà **ColumnMapping** della colonna **Element1_Id** verrà impostata su **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="4c89a-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="4c89a-118">Verranno creati un oggetto **DataRelation** e **ForeignKeyConstraint** usando le colonne **Element1_Id** di entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="4c89a-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="4c89a-119">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="4c89a-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="4c89a-120">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="4c89a-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="4c89a-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="4c89a-121">Element1_Id</span></span>|<span data-ttu-id="4c89a-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="4c89a-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="4c89a-123">0</span><span class="sxs-lookup"><span data-stu-id="4c89a-123">0</span></span>|<span data-ttu-id="4c89a-124">Text2</span><span class="sxs-lookup"><span data-stu-id="4c89a-124">Text2</span></span>|  
  
 <span data-ttu-id="4c89a-125">**tavolo:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="4c89a-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="4c89a-126">attr1</span><span class="sxs-lookup"><span data-stu-id="4c89a-126">attr1</span></span>|<span data-ttu-id="4c89a-127">attr2</span><span class="sxs-lookup"><span data-stu-id="4c89a-127">attr2</span></span>|<span data-ttu-id="4c89a-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="4c89a-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="4c89a-129">value1</span><span class="sxs-lookup"><span data-stu-id="4c89a-129">value1</span></span>|<span data-ttu-id="4c89a-130">value2</span><span class="sxs-lookup"><span data-stu-id="4c89a-130">value2</span></span>|<span data-ttu-id="4c89a-131">0</span><span class="sxs-lookup"><span data-stu-id="4c89a-131">0</span></span>|  
  
 <span data-ttu-id="4c89a-132">**DataRelation** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="4c89a-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="4c89a-133">**ParentTable** Element1</span><span class="sxs-lookup"><span data-stu-id="4c89a-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="4c89a-134">**ParentColumn** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="4c89a-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="4c89a-135">**ChildTable** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="4c89a-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="4c89a-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="4c89a-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="4c89a-137">**Annidati** True</span><span class="sxs-lookup"><span data-stu-id="4c89a-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="4c89a-138">**ForeignKeyConstraint** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="4c89a-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="4c89a-139">**Colonna** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="4c89a-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="4c89a-140">**ParentTable** Element1</span><span class="sxs-lookup"><span data-stu-id="4c89a-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="4c89a-141">**ChildTable** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="4c89a-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="4c89a-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="4c89a-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="4c89a-143">**AcceptRejectRule:** Nessuna</span><span class="sxs-lookup"><span data-stu-id="4c89a-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c89a-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c89a-144">See also</span></span>

- [<span data-ttu-id="4c89a-145">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="4c89a-145">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="4c89a-146">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="4c89a-146">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="4c89a-147">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="4c89a-147">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="4c89a-148">Annidamento di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="4c89a-148">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="4c89a-149">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="4c89a-149">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="4c89a-150">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="4c89a-150">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="4c89a-151">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4c89a-151">ADO.NET Overview</span></span>](../ado-net-overview.md)
