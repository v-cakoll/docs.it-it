---
title: Riepilogo del processo di inferenza dello schema dataset
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: b0dd22412ddda86aa2883a26353abb1516a94e17
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785951"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="47a38-102">Riepilogo del processo di inferenza dello schema dataset</span><span class="sxs-lookup"><span data-stu-id="47a38-102">Summary of the DataSet Schema Inference Process</span></span>
<span data-ttu-id="47a38-103">Il processo di inferenza determina innanzitutto, sulla base del documento XML, quali elementi verranno inferiti come tabelle.</span><span class="sxs-lookup"><span data-stu-id="47a38-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="47a38-104">Sulla base delle rimanenti informazioni XML, il processo di inferenza consente quindi di determinare le colonne per tali tabelle.</span><span class="sxs-lookup"><span data-stu-id="47a38-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="47a38-105">Nel caso di tabelle annidate, gli oggetti <xref:System.Data.DataRelation> e <xref:System.Data.ForeignKeyConstraint> vengono generati dal processo di inferenza.</span><span class="sxs-lookup"><span data-stu-id="47a38-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="47a38-106">Di seguito viene riportato un breve riepilogo delle regole di inferenza:</span><span class="sxs-lookup"><span data-stu-id="47a38-106">Following is a brief summary of inference rules:</span></span>  
  
- <span data-ttu-id="47a38-107">Gli elementi a cui sono associati attributi vengono inferiti come tabelle.</span><span class="sxs-lookup"><span data-stu-id="47a38-107">Elements that have attributes are inferred as tables.</span></span>  
  
- <span data-ttu-id="47a38-108">Gli elementi a cui sono associati elementi figlio vengono inferiti come tabelle.</span><span class="sxs-lookup"><span data-stu-id="47a38-108">Elements that have child elements are inferred as tables.</span></span>  
  
- <span data-ttu-id="47a38-109">Gli elementi ripetuti vengono inferiti come tabella singola.</span><span class="sxs-lookup"><span data-stu-id="47a38-109">Elements that repeat are inferred as a single table.</span></span>  
  
- <span data-ttu-id="47a38-110">Se all'elemento del documento, o radice, non sono associati attributi ed elementi figlio da inferire come colonne, tale elemento viene inferito come un tipo <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="47a38-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="47a38-111">In caso contrario, l'elemento del documento viene inferito come tabella.</span><span class="sxs-lookup"><span data-stu-id="47a38-111">Otherwise, the document element is inferred as a table.</span></span>  
  
- <span data-ttu-id="47a38-112">Gli attributi vengono inferiti come colonne.</span><span class="sxs-lookup"><span data-stu-id="47a38-112">Attributes are inferred as columns.</span></span>  
  
- <span data-ttu-id="47a38-113">Gli elementi a cui non sono associati attributi o elementi figlio e che non si ripetono vengono inferiti come colonne.</span><span class="sxs-lookup"><span data-stu-id="47a38-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
- <span data-ttu-id="47a38-114">Per gli elementi inferiti come tabelle nidificate all'interno di altri elementi inferiti come tabelle, viene creata una **DataRelation** annidata tra le due tabelle.</span><span class="sxs-lookup"><span data-stu-id="47a38-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="47a38-115">Una nuova colonna chiave primaria denominata **TableName_Id** viene aggiunta a entrambe le tabelle e utilizzata da **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="47a38-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="47a38-116">Viene creato un **vincolo ForeignKeyConstraint** tra le due tabelle usando la colonna **TableName_Id** .</span><span class="sxs-lookup"><span data-stu-id="47a38-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
- <span data-ttu-id="47a38-117">Per gli elementi inferiti come tabelle e che contengono testo ma privi di elementi figlio, viene creata una nuova colonna denominata **TableName_Text** per il testo di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="47a38-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="47a38-118">Se un elemento viene inferito come tabella e dispone di testo, ma a tale elemento sono associati anche elementi figlio, il testo verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="47a38-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a38-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47a38-119">See also</span></span>

- [<span data-ttu-id="47a38-120">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="47a38-120">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="47a38-121">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="47a38-121">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="47a38-122">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="47a38-122">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="47a38-123">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="47a38-123">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="47a38-124">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="47a38-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="47a38-125">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="47a38-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
