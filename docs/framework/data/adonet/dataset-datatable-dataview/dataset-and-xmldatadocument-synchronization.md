---
title: Sincronizzazione di DataSet e XmlDataDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: 5360a7bce1b5470271bc6b512484964ebb9fd8d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587778"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="12bf8-102">Sincronizzazione di DataSet e XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="12bf8-102">DataSet and XmlDataDocument Synchronization</span></span>
<span data-ttu-id="12bf8-103">Il tipo <xref:System.Data.DataSet> di ADO.NET fornisce una rappresentazione relazionale dei dati.</span><span class="sxs-lookup"><span data-stu-id="12bf8-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="12bf8-104">Per un accesso gerarchico ai dati, è possibile usare le classi XML disponibili in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="12bf8-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="12bf8-105">Questi due tipi di rappresentazione dei dati sono sempre stati usati separatamente.</span><span class="sxs-lookup"><span data-stu-id="12bf8-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="12bf8-106">Tuttavia, .NET Framework consente l'accesso sincrono, in tempo reale alle rappresentazioni sia relazionali e gerarchiche di dati tramite il **set di dati** oggetto e il <xref:System.Xml.XmlDataDocument> dell'oggetto, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="12bf8-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="12bf8-107">Quando un **set di dati** è sincronizzato con un **XmlDataDocument**, entrambi gli oggetti usano un singolo set di dati.</span><span class="sxs-lookup"><span data-stu-id="12bf8-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="12bf8-108">Ciò significa che se viene apportata una modifica per il **set di dati**, la modifica si rifletterà nel **XmlDataDocument**e viceversa.</span><span class="sxs-lookup"><span data-stu-id="12bf8-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="12bf8-109">La relazione tra il **set di dati** e il **XmlDataDocument** crea una notevole flessibilità, consentendo a una singola applicazione, usando un singolo set di dati, per l'intera famiglia di servizi incorporati di accesso tutto il **set di dati** (ad esempio i controlli Windows Form e Web Form e le finestre di progettazione di Visual Studio .NET), nonché la suite di servizi XML, tra cui fogli di stile XSL (Extensible Language), XSL Transformations (XSLT) e il percorso XML Language (XPath).</span><span class="sxs-lookup"><span data-stu-id="12bf8-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="12bf8-110">Non è necessario stabilire il set di servizi a cui è destinata l'applicazione poiché sono entrambi disponibili.</span><span class="sxs-lookup"><span data-stu-id="12bf8-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="12bf8-111">Esistono vari modi in cui è possibile sincronizzare un **set di dati** con un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="12bf8-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="12bf8-112">È possibile:</span><span class="sxs-lookup"><span data-stu-id="12bf8-112">You can:</span></span>  
  
-   <span data-ttu-id="12bf8-113">Popolare una **set di dati** con lo schema (vale a dire una struttura relazionale) e i dati, quindi sincronizzarlo con un nuovo oggetto **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="12bf8-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="12bf8-114">In questo modo si otterrà una visualizzazione gerarchica dei dati relazionali esistenti.</span><span class="sxs-lookup"><span data-stu-id="12bf8-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="12bf8-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="12bf8-115">For example:</span></span>  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema and data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema and data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    ```  
  
-   <span data-ttu-id="12bf8-116">Popolare una **set di dati** con solo schema (ad esempio una classe fortemente tipizzata **set di dati**), sincronizzarlo con un **XmlDataDocument**e quindi caricare il  **XmlDataDocument** da un documento XML.</span><span class="sxs-lookup"><span data-stu-id="12bf8-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="12bf8-117">In questo modo si otterrà una visualizzazione relazionale dei dati gerarchici esistenti.</span><span class="sxs-lookup"><span data-stu-id="12bf8-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="12bf8-118">I nomi di tabella e i nomi di colonna il **set di dati** dello schema deve corrispondere ai nomi degli elementi XML desiderati siano sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="12bf8-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="12bf8-119">Questo tipo di associazione rileva la differenza tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="12bf8-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="12bf8-120">Si noti che lo schema del **set di dati** solo deve corrispondere gli elementi XML che si desidera esporre nella visualizzazione relazionale.</span><span class="sxs-lookup"><span data-stu-id="12bf8-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="12bf8-121">È quindi possibile disporre di un documento XML di grandi dimensioni e di una "finestra" relazionale molto piccola su tale documento.</span><span class="sxs-lookup"><span data-stu-id="12bf8-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="12bf8-122">Il **XmlDataDocument** mantiene anche se l'intero documento XML le **DataSet** espone solo una piccola parte di esso.</span><span class="sxs-lookup"><span data-stu-id="12bf8-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="12bf8-123">(Per un esempio dettagliato, vedere [sincronizza un set di dati con un XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span><span class="sxs-lookup"><span data-stu-id="12bf8-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="12bf8-124">Esempio di codice seguente illustra i passaggi per la creazione di un **set di dati** e la compilazione dello schema, quindi la sincronizzazione con un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="12bf8-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="12bf8-125">Si noti che il **set di dati** dello schema deve solo corrispondere gli elementi dalle **XmlDataDocument** che si desidera esporre mediante il **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="12bf8-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema, but not data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema, but not data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
     <span data-ttu-id="12bf8-126">Non è possibile caricare un' **XmlDataDocument** se è stata sincronizzata con un **DataSet** che contiene i dati.</span><span class="sxs-lookup"><span data-stu-id="12bf8-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="12bf8-127">Se si tenta di eseguire tale operazione, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="12bf8-127">An exception will be thrown.</span></span>  
  
-   <span data-ttu-id="12bf8-128">Creare una nuova **XmlDataDocument** e caricarlo da un documento XML e quindi accedere alla visualizzazione relazionale dei dati tramite il **set di dati** proprietà del **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="12bf8-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="12bf8-129">È necessario impostare lo schema del **set di dati** prima di poter visualizzare i dati nel **XmlDataDocument** utilizzando il **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="12bf8-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="12bf8-130">Anche in questo caso, i nomi di nomi di tabella e colonna nel **set di dati** dello schema deve corrispondere ai nomi degli elementi XML desiderati siano sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="12bf8-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="12bf8-131">Questo tipo di associazione rileva la differenza tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="12bf8-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="12bf8-132">Esempio di codice seguente viene illustrato come accedere alla visualizzazione relazionale dei dati in un' **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="12bf8-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
    ```vb  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument  
    Dim dataSet As DataSet = xmlDoc.DataSet  
  
    ' Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    XmlDataDocument xmlDoc = new XmlDataDocument();  
    DataSet dataSet = xmlDoc.DataSet;  
  
    // Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
 <span data-ttu-id="12bf8-133">Un altro vantaggio della sincronizzazione di un **XmlDataDocument** con un **DataSet** è di mantenere la fedeltà di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="12bf8-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="12bf8-134">Se il **set di dati** viene popolato da un documento XML usando **ReadXml**, quando i dati vengono riscritti come un documento XML usando **WriteXml** possono variare notevolmente dal documento XML originale.</span><span class="sxs-lookup"><span data-stu-id="12bf8-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="12bf8-135">Infatti, il **set di dati** non conserva la formattazione, ad esempio spazi vuoti o le informazioni gerarchiche, ad esempio ordine degli elementi, il documento XML.</span><span class="sxs-lookup"><span data-stu-id="12bf8-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="12bf8-136">Il **set di dati** inoltre non contiene elementi dal documento XML che sono stati ignorati perché lo schema di cui non corrisponde la **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="12bf8-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="12bf8-137">La sincronizzazione di un **XmlDataDocument** con un **set di dati** consente di formattazione e gerarchica della struttura dell'elemento del documento XML originale venga mantenuto nel **XmlDataDocument**, mentre la **set di dati** contiene sole i dati e le informazioni appropriate per il **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="12bf8-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="12bf8-138">Durante la sincronizzazione una **set di dati** con un **XmlDataDocument**, i risultati possono variare a seconda se il <xref:System.Data.DataRelation> gli oggetti sono annidati.</span><span class="sxs-lookup"><span data-stu-id="12bf8-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="12bf8-139">Per altre informazioni, vedere [annidamento di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="12bf8-139">For more information, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="12bf8-140">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="12bf8-140">In This Section</span></span>  
 [<span data-ttu-id="12bf8-141">Sincronizzazione di un oggetto DataSet con un oggetto XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="12bf8-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="12bf8-142">Spiega come sincronizzare un oggetto fortemente tipizzato **set di dati**, con uno schema minimo, con un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="12bf8-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="12bf8-143">Esecuzione di una query XPath in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="12bf8-143">Performing an XPath Query on a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="12bf8-144">Viene illustrata l'esecuzione di una query XPath sul contenuto di un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="12bf8-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="12bf8-145">Applicazione di una trasformazione XSLT a un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="12bf8-145">Applying an XSLT Transform to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="12bf8-146">Illustra l'applicazione di una trasformazione XSLT al contenuto di un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="12bf8-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="12bf8-147">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="12bf8-147">Related Sections</span></span>  
 [<span data-ttu-id="12bf8-148">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="12bf8-148">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="12bf8-149">Viene descritto come la **set di dati** interagisce con il codice XML come origine dati, inclusi il caricamento e salvataggio permanente il contenuto di un **set di dati** come dati XML.</span><span class="sxs-lookup"><span data-stu-id="12bf8-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="12bf8-150">Annidamento di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="12bf8-150">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 <span data-ttu-id="12bf8-151">Viene illustrata l'importanza di annidato **DataRelation** oggetti una rappresentazione del contenuto di un **DataSet** come dati XML e viene descritto come creare queste relazioni.</span><span class="sxs-lookup"><span data-stu-id="12bf8-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="12bf8-152">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="12bf8-152">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="12bf8-153">Descrive la **set di dati** e come usarlo per gestire i dati dell'applicazione e interagire con le origini dati, inclusi database relazionali e XML.</span><span class="sxs-lookup"><span data-stu-id="12bf8-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="12bf8-154">Contiene informazioni di riferimento sui **XmlDataDocument** classe.</span><span class="sxs-lookup"><span data-stu-id="12bf8-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12bf8-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12bf8-155">See also</span></span>
- [<span data-ttu-id="12bf8-156">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="12bf8-156">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
