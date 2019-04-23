---
title: Sincronizzazione di DataSet e XmlDataDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: ea597d7caca3174b17ce16a1e9d70c022e3e75c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164736"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a>Sincronizzazione di DataSet e XmlDataDocument
Il tipo <xref:System.Data.DataSet> di ADO.NET fornisce una rappresentazione relazionale dei dati. Per un accesso gerarchico ai dati, è possibile usare le classi XML disponibili in .NET Framework. Questi due tipi di rappresentazione dei dati sono sempre stati usati separatamente. Tuttavia, .NET Framework consente l'accesso sincrono, in tempo reale alle rappresentazioni sia relazionali e gerarchiche di dati tramite il **set di dati** oggetto e il <xref:System.Xml.XmlDataDocument> dell'oggetto, rispettivamente.  
  
 Quando un **set di dati** è sincronizzato con un **XmlDataDocument**, entrambi gli oggetti usano un singolo set di dati. Ciò significa che se viene apportata una modifica per il **set di dati**, la modifica si rifletterà nel **XmlDataDocument**e viceversa. La relazione tra il **set di dati** e il **XmlDataDocument** crea una notevole flessibilità, consentendo a una singola applicazione, usando un singolo set di dati, per l'intera famiglia di servizi incorporati di accesso tutto il **set di dati** (ad esempio i controlli Windows Form e Web Form e le finestre di progettazione di Visual Studio .NET), nonché la suite di servizi XML, tra cui fogli di stile XSL (Extensible Language), XSL Transformations (XSLT) e il percorso XML Language (XPath). Non è necessario stabilire il set di servizi a cui è destinata l'applicazione poiché sono entrambi disponibili.  
  
 Esistono vari modi in cui è possibile sincronizzare un **set di dati** con un **XmlDataDocument**. È possibile:  
  
-   Popolare una **set di dati** con lo schema (vale a dire una struttura relazionale) e i dati, quindi sincronizzarlo con un nuovo oggetto **XmlDataDocument**. In questo modo si otterrà una visualizzazione gerarchica dei dati relazionali esistenti. Ad esempio:  
  
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
  
-   Popolare una **set di dati** con solo schema (ad esempio una classe fortemente tipizzata **set di dati**), sincronizzarlo con un **XmlDataDocument**e quindi caricare il  **XmlDataDocument** da un documento XML. In questo modo si otterrà una visualizzazione relazionale dei dati gerarchici esistenti. I nomi di tabella e i nomi di colonna il **set di dati** dello schema deve corrispondere ai nomi degli elementi XML desiderati siano sincronizzati. Questo tipo di associazione rileva la differenza tra maiuscole e minuscole.  
  
     Si noti che lo schema del **set di dati** solo deve corrispondere gli elementi XML che si desidera esporre nella visualizzazione relazionale. È quindi possibile disporre di un documento XML di grandi dimensioni e di una "finestra" relazionale molto piccola su tale documento. Il **XmlDataDocument** mantiene anche se l'intero documento XML le **DataSet** espone solo una piccola parte di esso. (Per un esempio dettagliato, vedere [sincronizza un set di dati con un XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)  
  
     Esempio di codice seguente illustra i passaggi per la creazione di un **set di dati** e la compilazione dello schema, quindi la sincronizzazione con un **XmlDataDocument**. Si noti che il **set di dati** dello schema deve solo corrispondere gli elementi dalle **XmlDataDocument** che si desidera esporre mediante il **set di dati**.  
  
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
  
     Non è possibile caricare un' **XmlDataDocument** se è stata sincronizzata con un **DataSet** che contiene i dati. Se si tenta di eseguire tale operazione, verrà generata un'eccezione.  
  
-   Creare una nuova **XmlDataDocument** e caricarlo da un documento XML e quindi accedere alla visualizzazione relazionale dei dati tramite il **set di dati** proprietà del **XmlDataDocument**. È necessario impostare lo schema del **set di dati** prima di poter visualizzare i dati nel **XmlDataDocument** utilizzando il **set di dati**. Anche in questo caso, i nomi di nomi di tabella e colonna nel **set di dati** dello schema deve corrispondere ai nomi degli elementi XML desiderati siano sincronizzati. Questo tipo di associazione rileva la differenza tra maiuscole e minuscole.  
  
     Esempio di codice seguente viene illustrato come accedere alla visualizzazione relazionale dei dati in un' **XmlDataDocument**.  
  
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
  
 Un altro vantaggio della sincronizzazione di un **XmlDataDocument** con un **DataSet** è di mantenere la fedeltà di un documento XML. Se il **set di dati** viene popolato da un documento XML usando **ReadXml**, quando i dati vengono riscritti come un documento XML usando **WriteXml** possono variare notevolmente dal documento XML originale. Infatti, il **set di dati** non conserva la formattazione, ad esempio spazi vuoti o le informazioni gerarchiche, ad esempio ordine degli elementi, il documento XML. Il **set di dati** inoltre non contiene elementi dal documento XML che sono stati ignorati perché lo schema di cui non corrisponde la **set di dati**. La sincronizzazione di un **XmlDataDocument** con un **set di dati** consente di formattazione e gerarchica della struttura dell'elemento del documento XML originale venga mantenuto nel **XmlDataDocument**, mentre la **set di dati** contiene sole i dati e le informazioni appropriate per il **DataSet**.  
  
 Durante la sincronizzazione una **set di dati** con un **XmlDataDocument**, i risultati possono variare a seconda se il <xref:System.Data.DataRelation> gli oggetti sono annidati. Per altre informazioni, vedere [annidamento di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Sincronizzazione di un oggetto DataSet con un oggetto XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Spiega come sincronizzare un oggetto fortemente tipizzato **set di dati**, con uno schema minimo, con un **XmlDataDocument**.  
  
 [Esecuzione di una query XPath in un oggetto DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 Viene illustrata l'esecuzione di una query XPath sul contenuto di un **set di dati**.  
  
 [Applicazione di una trasformazione XSLT a un oggetto DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 Illustra l'applicazione di una trasformazione XSLT al contenuto di un **set di dati**.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Viene descritto come la **set di dati** interagisce con il codice XML come origine dati, inclusi il caricamento e salvataggio permanente il contenuto di un **set di dati** come dati XML.  
  
 [Annidamento di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 Viene illustrata l'importanza di annidato **DataRelation** oggetti una rappresentazione del contenuto di un **DataSet** come dati XML e viene descritto come creare queste relazioni.  
  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Descrive la **set di dati** e come usarlo per gestire i dati dell'applicazione e interagire con le origini dati, inclusi database relazionali e XML.  
  
 <xref:System.Xml.XmlDataDocument>  
 Contiene informazioni di riferimento sui **XmlDataDocument** classe.  
  
## <a name="see-also"></a>Vedere anche

- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
