---
title: Generazione di dataset fortemente tipizzati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 84c0319c49534cc9a09ffd15d9a07b8ec18882b3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728739"
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="e3230-102">Generazione di dataset fortemente tipizzati</span><span class="sxs-lookup"><span data-stu-id="e3230-102">Generating Strongly Typed DataSets</span></span>
<span data-ttu-id="e3230-103">Dato un XML Schema conforme allo standard XSD (XML Schema Definition Language), è possibile generare un <xref:System.Data.DataSet> fortemente tipizzato usando lo strumento XSD.exe fornito con [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3230-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].</span></span>  
  
 <span data-ttu-id="e3230-104">(Per creare uno schema xsd dalle tabelle di database, vedere <xref:System.Data.DataSet.WriteXmlSchema%2A> oppure [utilizzo di dataset in Visual Studio](https://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span><span class="sxs-lookup"><span data-stu-id="e3230-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](https://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span></span>  
  
 <span data-ttu-id="e3230-105">Il codice seguente illustra la sintassi per la generazione di un **set di dati** usando questo strumento.</span><span class="sxs-lookup"><span data-stu-id="e3230-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="e3230-106">In questa sintassi, il `/d` direttiva richiede lo strumento per generare un **set di dati**e il `/l:` indica allo strumento del linguaggio da usare (ad esempio, c# o Visual Basic .NET).</span><span class="sxs-lookup"><span data-stu-id="e3230-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="e3230-107">L'opzione facoltativa `/eld` direttiva specifica che è possibile usare [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] per eseguire query sul generato **set di dati.**</span><span class="sxs-lookup"><span data-stu-id="e3230-107">The optional `/eld` directive specifies that you can use [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] to query against the generated **DataSet.**</span></span> <span data-ttu-id="e3230-108">Questa opzione viene usata quando si specifica anche l'opzione `/d`.</span><span class="sxs-lookup"><span data-stu-id="e3230-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="e3230-109">Per altre informazioni, vedere [Querying Typed DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="e3230-109">For more information, see [Querying Typed DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="e3230-110">L'opzione facoltativa `/n:` direttiva richiede lo strumento per generare anche uno spazio dei nomi per il **set di dati** chiamato **XSDSchema**.</span><span class="sxs-lookup"><span data-stu-id="e3230-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="e3230-111">L'output del comando è costituito dal file XSDSchemaFileName.dll, che può essere compilato e usato in un'applicazione ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e3230-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="e3230-112">È possibile compilare il codice generato come libreria o modulo.</span><span class="sxs-lookup"><span data-stu-id="e3230-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="e3230-113">Nel codice seguente viene mostrata la sintassi per la compilazione del codice generato come libreria usando il compilatore C# (csc.exe).</span><span class="sxs-lookup"><span data-stu-id="e3230-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="e3230-114">La direttiva `/t:` consente di richiedere allo strumento la compilazione in una libreria e la direttiva `/r:` consente di specificare le librerie dipendenti necessarie per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="e3230-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="e3230-115">L'output del comando è costituito dal file XSDSchemaFileName.dll, che può essere passato al compilatore quando si compila un'applicazione ADO.NET con la direttiva `/r:`.</span><span class="sxs-lookup"><span data-stu-id="e3230-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="e3230-116">Nel codice seguente viene mostrata la sintassi usata per l'accesso allo spazio dei nomi passato a XSD.exe in un'applicazione ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e3230-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="e3230-117">Esempio di codice seguente usa un oggetto tipizzato **set di dati** denominata **CustomerDataSet** per caricare un elenco di clienti il **Northwind** database.</span><span class="sxs-lookup"><span data-stu-id="e3230-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="e3230-118">Una volta caricati i dati usando il **riempire** metodo, l'esempio scorre in ciclo ogni cliente nella **clienti** tabella usando l'oggetto tipizzato **CustomersRow** ( **DataRow**) oggetti.</span><span class="sxs-lookup"><span data-stu-id="e3230-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="e3230-119">Ciò fornisce accesso diretto al **CustomerID** colonna, anziché tramite il **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="e3230-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
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
  
 <span data-ttu-id="e3230-120">Di seguito viene riportato l'XML Schema usato per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="e3230-120">Following is the XML Schema used for the example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e3230-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3230-121">See also</span></span>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="e3230-122">Set di dati tipizzati</span><span class="sxs-lookup"><span data-stu-id="e3230-122">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)
- [<span data-ttu-id="e3230-123">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="e3230-123">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="e3230-124">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="e3230-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
