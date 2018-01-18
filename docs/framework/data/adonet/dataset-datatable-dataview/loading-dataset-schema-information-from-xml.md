---
title: Caricamento delle informazioni dello schema di dataset da XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8b814715782710994f18163ccfcd3db342199145
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="b1e37-102">Caricamento delle informazioni dello schema di dataset da XML</span><span class="sxs-lookup"><span data-stu-id="b1e37-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="b1e37-103">Lo schema di un <xref:System.Data.DataSet> (relative tabelle, colonne, relazioni e vincoli) possono essere definiti a livello di codice creati il **riempimento** o **FillSchema** metodi di un <xref:System.Data.Common.DataAdapter>, o caricato da un Documento XML.</span><span class="sxs-lookup"><span data-stu-id="b1e37-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="b1e37-104">Per caricare **set di dati** informazioni sullo schema da un documento XML, è possibile utilizzare il **ReadXmlSchema** o **InferXmlSchema** metodo il **setdidati**.</span><span class="sxs-lookup"><span data-stu-id="b1e37-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="b1e37-105">**ReadXmlSchema** consente di caricare o inferire **set di dati** informazioni sullo schema dal documento contenente schema XML Schema definition language (XSD) o un documento XML con XML Schema inline.</span><span class="sxs-lookup"><span data-stu-id="b1e37-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="b1e37-106">**InferXmlSchema** consente di inferire lo schema dal documento XML, ignorando alcuni spazi dei nomi XML specificato.</span><span class="sxs-lookup"><span data-stu-id="b1e37-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1e37-107">Ordine delle tabelle in un **DataSet** potrebbero non essere mantenute quando si utilizza servizi Web o la serializzazione XML per trasferire un **DataSet** che è stato creato in memoria usando costrutti XSD (ad esempio relazioni annidate).</span><span class="sxs-lookup"><span data-stu-id="b1e37-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="b1e37-108">Pertanto, il destinatario del **DataSet** non deve dipendere ordine delle tabelle in questo caso.</span><span class="sxs-lookup"><span data-stu-id="b1e37-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="b1e37-109">Tuttavia, nella tabella di ordinamento viene sempre mantenuto se lo schema del **DataSet** trasferiti è stato letto dal file XSD anziché essere creato in memoria.</span><span class="sxs-lookup"><span data-stu-id="b1e37-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="b1e37-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="b1e37-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="b1e37-111">Per caricare lo schema di un **DataSet** da un documento XML senza caricare alcun dato, è possibile utilizzare il **ReadXmlSchema** metodo il **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="b1e37-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="b1e37-112">**ReadXmlSchema** crea **DataSet** schema definito tramite schema XML Schema definition language (XSD).</span><span class="sxs-lookup"><span data-stu-id="b1e37-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="b1e37-113">Il **ReadXmlSchema** metodo accetta un unico argomento di un nome di file, un flusso o un **XmlReader** contenente il documento XML da caricare.</span><span class="sxs-lookup"><span data-stu-id="b1e37-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="b1e37-114">È possibile che nel documento XML sia contenuto solo lo schema, oppure che in tale documento sia contenuto lo schema inline con elementi XML contenenti dati.</span><span class="sxs-lookup"><span data-stu-id="b1e37-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="b1e37-115">Per informazioni dettagliate sulla scrittura di uno schema inline come XML Schema, vedere [derivazione struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="b1e37-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="b1e37-116">Se il documento XML passato a **ReadXmlSchema** non contiene alcuna informazione sullo schema inline, **ReadXmlSchema** verrà dedotto automaticamente dagli elementi nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="b1e37-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="b1e37-117">Se il **DataSet** contiene già uno schema, lo schema corrente verrà esteso mediante l'aggiunta di nuove tabelle se non esiste già.</span><span class="sxs-lookup"><span data-stu-id="b1e37-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="b1e37-118">Nelle tabelle esistenti non verranno aggiunte nuove colonne.</span><span class="sxs-lookup"><span data-stu-id="b1e37-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="b1e37-119">Se una colonna da aggiungere già esiste nel **DataSet** ma non è un tipo incompatibile con la colonna trovato nel XML, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b1e37-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="b1e37-120">Per informazioni dettagliate su come **ReadXmlSchema** deduce uno schema da un documento XML, vedere [inferenza struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b1e37-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="b1e37-121">Anche se **ReadXmlSchema** consente di caricare o inferire solo lo schema di un **set di dati**, **ReadXml** metodo il **set di dati** di caricare o inferire sia lo schema e i dati contenuti nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="b1e37-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="b1e37-122">Per ulteriori informazioni, vedere [durante il caricamento di un set di dati da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b1e37-122">For more information, see [Loading a DataSet from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="b1e37-123">Gli esempi di codice seguente viene illustrato come caricare un **DataSet** schema da un documento o flusso XML.</span><span class="sxs-lookup"><span data-stu-id="b1e37-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="b1e37-124">Nel primo esempio viene passato a un nome di file XML Schema di **ReadXmlSchema** metodo.</span><span class="sxs-lookup"><span data-stu-id="b1e37-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="b1e37-125">Il secondo esempio viene illustrato un **System.IO**.</span><span class="sxs-lookup"><span data-stu-id="b1e37-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As System.IO.StreamReader = New System.IO.StreamReader ("schema.xsd");  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema(xmlStream)  
xmlStream.Close()  
```  
  
```csharp  
System.IO.StreamReader xmlStream = new System.IO.StreamReader("schema.xsd");  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema(xmlStream);  
xmlStream.Close();  
```  
  
## <a name="inferxmlschema"></a><span data-ttu-id="b1e37-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="b1e37-126">InferXmlSchema</span></span>  
 <span data-ttu-id="b1e37-127">È anche possibile indicare il **DataSet** dedurre lo schema da un documento XML usando il **InferXmlSchema** metodo il **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="b1e37-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="b1e37-128">**InferXmlSchema** funziona esattamente come eseguire entrambe le operazioni **ReadXml** con un **XmlReadMode** di **InferSchema** (carica i dati, nonché inferenza dello schema) e  **ReadXmlSchema** se il documento letto è presente alcuno schema inline.</span><span class="sxs-lookup"><span data-stu-id="b1e37-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="b1e37-129">Tuttavia, **InferXmlSchema** fornisce funzionalità aggiuntive di consentono di specificare particolare spazi dei nomi XML verrà ignorato durante l'inferenza dello schema.</span><span class="sxs-lookup"><span data-stu-id="b1e37-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="b1e37-130">**InferXmlSchema** accetta due argomenti obbligatori: il percorso del documento XML, specificato da un nome di file, un flusso o un **XmlReader**; e una matrice di stringhe degli spazi dei nomi XML verrà ignorato dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="b1e37-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="b1e37-131">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="b1e37-131">For example, consider the following XML:</span></span>  
  
```xml  
<NewDataSet xmlns:od="urn:schemas-microsoft-com:officedata">  
<Categories>  
  <CategoryID od:adotype="3">1</CategoryID>   
  <CategoryName od:maxLength="15" od:adotype="130">Beverages</CategoryName>   
  <Description od:adotype="203">Soft drinks and teas</Description>   
</Categories>  
<Products>  
  <ProductID od:adotype="20">1</ProductID>   
  <ReorderLevel od:adotype="3">10</ReorderLevel>   
  <Discontinued od:adotype="11">0</Discontinued>   
</Products>  
</NewDataSet>  
```  
  
 <span data-ttu-id="b1e37-132">A causa di attributi specificati per gli elementi nel documento XML precedente, sia il **ReadXmlSchema** (metodo) e **ReadXml** metodo con un **XmlReadMode** di **InferSchema** creeranno tabelle per ogni elemento nel documento: **categorie**, **CategoryID**, **CategoryName**, **Descrizione**, **prodotti**, **ProductID**, **ReorderLevel**, e **sospeso**.</span><span class="sxs-lookup"><span data-stu-id="b1e37-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="b1e37-133">(Per ulteriori informazioni, vedere [inferenza struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) Tuttavia, una struttura più appropriata, è possibile creare solo la **categorie** e **prodotti** tabelle e quindi creare **CategoryID**, **CategoryName** , e **descrizione** colonne il **categorie** tabella, e **ProductID**, **ReorderLevel**, e **Discontinued** colonne il **prodotti** tabella.</span><span class="sxs-lookup"><span data-stu-id="b1e37-133">(For more information, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="b1e37-134">Per assicurarsi che lo schema inferito ignora gli attributi specificati negli elementi XML, utilizzare il **InferXmlSchema** (metodo) e specificare lo spazio dei nomi XML per **officedata** venga ignorato, come illustrato di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b1e37-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1e37-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1e37-135">See Also</span></span>  
 [<span data-ttu-id="b1e37-136">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="b1e37-136">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="b1e37-137">Derivazione della struttura relazionale di DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="b1e37-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="b1e37-138">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="b1e37-138">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="b1e37-139">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="b1e37-139">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="b1e37-140">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="b1e37-140">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="b1e37-141">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="b1e37-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
