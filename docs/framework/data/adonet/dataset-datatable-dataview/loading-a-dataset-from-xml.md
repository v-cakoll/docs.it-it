---
title: Caricamento di un dataset da XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: 4c8b26651a1f4050145b6d43e03f9d4cc3d68202
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785288"
---
# <a name="loading-a-dataset-from-xml"></a>Caricamento di un dataset da XML
È possibile creare il contenuto di un <xref:System.Data.DataSet> di ADO.NET da un flusso o un documento XML. Inoltre, .NET Framework consente di definire con grande flessibilità le informazioni da caricare da XML e la modalità di creazione dello schema o struttura relazionale del <xref:System.Data.DataSet>.  
  
 Per compilare un <xref:System.Data.DataSet> <xref:System.Data.DataSet> oggetto con i dati da XML, usare il metodo **ReadXml** dell'oggetto. Il metodo **ReadXml** legge da un file, un flusso o un **XmlReader**e accetta come argomenti l'origine del codice XML più un argomento **XmlReadMode** facoltativo. Per ulteriori informazioni su **XmlReader**, vedere [lettura di dati XML con XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)). Il metodo **ReadXml** legge il contenuto del flusso o del documento XML e carica l' <xref:System.Data.DataSet> oggetto con i dati. Creerà inoltre lo schema relazionale di <xref:System.Data.DataSet> a seconda del valore di **XmlReadMode** specificato e della presenza di uno schema relazionale già esistente.  
  
 Nella tabella seguente vengono descritte le opzioni per l'argomento **XmlReadMode** .  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**Auto**|Questa è l'impostazione predefinita. Consente di esaminare il documento o flusso XML e di selezionare l'opzione più appropriata, nel seguente ordine:<br /><br /> -Se il codice XML è un DiffGram, viene utilizzato **DiffGram** .<br />-Se <xref:System.Data.DataSet> contiene uno schema o il codice XML contiene uno schema inline, viene usato **ReadSchema** .<br />-Se <xref:System.Data.DataSet> non contiene uno schema e il codice XML non contiene uno schema inline, viene usato **InferSchema** .<br /><br /> Se si conosce il formato del codice XML da leggere, per ottenere prestazioni ottimali è consigliabile impostare un **XmlReadMode**esplicito, invece di accettare il valore predefinito **automatico** .|  
|**ReadSchema**|Consente di leggere gli schemi inline e di caricare i dati e lo schema.<br /><br /> Se nel <xref:System.Data.DataSet> è già presente uno schema, vengono aggiunte nuove tabelle dallo schema inline allo schema esistente nel <xref:System.Data.DataSet>. Se nel <xref:System.Data.DataSet> sono già presenti delle tabelle dello schema inline, viene generata un'eccezione. Non sarà possibile modificare lo schema di una tabella esistente usando **XmlReadMode. ReadSchema**.<br /><br /> Se nel <xref:System.Data.DataSet> non è presente uno schema e non si dispone di uno schema inline, non verrà letto alcun dato.<br /><br /> È possibile definire lo schema inline usando lo schema XSD (XML Schema Definition Language). Per informazioni dettagliate sulla scrittura di uno schema inline come XML Schema, vedere [derivazione della struttura relazionale di DataSet da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Consente di ignorare eventuali schemi inline e di caricare i dati nello schema del <xref:System.Data.DataSet> esistente. Eventuali dati non corrispondenti allo schema esistente vengono eliminati. Se nel <xref:System.Data.DataSet> non è presente alcuno schema, non verrà caricato alcun dato.<br /><br /> Se i dati sono di DiffGram, **IgnoreSchema** ha la stessa funzionalità di **DiffGram** *.*|  
|**InferSchema**|Consente di ignorare eventuali schemi inline e di inferire uno schema in base alla struttura dei dati XML, che vengono quindi caricati.<br /><br /> Se nell'oggetto <xref:System.Data.DataSet> è già contenuto uno schema, lo schema corrente verrà esteso mediante l'aggiunta di colonne alle tabelle esistenti. Se non sono disponibili tabelle esistenti, non verranno aggiunte altre tabelle. Se esiste già una tabella inferita con uno spazio dei nomi diverso o se alcune colonne inferite è in conflitto con le colonne esistenti, verrà generata un'eccezione.<br /><br /> Per informazioni dettagliate sul modo in cui **ReadXmlSchema** deduce uno schema da un documento XML, vedere [deduzione della struttura relazionale di DataSet da XML](inferring-dataset-relational-structure-from-xml.md).|  
|**DiffGram**|Consente di leggere un DiffGram e di aggiungere i dati allo schema corrente. **DiffGram** unisce le nuove righe con le righe esistenti in cui i valori dell'identificatore univoco corrispondono. Vedere la nota relativa a "Unione di dati da XML" alla fine di questo argomento. Per ulteriori informazioni su DiffGram, vedere [DiffGram](diffgrams.md).|  
|**Frammento**|Consente di continuare a leggere più frammenti XML fino al raggiungimento della fine del flusso. I frammenti corrispondenti allo schema del <xref:System.Data.DataSet> vengono aggiunti alle tabelle appropriate. I frammenti non corrispondenti allo schema <xref:System.Data.DataSet> vengono eliminati.|  
  
> [!NOTE]
> Se si passa un oggetto **XmlReader** a **ReadXml** che è posizionato parte del percorso in un documento XML, **ReadXml** leggerà il nodo dell'elemento successivo e lo considererà come elemento radice, leggendo fino alla fine del nodo dell'elemento. Questa operazione non si applica se si specifica **XmlReadMode. Fragment**.  
  
## <a name="dtd-entities"></a>Entità DTD  
 Se il codice XML contiene entità definite in uno schema di Document Type Definition (DTD), verrà generata un'eccezione se si tenta di caricare <xref:System.Data.DataSet> un oggetto passando un nome file, un flusso o un **XmlReader** non di convalida a **ReadXml**. Al contrario, è necessario creare un **XmlValidatingReader**, con **EntityHandling** impostato su **EntityHandling. ExpandEntities**e passare il **XmlValidatingReader** a **ReadXml**. Il **XmlValidatingReader** espande le entità prima di essere lette da <xref:System.Data.DataSet>.  
  
 Negli esempi di codice seguenti viene illustrato come caricare un <xref:System.Data.DataSet> da un flusso XML. Nel primo esempio viene illustrato il passaggio di un nome di file al metodo **ReadXml** . Nel secondo esempio viene mostrato il caricamento di una stringa contenente XML tramite <xref:System.IO.StringReader>.  
  
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
> Se si chiama **ReadXml** per caricare un file di grandi dimensioni, è possibile che si verifichi un rallentamento delle prestazioni. Per garantire prestazioni ottimali per **ReadXml**, in un file di grandi dimensioni <xref:System.Data.DataTable.BeginLoadData%2A> , chiamare il metodo per <xref:System.Data.DataSet>ogni tabella in, quindi chiamare **ReadXml**. Chiamare infine <xref:System.Data.DataTable.EndLoadData%2A> per ogni tabella del <xref:System.Data.DataSet>, come indicato nell'esempio seguente.  
  
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
> Se lo schema XSD per l' <xref:System.Data.DataSet> oggetto include un **targetNamespace**, i dati potrebbero non essere letti e potrebbero verificarsi eccezioni, quando si chiama **ReadXml** per caricare <xref:System.Data.DataSet> l'oggetto con XML che contiene elementi senza spazio dei nomi idoneo. Per leggere gli elementi non qualificati, in questo caso, impostare **elementFormDefault** uguale a "qualified" nello schema XSD. Ad esempio:  
  
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
 Se nell'oggetto <xref:System.Data.DataSet> sono già presenti dati, i nuovi dati provenienti dal flusso o dal documento XML vengono aggiunti ai dati presenti nell'oggetto <xref:System.Data.DataSet>. **ReadXml** non esegue il merge dal codice XML <xref:System.Data.DataSet> alle informazioni sulle righe con chiavi primarie corrispondenti. Per sovrascrivere le informazioni sulle righe esistenti con nuove informazioni da XML, usare **ReadXml** per <xref:System.Data.DataSet>creare un nuovo <xref:System.Data.DataSet.Merge%2A> oggetto, <xref:System.Data.DataSet> quindi il nuovo <xref:System.Data.DataSet>nell'oggetto esistente. Si noti che il caricamento di un DiffGram utilizzando **ReadXml** con un **XmlReadMode** di **DiffGram** unirà le righe con lo stesso identificatore univoco.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [Uso di XML in un set di dati](using-xml-in-a-dataset.md)
- [DiffGram](diffgrams.md)
- [Derivazione della struttura relazionale di DataSet da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Deduzione della struttura relazionale di DataSet da XML](inferring-dataset-relational-structure-from-xml.md)
- [Caricamento delle informazioni dello schema DataSet da XML](loading-dataset-schema-information-from-xml.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
