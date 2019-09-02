---
title: Generazione di dataset fortemente tipizzati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 9bff69e28aa17da87da7e94d4e110c0375f043ae
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203699"
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="f8624-102">Generazione di dataset fortemente tipizzati</span><span class="sxs-lookup"><span data-stu-id="f8624-102">Generating Strongly Typed DataSets</span></span>
<span data-ttu-id="f8624-103">Dato un XML schema conforme allo standard XSD (XML Schema Definition Language), è possibile generare un oggetto fortemente tipizzato <xref:System.Data.DataSet> utilizzando lo strumento XSD. exe fornito con Windows Software Development Kit (SDK).</span><span class="sxs-lookup"><span data-stu-id="f8624-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the Windows Software Development Kit (SDK).</span></span>  
  
 <span data-ttu-id="f8624-104">Per creare un XSD dalle tabelle di database, vedere <xref:System.Data.DataSet.WriteXmlSchema%2A> o [uso dei set di dati in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="f8624-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span></span>  
  
 <span data-ttu-id="f8624-105">Nel codice seguente viene illustrata la sintassi per la generazione di un **set di dati** utilizzando questo strumento.</span><span class="sxs-lookup"><span data-stu-id="f8624-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="f8624-106">In questa sintassi, la `/d` direttiva indica allo strumento di generare un **set di dati**e `/l:` indica allo strumento quale lingua usare, ad esempio C# o Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="f8624-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="f8624-107">La direttiva `/eld` facoltativa specifica che è possibile utilizzare LINQ to DataSet per eseguire query sul **set di dati generato.**</span><span class="sxs-lookup"><span data-stu-id="f8624-107">The optional `/eld` directive specifies that you can use LINQ to DataSet to query against the generated **DataSet.**</span></span> <span data-ttu-id="f8624-108">Questa opzione viene usata quando si specifica anche l'opzione `/d`.</span><span class="sxs-lookup"><span data-stu-id="f8624-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="f8624-109">Per ulteriori informazioni, vedere [esecuzione di query su DataSet tipizzati](../querying-typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="f8624-109">For more information, see [Querying Typed DataSets](../querying-typed-datasets.md).</span></span> <span data-ttu-id="f8624-110">La direttiva `/n:` facoltativa indica allo strumento di generare anche uno spazio dei nomi per il **set di dati** denominato **XSDSchema. Namespace**.</span><span class="sxs-lookup"><span data-stu-id="f8624-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="f8624-111">L'output del comando è costituito dal file XSDSchemaFileName.dll, che può essere compilato e usato in un'applicazione ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="f8624-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="f8624-112">È possibile compilare il codice generato come libreria o modulo.</span><span class="sxs-lookup"><span data-stu-id="f8624-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="f8624-113">Nel codice seguente viene mostrata la sintassi per la compilazione del codice generato come libreria usando il compilatore C# (csc.exe).</span><span class="sxs-lookup"><span data-stu-id="f8624-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="f8624-114">La direttiva `/t:` consente di richiedere allo strumento la compilazione in una libreria e la direttiva `/r:` consente di specificare le librerie dipendenti necessarie per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="f8624-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="f8624-115">L'output del comando è costituito dal file XSDSchemaFileName.dll, che può essere passato al compilatore quando si compila un'applicazione ADO.NET con la direttiva `/r:`.</span><span class="sxs-lookup"><span data-stu-id="f8624-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="f8624-116">Nel codice seguente viene mostrata la sintassi usata per l'accesso allo spazio dei nomi passato a XSD.exe in un'applicazione ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="f8624-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="f8624-117">Nell'esempio di codice seguente viene utilizzato un **set di dati** tipizzato denominato **CustomerDataSet** per caricare un elenco di clienti dal database **Northwind** .</span><span class="sxs-lookup"><span data-stu-id="f8624-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="f8624-118">Una volta caricati i dati usando il metodo **Fill** , l'esempio scorre in ciclo ogni cliente nella tabella **Customers** usando l'oggetto tipizzato **CustomersRow** (**DataRow**).</span><span class="sxs-lookup"><span data-stu-id="f8624-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="f8624-119">Questo consente di accedere direttamente alla colonna **CustomerID** , anziché tramite DataColumnCollection.</span><span class="sxs-lookup"><span data-stu-id="f8624-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
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
  
 <span data-ttu-id="f8624-120">Di seguito viene riportato l'XML Schema usato per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="f8624-120">Following is the XML Schema used for the example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f8624-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8624-121">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="f8624-122">Set di dati tipizzati</span><span class="sxs-lookup"><span data-stu-id="f8624-122">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="f8624-123">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="f8624-123">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="f8624-124">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="f8624-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
