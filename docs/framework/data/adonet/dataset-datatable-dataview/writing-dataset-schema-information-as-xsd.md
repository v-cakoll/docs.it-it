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
ms.locfileid: "32760999"
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="31596-102">Scrittura di informazioni dello schema di dataset come XSD</span><span class="sxs-lookup"><span data-stu-id="31596-102">Writing DataSet Schema Information as XSD</span></span>
<span data-ttu-id="31596-103">È possibile scrivere lo schema di un tipo <xref:System.Data.DataSet> sotto forma di schema XSD (XML Schema Definition Language), in modo da consentirne il trasporto, con o senza dati correlati, in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="31596-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="31596-104">XML Schema possono essere scritti in un file, un flusso, un <xref:System.Xml.XmlWriter>, o una stringa è utile per la generazione di un oggetto fortemente tipizzato **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="31596-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="31596-105">Per ulteriori informazioni su fortemente tipizzati **DataSet** degli oggetti, vedere [tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="31596-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 <span data-ttu-id="31596-106">È possibile specificare come una colonna di una tabella è rappresentata nello Schema XML utilizzando il **ColumnMapping** proprietà del <xref:System.Data.DataColumn> oggetto.</span><span class="sxs-lookup"><span data-stu-id="31596-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="31596-107">Per ulteriori informazioni, vedere "Mapping di colonne a elementi, attributi e testo XML" in [scrittura contenuti di DataSet come dati XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="31596-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="31596-108">Per scrivere lo schema di un **set di dati** sotto forma di XML Schema in un file di flusso, o **XmlWriter**, utilizzare il **WriteXmlSchema** metodo il **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="31596-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="31596-109">**WriteXmlSchema** accetta un parametro che specifica la destinazione dello Schema XML risultante.</span><span class="sxs-lookup"><span data-stu-id="31596-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="31596-110">Gli esempi di codice seguente viene illustrato come scrivere lo Schema XML di un **DataSet** in un file passando una stringa contenente un nome file e un <xref:System.IO.StreamWriter> oggetto.</span><span class="sxs-lookup"><span data-stu-id="31596-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
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
  
 <span data-ttu-id="31596-111">Per ottenere lo schema di un **DataSet** e scriverlo sotto forma di stringa di XML Schema, utilizzare il **GetXmlSchema** (metodo), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="31596-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="31596-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31596-112">See Also</span></span>  
 [<span data-ttu-id="31596-113">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="31596-113">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="31596-114">Scrittura del contenuto di DataSet come dati XML</span><span class="sxs-lookup"><span data-stu-id="31596-114">Writing DataSet Contents as XML Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [<span data-ttu-id="31596-115">Set di dati tipizzati</span><span class="sxs-lookup"><span data-stu-id="31596-115">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="31596-116">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="31596-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="31596-117">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="31596-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
