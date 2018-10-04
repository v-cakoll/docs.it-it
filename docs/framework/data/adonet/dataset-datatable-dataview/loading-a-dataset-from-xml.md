---
title: Caricamento di un dataset da XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: 3a781f17ac3cabebce17955b9a7e2edda4d4fd4b
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48582775"
---
# <a name="loading-a-dataset-from-xml"></a>Caricamento di un dataset da XML
È possibile creare il contenuto di un <xref:System.Data.DataSet> di ADO.NET da un flusso o un documento XML. Inoltre, .NET Framework consente di definire con grande flessibilità le informazioni da caricare da XML e la modalità di creazione dello schema o struttura relazionale del <xref:System.Data.DataSet>.  
  
 Per riempire un <xref:System.Data.DataSet> con i dati da XML, usare il **ReadXml** metodo il <xref:System.Data.DataSet> oggetto. Il **ReadXml** metodo legge da un file, un flusso, o un' **XmlReader**e accetta come argomenti l'origine del documento XML, oltre facoltativo **XmlReadMode** argomento. (Per ulteriori informazioni sul **XmlReader**, vedere [NIB: lettura di dati XML con XmlTextReader](https://msdn.microsoft.com/library/762c069b-b50c-41b8-936e-39eacfb0d540).) Il **ReadXml** metodo legge il contenuto del flusso XML o documento e carica il <xref:System.Data.DataSet> con i dati. Viene creata anche lo schema relazionale delle <xref:System.Data.DataSet> in base il **XmlReadMode** specificato e se esiste già uno schema relazionale.  
  
 Nella tabella seguente vengono descritte le opzioni per la **XmlReadMode** argomento.  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**Auto**|Questa è l'impostazione predefinita. Consente di esaminare il documento o flusso XML e di selezionare l'opzione più appropriata, nel seguente ordine:<br /><br /> -Se il codice XML sia un DiffGram **DiffGram** viene usato.<br />-Se il <xref:System.Data.DataSet> contiene uno schema o il XML contiene uno schema inline **ReadSchema** viene usato.<br />-Se il <xref:System.Data.DataSet> non contiene uno schema e il codice XML non contiene uno schema inline **InferSchema** viene usato.<br /><br /> Se si conosce il formato del codice XML letto, per ottenere prestazioni ottimali è consigliabile impostare l'impostazione esplicita **XmlReadMode**, anziché di accettare le **automatico** predefinito.|  
|**ReadSchema**|Consente di leggere gli schemi inline e di caricare i dati e lo schema.<br /><br /> Se nel <xref:System.Data.DataSet> è già presente uno schema, vengono aggiunte nuove tabelle dallo schema inline allo schema esistente nel <xref:System.Data.DataSet>. Se nel <xref:System.Data.DataSet> sono già presenti delle tabelle dello schema inline, viene generata un'eccezione. Non sarà in grado di modificare lo schema di una tabella esistente usando **ReadSchema**.<br /><br /> Se nel <xref:System.Data.DataSet> non è presente uno schema e non si dispone di uno schema inline, non verrà letto alcun dato.<br /><br /> È possibile definire lo schema inline usando lo schema XSD (XML Schema Definition Language). Per informazioni dettagliate sulla scrittura di uno schema inline come XML Schema, vedere [derivazione struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Consente di ignorare eventuali schemi inline e di caricare i dati nello schema del <xref:System.Data.DataSet> esistente. Eventuali dati non corrispondenti allo schema esistente vengono eliminati. Se nel <xref:System.Data.DataSet> non è presente alcuno schema, non verrà caricato alcun dato.<br /><br /> Se i dati sono un DiffGram **IgnoreSchema** ha la stessa funzionalità **DiffGram** *.*|  
|**InferSchema**|Consente di ignorare eventuali schemi inline e di inferire uno schema in base alla struttura dei dati XML, che vengono quindi caricati.<br /><br /> Se nell'oggetto <xref:System.Data.DataSet> è già contenuto uno schema, lo schema corrente verrà esteso mediante l'aggiunta di colonne alle tabelle esistenti. Se non sono disponibili tabelle esistenti, non verranno aggiunte altre tabelle. Se esiste già una tabella inferita con uno spazio dei nomi diverso o se alcune colonne inferite è in conflitto con le colonne esistenti, verrà generata un'eccezione.<br /><br /> Per informazioni dettagliate sul **ReadXmlSchema** deduce uno schema da un documento XML, vedere [deduzione struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).|  
|**DiffGram**|Consente di leggere un DiffGram e di aggiungere i dati allo schema corrente. **DiffGram** unisce le nuove righe con le righe esistenti in cui corrispondono i valori dell'identificatore univoco. Vedere la nota relativa a "Unione di dati da XML" alla fine di questo argomento. Per altre informazioni sui DiffGram, vedere [DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
|**Frammento**|Consente di continuare a leggere più frammenti XML fino al raggiungimento della fine del flusso. I frammenti corrispondenti allo schema del <xref:System.Data.DataSet> vengono aggiunti alle tabelle appropriate. I frammenti non corrispondenti allo schema <xref:System.Data.DataSet> vengono eliminati.|  
  
> [!NOTE]
>  Se si passa un' **XmlReader** al **ReadXml** che fa parte posizionati in un documento XML, il modo in cui **ReadXml** leggerà il nodo successivo dell'elemento e lo considererà come radice elemento, leggendo fino alla fine del nodo elemento solo. Questo non è applicabile se si specifica **XmlReadMode**.  
  
## <a name="dtd-entities"></a>Entità DTD  
 Se il XML contiene le entità definite in uno schema definition (DTD) di tipo documento, verrà generata un'eccezione se si tenta di caricare un <xref:System.Data.DataSet> passando un file di nome, un flusso o non convalidante **XmlReader** a  **ReadXml**. In alternativa, è necessario creare un **XmlValidatingReader**, con **EntityHandling** impostata su **ExpandEntities**e passare il  **XmlValidatingReader** al **ReadXml**. Il **XmlValidatingReader** espande le entità prima di essere lette dal <xref:System.Data.DataSet>.  
  
 Negli esempi di codice seguenti viene illustrato come caricare un <xref:System.Data.DataSet> da un flusso XML. Il primo esempio viene illustrato un nome di file passato al **ReadXml** (metodo). Nel secondo esempio viene mostrato il caricamento di una stringa contenente XML tramite <xref:System.IO.StringReader>.  
  
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
>  Se si chiama **ReadXml** per caricare un file di dimensioni molto grande, si potrebbe verificarsi un rallentamento delle prestazioni. Per ottenere prestazioni ottimali **ReadXml**, in un file di grandi dimensioni, chiamare il <xref:System.Data.DataTable.BeginLoadData%2A> metodo per ogni tabella nel <xref:System.Data.DataSet>e quindi chiamare **ReadXml**. Chiamare infine <xref:System.Data.DataTable.EndLoadData%2A> per ogni tabella del <xref:System.Data.DataSet>, come indicato nell'esempio seguente.  
  
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
>  Se lo schema XSD per il <xref:System.Data.DataSet> include un **targetNamespace**, i dati non possono essere letti e che vengano generate eccezioni, quando si chiama **ReadXml** per caricare il <xref:System.Data.DataSet> con XML che contiene elementi senza spazio dei nomi validi. Per leggere gli elementi non qualificati in questo caso, impostare **elementFormDefault** uguale a "qualified" nello schema XSD. Ad esempio:  
  
```xml  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a>Unione di dati da XML  
 Se nell'oggetto <xref:System.Data.DataSet> sono già presenti dati, i nuovi dati provenienti dal flusso o dal documento XML vengono aggiunti ai dati presenti nell'oggetto <xref:System.Data.DataSet>. **ReadXml** non vengono unite da codice XML nel <xref:System.Data.DataSet> informazioni con chiavi primarie corrispondenti a ogni riga. Per sovrascrivere le informazioni di riga esistenti con nuove informazioni provenienti da XML, usare **ReadXml** per creare un nuovo <xref:System.Data.DataSet>, quindi <xref:System.Data.DataSet.Merge%2A> nuova <xref:System.Data.DataSet> esistente <xref:System.Data.DataSet>. Si noti che il caricamento di un DiffGram mediante **ReadXML** con un **XmlReadMode** dei **DiffGram** unirà le righe che contengono lo stesso identificatore univoco.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 [Derivazione della struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [Deduzione della struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Caricamento delle informazioni dello schema DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
