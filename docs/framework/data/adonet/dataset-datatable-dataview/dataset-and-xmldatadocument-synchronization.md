---
title: Sincronizzazione di DataSet e XmlDataDocument
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
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9cdfdf01b950d13ba77f76b126fe6d2ff430ef07
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="dataset-and-xmldatadocument-synchronization"></a>Sincronizzazione di DataSet e XmlDataDocument
Il tipo <xref:System.Data.DataSet> di ADO.NET fornisce una rappresentazione relazionale dei dati. Per un accesso gerarchico ai dati, è possibile usare le classi XML disponibili in .NET Framework. Questi due tipi di rappresentazione dei dati sono sempre stati usati separatamente. .NET Framework consente tuttavia l'accesso in tempo reale modalità sincrona alle rappresentazioni sia relazionali sia gerarchiche di dati tramite il **DataSet** oggetto e <xref:System.Xml.XmlDataDocument> dell'oggetto, rispettivamente.  
  
 Quando un **DataSet** è sincronizzato con un **XmlDataDocument**, entrambi gli oggetti utilizzano un singolo set di dati. Ciò significa che se viene apportata una modifica per il **DataSet**, la modifica verrà riflessa nel **XmlDataDocument**e viceversa. La relazione tra il **DataSet** e **XmlDataDocument** crea una notevole flessibilità, consentendo una singola applicazione, utilizzando un unico set di dati, per accedere l'intero gruppo di servizi creati racchiudere il **set di dati** (ad esempio controlli Windows Form e Web Form e le finestre di progettazione di Visual Studio .NET), nonché la suite di servizi XML, incluso foglio di stile XSL (Extensible Language), XSL Transformations (XSLT) e il percorso XML Language (XPath). Non è necessario stabilire il set di servizi a cui è destinata l'applicazione poiché sono entrambi disponibili.  
  
 Esistono diversi modi che è possibile sincronizzare un **DataSet** con un **XmlDataDocument**. È possibile:  
  
-   Popolare un **DataSet** con uno schema (ovvero, una struttura relazionale) e i dati, quindi sincronizzarlo con un nuovo **XmlDataDocument**. In questo modo si otterrà una visualizzazione gerarchica dei dati relazionali esistenti. Ad esempio:  
  
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
  
-   Popolare un **DataSet** con solo schema (ad esempio un oggetto fortemente tipizzato **set di dati**), sincronizzarlo con un **XmlDataDocument**e quindi caricare il  **XmlDataDocument** da un documento XML. In questo modo si otterrà una visualizzazione relazionale dei dati gerarchici esistenti. I nomi di tabella e i nomi di colonna il **DataSet** schema deve corrispondere ai nomi degli elementi XML che si desidera che siano sincronizzati. Questo tipo di associazione rileva la differenza tra maiuscole e minuscole.  
  
     Si noti che lo schema del **DataSet** solo deve corrispondere gli elementi XML che si desidera esporre nella visualizzazione relazionale. È quindi possibile disporre di un documento XML di grandi dimensioni e di una "finestra" relazionale molto piccola su tale documento. Il **XmlDataDocument** mantiene l'intero documento XML, anche se il **DataSet** espone solo una piccola parte di esso. (Per un esempio dettagliato, vedere [la sincronizzazione di un set di dati con un XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)  
  
     Esempio di codice seguente vengono illustrati i passaggi per la creazione di un **DataSet** e la compilazione dello schema e la sincronizzazione con un **XmlDataDocument**. Si noti che il **DataSet** schema deve solo gli elementi da corrispondere il **XmlDataDocument** che si desidera esporre mediante il **set di dati**.  
  
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
  
     Non è possibile caricare un **XmlDataDocument** se è sincronizzata con un **DataSet** che contiene i dati. Se si tenta di eseguire tale operazione, verrà generata un'eccezione.  
  
-   Creare un nuovo **XmlDataDocument** e caricarlo da un documento XML e quindi accedere alla visualizzazione relazionale dei dati mediante il **DataSet** proprietà del **XmlDataDocument**. È necessario impostare lo schema del **DataSet** prima di poter visualizzare i dati nel **XmlDataDocument** utilizzando il **set di dati**. Nuovamente, i nomi di nomi di tabella e colonna nel **DataSet** schema deve corrispondere ai nomi degli elementi XML che si desidera che siano sincronizzati. Questo tipo di associazione rileva la differenza tra maiuscole e minuscole.  
  
     Esempio di codice seguente viene illustrato come accedere alla visualizzazione relazionale dei dati in un **XmlDataDocument**.  
  
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
  
 Un altro vantaggio della sincronizzazione un **XmlDataDocument** con un **set di dati** è di mantenere la fedeltà di un documento XML. Se il **DataSet** viene popolato da un documento XML usando **ReadXml**, quando i dati vengono riscritti come documento XML utilizzando **WriteXml** possono variare notevolmente dal documento XML originale. In questo modo il **DataSet** non conserva la formattazione, ad esempio gli spazi vuoti o le informazioni gerarchiche, ad esempio ordine degli elementi, il documento XML. Il **set di dati** inoltre non contiene gli elementi del documento XML che sono stati ignorati perché lo schema di non corrispondenti di **set di dati**. Sincronizzazione di un **XmlDataDocument** con un **set di dati** consente la struttura dell'elemento gerarchica e formattazione del documento XML originale venga mantenuto nel **XmlDataDocument**, mentre il **DataSet** contiene solo dati e le informazioni appropriate per il **DataSet**.  
  
 Durante la sincronizzazione di un **set di dati** con un **XmlDataDocument**, possono ottenere risultati differenti a seconda se il <xref:System.Data.DataRelation> gli oggetti sono annidati. Per ulteriori informazioni, vedere [annidamento di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Sincronizzazione di un oggetto DataSet con un oggetto XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Viene illustrata la sincronizzazione di un oggetto fortemente tipizzato **DataSet**, con uno schema minimo, con un **XmlDataDocument**.  
  
 [Esecuzione di una query XPath in un oggetto DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 Viene illustrata l'esecuzione di una query XPath sul contenuto di un **DataSet**.  
  
 [Applicazione di una trasformazione XSLT a un oggetto DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 Viene illustrata l'applicazione di una trasformazione XSLT al contenuto di un **DataSet**.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Viene descritto come **DataSet** interagisce con XML come origine dati, inclusi il caricamento e il mantenimento del contenuto di un **set di dati** come dati XML.  
  
 [Annidamento di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 Viene illustrata l'importanza di nidificata **DataRelation** degli oggetti che rappresenta il contenuto di un **set di dati** come dati XML e viene descritto come creare queste relazioni.  
  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Viene descritto il **DataSet** e come usarlo per gestire i dati dell'applicazione e di interagire con le origini dati, inclusi database relazionali e XML.  
  
 <xref:System.Xml.XmlDataDocument>  
 Contiene informazioni di riferimento sul **XmlDataDocument** classe.  
  
## <a name="see-also"></a>Vedere anche  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
