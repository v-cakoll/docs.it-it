---
title: Scrittura di informazioni dello schema di dataset come XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: b2012b32b0751bc093b9b3267cbbfc2e1a408156
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="writing-dataset-schema-information-as-xsd"></a>Scrittura di informazioni dello schema di dataset come XSD
È possibile scrivere lo schema di un tipo <xref:System.Data.DataSet> sotto forma di schema XSD (XML Schema Definition Language), in modo da consentirne il trasporto, con o senza dati correlati, in un documento XML. XML Schema possono essere scritti in un file, un flusso, un <xref:System.Xml.XmlWriter>, o una stringa è utile per la generazione di un oggetto fortemente tipizzato **DataSet**. Per ulteriori informazioni su fortemente tipizzati **DataSet** degli oggetti, vedere [tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 È possibile specificare come una colonna di una tabella è rappresentata nello Schema XML utilizzando il **ColumnMapping** proprietà del <xref:System.Data.DataColumn> oggetto. Per ulteriori informazioni, vedere "Mapping di colonne a elementi, attributi e testo XML" in [scrittura contenuti di DataSet come dati XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Per scrivere lo schema di un **set di dati** sotto forma di XML Schema in un file di flusso, o **XmlWriter**, utilizzare il **WriteXmlSchema** metodo il **set di dati**. **WriteXmlSchema** accetta un parametro che specifica la destinazione dello Schema XML risultante. Gli esempi di codice seguente viene illustrato come scrivere lo Schema XML di un **DataSet** in un file passando una stringa contenente un nome file e un <xref:System.IO.StreamWriter> oggetto.  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 Per ottenere lo schema di un **DataSet** e scriverlo sotto forma di stringa di XML Schema, utilizzare il **GetXmlSchema** (metodo), come illustrato nell'esempio seguente.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Scrittura del contenuto di DataSet come dati XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [Set di dati tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
