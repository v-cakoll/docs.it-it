---
title: Caricamento delle informazioni dello schema di dataset da XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: b895ad59ed0ab2542ecdfb04b6db559e12edc55c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928384"
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="7b5c7-102">Caricamento delle informazioni dello schema di dataset da XML</span><span class="sxs-lookup"><span data-stu-id="7b5c7-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="7b5c7-103">Lo schema di un <xref:System.Data.DataSet> oggetto (le tabelle, le colonne, le relazioni e i vincoli) può essere definito a livello di codice, creato mediante i metodi <xref:System.Data.Common.DataAdapter> **Fill** o **FillSchema** di un oggetto o caricato da un documento XML.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="7b5c7-104">Per caricare le informazioni sullo schema del **set di dati** da un documento XML, è possibile usare il metodo **ReadXmlSchema** o **InferXmlSchema** del **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="7b5c7-105">**ReadXmlSchema** consente di caricare o dedurre le informazioni sullo schema del **set di dati** dal documento che contiene lo schema XSD (XML Schema Definition Language) o da un documento XML con XML Schema inline.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="7b5c7-106">**InferXmlSchema** consente di dedurre lo schema dal documento XML ignorando determinati spazi dei nomi XML specificati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b5c7-107">L'ordinamento delle tabelle in un **set di dati** potrebbe non essere mantenuto quando si utilizzano i servizi Web o la serializzazione XML per trasferire un **set di dati** creato in memoria utilizzando costrutti XSD, ad esempio relazioni annidate.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="7b5c7-108">Il destinatario del **set di dati** , pertanto, non deve dipendere dall'ordine delle tabelle in questo caso.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="7b5c7-109">Tuttavia, l'ordine delle tabelle viene sempre mantenuto se lo schema del **set di dati** trasferito è stato letto da file XSD anziché essere creato in memoria.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="7b5c7-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="7b5c7-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="7b5c7-111">Per caricare lo schema di un **DataSet** da un documento XML senza caricare dati, è possibile usare il metodo **ReadXmlSchema** del **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="7b5c7-112">**ReadXmlSchema** crea lo schema del **set di dati** definito utilizzando lo schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="7b5c7-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="7b5c7-113">Il metodo **ReadXmlSchema** accetta un solo argomento di un nome file, un flusso o un **XmlReader** che contiene il documento XML da caricare.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="7b5c7-114">È possibile che nel documento XML sia contenuto solo lo schema, oppure che in tale documento sia contenuto lo schema inline con elementi XML contenenti dati.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="7b5c7-115">Per informazioni dettagliate sulla scrittura di uno schema inline come XML Schema, vedere derivazione [della struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="7b5c7-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="7b5c7-116">Se il documento XML passato a **ReadXmlSchema** non contiene informazioni sullo schema inline, **ReadXmlSchema** dedurrà lo schema dagli elementi nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="7b5c7-117">Se il **set di dati** contiene già uno schema, lo schema corrente verrà esteso mediante l'aggiunta di nuove tabelle, se non esistono già.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="7b5c7-118">Nelle tabelle esistenti non verranno aggiunte nuove colonne.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="7b5c7-119">Se una colonna aggiunta esiste già nel set di **dati** ma dispone di un tipo incompatibile con la colonna trovata nel codice XML, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="7b5c7-120">Per informazioni dettagliate sul modo in cui **ReadXmlSchema** deduce uno schema da un documento XML, vedere [deduzione della struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7b5c7-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="7b5c7-121">Anche se **ReadXmlSchema** carica o deduce solo lo schema di un **set di dati**, il metodo **ReadXml** del **DataSet** carica o deduce sia lo schema che i dati contenuti nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="7b5c7-122">Per ulteriori informazioni, vedere [caricamento di un DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7b5c7-122">For more information, see [Loading a DataSet from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="7b5c7-123">Negli esempi di codice seguenti viene illustrato come caricare uno schema **DataSet** da un documento o flusso XML.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="7b5c7-124">Nel primo esempio viene illustrato come passare il nome di un file di XML Schema al metodo **ReadXmlSchema** .</span><span class="sxs-lookup"><span data-stu-id="7b5c7-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="7b5c7-125">Nel secondo esempio viene illustrato un oggetto **System. io. StreamReader**.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="7b5c7-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="7b5c7-126">InferXmlSchema</span></span>  
 <span data-ttu-id="7b5c7-127">È inoltre possibile indicare al **set di dati** di dedurre lo schema da un documento XML utilizzando il metodo **InferXmlSchema** del **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="7b5c7-128">**InferXmlSchema** funziona allo stesso modo di un oggetto **ReadXml** con un **XmlReadMode** di **InferSchema** (carica i dati e deduce lo schema) e **ReadXmlSchema** se il documento letto non contiene alcuno schema inline.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="7b5c7-129">Tuttavia, **InferXmlSchema** fornisce la funzionalità aggiuntiva che consente di specificare determinati spazi dei nomi XML da ignorare quando lo schema viene dedotto.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="7b5c7-130">**InferXmlSchema** accetta due argomenti obbligatori: la posizione del documento XML, specificata da un nome file, un flusso o un **XmlReader**; e una matrice di stringhe di spazi dei nomi XML che verranno ignorati dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="7b5c7-131">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="7b5c7-131">For example, consider the following XML:</span></span>  
  
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
  
 <span data-ttu-id="7b5c7-132">A causa degli attributi specificati per gli elementi nel documento XML precedente, sia il metodo **ReadXmlSchema** che il metodo **ReadXml** con **XmlReadMode** **InferSchema** creeranno tabelle per ogni elemento nel documento **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**e Discontinued.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="7b5c7-133">Per ulteriori informazioni, vedere [deduzione della struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md). Tuttavia, una struttura più appropriata consiste nel creare solo le tabelle Categories e Products, quindi creare le colonne **CategoryID**, **CategoryName**e **Description** nella tabella **Categories** eLe colonne ProductID, **ReorderLevel**e Discontinued nella tabella **Products** .</span><span class="sxs-lookup"><span data-stu-id="7b5c7-133">(For more information, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="7b5c7-134">Per assicurarsi che lo schema inferito ignori gli attributi specificati negli elementi XML, usare il metodo **InferXmlSchema** e specificare lo spazio dei nomi XML per **officedata** da ignorare, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b5c7-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b5c7-135">See also</span></span>

- [<span data-ttu-id="7b5c7-136">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="7b5c7-136">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="7b5c7-137">Derivazione della struttura relazionale di DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="7b5c7-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="7b5c7-138">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="7b5c7-138">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="7b5c7-139">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="7b5c7-139">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="7b5c7-140">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="7b5c7-140">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="7b5c7-141">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="7b5c7-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
