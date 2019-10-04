---
title: Scrittura del contenuto di dataset come dati XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: 9a63e79b2fce137ba9d21db861850a471cb42b9f
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833959"
---
# <a name="writing-dataset-contents-as-xml-data"></a>Scrittura del contenuto di dataset come dati XML
In ADO.NET è possibile scrivere una rappresentazione XML di un <xref:System.Data.DataSet>, con o senza schema. Se le informazioni relative allo schema sono incluse inline con il flusso o documento XML, tali informazioni verranno scritte usando il linguaggio XSD (XML Schema Definition Language). Nello schema sono contenute le definizioni delle tabelle del <xref:System.Data.DataSet>, oltre alle definizioni delle relazioni e dei vincoli.  
  
 Quando un <xref:System.Data.DataSet> viene scritto sotto forma di dati XML, le righe del <xref:System.Data.DataSet> vengono scritte usando le versioni correnti. È tuttavia possibile scrivere un <xref:System.Data.DataSet> in formato DiffGram, in modo da consentire l'inclusione sia dei valori correnti che dei valori originali delle righe.  
  
 La rappresentazione XML di <xref:System.Data.DataSet> può essere scritta in un file, un flusso, un **XmlWriter**o una stringa. Queste opzioni forniscono una notevole flessibilità per la modalità di trasporto della rappresentazione XML del <xref:System.Data.DataSet>. Per ottenere la rappresentazione XML di <xref:System.Data.DataSet> come stringa, usare il metodo **GetXml** , come illustrato nell'esempio seguente.  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 **GetXml** restituisce la rappresentazione XML del <xref:System.Data.DataSet> senza informazioni sullo schema. Per scrivere le informazioni sullo schema da <xref:System.Data.DataSet> (come XML Schema) a una stringa, usare **GetXmlSchema**.  
  
 Per scrivere un <xref:System.Data.DataSet> in un file, un flusso o un **XmlWriter**, usare il metodo **WriteXml** . Il primo parametro passato a **WriteXml** è la destinazione dell'output XML. Ad esempio, passare una stringa contenente un nome file, un oggetto **System. io. TextWriter** e così via. È possibile passare un secondo parametro facoltativo di un **XmlWriteMode** per specificare la modalità di scrittura dell'output XML.  
  
 Nella tabella seguente vengono illustrate le opzioni per **XmlWriteMode**.  
  
|Opzione XmlWriteMode|Descrizione|  
|-------------------------|-----------------|  
|**IgnoreSchema**|Scrive i contenuti correnti del <xref:System.Data.DataSet> sotto forma di dati XML, senza schema XML. Questa è l'impostazione predefinita.|  
|**WriteSchema**|Scrive il contenuto corrente dell'oggetto <xref:System.Data.DataSet> come dati XML con la struttura relazionale come XML Schema inline.|  
|**DiffGram**|Scrive l'intero oggetto <xref:System.Data.DataSet> come DiffGram, inclusi i valori originali e quelli correnti. Per ulteriori informazioni, vedere [DiffGram](diffgrams.md).|  
  
 Quando si scrive una rappresentazione XML di un <xref:System.Data.DataSet> che contiene oggetti **DataRelation** , è probabile che il codice XML risultante abbia le righe figlio di ogni relazione annidata all'interno dei relativi elementi padre. A tale scopo, impostare la proprietà **Nested** di **DataRelation** su **true** quando si aggiunge la **DataRelation** a <xref:System.Data.DataSet>. Per ulteriori informazioni, vedere [nidificazione di oggetti DataRelation](nesting-datarelations.md).  
  
 Di seguito sono riportati due esempi di come scrivere la rappresentazione XML di un <xref:System.Data.DataSet> in un file. Nel primo esempio il nome file per il codice XML risultante viene passato come stringa a **WriteXml**. Nel secondo esempio viene passato un oggetto **System. io. StreamWriter** .
  
```vb  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema)  
```  
  
```csharp  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema);  
```  
  
```vb  
Dim xmlSW As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xml")  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema)  
xmlSW.Close()  
```  
  
```csharp  
System.IO.StreamWriter xmlSW = new System.IO.StreamWriter("Customers.xml");  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema);  
xmlSW.Close();  
```  
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a>Mapping di colonne a elementi, attributi e testo XML  
 È possibile specificare il modo in cui una colonna di una tabella viene rappresentata in XML utilizzando la proprietà **ColumnMapping** dell'oggetto **DataColumn** . Nella tabella seguente vengono illustrati i diversi valori **MappingType** per la proprietà **ColumnMapping** di una colonna di tabella e il codice XML risultante.  
  
|Valore MappingType|Descrizione|  
|-----------------------|-----------------|  
|**Elemento**|Questa è l'impostazione predefinita. La colonna viene scritta sotto forma di elemento XML. ColumnName rappresenta il nome dell'elemento e i contenuti della colonna vengono scritti come testo dell'elemento. Esempio:<br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**Attribute**|La colonna viene scritta sotto forma di attributo XML dell'elemento XML per la riga corrente. ColumnName rappresenta il nome dell'attributo e i contenuti della colonna vengono scritti sotto forma di valore dell'attributo. Esempio:<br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**SimpleContent**|I contenuti della colonna vengono scritti sotto forma di testo nell'elemento XML per la riga corrente. Esempio:<br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> Si noti che non è possibile impostare **simpleContent** per una colonna di una tabella con colonne di **elementi** o relazioni annidate.|  
|**Nascosto**|La colonna non viene scritta nell'output XML.|  
  
## <a name="see-also"></a>Vedere anche

- [Uso di XML in un set di dati](using-xml-in-a-dataset.md)
- [DiffGram](diffgrams.md)
- [Annidamento di oggetti DataRelation](nesting-datarelations.md)
- [Scrittura di informazioni dello schema DataSet come XSD](writing-dataset-schema-information-as-xsd.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
