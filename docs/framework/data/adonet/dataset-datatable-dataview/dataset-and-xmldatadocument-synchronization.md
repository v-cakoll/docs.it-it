---
title: Sincronizzazione di DataSet e XmlDataDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: 3bbe28423385cae0f09f301c03b2b1a59edf101d
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205065"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="ee7ce-102">Sincronizzazione di DataSet e XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="ee7ce-102">DataSet and XmlDataDocument Synchronization</span></span>
<span data-ttu-id="ee7ce-103">Il tipo <xref:System.Data.DataSet> di ADO.NET fornisce una rappresentazione relazionale dei dati.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="ee7ce-104">Per un accesso gerarchico ai dati, è possibile usare le classi XML disponibili in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="ee7ce-105">Questi due tipi di rappresentazione dei dati sono sempre stati usati separatamente.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="ee7ce-106">Tuttavia, il .NET Framework consente l'accesso sincrono in tempo reale alle rappresentazioni relazionali e gerarchiche dei dati tramite l'oggetto **DataSet** e l' <xref:System.Xml.XmlDataDocument> oggetto, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="ee7ce-107">Quando un **set** di dati viene sincronizzato con un **XmlDataDocument**, entrambi gli oggetti utilizzano un singolo set di dati.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="ee7ce-108">Ciò significa che se viene apportata una modifica al **set di dati**, la modifica viene riflessa in **XmlDataDocument**e viceversa.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="ee7ce-109">La relazione tra il **set** di dati e il **XmlDataDocument** crea una grande flessibilità consentendo a una singola applicazione, usando un unico set di dati, di accedere all'intera suite di servizi compilati in base al **set** di dati, ad esempio Web Form e Windows Forms controlli e finestre di progettazione di Visual Studio .NET), nonché la suite di servizi XML che include Extensible Stylesheet Language (XSL), XSL Transformations (XSLT) e XML Path Language (XPath).</span><span class="sxs-lookup"><span data-stu-id="ee7ce-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="ee7ce-110">Non è necessario stabilire il set di servizi a cui è destinata l'applicazione poiché sono entrambi disponibili.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="ee7ce-111">Esistono diversi modi per sincronizzare un **set di dati** con un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="ee7ce-112">È possibile:</span><span class="sxs-lookup"><span data-stu-id="ee7ce-112">You can:</span></span>  
  
- <span data-ttu-id="ee7ce-113">Compilare un **set** di dati con lo schema, ovvero una struttura relazionale, e i dati, quindi sincronizzarli con un nuovo **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="ee7ce-114">In questo modo si otterrà una visualizzazione gerarchica dei dati relazionali esistenti.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="ee7ce-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ee7ce-115">For example:</span></span>  
  
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
  
- <span data-ttu-id="ee7ce-116">Compilare un **set di dati** solo con schema (ad esempio un **set di dati**fortemente tipizzato), sincronizzarlo con un **XmlDataDocument**, quindi caricare l'oggetto **XmlDataDocument** da un documento XML.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="ee7ce-117">In questo modo si otterrà una visualizzazione relazionale dei dati gerarchici esistenti.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="ee7ce-118">I nomi delle tabelle e delle colonne nello schema del **set di dati** devono corrispondere ai nomi degli elementi XML con cui si desidera che vengano sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="ee7ce-119">Questo tipo di associazione rileva la differenza tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="ee7ce-120">Si noti che lo schema del **set di dati** deve corrispondere solo agli elementi XML che si desidera esporre nella visualizzazione relazionale.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="ee7ce-121">È quindi possibile disporre di un documento XML di grandi dimensioni e di una "finestra" relazionale molto piccola su tale documento.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="ee7ce-122">**XmlDataDocument** conserva l'intero documento XML, anche se il set di **dati** ne espone solo una piccola parte.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="ee7ce-123">Per un esempio dettagliato, vedere [sincronizzazione di un DataSet con un oggetto XmlDataDocument](synchronizing-a-dataset-with-an-xmldatadocument.md).</span><span class="sxs-lookup"><span data-stu-id="ee7ce-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="ee7ce-124">Nell'esempio di codice seguente vengono illustrati i passaggi per la creazione di un **set di dati** e il popolamento dello schema, quindi la sincronizzazione con un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="ee7ce-125">Si noti che lo schema del **set di dati** deve corrispondere solo agli elementi del **XmlDataDocument** che si desidera esporre utilizzando il **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
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
  
     <span data-ttu-id="ee7ce-126">Non è possibile caricare un **XmlDataDocument** se è sincronizzato con un **DataSet** contenente dati.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="ee7ce-127">Se si tenta di eseguire tale operazione, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-127">An exception will be thrown.</span></span>  
  
- <span data-ttu-id="ee7ce-128">Creare un nuovo oggetto **XmlDataDocument** e caricarlo da un documento XML, quindi accedere alla visualizzazione relazionale dei dati usando la proprietà **DataSet** dell'oggetto **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="ee7ce-129">È necessario impostare lo schema del **set** di dati prima di poter visualizzare i dati nell'oggetto **XmlDataDocument** utilizzando il **set**di dati.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="ee7ce-130">Anche in questo caso, i nomi delle tabelle e delle colonne nello schema del **set di dati** devono corrispondere ai nomi degli elementi XML con cui si desidera che vengano sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="ee7ce-131">Questo tipo di associazione rileva la differenza tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="ee7ce-132">Nell'esempio di codice seguente viene illustrato come accedere alla visualizzazione relazionale dei dati in un oggetto **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
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
  
 <span data-ttu-id="ee7ce-133">Un altro vantaggio della sincronizzazione di un oggetto **XmlDataDocument** con un **DataSet** è che la fedeltà di un documento XML viene mantenuta.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="ee7ce-134">Se il **set** di dati viene popolato da un documento XML utilizzando **ReadXml**, quando i dati vengono riscritti come documento XML utilizzando **WriteXml** , può variare notevolmente dal documento XML originale.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="ee7ce-135">Questo perché il **set di dati** non mantiene la formattazione, ad esempio spazi vuoti, o informazioni gerarchiche, ad esempio l'ordine degli elementi, dal documento XML.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="ee7ce-136">Il **set di dati** non contiene inoltre elementi del documento XML che sono stati ignorati perché non corrispondono allo schema del **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="ee7ce-137">La sincronizzazione di un **XmlDataDocument** con un **set** di dati consente di mantenere la formattazione e la struttura gerarchica degli elementi del documento XML originale in **XmlDataDocument**, mentre il **set** di dati contiene solo dati e informazioni dello schema appropriate per il **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="ee7ce-138">Quando si sincronizza un **set di dati** con un oggetto **XmlDataDocument**, i risultati possono variare a seconda che <xref:System.Data.DataRelation> gli oggetti siano nidificati o meno.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="ee7ce-139">Per ulteriori informazioni, vedere [nidificazione](nesting-datarelations.md)di oggetti DataRelation.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-139">For more information, see [Nesting DataRelations](nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee7ce-140">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="ee7ce-140">In This Section</span></span>  
 [<span data-ttu-id="ee7ce-141">Sincronizzazione di un oggetto DataSet con un oggetto XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="ee7ce-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="ee7ce-142">Viene illustrata la sincronizzazione di un **DataSet**fortemente tipizzato, con uno schema minimo, con un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="ee7ce-143">Esecuzione di una query XPath in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="ee7ce-143">Performing an XPath Query on a DataSet</span></span>](performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="ee7ce-144">Viene illustrata l'esecuzione di una query XPath sul contenuto di un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="ee7ce-145">Applicazione di una trasformazione XSLT a un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="ee7ce-145">Applying an XSLT Transform to a DataSet</span></span>](applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="ee7ce-146">Viene illustrata l'applicazione di una trasformazione XSLT al contenuto di un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ee7ce-147">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="ee7ce-147">Related Sections</span></span>  
 [<span data-ttu-id="ee7ce-148">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="ee7ce-148">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="ee7ce-149">Viene descritto il modo in cui il **DataSet** interagisce con XML come origine dati, incluso il caricamento e il salvataggio permanente del contenuto di un **DataSet** come dati XML.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="ee7ce-150">Annidamento di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="ee7ce-150">Nesting DataRelations</span></span>](nesting-datarelations.md)  
 <span data-ttu-id="ee7ce-151">Viene illustrata l'importanza degli oggetti DataRelation annidati quando si rappresenta il contenuto di un **DataSet** come dati XML e viene descritto come creare tali relazioni.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="ee7ce-152">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="ee7ce-152">DataSets, DataTables, and DataViews</span></span>](index.md)  
 <span data-ttu-id="ee7ce-153">Viene descritto il **set** di dati e viene illustrato come utilizzarlo per gestire i dati dell'applicazione e interagire con le origini dati, inclusi i database relazionali e XML.</span><span class="sxs-lookup"><span data-stu-id="ee7ce-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="ee7ce-154">Contiene informazioni di riferimento sulla classe **XmlDataDocument** .</span><span class="sxs-lookup"><span data-stu-id="ee7ce-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee7ce-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee7ce-155">See also</span></span>

- [<span data-ttu-id="ee7ce-156">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="ee7ce-156">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
