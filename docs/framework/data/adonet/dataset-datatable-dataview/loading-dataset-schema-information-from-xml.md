---
title: Caricamento delle informazioni dello schema di dataset da XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 69994c546fea842ffef1c8c43d6d6f5bc35e0629
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151052"
---
# <a name="loading-dataset-schema-information-from-xml"></a>Caricamento delle informazioni dello schema di dataset da XML
Lo schema <xref:System.Data.DataSet> di un oggetto (tabelle, colonne, relazioni e vincoli) può essere definito <xref:System.Data.Common.DataAdapter>a livello di codice, creato dai metodi **Fill** o **FillSchema** di un oggetto , o caricato da un documento XML. Per caricare le informazioni sullo schema **del DataSet** da un documento XML, è possibile utilizzare il **metodo ReadXmlSchema** o **InferXmlSchema** del **DataSet**. **ReadXmlSchema** consente di caricare o dedurre le informazioni sullo schema **del DataSet** dal documento contenente lo schema XSD (XML Schema Definition Language) o da un documento XML con schema XML inline. **InferXmlSchema** consente di dedurre lo schema dal documento XML ignorando determinati spazi dei nomi XML specificati.  
  
> [!NOTE]
> L'ordinamento delle tabelle in un **DataSet** potrebbe non essere mantenuto quando si utilizzano servizi Web o la serializzazione XML per trasferire un **DataSet** creato in memoria utilizzando costrutti XSD (ad esempio relazioni annidate). Pertanto, il destinatario del **DataSet** non deve dipendere dall'ordinamento delle tabelle in questo caso. Tuttavia, l'ordine delle tabelle viene sempre mantenuto se lo schema del **DataSet** da trasferire è stato letto da file XSD, anziché essere creato in memoria.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 Per caricare lo schema di un **DataSet** da un documento XML senza caricare dati, è possibile utilizzare il metodo **ReadXmlSchema** del **DataSet**. **ReadXmlSchema** crea lo schema **DataSet** definito utilizzando lo schema XSD (XML Schema Definition Language).  
  
 Il **metodo ReadXmlSchema** accetta un singolo argomento di un nome file, un flusso o un **oggetto XmlReader** contenente il documento XML da caricare. È possibile che nel documento XML sia contenuto solo lo schema, oppure che in tale documento sia contenuto lo schema inline con elementi XML contenenti dati. Per informazioni dettagliate sulla scrittura dello schema inline come schema XML, vedere Derivazione della struttura relazionale del [DataSet dallo schema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Se il documento XML passato a **ReadXmlSchema** non contiene informazioni sullo schema inline, **ReadXmlSchema** dedurrà lo schema dagli elementi nel documento XML. Se il **DataSet** contiene già uno schema, lo schema corrente verrà esteso aggiungendo nuove tabelle se non esistono già. Nelle tabelle esistenti non verranno aggiunte nuove colonne. Se una colonna da aggiungere esiste già nel **DataSet** ma ha un tipo incompatibile con la colonna trovata nel codice XML, viene generata un'eccezione. Per informazioni dettagliate su come **ReadXmlSchema** deduce uno schema da un documento XML, vedere [Infereding DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).  
  
 Sebbene **ReadXmlSchema** carichi o deduce solo lo schema di un **DataSet,** il metodo **ReadXml** del **DataSet** carica o deduce sia lo schema che i dati contenuti nel documento XML. Per ulteriori informazioni, vedere [Caricamento di un DataSet da XML.](loading-a-dataset-from-xml.md)  
  
 Negli esempi di codice seguenti viene illustrato come caricare uno schema **DataSet** da un flusso o un documento XML. Nel primo esempio viene illustrato un nome di file XML Schema passato al metodo **ReadXmlSchema.** Nel secondo esempio viene illustrato un **oggetto System.IO.StreamReader**.  
  
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
 È inoltre possibile indicare al **DataSet** di dedurre lo schema da un documento XML utilizzando il metodo **InferXmlSchema** del **DataSet**. **InferXmlSchema** funziona allo stesso modo di **ReadXml** con un **XmlReadMode** di **InferSchema** (carica i dati e deduce lo schema) e **ReadXmlSchema** se il documento letto non contiene alcuno schema inline. Tuttavia, **InferXmlSchema** fornisce la funzionalità aggiuntiva di consentire di specificare particolari spazi dei nomi XML da ignorare quando lo schema viene dedotto. **InferXmlSchema** accetta due argomenti obbligatori: il percorso del documento XML, specificato da un nome file, un flusso o un **XmlReader**; e una matrice di stringhe di spazi dei nomi XML da ignorare dall'operazione.  
  
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
  
 A causa degli attributi specificati per gli elementi nel documento XML precedente, sia il metodo **ReadXmlSchema che** il metodo **ReadXml** con **un oggetto XmlReadMode** di **InferSchema** creerebbero tabelle per ogni elemento del documento: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**e **Discontinued**. Per ulteriori informazioni, vedere [Infering DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md). Tuttavia, una struttura più appropriata consiste nel creare solo le tabelle **Categories** e **Products** e quindi creare le colonne **CategoryID**, **CategoryName**e **Description** nella tabella **Categories** e **ProductID**, **ReorderLevel**e **Discontinued** nella tabella **Products** . Per assicurarsi che lo schema dedotto ignori gli attributi specificati negli elementi XML, utilizzare il metodo **InferXmlSchema** e specificare lo spazio dei nomi XML affinché **officedata** venga ignorato, come illustrato nell'esempio seguente.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di XML in un dataset](using-xml-in-a-dataset.md)
- [Derivazione della struttura relazionale di dataset da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Deduzione della struttura relazionale di dataset da XML](inferring-dataset-relational-structure-from-xml.md)
- [Caricamento di un dataset da XML](loading-a-dataset-from-xml.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
