---
title: Limitazioni all'inferenza
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 10347abc5b01edb4ec6fbf97221d44f4bfb88f54
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784586"
---
# <a name="inference-limitations"></a><span data-ttu-id="6b8aa-102">Limitazioni all'inferenza</span><span class="sxs-lookup"><span data-stu-id="6b8aa-102">Inference Limitations</span></span>
<span data-ttu-id="6b8aa-103">Il processo di inferenza di uno schema di un tipo <xref:System.Data.DataSet> da un documento XML può fornire come risultato diversi schemi a seconda degli elementi XML presenti in ogni documento.</span><span class="sxs-lookup"><span data-stu-id="6b8aa-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="6b8aa-104">Si considerino ad esempio i seguenti documenti XML:</span><span class="sxs-lookup"><span data-stu-id="6b8aa-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="6b8aa-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="6b8aa-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="6b8aa-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="6b8aa-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="6b8aa-107">Per "Document1", il processo di inferenza produce un **set di dati** denominato "DocumentElement" e una tabella denominata "Element1", perché "Element1" è un elemento ripetuto.</span><span class="sxs-lookup"><span data-stu-id="6b8aa-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="6b8aa-108">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="6b8aa-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="6b8aa-109">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="6b8aa-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="6b8aa-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="6b8aa-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="6b8aa-111">Text1</span><span class="sxs-lookup"><span data-stu-id="6b8aa-111">Text1</span></span>|  
|<span data-ttu-id="6b8aa-112">Text2</span><span class="sxs-lookup"><span data-stu-id="6b8aa-112">Text2</span></span>|  
  
 <span data-ttu-id="6b8aa-113">Tuttavia, per "Document2", il processo di inferenza produce un **set di dati** denominato "NewDataSet" e una tabella denominata "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="6b8aa-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="6b8aa-114">"Element1" viene inferito come colonna in quanto privo di attributi o elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="6b8aa-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="6b8aa-115">**DataSet** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="6b8aa-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="6b8aa-116">**tavolo:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="6b8aa-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="6b8aa-117">Element1</span><span class="sxs-lookup"><span data-stu-id="6b8aa-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="6b8aa-118">Text1</span><span class="sxs-lookup"><span data-stu-id="6b8aa-118">Text1</span></span>|  
  
 <span data-ttu-id="6b8aa-119">È possibile che lo scopo di tali documenti XML fosse la creazione dello stesso schema, ma il processo di inferenza consente di produrre risultati molto diversi in base agli elementi contenuti in ogni documento.</span><span class="sxs-lookup"><span data-stu-id="6b8aa-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="6b8aa-120">Per evitare le discrepanze che possono verificarsi durante la generazione dello schema da un documento XML, è consigliabile specificare in modo esplicito uno schema utilizzando il linguaggio XSD (XML Schema Definition Language) o XDR (XML-Data Reduced) durante il caricamento di un **DataSet** da XML.</span><span class="sxs-lookup"><span data-stu-id="6b8aa-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="6b8aa-121">Per ulteriori informazioni su come specificare in modo esplicito uno schema del **set di dati** con XML Schema, vedere [derivazione della struttura relazionale di DataSet da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="6b8aa-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b8aa-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b8aa-122">See also</span></span>

- [<span data-ttu-id="6b8aa-123">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="6b8aa-123">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="6b8aa-124">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="6b8aa-124">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="6b8aa-125">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="6b8aa-125">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="6b8aa-126">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="6b8aa-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="6b8aa-127">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="6b8aa-127">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="6b8aa-128">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6b8aa-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
