---
title: Caricamento delle informazioni dello schema di dataset da XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: a076dcbbe79a7ec0dfbd727e0d0c752bd4675eef
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515982"
---
# <a name="loading-dataset-schema-information-from-xml"></a>Caricamento delle informazioni dello schema di dataset da XML
Lo schema di un <xref:System.Data.DataSet> (le tabelle, colonne, relazioni e vincoli) possono essere definiti a livello di codice creati dal **riempire** o **FillSchema** metodi di un <xref:System.Data.Common.DataAdapter>, o caricato da un Documento XML. Per caricare **set di dati** informazioni sullo schema da un documento XML, è possibile usare il **ReadXmlSchema** o la **InferXmlSchema** metodo il **set di dati**. **ReadXmlSchema** consente di caricare o inferire **set di dati** informazioni sullo schema dal documento contenente schema di XML Schema definition language (XSD) o un documento XML con XML Schema inline. **InferXmlSchema** consente di inferire lo schema dal documento XML, ignorando alcuni spazi dei nomi XML specificato.  
  
> [!NOTE]
>  Ordine delle tabelle in un **set di dati** potrebbero non essere mantenute quando si usa servizi Web o la serializzazione XML per trasferire una **DataSet** che è stato creato in memoria usando costrutti XSD (ad esempio relazioni annidate). Pertanto, il destinatario del **set di dati** dovrebbe fare affidamento sull'ordine delle tabelle in questo caso. Tuttavia, ordine delle tabelle viene sempre mantenuto se lo schema del **set di dati** in fase di trasferimento è stato letto dal file XSD anziché essere creato in memoria.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 Per caricare lo schema di un **set di dati** da un documento XML senza caricare alcun dato, è possibile utilizzare il **ReadXmlSchema** metodo per il **set di dati**. **ReadXmlSchema** consente di creare **set di dati** allo schema definito tramite schema di XML Schema definition language (XSD).  
  
 Il **ReadXmlSchema** metodo accetta un singolo argomento di un nome di file, un flusso, o un' **XmlReader** contenente il documento XML da caricare. È possibile che nel documento XML sia contenuto solo lo schema, oppure che in tale documento sia contenuto lo schema inline con elementi XML contenenti dati. Per informazioni dettagliate sulla scrittura di uno schema inline come XML Schema, vedere [derivazione struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Se il documento XML passato al **ReadXmlSchema** non contiene alcuna informazione, lo schema inline **ReadXmlSchema** lo schema dagli elementi nel documento XML. Se il **set di dati** contiene già uno schema, lo schema corrente verrà esteso mediante l'aggiunta di nuove tabelle se non esistono già. Nelle tabelle esistenti non verranno aggiunte nuove colonne. Se una colonna da aggiungere già esiste nel **set di dati** ma ha un tipo incompatibile con la colonna trovato nel XML schema, viene generata un'eccezione. Per informazioni dettagliate sul **ReadXmlSchema** deduce uno schema da un documento XML, vedere [deduzione struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).  
  
 Sebbene **ReadXmlSchema** caricare o inferire solo lo schema di un **set di dati**, il **ReadXml** metodo del **set di dati** caricare o inferire sia lo schema e i dati contenuti nel documento XML. Per altre informazioni, vedere [caricamento di un DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).  
  
 Gli esempi di codice seguenti illustrano come caricare un **set di dati** dello schema da un documento o flusso XML. Nel primo esempio viene usato un nome di file XML Schema passato per il **ReadXmlSchema** (metodo). Il secondo esempio viene illustrato un **StreamReader**.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As System.IO.StreamReader = New System.IO.StreamReader ("schema.xsd");  
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
  
## <a name="inferxmlschema"></a>InferXmlSchema  
 È possibile anche istruire il **set di dati** dedurre lo schema da un documento XML usando la **InferXmlSchema** metodo per il **set di dati**. **InferXmlSchema** funziona esattamente come eseguire entrambe le operazioni **ReadXml** con un **XmlReadMode** dei **InferSchema** (carica i dati, nonché deduce lo schema) e **ReadXmlSchema** se il documento letto è presente alcuno schema inline. Tuttavia **InferXmlSchema** fornisce ulteriore possibilità, consentendo di specificare spazi dei nomi XML specifico deve essere ignorata quando lo schema viene dedotto. **InferXmlSchema** accetta due argomenti necessari: il percorso del documento XML, specificato da un nome di file, un flusso, o un' **XmlReader**; e una matrice di stringhe degli spazi dei nomi XML verrà ignorato dall'operazione.  
  
 Ad esempio, si consideri il seguente codice XML:  
  
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
  
 A causa di attributi specificati per gli elementi nel documento XML precedente, sia la **ReadXmlSchema** metodo e il **ReadXml** metodo con un **XmlReadMode** di **InferSchema** creeranno tabelle per ogni elemento nel documento: **categorie**, **CategoryID**, **CategoryName**, **Descrizione**, **prodotti**, **ProductID**, **ReorderLevel**, e **sospeso**. (Per altre informazioni, vedere [deduzione struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) Tuttavia, una struttura più appropriata, è possibile creare solo le **categorie** e **prodotti** tabelle e quindi creare **CategoryID**, **CategoryName** , e **Description** le colonne nel **categorie** tabella, e **ProductID**, **ReorderLevel**, e **Discontinued** colonne il **prodotti** tabella. Per assicurarsi che lo schema inferito ignora gli attributi specificati negli elementi XML, usare il **InferXmlSchema** (metodo) e specificare lo spazio dei nomi XML per **officedata** venga ignorato, come illustrato di esempio seguente.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Derivazione della struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [Deduzione della struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Caricamento di un oggetto DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
