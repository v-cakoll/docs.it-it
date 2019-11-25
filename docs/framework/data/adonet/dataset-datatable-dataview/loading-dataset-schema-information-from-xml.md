---
title: Caricamento delle informazioni dello schema di dataset da XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: d834f0c4517f4ff9fe8645257d5a947c03893881
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968401"
---
# <a name="loading-dataset-schema-information-from-xml"></a>Caricamento delle informazioni dello schema di dataset da XML
Lo schema di un <xref:System.Data.DataSet> (le tabelle, le colonne, le relazioni e i vincoli) può essere definito a livello di codice, creato mediante i metodi **Fill** o **FillSchema** di un <xref:System.Data.Common.DataAdapter>oppure caricato da un documento XML. Per caricare le informazioni sullo schema del **set di dati** da un documento XML, è possibile usare il metodo **ReadXmlSchema** o **InferXmlSchema** del **set di dati**. **ReadXmlSchema** consente di caricare o dedurre le informazioni sullo schema del **set di dati** dal documento che contiene lo schema XSD (XML Schema Definition Language) o da un documento XML con XML Schema inline. **InferXmlSchema** consente di dedurre lo schema dal documento XML ignorando determinati spazi dei nomi XML specificati dall'utente.  
  
> [!NOTE]
> L'ordinamento delle tabelle in un **set di dati** potrebbe non essere mantenuto quando si utilizzano i servizi Web o la serializzazione XML per trasferire un **set di dati** creato in memoria utilizzando costrutti XSD, ad esempio relazioni annidate. Il destinatario del **set di dati** , pertanto, non deve dipendere dall'ordine delle tabelle in questo caso. Tuttavia, l'ordine delle tabelle viene sempre mantenuto se lo schema del **set di dati** trasferito è stato letto da file XSD anziché essere creato in memoria.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 Per caricare lo schema di un **DataSet** da un documento XML senza caricare dati, è possibile usare il metodo **ReadXmlSchema** del **DataSet**. **ReadXmlSchema** crea lo schema del **set di dati** definito utilizzando lo schema XSD (XML Schema Definition Language).  
  
 Il metodo **ReadXmlSchema** accetta un solo argomento di un nome file, un flusso o un **XmlReader** che contiene il documento XML da caricare. È possibile che nel documento XML sia contenuto solo lo schema, oppure che in tale documento sia contenuto lo schema inline con elementi XML contenenti dati. Per informazioni dettagliate sulla scrittura di uno schema inline come XML Schema, vedere [derivazione della struttura relazionale di DataSet da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Se il documento XML passato a **ReadXmlSchema** non contiene informazioni sullo schema inline, **ReadXmlSchema** dedurrà lo schema dagli elementi nel documento XML. Se il **set di dati** contiene già uno schema, lo schema corrente verrà esteso mediante l'aggiunta di nuove tabelle, se non esistono già. Nelle tabelle esistenti non verranno aggiunte nuove colonne. Se una colonna aggiunta esiste già nel set di **dati** ma dispone di un tipo incompatibile con la colonna trovata nel codice XML, viene generata un'eccezione. Per informazioni dettagliate sul modo in cui **ReadXmlSchema** deduce uno schema da un documento XML, vedere [deduzione della struttura relazionale di DataSet da XML](inferring-dataset-relational-structure-from-xml.md).  
  
 Anche se **ReadXmlSchema** carica o deduce solo lo schema di un **set di dati**, il metodo **ReadXml** del **DataSet** carica o deduce sia lo schema che i dati contenuti nel documento XML. Per ulteriori informazioni, vedere [caricamento di un DataSet da XML](loading-a-dataset-from-xml.md).  
  
 Negli esempi di codice seguenti viene illustrato come caricare uno schema **DataSet** da un documento o flusso XML. Nel primo esempio viene illustrato come passare il nome di un file di XML Schema al metodo **ReadXmlSchema** . Nel secondo esempio viene illustrato un oggetto **System. io. StreamReader**.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As New System.IO.StreamReader("schema.xsd")
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
 È inoltre possibile indicare al **set di dati** di dedurre lo schema da un documento XML utilizzando il metodo **InferXmlSchema** del **set di dati**. **InferXmlSchema** funziona allo stesso modo di un oggetto **ReadXml** con un **XmlReadMode** di **InferSchema** (carica i dati e deduce lo schema) e **ReadXmlSchema** se il documento letto non contiene alcuno schema inline. Tuttavia, **InferXmlSchema** fornisce la funzionalità aggiuntiva che consente di specificare determinati spazi dei nomi XML da ignorare quando lo schema viene dedotto. **InferXmlSchema** accetta due argomenti obbligatori: la posizione del documento XML, specificata da un nome file, un flusso o un **XmlReader**; e una matrice di stringhe di spazi dei nomi XML che verranno ignorati dall'operazione.  
  
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
  
 A causa degli attributi specificati per gli elementi nel documento XML precedente, sia il metodo **ReadXmlSchema** che il metodo **ReadXml** con **XmlReadMode** **InferSchema** creeranno tabelle per ogni elemento nel documento: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**e **Discontinued**. Per ulteriori informazioni, vedere [deduzione della struttura relazionale di DataSet da XML](inferring-dataset-relational-structure-from-xml.md). Tuttavia, una struttura più appropriata consiste nel creare solo le tabelle **Categories** e **Products** , quindi creare le **colonne CategoryID**, **CategoryName**e **Description** nella tabella **Categories** e le **colonne ProductID**, **ReorderLevel**e **Discontinued** nella tabella **Products** . Per assicurarsi che lo schema inferito ignori gli attributi specificati negli elementi XML, usare il metodo **InferXmlSchema** e specificare lo spazio dei nomi XML per **officedata** da ignorare, come illustrato nell'esempio seguente.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>Vedere anche

- [Uso di XML in un set di dati](using-xml-in-a-dataset.md)
- [Derivazione della struttura relazionale di DataSet da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Deduzione della struttura relazionale di DataSet da XML](inferring-dataset-relational-structure-from-xml.md)
- [Caricamento di un oggetto DataSet da XML](loading-a-dataset-from-xml.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
