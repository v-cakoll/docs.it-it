---
title: Limitazioni all'inferenza
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 308d2ffdd9e2cb16626861e25613657f341a4ccb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076243"
---
# <a name="inference-limitations"></a><span data-ttu-id="a3c73-102">Limitazioni all'inferenza</span><span class="sxs-lookup"><span data-stu-id="a3c73-102">Inference Limitations</span></span>
<span data-ttu-id="a3c73-103">Il processo di inferenza di uno schema di un tipo <xref:System.Data.DataSet> da un documento XML può fornire come risultato diversi schemi a seconda degli elementi XML presenti in ogni documento.</span><span class="sxs-lookup"><span data-stu-id="a3c73-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="a3c73-104">Si considerino ad esempio i seguenti documenti XML:</span><span class="sxs-lookup"><span data-stu-id="a3c73-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="a3c73-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="a3c73-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a3c73-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="a3c73-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a3c73-107">Nel caso di "Document1", il processo di inferenza produce una **set di dati** denominato "DocumentElement" e una tabella denominata "Element1", poiché "Element1" è un elemento ripetuto.</span><span class="sxs-lookup"><span data-stu-id="a3c73-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="a3c73-108">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a3c73-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a3c73-109">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="a3c73-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a3c73-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="a3c73-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="a3c73-111">Text1</span><span class="sxs-lookup"><span data-stu-id="a3c73-111">Text1</span></span>|  
|<span data-ttu-id="a3c73-112">Text2</span><span class="sxs-lookup"><span data-stu-id="a3c73-112">Text2</span></span>|  
  
 <span data-ttu-id="a3c73-113">Tuttavia, per "Document2", il processo di inferenza produce una **set di dati** denominato "NewDataSet" e una tabella denominata "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="a3c73-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="a3c73-114">"Element1" viene inferito come colonna in quanto privo di attributi o elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="a3c73-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="a3c73-115">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="a3c73-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="a3c73-116">**tavolo:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a3c73-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="a3c73-117">Element1</span><span class="sxs-lookup"><span data-stu-id="a3c73-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="a3c73-118">Text1</span><span class="sxs-lookup"><span data-stu-id="a3c73-118">Text1</span></span>|  
  
 <span data-ttu-id="a3c73-119">È possibile che lo scopo di tali documenti XML fosse la creazione dello stesso schema, ma il processo di inferenza consente di produrre risultati molto diversi in base agli elementi contenuti in ogni documento.</span><span class="sxs-lookup"><span data-stu-id="a3c73-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="a3c73-120">Per evitare le discrepanze che possono verificarsi durante la generazione dello schema da un documento XML, è consigliabile specificare in modo esplicito uno schema tramite il linguaggio XML Schema definition (XSD) o XML-Data Reduced (XDR) durante il caricamento di un **set di dati** da STRINGA XML.</span><span class="sxs-lookup"><span data-stu-id="a3c73-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="a3c73-121">Per altre informazioni su come specificare in modo esplicito un **set di dati** dello schema con uno Schema XML, vedere [derivazione struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="a3c73-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c73-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3c73-122">See also</span></span>

- [<span data-ttu-id="a3c73-123">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="a3c73-123">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="a3c73-124">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="a3c73-124">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="a3c73-125">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="a3c73-125">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="a3c73-126">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="a3c73-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="a3c73-127">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="a3c73-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="a3c73-128">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="a3c73-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
