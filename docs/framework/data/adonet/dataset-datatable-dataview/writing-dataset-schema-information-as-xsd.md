---
title: Scrittura di informazioni dello schema di dataset come XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 8403f9d9be88f34e473fd3512f5499193245d227
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099443"
---
# <a name="writing-dataset-schema-information-as-xsd"></a>Scrittura di informazioni dello schema di dataset come XSD
È possibile scrivere lo schema di un tipo <xref:System.Data.DataSet> sotto forma di schema XSD (XML Schema Definition Language), in modo da consentirne il trasporto, con o senza dati correlati, in un documento XML. XML Schema può essere scritto in un file, un flusso, un <xref:System.Xml.XmlWriter>, o una stringa; è utile per la generazione di un oggetto fortemente tipizzato **set di dati**. Per altre informazioni sulle fortemente tipizzate **set di dati** oggetti, vedere [tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 È possibile specificare come una colonna di una tabella verrà rappresentata in XML Schema usando il **ColumnMapping** proprietà del <xref:System.Data.DataColumn> oggetto. Per altre informazioni, vedere "Mapping di colonne a elementi XML, attributi e testo" nella [scrivere contenuti di DataSet come dati XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Per scrivere lo schema di un **set di dati** come Schema XML, in un file di flusso, o **XmlWriter**, usare il **WriteXmlSchema** metodo del **set di dati**. **WriteXmlSchema** accetta un parametro che specifica la destinazione dello Schema XML risultante. Gli esempi di codice seguenti illustrano come scrivere il XML Schema di un **set di dati** in un file passando una stringa contenente un nome file e un <xref:System.IO.StreamWriter> oggetto.  
  
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
  
 Per ottenere lo schema di un **set di dati** e scriverlo sotto forma di stringa XML Schema, utilizzare il **GetXmlSchema** metodo, come illustrato nell'esempio seguente.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di XML in un dataset](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [Scrittura del contenuto di dataset come dati XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)
- [Dataset tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)
- [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
