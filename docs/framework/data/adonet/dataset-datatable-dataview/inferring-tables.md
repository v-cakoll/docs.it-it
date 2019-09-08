---
title: Deduzione di tabelle
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 52ffd3fe90eb491dd01acf8538276cc828fdb309
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784489"
---
# <a name="inferring-tables"></a><span data-ttu-id="d3f4a-102">Deduzione di tabelle</span><span class="sxs-lookup"><span data-stu-id="d3f4a-102">Inferring Tables</span></span>
<span data-ttu-id="d3f4a-103">Durante l'inferenza di uno schema per un tipo <xref:System.Data.DataSet> da un documento XML, ADO.NET determina innanzitutto quali elementi XML rappresentano tabelle.</span><span class="sxs-lookup"><span data-stu-id="d3f4a-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="d3f4a-104">Le strutture XML seguenti generano una tabella per lo schema del **set di dati** :</span><span class="sxs-lookup"><span data-stu-id="d3f4a-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="d3f4a-105">Elementi con attributi</span><span class="sxs-lookup"><span data-stu-id="d3f4a-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="d3f4a-106">Elementi con elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d3f4a-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="d3f4a-107">Elementi ripetuti</span><span class="sxs-lookup"><span data-stu-id="d3f4a-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="d3f4a-108">Elementi con attributi</span><span class="sxs-lookup"><span data-stu-id="d3f4a-108">Elements with Attributes</span></span>  
 <span data-ttu-id="d3f4a-109">Gli elementi in cui sono stati specificati degli attributi daranno come risultato delle tabelle inferite.</span><span class="sxs-lookup"><span data-stu-id="d3f4a-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="d3f4a-110">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="d3f4a-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="d3f4a-111">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="d3f4a-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="d3f4a-112">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d3f4a-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="d3f4a-113">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="d3f4a-114">attr1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-114">attr1</span></span>|<span data-ttu-id="d3f4a-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="d3f4a-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="d3f4a-116">value1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-116">value1</span></span>||  
|<span data-ttu-id="d3f4a-117">value2</span><span class="sxs-lookup"><span data-stu-id="d3f4a-117">value2</span></span>|<span data-ttu-id="d3f4a-118">Text1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="d3f4a-119">Elementi con elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d3f4a-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="d3f4a-120">Gli elementi a cui sono associati elementi figlio daranno come risultato delle tabelle inferite.</span><span class="sxs-lookup"><span data-stu-id="d3f4a-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="d3f4a-121">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="d3f4a-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="d3f4a-122">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="d3f4a-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="d3f4a-123">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d3f4a-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="d3f4a-124">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="d3f4a-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="d3f4a-126">Text1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-126">Text1</span></span>|  
  
 <span data-ttu-id="d3f4a-127">L'elemento del documento, o elemento radice, dà come risultato una tabella inferita nel caso in cui a tale elemento siano associati attributi o elementi figlio che vengono inferiti come colonne.</span><span class="sxs-lookup"><span data-stu-id="d3f4a-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="d3f4a-128">Se l'elemento del documento non ha attributi e nessun elemento figlio da inferire come colonne, l'elemento viene dedotto come un set di **dati**.</span><span class="sxs-lookup"><span data-stu-id="d3f4a-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="d3f4a-129">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="d3f4a-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="d3f4a-130">Il processo di inferenza produce una tabella denominata "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="d3f4a-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="d3f4a-131">**DataSet** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="d3f4a-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="d3f4a-132">**tavolo:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d3f4a-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="d3f4a-133">Element1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-133">Element1</span></span>|<span data-ttu-id="d3f4a-134">Element2</span><span class="sxs-lookup"><span data-stu-id="d3f4a-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="d3f4a-135">Text1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-135">Text1</span></span>|<span data-ttu-id="d3f4a-136">Text2</span><span class="sxs-lookup"><span data-stu-id="d3f4a-136">Text2</span></span>|  
  
 <span data-ttu-id="d3f4a-137">Si consideri in alternativa il seguente elemento XML:</span><span class="sxs-lookup"><span data-stu-id="d3f4a-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="d3f4a-138">Il processo di inferenza produce un **set di dati** denominato "DocumentElement" contenente una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="d3f4a-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="d3f4a-139">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d3f4a-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="d3f4a-140">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="d3f4a-141">attr1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-141">attr1</span></span>|<span data-ttu-id="d3f4a-142">attr2</span><span class="sxs-lookup"><span data-stu-id="d3f4a-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="d3f4a-143">value1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-143">value1</span></span>|<span data-ttu-id="d3f4a-144">value2</span><span class="sxs-lookup"><span data-stu-id="d3f4a-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="d3f4a-145">Elementi ripetuti</span><span class="sxs-lookup"><span data-stu-id="d3f4a-145">Repeating Elements</span></span>  
 <span data-ttu-id="d3f4a-146">Gli elementi ripetuti danno come risultato una singola tabella inferita.</span><span class="sxs-lookup"><span data-stu-id="d3f4a-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="d3f4a-147">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="d3f4a-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="d3f4a-148">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="d3f4a-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="d3f4a-149">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d3f4a-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="d3f4a-150">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="d3f4a-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="d3f4a-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="d3f4a-152">Text1</span><span class="sxs-lookup"><span data-stu-id="d3f4a-152">Text1</span></span>|  
|<span data-ttu-id="d3f4a-153">Text2</span><span class="sxs-lookup"><span data-stu-id="d3f4a-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3f4a-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3f4a-154">See also</span></span>

- [<span data-ttu-id="d3f4a-155">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="d3f4a-155">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="d3f4a-156">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="d3f4a-156">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="d3f4a-157">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="d3f4a-157">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="d3f4a-158">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="d3f4a-158">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="d3f4a-159">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="d3f4a-159">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="d3f4a-160">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d3f4a-160">ADO.NET Overview</span></span>](../ado-net-overview.md)
