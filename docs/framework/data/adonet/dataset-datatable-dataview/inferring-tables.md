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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2c00dd11d4d93e5d3b0e2f1c3b75765056a10cab
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-tables"></a><span data-ttu-id="12b01-102">Deduzione di tabelle</span><span class="sxs-lookup"><span data-stu-id="12b01-102">Inferring Tables</span></span>
<span data-ttu-id="12b01-103">Durante l'inferenza di uno schema per un tipo <xref:System.Data.DataSet> da un documento XML, ADO.NET determina innanzitutto quali elementi XML rappresentano tabelle.</span><span class="sxs-lookup"><span data-stu-id="12b01-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="12b01-104">Le seguenti strutture XML come risultato una tabella per la **DataSet** schema:</span><span class="sxs-lookup"><span data-stu-id="12b01-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
-   <span data-ttu-id="12b01-105">Elementi con attributi</span><span class="sxs-lookup"><span data-stu-id="12b01-105">Elements with attributes</span></span>  
  
-   <span data-ttu-id="12b01-106">Elementi con elementi figlio</span><span class="sxs-lookup"><span data-stu-id="12b01-106">Elements with child elements</span></span>  
  
-   <span data-ttu-id="12b01-107">Elementi ripetuti</span><span class="sxs-lookup"><span data-stu-id="12b01-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="12b01-108">Elementi con attributi</span><span class="sxs-lookup"><span data-stu-id="12b01-108">Elements with Attributes</span></span>  
 <span data-ttu-id="12b01-109">Gli elementi in cui sono stati specificati degli attributi daranno come risultato delle tabelle inferite.</span><span class="sxs-lookup"><span data-stu-id="12b01-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="12b01-110">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="12b01-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="12b01-111">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="12b01-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="12b01-112">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="12b01-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="12b01-113">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="12b01-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="12b01-114">attr1</span><span class="sxs-lookup"><span data-stu-id="12b01-114">attr1</span></span>|<span data-ttu-id="12b01-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="12b01-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="12b01-116">value1</span><span class="sxs-lookup"><span data-stu-id="12b01-116">value1</span></span>||  
|<span data-ttu-id="12b01-117">value2</span><span class="sxs-lookup"><span data-stu-id="12b01-117">value2</span></span>|<span data-ttu-id="12b01-118">Text1</span><span class="sxs-lookup"><span data-stu-id="12b01-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="12b01-119">Elementi con elementi figlio</span><span class="sxs-lookup"><span data-stu-id="12b01-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="12b01-120">Gli elementi a cui sono associati elementi figlio daranno come risultato delle tabelle inferite.</span><span class="sxs-lookup"><span data-stu-id="12b01-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="12b01-121">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="12b01-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="12b01-122">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="12b01-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="12b01-123">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="12b01-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="12b01-124">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="12b01-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="12b01-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="12b01-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="12b01-126">Text1</span><span class="sxs-lookup"><span data-stu-id="12b01-126">Text1</span></span>|  
  
 <span data-ttu-id="12b01-127">L'elemento del documento, o elemento radice, dà come risultato una tabella inferita nel caso in cui a tale elemento siano associati attributi o elementi figlio che vengono inferiti come colonne.</span><span class="sxs-lookup"><span data-stu-id="12b01-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="12b01-128">Se l'elemento del documento dispone di alcun attributo e non gli elementi figlio da inferire come colonne, l'elemento viene inferito come un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="12b01-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="12b01-129">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="12b01-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="12b01-130">Il processo di inferenza produce una tabella denominata "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="12b01-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="12b01-131">**Set di dati:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="12b01-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="12b01-132">**Tabella:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="12b01-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="12b01-133">Element1</span><span class="sxs-lookup"><span data-stu-id="12b01-133">Element1</span></span>|<span data-ttu-id="12b01-134">Element2</span><span class="sxs-lookup"><span data-stu-id="12b01-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="12b01-135">Text1</span><span class="sxs-lookup"><span data-stu-id="12b01-135">Text1</span></span>|<span data-ttu-id="12b01-136">Text2</span><span class="sxs-lookup"><span data-stu-id="12b01-136">Text2</span></span>|  
  
 <span data-ttu-id="12b01-137">Si consideri in alternativa il seguente elemento XML:</span><span class="sxs-lookup"><span data-stu-id="12b01-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="12b01-138">Il processo di inferenza produce una **DataSet** denominato "DocumentElement" contenente una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="12b01-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="12b01-139">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="12b01-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="12b01-140">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="12b01-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="12b01-141">attr1</span><span class="sxs-lookup"><span data-stu-id="12b01-141">attr1</span></span>|<span data-ttu-id="12b01-142">attr2</span><span class="sxs-lookup"><span data-stu-id="12b01-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="12b01-143">value1</span><span class="sxs-lookup"><span data-stu-id="12b01-143">value1</span></span>|<span data-ttu-id="12b01-144">value2</span><span class="sxs-lookup"><span data-stu-id="12b01-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="12b01-145">Elementi ripetuti</span><span class="sxs-lookup"><span data-stu-id="12b01-145">Repeating Elements</span></span>  
 <span data-ttu-id="12b01-146">Gli elementi ripetuti danno come risultato una singola tabella inferita.</span><span class="sxs-lookup"><span data-stu-id="12b01-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="12b01-147">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="12b01-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="12b01-148">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="12b01-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="12b01-149">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="12b01-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="12b01-150">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="12b01-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="12b01-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="12b01-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="12b01-152">Text1</span><span class="sxs-lookup"><span data-stu-id="12b01-152">Text1</span></span>|  
|<span data-ttu-id="12b01-153">Text2</span><span class="sxs-lookup"><span data-stu-id="12b01-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12b01-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12b01-154">See Also</span></span>  
 [<span data-ttu-id="12b01-155">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="12b01-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="12b01-156">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="12b01-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="12b01-157">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="12b01-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="12b01-158">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="12b01-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="12b01-159">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="12b01-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="12b01-160">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="12b01-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
