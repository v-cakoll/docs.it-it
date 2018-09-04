---
title: Deduzione di tabelle
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 38709f91e01c7f85d9e8482bdd49bc0892121f09
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528172"
---
# <a name="inferring-tables"></a><span data-ttu-id="c893f-102">Deduzione di tabelle</span><span class="sxs-lookup"><span data-stu-id="c893f-102">Inferring Tables</span></span>
<span data-ttu-id="c893f-103">Durante l'inferenza di uno schema per un tipo <xref:System.Data.DataSet> da un documento XML, ADO.NET determina innanzitutto quali elementi XML rappresentano tabelle.</span><span class="sxs-lookup"><span data-stu-id="c893f-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="c893f-104">Le strutture XML seguente come risultato una tabella per la **set di dati** dello schema:</span><span class="sxs-lookup"><span data-stu-id="c893f-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
-   <span data-ttu-id="c893f-105">Elementi con attributi</span><span class="sxs-lookup"><span data-stu-id="c893f-105">Elements with attributes</span></span>  
  
-   <span data-ttu-id="c893f-106">Elementi con elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c893f-106">Elements with child elements</span></span>  
  
-   <span data-ttu-id="c893f-107">Elementi ripetuti</span><span class="sxs-lookup"><span data-stu-id="c893f-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="c893f-108">Elementi con attributi</span><span class="sxs-lookup"><span data-stu-id="c893f-108">Elements with Attributes</span></span>  
 <span data-ttu-id="c893f-109">Gli elementi in cui sono stati specificati degli attributi daranno come risultato delle tabelle inferite.</span><span class="sxs-lookup"><span data-stu-id="c893f-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="c893f-110">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="c893f-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c893f-111">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="c893f-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="c893f-112">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c893f-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="c893f-113">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="c893f-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="c893f-114">attr1</span><span class="sxs-lookup"><span data-stu-id="c893f-114">attr1</span></span>|<span data-ttu-id="c893f-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="c893f-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="c893f-116">value1</span><span class="sxs-lookup"><span data-stu-id="c893f-116">value1</span></span>||  
|<span data-ttu-id="c893f-117">value2</span><span class="sxs-lookup"><span data-stu-id="c893f-117">value2</span></span>|<span data-ttu-id="c893f-118">Text1</span><span class="sxs-lookup"><span data-stu-id="c893f-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="c893f-119">Elementi con elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c893f-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="c893f-120">Gli elementi a cui sono associati elementi figlio daranno come risultato delle tabelle inferite.</span><span class="sxs-lookup"><span data-stu-id="c893f-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="c893f-121">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="c893f-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c893f-122">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="c893f-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="c893f-123">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c893f-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="c893f-124">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="c893f-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="c893f-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="c893f-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="c893f-126">Text1</span><span class="sxs-lookup"><span data-stu-id="c893f-126">Text1</span></span>|  
  
 <span data-ttu-id="c893f-127">L'elemento del documento, o elemento radice, dà come risultato una tabella inferita nel caso in cui a tale elemento siano associati attributi o elementi figlio che vengono inferiti come colonne.</span><span class="sxs-lookup"><span data-stu-id="c893f-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="c893f-128">Se l'elemento documento presenta alcun attributo e nessun elemento figlio da inferire come colonne, l'elemento viene inferito come un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="c893f-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="c893f-129">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="c893f-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c893f-130">Il processo di inferenza produce una tabella denominata "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="c893f-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="c893f-131">**Set di dati:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="c893f-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="c893f-132">**Tabella:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c893f-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="c893f-133">Element1</span><span class="sxs-lookup"><span data-stu-id="c893f-133">Element1</span></span>|<span data-ttu-id="c893f-134">Element2</span><span class="sxs-lookup"><span data-stu-id="c893f-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="c893f-135">Text1</span><span class="sxs-lookup"><span data-stu-id="c893f-135">Text1</span></span>|<span data-ttu-id="c893f-136">Text2</span><span class="sxs-lookup"><span data-stu-id="c893f-136">Text2</span></span>|  
  
 <span data-ttu-id="c893f-137">Si consideri in alternativa il seguente elemento XML:</span><span class="sxs-lookup"><span data-stu-id="c893f-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c893f-138">Il processo di inferenza produce una **set di dati** denominata "DocumentElement" contenente una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="c893f-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="c893f-139">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c893f-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="c893f-140">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="c893f-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="c893f-141">attr1</span><span class="sxs-lookup"><span data-stu-id="c893f-141">attr1</span></span>|<span data-ttu-id="c893f-142">attr2</span><span class="sxs-lookup"><span data-stu-id="c893f-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="c893f-143">value1</span><span class="sxs-lookup"><span data-stu-id="c893f-143">value1</span></span>|<span data-ttu-id="c893f-144">value2</span><span class="sxs-lookup"><span data-stu-id="c893f-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="c893f-145">Elementi ripetuti</span><span class="sxs-lookup"><span data-stu-id="c893f-145">Repeating Elements</span></span>  
 <span data-ttu-id="c893f-146">Gli elementi ripetuti danno come risultato una singola tabella inferita.</span><span class="sxs-lookup"><span data-stu-id="c893f-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="c893f-147">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="c893f-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c893f-148">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="c893f-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="c893f-149">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c893f-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="c893f-150">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="c893f-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="c893f-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="c893f-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="c893f-152">Text1</span><span class="sxs-lookup"><span data-stu-id="c893f-152">Text1</span></span>|  
|<span data-ttu-id="c893f-153">Text2</span><span class="sxs-lookup"><span data-stu-id="c893f-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c893f-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c893f-154">See Also</span></span>  
 [<span data-ttu-id="c893f-155">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="c893f-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="c893f-156">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="c893f-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="c893f-157">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="c893f-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="c893f-158">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="c893f-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="c893f-159">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="c893f-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="c893f-160">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="c893f-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
