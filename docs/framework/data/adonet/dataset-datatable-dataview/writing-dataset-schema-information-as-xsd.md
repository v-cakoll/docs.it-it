---
title: Scrittura di informazioni dello schema di dataset come XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: f86e9100489ddf35d8ef5f98e386306a7dbfd4ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784175"
---
# <a name="writing-dataset-schema-information-as-xsd"></a>Scrittura di informazioni dello schema di dataset come XSD
È possibile scrivere lo schema di un tipo <xref:System.Data.DataSet> sotto forma di schema XSD (XML Schema Definition Language), in modo da consentirne il trasporto, con o senza dati correlati, in un documento XML. XML schema può essere scritto in un file, in un flusso <xref:System.Xml.XmlWriter>o in una stringa. è utile per generare un set di **dati**fortemente tipizzato. Per ulteriori informazioni sugli oggetti **DataSet** fortemente tipizzati, vedere DataSet [tipizzati](typed-datasets.md).  
  
 È possibile specificare la modalità di rappresentazione di una colonna di una tabella in XML schema utilizzando la proprietà ColumnMapping <xref:System.Data.DataColumn> dell'oggetto. Per ulteriori informazioni, vedere "mapping di colonne a elementi, attributi e testo XML" nella [scrittura di contenuto del set di dati come dati XML](writing-dataset-contents-as-xml-data.md).  
  
 Per scrivere lo schema di un **set di dati** come XML Schema, in un file, in un flusso o in un **XmlWriter**, usare il metodo **WriteXmlSchema** del **set di dati**. **WriteXmlSchema** accetta un parametro che specifica la destinazione dell'XML schema risultante. Negli esempi di codice seguenti viene illustrato come scrivere lo schema XML di un **set di dati** in un file passando una stringa contenente un nome file <xref:System.IO.StreamWriter> e un oggetto.  
  
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
  
 Per ottenere lo schema di un **set di dati** e scriverlo come stringa di XML Schema, usare il metodo **GetXmlSchema** , come illustrato nell'esempio seguente.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a>Vedere anche

- [Uso di XML in un set di dati](using-xml-in-a-dataset.md)
- [Scrittura del contenuto di DataSet come dati XML](writing-dataset-contents-as-xml-data.md)
- [Set di dati tipizzati](typed-datasets.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
