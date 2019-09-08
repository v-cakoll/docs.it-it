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
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="9692c-102">Scrittura di informazioni dello schema di dataset come XSD</span><span class="sxs-lookup"><span data-stu-id="9692c-102">Writing DataSet Schema Information as XSD</span></span>
<span data-ttu-id="9692c-103">È possibile scrivere lo schema di un tipo <xref:System.Data.DataSet> sotto forma di schema XSD (XML Schema Definition Language), in modo da consentirne il trasporto, con o senza dati correlati, in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="9692c-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="9692c-104">XML schema può essere scritto in un file, in un flusso <xref:System.Xml.XmlWriter>o in una stringa. è utile per generare un set di **dati**fortemente tipizzato.</span><span class="sxs-lookup"><span data-stu-id="9692c-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="9692c-105">Per ulteriori informazioni sugli oggetti **DataSet** fortemente tipizzati, vedere DataSet [tipizzati](typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="9692c-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](typed-datasets.md).</span></span>  
  
 <span data-ttu-id="9692c-106">È possibile specificare la modalità di rappresentazione di una colonna di una tabella in XML schema utilizzando la proprietà ColumnMapping <xref:System.Data.DataColumn> dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9692c-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="9692c-107">Per ulteriori informazioni, vedere "mapping di colonne a elementi, attributi e testo XML" nella [scrittura di contenuto del set di dati come dati XML](writing-dataset-contents-as-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="9692c-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="9692c-108">Per scrivere lo schema di un **set di dati** come XML Schema, in un file, in un flusso o in un **XmlWriter**, usare il metodo **WriteXmlSchema** del **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="9692c-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="9692c-109">**WriteXmlSchema** accetta un parametro che specifica la destinazione dell'XML schema risultante.</span><span class="sxs-lookup"><span data-stu-id="9692c-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="9692c-110">Negli esempi di codice seguenti viene illustrato come scrivere lo schema XML di un **set di dati** in un file passando una stringa contenente un nome file <xref:System.IO.StreamWriter> e un oggetto.</span><span class="sxs-lookup"><span data-stu-id="9692c-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
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
  
 <span data-ttu-id="9692c-111">Per ottenere lo schema di un **set di dati** e scriverlo come stringa di XML Schema, usare il metodo **GetXmlSchema** , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9692c-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="9692c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9692c-112">See also</span></span>

- [<span data-ttu-id="9692c-113">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="9692c-113">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="9692c-114">Scrittura del contenuto di DataSet come dati XML</span><span class="sxs-lookup"><span data-stu-id="9692c-114">Writing DataSet Contents as XML Data</span></span>](writing-dataset-contents-as-xml-data.md)
- [<span data-ttu-id="9692c-115">Set di dati tipizzati</span><span class="sxs-lookup"><span data-stu-id="9692c-115">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="9692c-116">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="9692c-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="9692c-117">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9692c-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
