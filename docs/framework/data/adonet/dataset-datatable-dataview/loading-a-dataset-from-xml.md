---
title: Caricamento di un dataset da XML
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
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: db507bf4f90d875960408857c7e6b1e3aa145730
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="loading-a-dataset-from-xml"></a><span data-ttu-id="0a653-102">Caricamento di un dataset da XML</span><span class="sxs-lookup"><span data-stu-id="0a653-102">Loading a DataSet from XML</span></span>
<span data-ttu-id="0a653-103">È possibile creare il contenuto di un <xref:System.Data.DataSet> di ADO.NET da un flusso o un documento XML.</span><span class="sxs-lookup"><span data-stu-id="0a653-103">The contents of an ADO.NET <xref:System.Data.DataSet> can be created from an XML stream or document.</span></span> <span data-ttu-id="0a653-104">Inoltre, .NET Framework consente di definire con grande flessibilità le informazioni da caricare da XML e la modalità di creazione dello schema o struttura relazionale del <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0a653-104">In addition, with the .NET Framework you have great flexibility over what information is loaded from XML, and how the schema or relational structure of the <xref:System.Data.DataSet> is created.</span></span>  
  
 <span data-ttu-id="0a653-105">Per riempire un <xref:System.Data.DataSet> con dati da XML, utilizzare il **ReadXml** metodo il <xref:System.Data.DataSet> oggetto.</span><span class="sxs-lookup"><span data-stu-id="0a653-105">To fill a <xref:System.Data.DataSet> with data from XML, use the **ReadXml** method of the <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="0a653-106">Il **ReadXml** metodo legge da un file, un flusso o un **XmlReader**e accetta come argomenti l'origine del documento XML, oltre facoltativa **XmlReadMode** argomento.</span><span class="sxs-lookup"><span data-stu-id="0a653-106">The **ReadXml** method reads from a file, a stream, or an **XmlReader**, and takes as arguments the source of the XML plus an optional **XmlReadMode** argument.</span></span> <span data-ttu-id="0a653-107">(Per ulteriori informazioni sul **XmlReader**, vedere [NIB: lettura di dati XML con XmlTextReader](http://msdn.microsoft.com/en-us/762c069b-b50c-41b8-936e-39eacfb0d540).) Il **ReadXml** metodo legge il contenuto del flusso XML o documento e carica il <xref:System.Data.DataSet> con i dati.</span><span class="sxs-lookup"><span data-stu-id="0a653-107">(For more information about the **XmlReader**, see [NIB: Reading XML Data with XmlTextReader](http://msdn.microsoft.com/en-us/762c069b-b50c-41b8-936e-39eacfb0d540).) The **ReadXml** method reads the contents of the XML stream or document and loads the <xref:System.Data.DataSet> with data.</span></span> <span data-ttu-id="0a653-108">Viene creata anche lo schema relazionale del <xref:System.Data.DataSet> a seconda di **XmlReadMode** specificato e l'eventuale esistenza di uno schema relazionale.</span><span class="sxs-lookup"><span data-stu-id="0a653-108">It will also create the relational schema of the <xref:System.Data.DataSet> depending on the **XmlReadMode** specified and whether or not a relational schema already exists.</span></span>  
  
 <span data-ttu-id="0a653-109">Nella tabella seguente vengono descritte le opzioni per il **XmlReadMode** argomento.</span><span class="sxs-lookup"><span data-stu-id="0a653-109">The following table describes the options for the **XmlReadMode** argument.</span></span>  
  
|<span data-ttu-id="0a653-110">Opzione</span><span class="sxs-lookup"><span data-stu-id="0a653-110">Option</span></span>|<span data-ttu-id="0a653-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a653-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0a653-112">**Auto**</span><span class="sxs-lookup"><span data-stu-id="0a653-112">**Auto**</span></span>|<span data-ttu-id="0a653-113">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0a653-113">This is the default.</span></span> <span data-ttu-id="0a653-114">Consente di esaminare il documento o flusso XML e di selezionare l'opzione più appropriata, nel seguente ordine:</span><span class="sxs-lookup"><span data-stu-id="0a653-114">Examines the XML and chooses the most appropriate option in the following order:</span></span><br /><br /> <span data-ttu-id="0a653-115">-Se il codice XML è un DiffGram, **DiffGram** viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="0a653-115">-   If the XML is a DiffGram, **DiffGram** is used.</span></span><br /><span data-ttu-id="0a653-116">-Se il <xref:System.Data.DataSet> contiene uno schema o il file XML contiene uno schema inline, **ReadSchema** viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="0a653-116">-   If the <xref:System.Data.DataSet> contains a schema or the XML contains an inline schema, **ReadSchema** is used.</span></span><br /><span data-ttu-id="0a653-117">-Se il <xref:System.Data.DataSet> non contiene uno schema e il codice XML non contiene uno schema inline, **InferSchema** viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="0a653-117">-   If the <xref:System.Data.DataSet> does not contain a schema and the XML does not contain an inline schema, **InferSchema** is used.</span></span><br /><br /> <span data-ttu-id="0a653-118">Se si conosce il formato del codice XML letto, per prestazioni ottimali è consigliabile impostare esplicita **XmlReadMode**, invece di accettare il **Auto** predefinito.</span><span class="sxs-lookup"><span data-stu-id="0a653-118">If you know the format of the XML being read, for best performance it is recommended that you set an explicit **XmlReadMode**, rather than accept the **Auto** default.</span></span>|  
|<span data-ttu-id="0a653-119">**ReadSchema**</span><span class="sxs-lookup"><span data-stu-id="0a653-119">**ReadSchema**</span></span>|<span data-ttu-id="0a653-120">Consente di leggere gli schemi inline e di caricare i dati e lo schema.</span><span class="sxs-lookup"><span data-stu-id="0a653-120">Reads any inline schema and loads the data and schema.</span></span><br /><br /> <span data-ttu-id="0a653-121">Se nel <xref:System.Data.DataSet> è già presente uno schema, vengono aggiunte nuove tabelle dallo schema inline allo schema esistente nel <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0a653-121">If the <xref:System.Data.DataSet> already contains a schema, new tables are added from the inline schema to the existing schema in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0a653-122">Se nel <xref:System.Data.DataSet> sono già presenti delle tabelle dello schema inline, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0a653-122">If any tables in the inline schema already exist in the <xref:System.Data.DataSet>, an exception is thrown.</span></span> <span data-ttu-id="0a653-123">Non sarà in grado di modificare lo schema di una tabella esistente usando **ReadSchema**.</span><span class="sxs-lookup"><span data-stu-id="0a653-123">You will not be able to modify the schema of an existing table using **XmlReadMode.ReadSchema**.</span></span><br /><br /> <span data-ttu-id="0a653-124">Se nel <xref:System.Data.DataSet> non è presente uno schema e non si dispone di uno schema inline, non verrà letto alcun dato.</span><span class="sxs-lookup"><span data-stu-id="0a653-124">If the <xref:System.Data.DataSet> does not contain a schema, and there is no inline schema, no data is read.</span></span><br /><br /> <span data-ttu-id="0a653-125">È possibile definire lo schema inline usando lo schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="0a653-125">Inline schema can be defined using XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="0a653-126">Per informazioni dettagliate sulla scrittura di uno schema inline come XML Schema, vedere [derivazione struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="0a653-126">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>|  
|<span data-ttu-id="0a653-127">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="0a653-127">**IgnoreSchema**</span></span>|<span data-ttu-id="0a653-128">Consente di ignorare eventuali schemi inline e di caricare i dati nello schema del <xref:System.Data.DataSet> esistente.</span><span class="sxs-lookup"><span data-stu-id="0a653-128">Ignores any inline schema and loads the data into the existing <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="0a653-129">Eventuali dati non corrispondenti allo schema esistente vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="0a653-129">Any data that does not match the existing schema is discarded.</span></span> <span data-ttu-id="0a653-130">Se nel <xref:System.Data.DataSet> non è presente alcuno schema, non verrà caricato alcun dato.</span><span class="sxs-lookup"><span data-stu-id="0a653-130">If no schema exists in the <xref:System.Data.DataSet>, no data is loaded.</span></span><br /><br /> <span data-ttu-id="0a653-131">Se i dati sono di tipo DiffGram, **IgnoreSchema** ha la stessa funzionalità come **DiffGram** *.*</span><span class="sxs-lookup"><span data-stu-id="0a653-131">If the data is a DiffGram, **IgnoreSchema** has the same functionality as **DiffGram** *.*</span></span>|  
|<span data-ttu-id="0a653-132">**InferSchema**</span><span class="sxs-lookup"><span data-stu-id="0a653-132">**InferSchema**</span></span>|<span data-ttu-id="0a653-133">Consente di ignorare eventuali schemi inline e di inferire uno schema in base alla struttura dei dati XML, che vengono quindi caricati.</span><span class="sxs-lookup"><span data-stu-id="0a653-133">Ignores any inline schema and infers the schema per the structure of the XML data, then loads the data.</span></span><br /><br /> <span data-ttu-id="0a653-134">Se nell'oggetto <xref:System.Data.DataSet> è già contenuto uno schema, lo schema corrente verrà esteso mediante l'aggiunta di colonne alle tabelle esistenti.</span><span class="sxs-lookup"><span data-stu-id="0a653-134">If the <xref:System.Data.DataSet> already contains a schema, the current schema is extended by adding columns to existing tables.</span></span> <span data-ttu-id="0a653-135">Se non sono disponibili tabelle esistenti, non verranno aggiunte altre tabelle.</span><span class="sxs-lookup"><span data-stu-id="0a653-135">Extra tables will not be added if there are not existing tables.</span></span> <span data-ttu-id="0a653-136">Se esiste già una tabella inferita con uno spazio dei nomi diverso o se alcune colonne inferite è in conflitto con le colonne esistenti, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0a653-136">An exception is thrown if an inferred table already exists with a different namespace, or if any inferred columns conflict with existing columns.</span></span><br /><br /> <span data-ttu-id="0a653-137">Per informazioni dettagliate su come **ReadXmlSchema** deduce uno schema da un documento XML, vedere [inferenza struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0a653-137">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>|  
|<span data-ttu-id="0a653-138">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="0a653-138">**DiffGram**</span></span>|<span data-ttu-id="0a653-139">Consente di leggere un DiffGram e di aggiungere i dati allo schema corrente.</span><span class="sxs-lookup"><span data-stu-id="0a653-139">Reads a DiffGram and adds the data to the current schema.</span></span> <span data-ttu-id="0a653-140">**DiffGram** unisce le nuove righe con righe esistenti in corrispondano dei valori dell'identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="0a653-140">**DiffGram** merges new rows with existing rows where the unique identifier values match.</span></span> <span data-ttu-id="0a653-141">Vedere la nota relativa a "Unione di dati da XML" alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0a653-141">See "Merging Data from XML" at the end of this topic.</span></span> <span data-ttu-id="0a653-142">Per ulteriori informazioni sui DiffGram, vedere [DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="0a653-142">For more information about DiffGrams, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>|  
|<span data-ttu-id="0a653-143">**Frammento**</span><span class="sxs-lookup"><span data-stu-id="0a653-143">**Fragment**</span></span>|<span data-ttu-id="0a653-144">Consente di continuare a leggere più frammenti XML fino al raggiungimento della fine del flusso.</span><span class="sxs-lookup"><span data-stu-id="0a653-144">Continues reading multiple XML fragments until the end of the stream is reached.</span></span> <span data-ttu-id="0a653-145">I frammenti corrispondenti allo schema del <xref:System.Data.DataSet> vengono aggiunti alle tabelle appropriate.</span><span class="sxs-lookup"><span data-stu-id="0a653-145">Fragments that match the <xref:System.Data.DataSet> schema are appended to the appropriate tables.</span></span> <span data-ttu-id="0a653-146">I frammenti non corrispondenti allo schema <xref:System.Data.DataSet> vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="0a653-146">Fragments that do not match the <xref:System.Data.DataSet> schema are discarded.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="0a653-147">Se si passa un **XmlReader** a **ReadXml** che posizionato fanno parte del modo in cui in un documento XML, **ReadXml** leggerà il nodo successivo dell'elemento e lo considererà come radice elemento durante la lettura fino alla fine della solo il nodo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="0a653-147">If you pass an **XmlReader** to **ReadXml** that is positioned part of the way into an XML document, **ReadXml** will read to the next element node and will treat that as the root element, reading until the end of the element node only.</span></span> <span data-ttu-id="0a653-148">Non si applica se si specifica **XmlReadMode**.</span><span class="sxs-lookup"><span data-stu-id="0a653-148">This does not apply if you specify **XmlReadMode.Fragment**.</span></span>  
  
## <a name="dtd-entities"></a><span data-ttu-id="0a653-149">Entità DTD</span><span class="sxs-lookup"><span data-stu-id="0a653-149">DTD Entities</span></span>  
 <span data-ttu-id="0a653-150">Se il codice XML è presenti entità definite in uno schema di definizione (DTD) di tipo di documento, verrà generata un'eccezione se si tenta di caricare un <xref:System.Data.DataSet> passando un file di nome, un flusso o non convalidante **XmlReader** a  **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="0a653-150">If your XML contains entities defined in a document type definition (DTD) schema, an exception will be thrown if you attempt to load a <xref:System.Data.DataSet> by passing a file name, stream, or non-validating **XmlReader** to **ReadXml**.</span></span> <span data-ttu-id="0a653-151">In alternativa, è necessario creare un **XmlValidatingReader**, con **EntityHandling** impostato su **EntityHandling. ExpandEntities**e passare il  **XmlValidatingReader** a **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="0a653-151">Instead, you must create an **XmlValidatingReader**, with **EntityHandling** set to **EntityHandling.ExpandEntities**, and pass your **XmlValidatingReader** to **ReadXml**.</span></span> <span data-ttu-id="0a653-152">Il **XmlValidatingReader** prima di essere lette dall'entità verranno espanse il <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0a653-152">The **XmlValidatingReader** will expand the entities prior to being read by the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="0a653-153">Negli esempi di codice seguenti viene illustrato come caricare un <xref:System.Data.DataSet> da un flusso XML.</span><span class="sxs-lookup"><span data-stu-id="0a653-153">The following code examples show how to load a <xref:System.Data.DataSet> from an XML stream.</span></span> <span data-ttu-id="0a653-154">Nel primo esempio viene passato a un nome di file di **ReadXml** metodo.</span><span class="sxs-lookup"><span data-stu-id="0a653-154">The first example shows a file name being passed to the **ReadXml** method.</span></span> <span data-ttu-id="0a653-155">Nel secondo esempio viene mostrato il caricamento di una stringa contenente XML tramite <xref:System.IO.StringReader>.</span><span class="sxs-lookup"><span data-stu-id="0a653-155">The second example shows a string that contains XML being loaded using a <xref:System.IO.StringReader>.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema);  
```  
  
```vb  
Dim dataSet As DataSet = New DataSet  
Dim dataTable As DataTable = New DataTable("table1")  
dataTable.Columns.Add("col1", Type.GetType("System.String"))  
dataSet.Tables.Add(dataTable)  
  
Dim xmlData As String = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>"  
  
Dim xmlSR As System.IO.StringReader = New System.IO.StringReader(xmlData)  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
DataTable dataTable = new DataTable("table1");  
dataTable.Columns.Add("col1", typeof(string));  
dataSet.Tables.Add(dataTable);  
  
string xmlData = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>";  
  
System.IO.StringReader xmlSR = new System.IO.StringReader(xmlData);  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema);  
```  
  
> [!NOTE]
>  <span data-ttu-id="0a653-156">Se si chiama **ReadXml** per caricare un file di dimensioni molto grande, potrebbero verificarsi un rallentamento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0a653-156">If you call **ReadXml** to load a very large file, you may encounter slow performance.</span></span> <span data-ttu-id="0a653-157">Per garantire prestazioni ottimali per **ReadXml**, in un file di grandi dimensioni, chiamare il <xref:System.Data.DataTable.BeginLoadData%2A> metodo per ogni tabella di <xref:System.Data.DataSet>e quindi chiamare **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="0a653-157">To ensure best performance for **ReadXml**, on a large file, call the <xref:System.Data.DataTable.BeginLoadData%2A> method for each table in the <xref:System.Data.DataSet>, and then call **ReadXml**.</span></span> <span data-ttu-id="0a653-158">Chiamare infine <xref:System.Data.DataTable.EndLoadData%2A> per ogni tabella del <xref:System.Data.DataSet>, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0a653-158">Finally, call <xref:System.Data.DataTable.EndLoadData%2A> for each table in the <xref:System.Data.DataSet>, as shown in the following example.</span></span>  
  
```vb  
Dim dataTable As DataTable  
  
For Each dataTable In dataSet.Tables  
   dataTable.BeginLoadData()  
Next  
  
dataSet.ReadXml("file.xml")  
  
For Each dataTable in dataSet.Tables  
   dataTable.EndLoadData()  
Next  
```  
  
```csharp  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.BeginLoadData();  
  
dataSet.ReadXml("file.xml");   
  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.EndLoadData();  
```  
  
> [!NOTE]
>  <span data-ttu-id="0a653-159">Se lo schema XSD per il <xref:System.Data.DataSet> include un **targetNamespace**, non è possibile leggere i dati e che vengano generate eccezioni, quando si chiama **ReadXml** per caricare il <xref:System.Data.DataSet> con XML contenente elementi senza spazio dei nomi validi.</span><span class="sxs-lookup"><span data-stu-id="0a653-159">If the XSD schema for your <xref:System.Data.DataSet> includes a **targetNamespace**, data may not be read, and you may encounter exceptions, when calling **ReadXml** to load the <xref:System.Data.DataSet> with XML that contains elements with no qualifying namespace.</span></span> <span data-ttu-id="0a653-160">Per leggere elementi non qualificati in questo caso, impostare **elementFormDefault** uguale a "qualified" nello schema XSD.</span><span class="sxs-lookup"><span data-stu-id="0a653-160">To read unqualified elements in this case, set **elementFormDefault** equal to "qualified" in your XSD schema.</span></span> <span data-ttu-id="0a653-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0a653-161">For example:</span></span>  
  
```xml  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a><span data-ttu-id="0a653-162">Unione di dati da XML</span><span class="sxs-lookup"><span data-stu-id="0a653-162">Merging Data from XML</span></span>  
 <span data-ttu-id="0a653-163">Se nell'oggetto <xref:System.Data.DataSet> sono già presenti dati, i nuovi dati provenienti dal flusso o dal documento XML vengono aggiunti ai dati presenti nell'oggetto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0a653-163">If the <xref:System.Data.DataSet> already contains data, the new data from the XML is added to the data already present in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0a653-164">**ReadXml** non vengono unite da codice XML nel <xref:System.Data.DataSet> informazioni con chiavi primarie corrispondenti a ogni riga.</span><span class="sxs-lookup"><span data-stu-id="0a653-164">**ReadXml** does not merge from the XML into the <xref:System.Data.DataSet> any row information with matching primary keys.</span></span> <span data-ttu-id="0a653-165">Per sovrascrivere le informazioni di riga esistenti con nuove informazioni da XML, utilizzare **ReadXml** per creare un nuovo <xref:System.Data.DataSet>e quindi <xref:System.Data.DataSet.Merge%2A> nuovo <xref:System.Data.DataSet> in esistente <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0a653-165">To overwrite existing row information with new information from XML, use **ReadXml** to create a new <xref:System.Data.DataSet>, and then <xref:System.Data.DataSet.Merge%2A> the new <xref:System.Data.DataSet> into the existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0a653-166">Si noti che il caricamento di un DiffGram tramite **ReadXML** con un **XmlReadMode** di **DiffGram** consentirà di unire righe che hanno lo stesso identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="0a653-166">Note that loading a DiffGram using **ReadXML** with an **XmlReadMode** of **DiffGram** will merge rows that have the same unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a653-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a653-167">See Also</span></span>  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="0a653-168">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="0a653-168">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="0a653-169">DiffGram</span><span class="sxs-lookup"><span data-stu-id="0a653-169">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 [<span data-ttu-id="0a653-170">La derivazione di struttura relazionale di DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="0a653-170">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="0a653-171">Inferenza della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="0a653-171">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="0a653-172">Il caricamento delle informazioni dello Schema di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="0a653-172">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="0a653-173">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="0a653-173">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="0a653-174">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="0a653-174">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
