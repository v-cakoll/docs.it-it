---
title: Generazione di dataset fortemente tipizzati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: f1c1fd77bed700fae8e5a658da8b267120518ca9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786301"
---
# <a name="generating-strongly-typed-datasets"></a>Generazione di dataset fortemente tipizzati
Dato un XML schema conforme allo standard XSD (XML Schema Definition Language), è possibile generare un oggetto fortemente tipizzato <xref:System.Data.DataSet> utilizzando lo strumento XSD. exe fornito con Windows Software Development Kit (SDK).  
  
 Per creare un XSD dalle tabelle di database, vedere <xref:System.Data.DataSet.WriteXmlSchema%2A> o [uso dei set di dati in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).  
  
 Nel codice seguente viene illustrata la sintassi per la generazione di un **set di dati** utilizzando questo strumento.  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 In questa sintassi, la `/d` direttiva indica allo strumento di generare un **set di dati**e `/l:` indica allo strumento quale lingua usare, ad esempio C# o Visual Basic .NET. La direttiva `/eld` facoltativa specifica che è possibile utilizzare LINQ to DataSet per eseguire query sul **set di dati generato.** Questa opzione viene usata quando si specifica anche l'opzione `/d`. Per ulteriori informazioni, vedere [esecuzione di query su DataSet tipizzati](../querying-typed-datasets.md). La direttiva `/n:` facoltativa indica allo strumento di generare anche uno spazio dei nomi per il **set di dati** denominato **XSDSchema. Namespace**. L'output del comando è costituito dal file XSDSchemaFileName.dll, che può essere compilato e usato in un'applicazione ADO.NET. È possibile compilare il codice generato come libreria o modulo.  
  
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
  
 Nell'esempio di codice seguente viene utilizzato un **set di dati** tipizzato denominato **CustomerDataSet** per caricare un elenco di clienti dal database **Northwind** . Una volta caricati i dati usando il metodo **Fill** , l'esempio scorre in ciclo ogni cliente nella tabella **Customers** usando l'oggetto tipizzato **CustomersRow** (**DataRow**). Questo consente di accedere direttamente alla colonna **CustomerID** , anziché tramite **DataColumnCollection**.  
  
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

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [Set di dati tipizzati](typed-datasets.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
