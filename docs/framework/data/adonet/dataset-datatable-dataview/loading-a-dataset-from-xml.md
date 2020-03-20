---
title: Caricamento di un dataset da XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: c21ed3bb31add285d64272040680433fff4e16fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151065"
---
# <a name="loading-a-dataset-from-xml"></a>Caricamento di un dataset da XML
È possibile creare il contenuto di un <xref:System.Data.DataSet> di ADO.NET da un flusso o un documento XML. Inoltre, .NET Framework consente di definire con grande flessibilità le informazioni da caricare da XML e la modalità di creazione dello schema o struttura relazionale del <xref:System.Data.DataSet>.  
  
 Per riempire <xref:System.Data.DataSet> un con i dati da XML, utilizzare il **ReadXml** metodo dell'oggetto. <xref:System.Data.DataSet> Il **metodo ReadXml** legge da un file, un flusso o un **oggetto XmlReader**e accetta come argomenti l'origine del codice XML più un argomento **Facoltativo XmlReadMode.** Per ulteriori informazioni su **XmlReader**, vedere [Lettura di dati XML con XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)). Il **ReadXml** metodo legge il contenuto del flusso <xref:System.Data.DataSet> o del documento XML e carica i dati con. Verrà inoltre creato lo schema <xref:System.Data.DataSet> relazionale del componente dal **XmlReadMode** specificato e se esiste già uno schema relazionale.  
  
 Nella tabella seguente vengono descritte le opzioni per l'argomento **XmlReadMode.**  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**Auto**|Questa è la modalità predefinita. Consente di esaminare il documento o flusso XML e di selezionare l'opzione più appropriata, nel seguente ordine:<br /><br /> - Se il codice XML è un DiffGram, viene utilizzato DiffGram.- If the XML is a **DiffGram, DiffGram** is used.<br />- Se <xref:System.Data.DataSet> l'oggetto contiene uno schema o il codice XML contiene uno schema inline, viene utilizzato **ReadSchema.- If** the contains a schema or the XML contains an inline schema, ReadSchema is used.<br />- Se <xref:System.Data.DataSet> l'oggetto non contiene uno schema e il codice XML non contiene uno schema inline, viene utilizzato **InferSchema.**<br /><br /> Se si conosce il formato del codice XML letto, per ottenere prestazioni ottimali, è consigliabile impostare un **XmlReadMode**esplicito, anziché accettare l'impostazione predefinita **Auto.**|  
|**ReadSchema**|Consente di leggere gli schemi inline e di caricare i dati e lo schema.<br /><br /> Se nel <xref:System.Data.DataSet> è già presente uno schema, vengono aggiunte nuove tabelle dallo schema inline allo schema esistente nel <xref:System.Data.DataSet>. Se nel <xref:System.Data.DataSet> sono già presenti delle tabelle dello schema inline, viene generata un'eccezione. Non sarà possibile modificare lo schema di una tabella esistente utilizzando **XmlReadMode.ReadSchema**.<br /><br /> Se nel <xref:System.Data.DataSet> non è presente uno schema e non si dispone di uno schema inline, non verrà letto alcun dato.<br /><br /> È possibile definire lo schema inline usando lo schema XSD (XML Schema Definition Language). Per informazioni dettagliate sulla scrittura dello schema inline come schema XML, vedere Derivazione della struttura relazionale del [DataSet dallo schema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Consente di ignorare eventuali schemi inline e di caricare i dati nello schema del <xref:System.Data.DataSet> esistente. Eventuali dati non corrispondenti allo schema esistente vengono eliminati. Se nel <xref:System.Data.DataSet> non è presente alcuno schema, non verrà caricato alcun dato.<br /><br /> Se i dati sono Un DiffGram, **IgnoreSchema** ha la stessa funzionalità di **DiffGram** *.*|  
|**InferSchema**|Consente di ignorare eventuali schemi inline e di inferire uno schema in base alla struttura dei dati XML, che vengono quindi caricati.<br /><br /> Se nell'oggetto <xref:System.Data.DataSet> è già contenuto uno schema, lo schema corrente verrà esteso mediante l'aggiunta di colonne alle tabelle esistenti. Se non sono disponibili tabelle esistenti, non verranno aggiunte altre tabelle. Se esiste già una tabella inferita con uno spazio dei nomi diverso o se alcune colonne inferite è in conflitto con le colonne esistenti, verrà generata un'eccezione.<br /><br /> Per informazioni dettagliate su come **ReadXmlSchema** deduce uno schema da un documento XML, vedere [Infereding DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).|  
|**Diffgram**|Consente di leggere un DiffGram e di aggiungere i dati allo schema corrente. **DiffGram** unisce le nuove righe con le righe esistenti in cui i valori dell'identificatore univoco corrispondono. Vedere la nota relativa a "Unione di dati da XML" alla fine di questo argomento. Per ulteriori informazioni sui DiffGram, vedere [DiffGrams](diffgrams.md).|  
|**Frammento**|Consente di continuare a leggere più frammenti XML fino al raggiungimento della fine del flusso. I frammenti corrispondenti allo schema del <xref:System.Data.DataSet> vengono aggiunti alle tabelle appropriate. I frammenti non corrispondenti allo schema <xref:System.Data.DataSet> vengono eliminati.|  
  
> [!NOTE]
> Se si passa un **XmlReader** a **ReadXml** posizionato a parte del modo in un documento XML, **ReadXml** leggerà il nodo elemento successivo e lo considererà come l'elemento radice, leggendo fino alla fine del nodo elemento. Ciò non si applica se si specifica **XmlReadMode.Fragment**.  
  
## <a name="dtd-entities"></a>Entità DTD  
 Se il codice XML contiene entità definite in uno schema DTD (Document Type Definition), verrà generata un'eccezione se si tenta di caricare un <xref:System.Data.DataSet> oggetto passando un nome file, un flusso o una non **convalidaggio di XmlReader** a **ReadXml**. È invece necessario creare un **XmlValidatingReader**, con **EntityHandling** impostato su **EntityHandling.ExpandEntities**, e passare **XmlValidatingReader** a **ReadXml**. **XmlValidatingReader** espanderà le entità prima di <xref:System.Data.DataSet>essere lette dal file .  
  
 Negli esempi di codice seguenti viene illustrato come caricare un <xref:System.Data.DataSet> da un flusso XML. Nel primo esempio viene illustrato un nome di file passato al metodo **ReadXml.** Nel secondo esempio viene mostrato il caricamento di una stringa contenente XML tramite <xref:System.IO.StringReader>.  
  
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
> Se si chiama **ReadXml** per caricare un file di grandi dimensioni, è possibile riscontrare un rallentamento delle prestazioni. Per garantire prestazioni ottimali per **ReadXml**, <xref:System.Data.DataTable.BeginLoadData%2A> in un file <xref:System.Data.DataSet>di grandi dimensioni, chiamare il metodo per ogni tabella in , quindi **chiamare ReadXml**. Chiamare infine <xref:System.Data.DataTable.EndLoadData%2A> per ogni tabella del <xref:System.Data.DataSet>, come indicato nell'esempio seguente.  
  
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
> Se lo schema <xref:System.Data.DataSet> XSD per l'oggetto include un **targetNamespace**, i dati potrebbero non <xref:System.Data.DataSet> essere letti e potrebbero verificarsi eccezioni quando si chiama **ReadXml** per caricare l'oggetto con CODICE XML che contiene elementi senza spazio dei nomi qualificante. Per leggere gli elementi non qualificati in questo caso, impostare **elementFormDefault** uguale a "qualified" nello schema XSD. Ad esempio:  
  
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
 Se nell'oggetto <xref:System.Data.DataSet> sono già presenti dati, i nuovi dati provenienti dal flusso o dal documento XML vengono aggiunti ai dati presenti nell'oggetto <xref:System.Data.DataSet>. **ReadXml** non esegue l'unione <xref:System.Data.DataSet> dal codice XML nelle informazioni di riga con le chiavi primarie corrispondenti. Per sovrascrivere le informazioni sulle righe esistenti con nuove informazioni provenienti <xref:System.Data.DataSet> da <xref:System.Data.DataSet>XML, utilizzare **ReadXml** per creare un nuovo <xref:System.Data.DataSet>file , quindi <xref:System.Data.DataSet.Merge%2A> il nuovo nel file esistente . Si noti che il caricamento di un DiffGram utilizzando **ReadXML** con un **XmlReadMode** di **DiffGram** unirà le righe che hanno lo stesso identificatore univoco.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [Utilizzo di XML in un dataset](using-xml-in-a-dataset.md)
- [DiffGram](diffgrams.md)
- [Derivazione della struttura relazionale di dataset da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Deduzione della struttura relazionale di dataset da XML](inferring-dataset-relational-structure-from-xml.md)
- [Caricamento delle informazioni dello schema di dataset da XML](loading-dataset-schema-information-from-xml.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
