---
title: Generazione di dataset fortemente tipizzati
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
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 61836196d9e11d3c87c43d4faaaeff54125bf706
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="generating-strongly-typed-datasets"></a>Generazione di dataset fortemente tipizzati
Dato un XML Schema conforme allo standard XSD (XML Schema Definition Language), è possibile generare un <xref:System.Data.DataSet> fortemente tipizzato usando lo strumento XSD.exe fornito con [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].  
  
 (Per creare un file xsd dalle tabelle di database, vedere <xref:System.Data.DataSet.WriteXmlSchema%2A> o [uso di dataset in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).  
  
 Il codice seguente viene illustrata la sintassi per la generazione di un **DataSet** con questo strumento.  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 In questa sintassi, il `/d` direttiva richiede lo strumento per generare un **DataSet**e `/l:` indica allo strumento la lingua da utilizzare (ad esempio, c# o Visual Basic .NET). Facoltativo `/eld` direttiva specifica che è possibile utilizzare [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] per eseguire query sul generato **set di dati.** Questa opzione viene usata quando si specifica anche l'opzione `/d`. Per ulteriori informazioni, vedere [l'esecuzione di query di dataset tipizzati](../../../../../docs/framework/data/adonet/querying-typed-datasets.md). Facoltativo `/n:` direttiva richiede lo strumento per generare anche uno spazio dei nomi per il **DataSet** chiamato **XSDSchema**. L'output del comando è costituito dal file XSDSchemaFileName.dll, che può essere compilato e usato in un'applicazione ADO.NET. È possibile compilare il codice generato come libreria o modulo.  
  
 Nel codice seguente viene mostrata la sintassi per la compilazione del codice generato come libreria usando il compilatore C# (csc.exe).  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 La direttiva `/t:` consente di richiedere allo strumento la compilazione in una libreria e la direttiva `/r:` consente di specificare le librerie dipendenti necessarie per la compilazione. L'output del comando è costituito dal file XSDSchemaFileName.dll, che può essere passato al compilatore quando si compila un'applicazione ADO.NET con la direttiva `/r:`.  
  
 Nel codice seguente viene mostrata la sintassi usata per l'accesso allo spazio dei nomi passato a XSD.exe in un'applicazione ADO.NET.  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 L'esempio di codice seguente viene utilizzato un oggetto tipizzato **DataSet** denominato **CustomerDataSet** per caricare un elenco di clienti il **Northwind** database. Una volta caricati i dati utilizzando il **riempimento** (metodo), l'esempio scorre in ciclo ogni cliente nel **clienti** tabella utilizzando l'oggetto tipizzato **CustomersRow** ( **DataRow**) oggetto. Fornisce l'accesso diretto al **CustomerID** colonna, in contrapposizione a tramite il **DataColumnCollection**.  
  
```vb  
Dim customers As CustomerDataSet= New CustomerDataSet()  
Dim adapter As SqlDataAdapter New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers;", _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=Northwind")  
  
adapter.Fill(customers, "Customers")  
  
Dim customerRow As CustomerDataSet.CustomersRow  
For Each customerRow In customers.Customers  
  Console.WriteLine(customerRow.CustomerID)  
Next  
```  
  
```csharp  
CustomerDataSet customers = new CustomerDataSet();  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers;",  
  "Data Source=(local);Integrated " +  
  "Security=SSPI;Initial Catalog=Northwind");  
  
adapter.Fill(customers, "Customers");  
  
foreach(CustomerDataSet.CustomersRow customerRow in customers.Customers)  
  Console.WriteLine(customerRow.CustomerID);  
```  
  
 Di seguito viene riportato l'XML Schema usato per l'esempio.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [Set di dati tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
