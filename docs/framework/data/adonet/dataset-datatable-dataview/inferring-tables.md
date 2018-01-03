---
title: Deduzione di tabelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: dacf3518f77067a34b0da3a8e6438b813fca3912
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="inferring-tables"></a><span data-ttu-id="25858-102">Deduzione di tabelle</span><span class="sxs-lookup"><span data-stu-id="25858-102">Inferring Tables</span></span>
<span data-ttu-id="25858-103">Durante l'inferenza di uno schema per un tipo <xref:System.Data.DataSet> da un documento XML, ADO.NET determina innanzitutto quali elementi XML rappresentano tabelle.</span><span class="sxs-lookup"><span data-stu-id="25858-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="25858-104">Le seguenti strutture XML come risultato una tabella per la **DataSet** schema:</span><span class="sxs-lookup"><span data-stu-id="25858-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
-   <span data-ttu-id="25858-105">Elementi con attributi</span><span class="sxs-lookup"><span data-stu-id="25858-105">Elements with attributes</span></span>  
  
-   <span data-ttu-id="25858-106">Elementi con elementi figlio</span><span class="sxs-lookup"><span data-stu-id="25858-106">Elements with child elements</span></span>  
  
-   <span data-ttu-id="25858-107">Elementi ripetuti</span><span class="sxs-lookup"><span data-stu-id="25858-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="25858-108">Elementi con attributi</span><span class="sxs-lookup"><span data-stu-id="25858-108">Elements with Attributes</span></span>  
 <span data-ttu-id="25858-109">Gli elementi in cui sono stati specificati degli attributi daranno come risultato delle tabelle inferite.</span><span class="sxs-lookup"><span data-stu-id="25858-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="25858-110">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="25858-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="25858-111">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="25858-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="25858-112">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="25858-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="25858-113">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="25858-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="25858-114">attr1</span><span class="sxs-lookup"><span data-stu-id="25858-114">attr1</span></span>|<span data-ttu-id="25858-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="25858-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="25858-116">value1</span><span class="sxs-lookup"><span data-stu-id="25858-116">value1</span></span>||  
|<span data-ttu-id="25858-117">value2</span><span class="sxs-lookup"><span data-stu-id="25858-117">value2</span></span>|<span data-ttu-id="25858-118">Text1</span><span class="sxs-lookup"><span data-stu-id="25858-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="25858-119">Elementi con elementi figlio</span><span class="sxs-lookup"><span data-stu-id="25858-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="25858-120">Gli elementi a cui sono associati elementi figlio daranno come risultato delle tabelle inferite.</span><span class="sxs-lookup"><span data-stu-id="25858-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="25858-121">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="25858-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="25858-122">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="25858-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="25858-123">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="25858-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="25858-124">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="25858-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="25858-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="25858-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="25858-126">Text1</span><span class="sxs-lookup"><span data-stu-id="25858-126">Text1</span></span>|  
  
 <span data-ttu-id="25858-127">L'elemento del documento, o elemento radice, dà come risultato una tabella inferita nel caso in cui a tale elemento siano associati attributi o elementi figlio che vengono inferiti come colonne.</span><span class="sxs-lookup"><span data-stu-id="25858-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="25858-128">Se l'elemento del documento dispone di alcun attributo e non gli elementi figlio da inferire come colonne, l'elemento viene inferito come un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="25858-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="25858-129">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="25858-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="25858-130">Il processo di inferenza produce una tabella denominata "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="25858-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="25858-131">**Set di dati:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="25858-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="25858-132">**Tabella:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="25858-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="25858-133">Element1</span><span class="sxs-lookup"><span data-stu-id="25858-133">Element1</span></span>|<span data-ttu-id="25858-134">Element2</span><span class="sxs-lookup"><span data-stu-id="25858-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="25858-135">Text1</span><span class="sxs-lookup"><span data-stu-id="25858-135">Text1</span></span>|<span data-ttu-id="25858-136">Text2</span><span class="sxs-lookup"><span data-stu-id="25858-136">Text2</span></span>|  
  
 <span data-ttu-id="25858-137">Si consideri in alternativa il seguente elemento XML:</span><span class="sxs-lookup"><span data-stu-id="25858-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="25858-138">Il processo di inferenza produce una **DataSet** denominato "DocumentElement" contenente una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="25858-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="25858-139">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="25858-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="25858-140">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="25858-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="25858-141">attr1</span><span class="sxs-lookup"><span data-stu-id="25858-141">attr1</span></span>|<span data-ttu-id="25858-142">attr2</span><span class="sxs-lookup"><span data-stu-id="25858-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="25858-143">value1</span><span class="sxs-lookup"><span data-stu-id="25858-143">value1</span></span>|<span data-ttu-id="25858-144">value2</span><span class="sxs-lookup"><span data-stu-id="25858-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="25858-145">Elementi ripetuti</span><span class="sxs-lookup"><span data-stu-id="25858-145">Repeating Elements</span></span>  
 <span data-ttu-id="25858-146">Gli elementi ripetuti danno come risultato una singola tabella inferita.</span><span class="sxs-lookup"><span data-stu-id="25858-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="25858-147">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="25858-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="25858-148">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="25858-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="25858-149">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="25858-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="25858-150">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="25858-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="25858-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="25858-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="25858-152">Text1</span><span class="sxs-lookup"><span data-stu-id="25858-152">Text1</span></span>|  
|<span data-ttu-id="25858-153">Text2</span><span class="sxs-lookup"><span data-stu-id="25858-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25858-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25858-154">See Also</span></span>  
 [<span data-ttu-id="25858-155">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="25858-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="25858-156">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="25858-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="25858-157">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="25858-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="25858-158">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="25858-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="25858-159">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="25858-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="25858-160">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="25858-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
