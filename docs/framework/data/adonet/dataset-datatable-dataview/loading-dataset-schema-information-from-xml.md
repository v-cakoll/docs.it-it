---
title: Caricamento delle informazioni dello schema di dataset da XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 69994c546fea842ffef1c8c43d6d6f5bc35e0629
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151052"
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="02e7d-102">Caricamento delle informazioni dello schema di dataset da XML</span><span class="sxs-lookup"><span data-stu-id="02e7d-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="02e7d-103">Lo schema <xref:System.Data.DataSet> di un oggetto (tabelle, colonne, relazioni e vincoli) può essere definito <xref:System.Data.Common.DataAdapter>a livello di codice, creato dai metodi **Fill** o **FillSchema** di un oggetto , o caricato da un documento XML.</span><span class="sxs-lookup"><span data-stu-id="02e7d-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="02e7d-104">Per caricare le informazioni sullo schema **del DataSet** da un documento XML, è possibile utilizzare il **metodo ReadXmlSchema** o **InferXmlSchema** del **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="02e7d-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="02e7d-105">**ReadXmlSchema** consente di caricare o dedurre le informazioni sullo schema **del DataSet** dal documento contenente lo schema XSD (XML Schema Definition Language) o da un documento XML con schema XML inline.</span><span class="sxs-lookup"><span data-stu-id="02e7d-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="02e7d-106">**InferXmlSchema** consente di dedurre lo schema dal documento XML ignorando determinati spazi dei nomi XML specificati.</span><span class="sxs-lookup"><span data-stu-id="02e7d-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02e7d-107">L'ordinamento delle tabelle in un **DataSet** potrebbe non essere mantenuto quando si utilizzano servizi Web o la serializzazione XML per trasferire un **DataSet** creato in memoria utilizzando costrutti XSD (ad esempio relazioni annidate).</span><span class="sxs-lookup"><span data-stu-id="02e7d-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="02e7d-108">Pertanto, il destinatario del **DataSet** non deve dipendere dall'ordinamento delle tabelle in questo caso.</span><span class="sxs-lookup"><span data-stu-id="02e7d-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="02e7d-109">Tuttavia, l'ordine delle tabelle viene sempre mantenuto se lo schema del **DataSet** da trasferire è stato letto da file XSD, anziché essere creato in memoria.</span><span class="sxs-lookup"><span data-stu-id="02e7d-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="02e7d-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="02e7d-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="02e7d-111">Per caricare lo schema di un **DataSet** da un documento XML senza caricare dati, è possibile utilizzare il metodo **ReadXmlSchema** del **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="02e7d-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="02e7d-112">**ReadXmlSchema** crea lo schema **DataSet** definito utilizzando lo schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="02e7d-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="02e7d-113">Il **metodo ReadXmlSchema** accetta un singolo argomento di un nome file, un flusso o un **oggetto XmlReader** contenente il documento XML da caricare.</span><span class="sxs-lookup"><span data-stu-id="02e7d-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="02e7d-114">È possibile che nel documento XML sia contenuto solo lo schema, oppure che in tale documento sia contenuto lo schema inline con elementi XML contenenti dati.</span><span class="sxs-lookup"><span data-stu-id="02e7d-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="02e7d-115">Per informazioni dettagliate sulla scrittura dello schema inline come schema XML, vedere Derivazione della struttura relazionale del [DataSet dallo schema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="02e7d-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="02e7d-116">Se il documento XML passato a **ReadXmlSchema** non contiene informazioni sullo schema inline, **ReadXmlSchema** dedurrà lo schema dagli elementi nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="02e7d-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="02e7d-117">Se il **DataSet** contiene già uno schema, lo schema corrente verrà esteso aggiungendo nuove tabelle se non esistono già.</span><span class="sxs-lookup"><span data-stu-id="02e7d-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="02e7d-118">Nelle tabelle esistenti non verranno aggiunte nuove colonne.</span><span class="sxs-lookup"><span data-stu-id="02e7d-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="02e7d-119">Se una colonna da aggiungere esiste già nel **DataSet** ma ha un tipo incompatibile con la colonna trovata nel codice XML, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="02e7d-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="02e7d-120">Per informazioni dettagliate su come **ReadXmlSchema** deduce uno schema da un documento XML, vedere [Infereding DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="02e7d-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="02e7d-121">Sebbene **ReadXmlSchema** carichi o deduce solo lo schema di un **DataSet,** il metodo **ReadXml** del **DataSet** carica o deduce sia lo schema che i dati contenuti nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="02e7d-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="02e7d-122">Per ulteriori informazioni, vedere [Caricamento di un DataSet da XML.](loading-a-dataset-from-xml.md)</span><span class="sxs-lookup"><span data-stu-id="02e7d-122">For more information, see [Loading a DataSet from XML](loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="02e7d-123">Negli esempi di codice seguenti viene illustrato come caricare uno schema **DataSet** da un flusso o un documento XML.</span><span class="sxs-lookup"><span data-stu-id="02e7d-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="02e7d-124">Nel primo esempio viene illustrato un nome di file XML Schema passato al metodo **ReadXmlSchema.**</span><span class="sxs-lookup"><span data-stu-id="02e7d-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="02e7d-125">Nel secondo esempio viene illustrato un **oggetto System.IO.StreamReader**.</span><span class="sxs-lookup"><span data-stu-id="02e7d-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As New System.IO.StreamReader("schema.xsd")
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="02e7d-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="02e7d-126">InferXmlSchema</span></span>  
 <span data-ttu-id="02e7d-127">È inoltre possibile indicare al **DataSet** di dedurre lo schema da un documento XML utilizzando il metodo **InferXmlSchema** del **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="02e7d-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="02e7d-128">**InferXmlSchema** funziona allo stesso modo di **ReadXml** con un **XmlReadMode** di **InferSchema** (carica i dati e deduce lo schema) e **ReadXmlSchema** se il documento letto non contiene alcuno schema inline.</span><span class="sxs-lookup"><span data-stu-id="02e7d-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="02e7d-129">Tuttavia, **InferXmlSchema** fornisce la funzionalità aggiuntiva di consentire di specificare particolari spazi dei nomi XML da ignorare quando lo schema viene dedotto.</span><span class="sxs-lookup"><span data-stu-id="02e7d-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="02e7d-130">**InferXmlSchema** accetta due argomenti obbligatori: il percorso del documento XML, specificato da un nome file, un flusso o un **XmlReader**; e una matrice di stringhe di spazi dei nomi XML da ignorare dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="02e7d-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="02e7d-131">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="02e7d-131">For example, consider the following XML:</span></span>  
  
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
  
 <span data-ttu-id="02e7d-132">A causa degli attributi specificati per gli elementi nel documento XML precedente, sia il metodo **ReadXmlSchema che** il metodo **ReadXml** con **un oggetto XmlReadMode** di **InferSchema** creerebbero tabelle per ogni elemento del documento: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**e **Discontinued**.</span><span class="sxs-lookup"><span data-stu-id="02e7d-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="02e7d-133">Per ulteriori informazioni, vedere [Infering DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md). Tuttavia, una struttura più appropriata consiste nel creare solo le tabelle **Categories** e **Products** e quindi creare le colonne **CategoryID**, **CategoryName**e **Description** nella tabella **Categories** e **ProductID**, **ReorderLevel**e **Discontinued** nella tabella **Products** .</span><span class="sxs-lookup"><span data-stu-id="02e7d-133">(For more information, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="02e7d-134">Per assicurarsi che lo schema dedotto ignori gli attributi specificati negli elementi XML, utilizzare il metodo **InferXmlSchema** e specificare lo spazio dei nomi XML affinché **officedata** venga ignorato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="02e7d-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="02e7d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02e7d-135">See also</span></span>

- [<span data-ttu-id="02e7d-136">Utilizzo di XML in un dataset</span><span class="sxs-lookup"><span data-stu-id="02e7d-136">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="02e7d-137">Derivazione della struttura relazionale di dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="02e7d-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="02e7d-138">Deduzione della struttura relazionale di dataset da XML</span><span class="sxs-lookup"><span data-stu-id="02e7d-138">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="02e7d-139">Caricamento di un dataset da XML</span><span class="sxs-lookup"><span data-stu-id="02e7d-139">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="02e7d-140">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="02e7d-140">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="02e7d-141">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="02e7d-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
