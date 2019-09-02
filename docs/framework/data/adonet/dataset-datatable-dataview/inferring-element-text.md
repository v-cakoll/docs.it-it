---
title: Deduzione del testo dell'elemento
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: d8d64c0cbb0aecf736a54fa6816e286ab7efa191
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203537"
---
# <a name="inferring-element-text"></a><span data-ttu-id="17158-102">Deduzione del testo dell'elemento</span><span class="sxs-lookup"><span data-stu-id="17158-102">Inferring Element Text</span></span>
<span data-ttu-id="17158-103">Se un elemento contiene testo e non ha elementi figlio da inferire come tabelle, ad esempio elementi con attributi o elementi ripetuti, viene aggiunta una nuova colonna con il nome **TableName_Text** alla tabella dedotta per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="17158-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="17158-104">Il testo contenuto nell'elemento viene aggiunto a una riga della tabella e archiviato nella nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="17158-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="17158-105">La proprietà **ColumnMapping** della nuova colonna verrà impostata su **MappingType. simpleContent**.</span><span class="sxs-lookup"><span data-stu-id="17158-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="17158-106">Ad esempio, si consideri il seguente codice XML.</span><span class="sxs-lookup"><span data-stu-id="17158-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="17158-107">Il processo di inferenza produrrà una tabella denominata **Element1** con due colonne: **attr1** e **Element1_Text**.</span><span class="sxs-lookup"><span data-stu-id="17158-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="17158-108">La proprietà **ColumnMapping** della colonna **attr1** verrà impostata su **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="17158-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="17158-109">La proprietà **ColumnMapping** della colonna **Element1_Text** verrà impostata su **MappingType. simpleContent**.</span><span class="sxs-lookup"><span data-stu-id="17158-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="17158-110">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="17158-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="17158-111">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="17158-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="17158-112">attr1</span><span class="sxs-lookup"><span data-stu-id="17158-112">attr1</span></span>|<span data-ttu-id="17158-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="17158-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="17158-114">value1</span><span class="sxs-lookup"><span data-stu-id="17158-114">value1</span></span>|<span data-ttu-id="17158-115">Text1</span><span class="sxs-lookup"><span data-stu-id="17158-115">Text1</span></span>|  
  
 <span data-ttu-id="17158-116">Se in un elemento è presente del testo ma a tale elemento sono associati anche elementi figlio contenenti testo, alla tabella non verrà aggiunta alcuna colonna in cui archiviare il testo contenuto nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="17158-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="17158-117">Il testo contenuto nell'elemento verrà ignorato e il testo degli elementi figlio viene incluso in una riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="17158-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="17158-118">Ad esempio, si consideri il seguente codice XML.</span><span class="sxs-lookup"><span data-stu-id="17158-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="17158-119">Il processo di inferenza produrrà una tabella denominata **Element1** con una colonna denominata **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="17158-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="17158-120">Il testo per l'elemento **ChildElement1** verrà incluso in una riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="17158-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="17158-121">Il testo rimanente verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="17158-121">The other text will be ignored.</span></span> <span data-ttu-id="17158-122">La proprietà **ColumnMapping** della colonna **ChildElement1** verrà impostata su **MappingType. Element**.</span><span class="sxs-lookup"><span data-stu-id="17158-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="17158-123">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="17158-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="17158-124">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="17158-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="17158-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="17158-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="17158-126">Text2</span><span class="sxs-lookup"><span data-stu-id="17158-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17158-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17158-127">See also</span></span>

- [<span data-ttu-id="17158-128">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="17158-128">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="17158-129">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="17158-129">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="17158-130">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="17158-130">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="17158-131">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="17158-131">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="17158-132">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="17158-132">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="17158-133">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="17158-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
