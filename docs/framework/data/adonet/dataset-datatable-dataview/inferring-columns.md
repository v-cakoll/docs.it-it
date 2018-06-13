---
title: Deduzione di colonne
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: da98bcbc4537e08a6f8565b36f8b84b476efd027
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761077"
---
# <a name="inferring-columns"></a><span data-ttu-id="089fb-102">Deduzione di colonne</span><span class="sxs-lookup"><span data-stu-id="089fb-102">Inferring Columns</span></span>
<span data-ttu-id="089fb-103">Una volta che ADO.NET ha determinato quali elementi di un documento XML devono essere inferiti come tabelle per un tipo <xref:System.Data.DataSet>, vengono inferite le colonne di tali tabelle.</span><span class="sxs-lookup"><span data-stu-id="089fb-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="089fb-104">ADO.NET 2.0 è stato introdotto un nuovo motore di inferenza dello schema che consente di inferire un tipo di dati fortemente tipizzati per ogni **simpleType** elemento.</span><span class="sxs-lookup"><span data-stu-id="089fb-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="089fb-105">Nelle versioni precedenti, il tipo di dati di un tipo derivato **simpleType** era sempre **xsd: String**.</span><span class="sxs-lookup"><span data-stu-id="089fb-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="089fb-106">Migrazione e compatibilità con versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="089fb-106">Migration and Backward Compatibility</span></span>  
 <span data-ttu-id="089fb-107">Il **ReadXml** metodo accetta un argomento di tipo **InferSchema**.</span><span class="sxs-lookup"><span data-stu-id="089fb-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="089fb-108">Tale argomento consente di specificare il comportamento di inferenza compatibile con versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="089fb-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="089fb-109">I valori disponibili per il **InferSchema** enumerazione vengono visualizzati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="089fb-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="089fb-110">Fornisce compatibilità con le versioni precedenti inferendo sempre un tipo semplice come <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="089fb-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="089fb-111">Inferisce un tipo di dati tipizzato in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="089fb-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="089fb-112">Viene generata un'eccezione se usato con un tipo <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="089fb-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="089fb-113">Ignora tutti gli schemi inline e legge i dati nello schema <xref:System.Data.DataSet> esistente.</span><span class="sxs-lookup"><span data-stu-id="089fb-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="089fb-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="089fb-114">Attributes</span></span>  
 <span data-ttu-id="089fb-115">Come definito in [inferenza di tabelle](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), un elemento con attributi verrà inferito come tabella.</span><span class="sxs-lookup"><span data-stu-id="089fb-115">As defined in [Inferring Tables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="089fb-116">Gli attributi di tale elemento verranno quindi inferiti come colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="089fb-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="089fb-117">Il **ColumnMapping** delle colonne verrà impostata su **MappingType. Attribute**, per assicurare che i nomi delle colonne verrà scritto come attributi se lo schema viene scritto in XML.</span><span class="sxs-lookup"><span data-stu-id="089fb-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="089fb-118">I valori degli attributi vengono archiviati in una riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="089fb-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="089fb-119">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="089fb-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="089fb-120">Il processo di inferenza genererà una tabella denominata **Element1** con due colonne, **attr1** e **attr2**.</span><span class="sxs-lookup"><span data-stu-id="089fb-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="089fb-121">Il **ColumnMapping** entrambe le colonne verrà impostata su **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="089fb-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="089fb-122">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="089fb-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="089fb-123">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="089fb-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="089fb-124">attr1</span><span class="sxs-lookup"><span data-stu-id="089fb-124">attr1</span></span>|<span data-ttu-id="089fb-125">attr2</span><span class="sxs-lookup"><span data-stu-id="089fb-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="089fb-126">value1</span><span class="sxs-lookup"><span data-stu-id="089fb-126">value1</span></span>|<span data-ttu-id="089fb-127">value2</span><span class="sxs-lookup"><span data-stu-id="089fb-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="089fb-128">Elementi privi di attributi o elementi figlio</span><span class="sxs-lookup"><span data-stu-id="089fb-128">Elements Without Attributes or Child Elements</span></span>  
 <span data-ttu-id="089fb-129">Se un elemento non dispone di elementi figlio o attributi, tale elemento verrà inferito come colonna.</span><span class="sxs-lookup"><span data-stu-id="089fb-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="089fb-130">Il **ColumnMapping** della colonna verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="089fb-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="089fb-131">Il testo degli elementi figlio è archiviato in una riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="089fb-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="089fb-132">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="089fb-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="089fb-133">Il processo di inferenza genererà una tabella denominata **Element1** con due colonne, **ChildElement1** e **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="089fb-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="089fb-134">Il **ColumnMapping** entrambe le colonne verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="089fb-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="089fb-135">**Set di dati:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="089fb-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="089fb-136">**Tabella:** Element1</span><span class="sxs-lookup"><span data-stu-id="089fb-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="089fb-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="089fb-137">ChildElement1</span></span>|<span data-ttu-id="089fb-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="089fb-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="089fb-139">Text1</span><span class="sxs-lookup"><span data-stu-id="089fb-139">Text1</span></span>|<span data-ttu-id="089fb-140">Text2</span><span class="sxs-lookup"><span data-stu-id="089fb-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="089fb-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="089fb-141">See Also</span></span>  
 [<span data-ttu-id="089fb-142">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="089fb-142">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="089fb-143">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="089fb-143">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="089fb-144">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="089fb-144">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="089fb-145">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="089fb-145">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="089fb-146">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="089fb-146">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="089fb-147">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="089fb-147">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
