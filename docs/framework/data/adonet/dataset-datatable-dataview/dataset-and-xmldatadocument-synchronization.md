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
# <a name="dataset-and-xmldatadocument-synchronization"></a>Sincronizzazione di DataSet e XmlDataDocument
Il tipo <xref:System.Data.DataSet> di ADO.NET fornisce una rappresentazione relazionale dei dati. Per un accesso gerarchico ai dati, è possibile usare le classi XML disponibili in .NET Framework. Questi due tipi di rappresentazione dei dati sono sempre stati usati separatamente. Tuttavia, il .NET Framework consente l'accesso sincrono in tempo reale alle rappresentazioni relazionali e gerarchiche dei dati tramite l'oggetto **DataSet** e l' <xref:System.Xml.XmlDataDocument> oggetto, rispettivamente.  
  
 Quando un **set** di dati viene sincronizzato con un **XmlDataDocument**, entrambi gli oggetti utilizzano un singolo set di dati. Ciò significa che se viene apportata una modifica al **set di dati**, la modifica viene riflessa in **XmlDataDocument**e viceversa. La relazione tra il **set** di dati e il **XmlDataDocument** crea una grande flessibilità consentendo a una singola applicazione, usando un unico set di dati, di accedere all'intera suite di servizi compilati in base al **set** di dati, ad esempio Web Form e Windows Forms controlli e finestre di progettazione di Visual Studio .NET), nonché la suite di servizi XML che include Extensible Stylesheet Language (XSL), XSL Transformations (XSLT) e XML Path Language (XPath). Non è necessario stabilire il set di servizi a cui è destinata l'applicazione poiché sono entrambi disponibili.  
  
 Esistono diversi modi per sincronizzare un **set di dati** con un **XmlDataDocument**. È possibile:  
  
- Compilare un **set** di dati con lo schema, ovvero una struttura relazionale, e i dati, quindi sincronizzarli con un nuovo **XmlDataDocument**. In questo modo si otterrà una visualizzazione gerarchica dei dati relazionali esistenti. Ad esempio:  
  
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
  
- Compilare un **set di dati** solo con schema (ad esempio un **set di dati**fortemente tipizzato), sincronizzarlo con un **XmlDataDocument**, quindi caricare l'oggetto **XmlDataDocument** da un documento XML. In questo modo si otterrà una visualizzazione relazionale dei dati gerarchici esistenti. I nomi delle tabelle e delle colonne nello schema del **set di dati** devono corrispondere ai nomi degli elementi XML con cui si desidera che vengano sincronizzati. Questo tipo di associazione rileva la differenza tra maiuscole e minuscole.  
  
     Si noti che lo schema del **set di dati** deve corrispondere solo agli elementi XML che si desidera esporre nella visualizzazione relazionale. È quindi possibile disporre di un documento XML di grandi dimensioni e di una "finestra" relazionale molto piccola su tale documento. **XmlDataDocument** conserva l'intero documento XML, anche se il set di **dati** ne espone solo una piccola parte. Per un esempio dettagliato, vedere [sincronizzazione di un DataSet con un oggetto XmlDataDocument](synchronizing-a-dataset-with-an-xmldatadocument.md).  
  
     Nell'esempio di codice seguente vengono illustrati i passaggi per la creazione di un **set di dati** e il popolamento dello schema, quindi la sincronizzazione con un **XmlDataDocument**. Si noti che lo schema del **set di dati** deve corrispondere solo agli elementi del **XmlDataDocument** che si desidera esporre utilizzando il **set di dati**.  
  
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
  
     Non è possibile caricare un **XmlDataDocument** se è sincronizzato con un **DataSet** contenente dati. Se si tenta di eseguire tale operazione, verrà generata un'eccezione.  
  
- Creare un nuovo oggetto **XmlDataDocument** e caricarlo da un documento XML, quindi accedere alla visualizzazione relazionale dei dati usando la proprietà **DataSet** dell'oggetto **XmlDataDocument**. È necessario impostare lo schema del **set** di dati prima di poter visualizzare i dati nell'oggetto **XmlDataDocument** utilizzando il **set**di dati. Anche in questo caso, i nomi delle tabelle e delle colonne nello schema del **set di dati** devono corrispondere ai nomi degli elementi XML con cui si desidera che vengano sincronizzati. Questo tipo di associazione rileva la differenza tra maiuscole e minuscole.  
  
     Nell'esempio di codice seguente viene illustrato come accedere alla visualizzazione relazionale dei dati in un oggetto **XmlDataDocument**.  
  
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
  
 Un altro vantaggio della sincronizzazione di un oggetto **XmlDataDocument** con un **DataSet** è che la fedeltà di un documento XML viene mantenuta. Se il **set** di dati viene popolato da un documento XML utilizzando **ReadXml**, quando i dati vengono riscritti come documento XML utilizzando **WriteXml** , può variare notevolmente dal documento XML originale. Questo perché il **set di dati** non mantiene la formattazione, ad esempio spazi vuoti, o informazioni gerarchiche, ad esempio l'ordine degli elementi, dal documento XML. Il **set di dati** non contiene inoltre elementi del documento XML che sono stati ignorati perché non corrispondono allo schema del **set di dati**. La sincronizzazione di un **XmlDataDocument** con un **set** di dati consente di mantenere la formattazione e la struttura gerarchica degli elementi del documento XML originale in **XmlDataDocument**, mentre il **set** di dati contiene solo dati e informazioni dello schema appropriate per il **set di dati**.  
  
 Quando si sincronizza un **set di dati** con un oggetto **XmlDataDocument**, i risultati possono variare a seconda che <xref:System.Data.DataRelation> gli oggetti siano nidificati o meno. Per ulteriori informazioni, vedere [nidificazione](nesting-datarelations.md)di oggetti DataRelation.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Sincronizzazione di un oggetto DataSet con un oggetto XmlDataDocument](synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Viene illustrata la sincronizzazione di un **DataSet**fortemente tipizzato, con uno schema minimo, con un **XmlDataDocument**.  
  
 [Esecuzione di una query XPath in un oggetto DataSet](performing-an-xpath-query-on-a-dataset.md)  
 Viene illustrata l'esecuzione di una query XPath sul contenuto di un **set di dati**.  
  
 [Applicazione di una trasformazione XSLT a un oggetto DataSet](applying-an-xslt-transform-to-a-dataset.md)  
 Viene illustrata l'applicazione di una trasformazione XSLT al contenuto di un **set di dati**.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Uso di XML in un set di dati](using-xml-in-a-dataset.md)  
 Viene descritto il modo in cui il **DataSet** interagisce con XML come origine dati, incluso il caricamento e il salvataggio permanente del contenuto di un **DataSet** come dati XML.  
  
 [Annidamento di oggetti DataRelation](nesting-datarelations.md)  
 Viene illustrata l'importanza degli oggetti DataRelation annidati quando si rappresenta il contenuto di un **DataSet** come dati XML e viene descritto come creare tali relazioni.  
  
 [Oggetti DataSet, DataTable e DataView](index.md)  
 Viene descritto il **set** di dati e viene illustrato come utilizzarlo per gestire i dati dell'applicazione e interagire con le origini dati, inclusi i database relazionali e XML.  
  
 <xref:System.Xml.XmlDataDocument>  
 Contiene informazioni di riferimento sulla classe **XmlDataDocument** .  
  
## <a name="see-also"></a>Vedere anche

- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
