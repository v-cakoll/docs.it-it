---
title: Deduzione del testo dell'elemento
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 3fdd110a14ddfd6065ed552171a8d76ef64e2fb5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784545"
---
# <a name="inferring-element-text"></a><span data-ttu-id="62cc0-102">Deduzione del testo dell'elemento</span><span class="sxs-lookup"><span data-stu-id="62cc0-102">Inferring Element Text</span></span>
<span data-ttu-id="62cc0-103">Se un elemento contiene testo e non ha elementi figlio da inferire come tabelle, ad esempio elementi con attributi o elementi ripetuti, viene aggiunta una nuova colonna con il nome **TableName_Text** alla tabella dedotta per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="62cc0-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="62cc0-104">Il testo contenuto nell'elemento viene aggiunto a una riga della tabella e archiviato nella nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="62cc0-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="62cc0-105">La proprietà **ColumnMapping** della nuova colonna verrà impostata su **MappingType. simpleContent**.</span><span class="sxs-lookup"><span data-stu-id="62cc0-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="62cc0-106">Ad esempio, si consideri il seguente codice XML.</span><span class="sxs-lookup"><span data-stu-id="62cc0-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="62cc0-107">Il processo di inferenza produrrà una tabella denominata **Element1** con due colonne: **attr1** e **Element1_Text**.</span><span class="sxs-lookup"><span data-stu-id="62cc0-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="62cc0-108">La proprietà **ColumnMapping** della colonna **attr1** verrà impostata su **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="62cc0-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="62cc0-109">La proprietà **ColumnMapping** della colonna **Element1_Text** verrà impostata su **MappingType. simpleContent**.</span><span class="sxs-lookup"><span data-stu-id="62cc0-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="62cc0-110">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="62cc0-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="62cc0-111">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="62cc0-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="62cc0-112">attr1</span><span class="sxs-lookup"><span data-stu-id="62cc0-112">attr1</span></span>|<span data-ttu-id="62cc0-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="62cc0-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="62cc0-114">value1</span><span class="sxs-lookup"><span data-stu-id="62cc0-114">value1</span></span>|<span data-ttu-id="62cc0-115">Text1</span><span class="sxs-lookup"><span data-stu-id="62cc0-115">Text1</span></span>|  
  
 <span data-ttu-id="62cc0-116">Se in un elemento è presente del testo ma a tale elemento sono associati anche elementi figlio contenenti testo, alla tabella non verrà aggiunta alcuna colonna in cui archiviare il testo contenuto nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="62cc0-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="62cc0-117">Il testo contenuto nell'elemento verrà ignorato e il testo degli elementi figlio viene incluso in una riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="62cc0-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="62cc0-118">Ad esempio, si consideri il seguente codice XML.</span><span class="sxs-lookup"><span data-stu-id="62cc0-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="62cc0-119">Il processo di inferenza produrrà una tabella denominata **Element1** con una colonna denominata **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="62cc0-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="62cc0-120">Il testo per l'elemento **ChildElement1** verrà incluso in una riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="62cc0-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="62cc0-121">Il testo rimanente verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="62cc0-121">The other text will be ignored.</span></span> <span data-ttu-id="62cc0-122">La proprietà **ColumnMapping** della colonna **ChildElement1** verrà impostata su **MappingType. Element**.</span><span class="sxs-lookup"><span data-stu-id="62cc0-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="62cc0-123">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="62cc0-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="62cc0-124">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="62cc0-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="62cc0-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="62cc0-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="62cc0-126">Text2</span><span class="sxs-lookup"><span data-stu-id="62cc0-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62cc0-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62cc0-127">See also</span></span>

- [<span data-ttu-id="62cc0-128">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="62cc0-128">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="62cc0-129">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="62cc0-129">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="62cc0-130">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="62cc0-130">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="62cc0-131">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="62cc0-131">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="62cc0-132">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="62cc0-132">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="62cc0-133">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="62cc0-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
