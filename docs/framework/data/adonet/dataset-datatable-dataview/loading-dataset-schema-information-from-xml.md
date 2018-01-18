---
title: Caricamento delle informazioni dello schema di dataset da XML
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
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8b814715782710994f18163ccfcd3db342199145
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="loading-dataset-schema-information-from-xml"></a>Caricamento delle informazioni dello schema di dataset da XML
Lo schema di un <xref:System.Data.DataSet> (relative tabelle, colonne, relazioni e vincoli) possono essere definiti a livello di codice creati il **riempimento** o **FillSchema** metodi di un <xref:System.Data.Common.DataAdapter>, o caricato da un Documento XML. Per caricare **set di dati** informazioni sullo schema da un documento XML, è possibile utilizzare il **ReadXmlSchema** o **InferXmlSchema** metodo il **setdidati**. **ReadXmlSchema** consente di caricare o inferire **set di dati** informazioni sullo schema dal documento contenente schema XML Schema definition language (XSD) o un documento XML con XML Schema inline. **InferXmlSchema** consente di inferire lo schema dal documento XML, ignorando alcuni spazi dei nomi XML specificato.  
  
> [!NOTE]
>  Ordine delle tabelle in un **DataSet** potrebbero non essere mantenute quando si utilizza servizi Web o la serializzazione XML per trasferire un **DataSet** che è stato creato in memoria usando costrutti XSD (ad esempio relazioni annidate). Pertanto, il destinatario del **DataSet** non deve dipendere ordine delle tabelle in questo caso. Tuttavia, nella tabella di ordinamento viene sempre mantenuto se lo schema del **DataSet** trasferiti è stato letto dal file XSD anziché essere creato in memoria.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 Per caricare lo schema di un **DataSet** da un documento XML senza caricare alcun dato, è possibile utilizzare il **ReadXmlSchema** metodo il **set di dati**. **ReadXmlSchema** crea **DataSet** schema definito tramite schema XML Schema definition language (XSD).  
  
 Il **ReadXmlSchema** metodo accetta un unico argomento di un nome di file, un flusso o un **XmlReader** contenente il documento XML da caricare. È possibile che nel documento XML sia contenuto solo lo schema, oppure che in tale documento sia contenuto lo schema inline con elementi XML contenenti dati. Per informazioni dettagliate sulla scrittura di uno schema inline come XML Schema, vedere [derivazione struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Se il documento XML passato a **ReadXmlSchema** non contiene alcuna informazione sullo schema inline, **ReadXmlSchema** verrà dedotto automaticamente dagli elementi nel documento XML. Se il **DataSet** contiene già uno schema, lo schema corrente verrà esteso mediante l'aggiunta di nuove tabelle se non esiste già. Nelle tabelle esistenti non verranno aggiunte nuove colonne. Se una colonna da aggiungere già esiste nel **DataSet** ma non è un tipo incompatibile con la colonna trovato nel XML, viene generata un'eccezione. Per informazioni dettagliate su come **ReadXmlSchema** deduce uno schema da un documento XML, vedere [inferenza struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).  
  
 Anche se **ReadXmlSchema** consente di caricare o inferire solo lo schema di un **set di dati**, **ReadXml** metodo il **set di dati** di caricare o inferire sia lo schema e i dati contenuti nel documento XML. Per ulteriori informazioni, vedere [durante il caricamento di un set di dati da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).  
  
 Gli esempi di codice seguente viene illustrato come caricare un **DataSet** schema da un documento o flusso XML. Nel primo esempio viene passato a un nome di file XML Schema di **ReadXmlSchema** metodo. Il secondo esempio viene illustrato un **System.IO**.  
  
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
 È anche possibile indicare il **DataSet** dedurre lo schema da un documento XML usando il **InferXmlSchema** metodo il **set di dati**. **InferXmlSchema** funziona esattamente come eseguire entrambe le operazioni **ReadXml** con un **XmlReadMode** di **InferSchema** (carica i dati, nonché inferenza dello schema) e  **ReadXmlSchema** se il documento letto è presente alcuno schema inline. Tuttavia, **InferXmlSchema** fornisce funzionalità aggiuntive di consentono di specificare particolare spazi dei nomi XML verrà ignorato durante l'inferenza dello schema. **InferXmlSchema** accetta due argomenti obbligatori: il percorso del documento XML, specificato da un nome di file, un flusso o un **XmlReader**; e una matrice di stringhe degli spazi dei nomi XML verrà ignorato dall'operazione.  
  
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
  
 A causa di attributi specificati per gli elementi nel documento XML precedente, sia il **ReadXmlSchema** (metodo) e **ReadXml** metodo con un **XmlReadMode** di **InferSchema** creeranno tabelle per ogni elemento nel documento: **categorie**, **CategoryID**, **CategoryName**, **Descrizione**, **prodotti**, **ProductID**, **ReorderLevel**, e **sospeso**. (Per ulteriori informazioni, vedere [inferenza struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) Tuttavia, una struttura più appropriata, è possibile creare solo la **categorie** e **prodotti** tabelle e quindi creare **CategoryID**, **CategoryName** , e **descrizione** colonne il **categorie** tabella, e **ProductID**, **ReorderLevel**, e **Discontinued** colonne il **prodotti** tabella. Per assicurarsi che lo schema inferito ignora gli attributi specificati negli elementi XML, utilizzare il **InferXmlSchema** (metodo) e specificare lo spazio dei nomi XML per **officedata** venga ignorato, come illustrato di esempio seguente.  
  
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
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
