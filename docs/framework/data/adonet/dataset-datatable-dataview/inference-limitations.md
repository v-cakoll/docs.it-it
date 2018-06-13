---
title: Limitazioni all'inferenza
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: b3ad1e66a6a1a4cb2a2aab7b2f86f38e5c784876
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760050"
---
# <a name="inference-limitations"></a><span data-ttu-id="b422c-102">Limitazioni all'inferenza</span><span class="sxs-lookup"><span data-stu-id="b422c-102">Inference Limitations</span></span>
<span data-ttu-id="b422c-103">Il processo di inferenza di uno schema di un tipo <xref:System.Data.DataSet> da un documento XML può fornire come risultato diversi schemi a seconda degli elementi XML presenti in ogni documento.</span><span class="sxs-lookup"><span data-stu-id="b422c-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="b422c-104">Si considerino ad esempio i seguenti documenti XML:</span><span class="sxs-lookup"><span data-stu-id="b422c-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="b422c-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="b422c-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="b422c-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="b422c-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="b422c-107">Nel caso di "Document1", il processo di inferenza produce una **DataSet** denominato "DocumentElement" e una tabella denominata "Element1", poiché "Element1" è un elemento ripetuto.</span><span class="sxs-lookup"><span data-stu-id="b422c-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="b422c-108">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b422c-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="b422c-109">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="b422c-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="b422c-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="b422c-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="b422c-111">Text1</span><span class="sxs-lookup"><span data-stu-id="b422c-111">Text1</span></span>|  
|<span data-ttu-id="b422c-112">Text2</span><span class="sxs-lookup"><span data-stu-id="b422c-112">Text2</span></span>|  
  
 <span data-ttu-id="b422c-113">Tuttavia, per "Document2", il processo di inferenza produce una **DataSet** denominato "NewDataSet" e una tabella denominata "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="b422c-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="b422c-114">"Element1" viene inferito come colonna in quanto privo di attributi o elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="b422c-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="b422c-115">**Set di dati:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="b422c-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="b422c-116">**Tabella:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b422c-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="b422c-117">Element1</span><span class="sxs-lookup"><span data-stu-id="b422c-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="b422c-118">Text1</span><span class="sxs-lookup"><span data-stu-id="b422c-118">Text1</span></span>|  
  
 <span data-ttu-id="b422c-119">È possibile che lo scopo di tali documenti XML fosse la creazione dello stesso schema, ma il processo di inferenza consente di produrre risultati molto diversi in base agli elementi contenuti in ogni documento.</span><span class="sxs-lookup"><span data-stu-id="b422c-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="b422c-120">Per evitare eventuali discrepanze nella generazione di schema da un documento XML, è consigliabile specificare in modo esplicito uno schema mediante il linguaggio XML Schema definition (XSD) o (XML-Data Reduced) durante il caricamento di un **DataSet** da XML.</span><span class="sxs-lookup"><span data-stu-id="b422c-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="b422c-121">Per ulteriori informazioni su come specificare in modo esplicito un **DataSet** schema con uno Schema XML, vedere [derivazione struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="b422c-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b422c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b422c-122">See Also</span></span>  
 [<span data-ttu-id="b422c-123">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="b422c-123">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="b422c-124">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="b422c-124">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="b422c-125">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="b422c-125">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="b422c-126">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="b422c-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="b422c-127">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="b422c-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="b422c-128">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="b422c-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
