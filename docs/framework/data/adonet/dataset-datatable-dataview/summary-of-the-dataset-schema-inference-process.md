---
title: Riepilogo del processo di inferenza dello schema dataset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 63ab866785f1fea66ed72fa17589a5be790fcdaa
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="7ec54-102">Riepilogo del processo di inferenza dello schema dataset</span><span class="sxs-lookup"><span data-stu-id="7ec54-102">Summary of the DataSet Schema Inference Process</span></span>
<span data-ttu-id="7ec54-103">Il processo di inferenza determina innanzitutto, sulla base del documento XML, quali elementi verranno inferiti come tabelle.</span><span class="sxs-lookup"><span data-stu-id="7ec54-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="7ec54-104">Sulla base delle rimanenti informazioni XML, il processo di inferenza consente quindi di determinare le colonne per tali tabelle.</span><span class="sxs-lookup"><span data-stu-id="7ec54-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="7ec54-105">Nel caso di tabelle annidate, gli oggetti <xref:System.Data.DataRelation> e <xref:System.Data.ForeignKeyConstraint> vengono generati dal processo di inferenza.</span><span class="sxs-lookup"><span data-stu-id="7ec54-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="7ec54-106">Di seguito viene riportato un breve riepilogo delle regole di inferenza:</span><span class="sxs-lookup"><span data-stu-id="7ec54-106">Following is a brief summary of inference rules:</span></span>  
  
-   <span data-ttu-id="7ec54-107">Gli elementi a cui sono associati attributi vengono inferiti come tabelle.</span><span class="sxs-lookup"><span data-stu-id="7ec54-107">Elements that have attributes are inferred as tables.</span></span>  
  
-   <span data-ttu-id="7ec54-108">Gli elementi a cui sono associati elementi figlio vengono inferiti come tabelle.</span><span class="sxs-lookup"><span data-stu-id="7ec54-108">Elements that have child elements are inferred as tables.</span></span>  
  
-   <span data-ttu-id="7ec54-109">Gli elementi ripetuti vengono inferiti come tabella singola.</span><span class="sxs-lookup"><span data-stu-id="7ec54-109">Elements that repeat are inferred as a single table.</span></span>  
  
-   <span data-ttu-id="7ec54-110">Se all'elemento del documento, o radice, non sono associati attributi ed elementi figlio da inferire come colonne, tale elemento viene inferito come un tipo <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="7ec54-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="7ec54-111">In caso contrario, l'elemento del documento viene inferito come tabella.</span><span class="sxs-lookup"><span data-stu-id="7ec54-111">Otherwise, the document element is inferred as a table.</span></span>  
  
-   <span data-ttu-id="7ec54-112">Gli attributi vengono inferiti come colonne.</span><span class="sxs-lookup"><span data-stu-id="7ec54-112">Attributes are inferred as columns.</span></span>  
  
-   <span data-ttu-id="7ec54-113">Gli elementi a cui non sono associati attributi o elementi figlio e che non si ripetono vengono inferiti come colonne.</span><span class="sxs-lookup"><span data-stu-id="7ec54-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
-   <span data-ttu-id="7ec54-114">Per gli elementi che vengono inferiti come tabelle annidate all'interno di altri elementi inferiti come tabelle, nidificate **DataRelation** viene creato tra due tabelle.</span><span class="sxs-lookup"><span data-stu-id="7ec54-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="7ec54-115">Una nuova colonna di chiave primaria denominata **TableName_Id** viene aggiunta a entrambe le tabelle e utilizzato per il **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="7ec54-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="7ec54-116">Oggetto **ForeignKeyConstraint** viene creato tra due tabelle utilizzando il **TableName_Id** colonna.</span><span class="sxs-lookup"><span data-stu-id="7ec54-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
-   <span data-ttu-id="7ec54-117">Per gli elementi che vengono inferiti come tabelle e contenenti testo ma non gli elementi figlio, una nuova colonna denominata **TableName_Text** viene creato per il testo di ognuno degli elementi.</span><span class="sxs-lookup"><span data-stu-id="7ec54-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="7ec54-118">Se un elemento viene inferito come tabella e dispone di testo, ma a tale elemento sono associati anche elementi figlio, il testo verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="7ec54-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec54-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ec54-119">See Also</span></span>  
 [<span data-ttu-id="7ec54-120">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="7ec54-120">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="7ec54-121">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="7ec54-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="7ec54-122">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="7ec54-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="7ec54-123">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="7ec54-123">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="7ec54-124">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="7ec54-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="7ec54-125">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="7ec54-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
