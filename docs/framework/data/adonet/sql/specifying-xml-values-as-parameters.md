---
title: Specifica di valori XML come parametri
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2c4d08b8-fc29-4614-97fa-29c8ff7ca5b3
ms.openlocfilehash: acb94efd8b6b6b66d0cc84309c2d68ad692b08d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174498"
---
# <a name="specifying-xml-values-as-parameters"></a><span data-ttu-id="c103e-102">Specifica di valori XML come parametri</span><span class="sxs-lookup"><span data-stu-id="c103e-102">Specifying XML Values as Parameters</span></span>
<span data-ttu-id="c103e-103">Se una query richiede un parametro il cui valore è una stringa XML, è possibile fornire tale valore con un'istanza del tipo di dati **SqlXml**.</span><span class="sxs-lookup"><span data-stu-id="c103e-103">If a query requires a parameter whose value is an XML string, developers can supply that value using an instance of the **SqlXml** data type.</span></span> <span data-ttu-id="c103e-104">L'operazione è semplicissima in quanto le colonne XML in SQL Server accettano valori di parametro esattamente come altri tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="c103e-104">There really are no tricks; XML columns in SQL Server accept parameter values in exactly the same way as other data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c103e-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="c103e-105">Example</span></span>  
 <span data-ttu-id="c103e-106">L'applicazione console seguente crea una nuova tabella nel database **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="c103e-106">The following console application creates a new table in the **AdventureWorks** database.</span></span> <span data-ttu-id="c103e-107">La nuova tabella include la colonna **SalesID** e la colonna XML **SalesInfo**.</span><span class="sxs-lookup"><span data-stu-id="c103e-107">The new table includes a column named **SalesID** and an XML column named **SalesInfo**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c103e-108">Per impostazione predefinita, il database di esempio **AdventureWorks** non viene installato insieme a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c103e-108">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="c103e-109">Per installarlo, è sufficiente eseguire il programma di installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c103e-109">You can install it by running SQL Server Setup.</span></span>  
  
 <span data-ttu-id="c103e-110">Nell'esempio viene preparato un oggetto <xref:System.Data.SqlClient.SqlCommand> per inserire una riga nella nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="c103e-110">The example prepares a <xref:System.Data.SqlClient.SqlCommand> object to insert a row in the new table.</span></span> <span data-ttu-id="c103e-111">Successivamente, i dati XML per la colonna **SalesInfo** vengono forniti da un file salvato.</span><span class="sxs-lookup"><span data-stu-id="c103e-111">A saved file provides the XML data needed for the **SalesInfo** column.</span></span>  
  
 <span data-ttu-id="c103e-112">Per creare il file necessario per l'esecuzione dell'esempio, creare un nuovo file di testo nella stessa cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="c103e-112">To create the file needed for the example to run, create a new text file in the same folder as your project.</span></span> <span data-ttu-id="c103e-113">Denominare il file MyTestStoreData.xml.</span><span class="sxs-lookup"><span data-stu-id="c103e-113">Name the file MyTestStoreData.xml.</span></span> <span data-ttu-id="c103e-114">Aprire il file nel Blocco note e copiare e incollare il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="c103e-114">Open the file in Notepad and copy and paste the following text:</span></span>  
  
```xml  
<StoreSurvey xmlns="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>300000</AnnualSales>  
  <AnnualRevenue>30000</AnnualRevenue>  
  <BankName>International Bank</BankName>  
  <BusinessType>BM</BusinessType>  
  <YearOpened>1970</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>7000</SquareFeet>  
  <Brands>3</Brands>  
  <Internet>T1</Internet>  
  <NumberEmployees>2</NumberEmployees>  
</StoreSurvey>  
```  
  
```vb  
Imports System  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Xml  
  
Module Module1  
    Sub Main()  
  
        Using connection As SqlConnection = New SqlConnection(GetConnectionString())  
        connection.Open()  
  
        ' Create a sample table (dropping first if it already  
        ' exists.)  
        Dim commandNewTable As String = _  
         "IF EXISTS (SELECT * FROM dbo.sysobjects " & _  
         "WHERE id = object_id(N'[dbo].[XmlDataTypeSample]') " & _  
         "AND OBJECTPROPERTY(id, N'IsUserTable') = 1) " & _  
         "DROP TABLE [dbo].[XmlDataTypeSample];" & _  
         "CREATE TABLE [dbo].[XmlDataTypeSample](" & _  
         "[SalesID] [int] IDENTITY(1,1) NOT NULL, " & _  
         "[SalesInfo] [xml])"  
  
        Dim commandAdd As New _  
         SqlCommand(commandNewTable, connection)  
        commandAdd.ExecuteNonQuery()  
  
        Dim commandText As String = _  
         "INSERT INTO [dbo].[XmlDataTypeSample] " & _  
           "([SalesInfo] ) " & _  
           "VALUES(@xmlParameter )"  
  
        Dim command As New SqlCommand(commandText, connection)  
  
        ' Read the saved XML document as a
        ' SqlXml-data typed variable.  
        Dim newXml As SqlXml = _  
         New SqlXml(New XmlTextReader("MyTestStoreData.xml"))  
  
        ' Supply the SqlXml value for the value of the parameter.  
        command.Parameters.AddWithValue("@xmlParameter", newXml)  
  
        Dim result As Integer = command.ExecuteNonQuery()  
        Console.WriteLine(result & " row was added.")  
        Console.WriteLine("Press Enter to continue.")  
        Console.ReadLine()  
    End Using  
End Sub  
  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,
        ' you can retrieve it from a configuration file.
        Return "Data Source=(local);Integrated Security=SSPI;" & _  
          "Initial Catalog=AdventureWorks"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Xml;  
using System.Data.SqlTypes;  
  
class Class1  
{  
    static void Main()  
    {  
        using (SqlConnection connection = new SqlConnection(GetConnectionString()))  
       {  
        connection.Open();  
        //  Create a sample table (dropping first if it already  
        //  exists.)  
  
        string commandNewTable =
            "IF EXISTS (SELECT * FROM dbo.sysobjects " +
            "WHERE id = " +  
                  "object_id(N'[dbo].[XmlDataTypeSample]') " +
            "AND OBJECTPROPERTY(id, N'IsUserTable') = 1) " +
            "DROP TABLE [dbo].[XmlDataTypeSample];" +
            "CREATE TABLE [dbo].[XmlDataTypeSample](" +
            "[SalesID] [int] IDENTITY(1,1) NOT NULL, " +
            "[SalesInfo] [xml])";  
        SqlCommand commandAdd =
                   new SqlCommand(commandNewTable, connection);  
        commandAdd.ExecuteNonQuery();  
        string commandText =
            "INSERT INTO [dbo].[XmlDataTypeSample] " +
            "([SalesInfo] ) " +
            "VALUES(@xmlParameter )";  
        SqlCommand command =
                  new SqlCommand(commandText, connection);  
  
        //  Read the saved XML document as a
        //  SqlXml-data typed variable.  
        SqlXml newXml =
            new SqlXml(new XmlTextReader("MyTestStoreData.xml"));  
  
        //  Supply the SqlXml value for the value of the parameter.  
        command.Parameters.AddWithValue("@xmlParameter", newXml);  
  
        int result = command.ExecuteNonQuery();  
        Console.WriteLine(result + " row was added.");  
        Console.WriteLine("Press Enter to continue.");  
        Console.ReadLine();  
    }  
  }  
  
    private static string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,
        // you can retrieve it from a configuration file.
        return "Data Source=(local);Integrated Security=true;" +  
        "Initial Catalog=AdventureWorks; ";  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c103e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c103e-115">See also</span></span>

- <xref:System.Data.SqlTypes.SqlXml>
- [<span data-ttu-id="c103e-116">XML Data in SQL Server</span><span class="sxs-lookup"><span data-stu-id="c103e-116">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)
- [<span data-ttu-id="c103e-117">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c103e-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
