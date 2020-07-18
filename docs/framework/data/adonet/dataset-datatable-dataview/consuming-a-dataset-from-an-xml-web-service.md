---
title: Utilizzare un set di dati da un servizio Web XML
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: e6dc32274cc3b0d7ec9d66a837a422c87fb2468b
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416208"
---
# <a name="consume-a-dataset-from-an-xml-web-service"></a>Utilizzare un set di dati da un servizio Web XML

Il <xref:System.Data.DataSet> è stato progettato con una struttura disconnessa, in parte per facilitare il trasporto di dati su Internet. Il **set di dati** è "serializzabile" in quanto può essere specificato come input o output dai servizi Web XML senza che sia necessario scrivere codice aggiuntivo per trasmettere il contenuto del **set di dati** da un servizio Web XML a un client e viceversa. Il **set di dati** viene convertito in modo implicito in un flusso XML utilizzando il formato DiffGram, inviato in rete e quindi ricostruito dal flusso XML come **set di dati** all'estremità ricevente. Ciò offre un metodo semplice e flessibile per la trasmissione e la restituzione di dati relazionali mediante i servizi Web XML. Per ulteriori informazioni sul formato DiffGram, vedere [DiffGram](diffgrams.md).  
  
 Nell'esempio seguente viene illustrato come creare un servizio Web XML e un client che utilizzano il **set** di dati per trasportare dati relazionali (compresi i dati modificati) e risolvere eventuali aggiornamenti nell'origine dati originale.  
  
> [!NOTE]
> `DataSet`La trasmissione `DataTable` di istanze o come parte delle chiamate al servizio Web XML non è sicura se l'input non è attendibile. Per ulteriori informazioni, vedere la [Guida alla sicurezza di DataSet e DataTable](security-guidance.md).
> Si consiglia inoltre di considerare sempre le implicazioni di sicurezza per la creazione di un servizio Web XML. Per informazioni sulla protezione di un servizio Web XML, vedere [protezione di servizi Web XML creati con ASP.NET](/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).  
  
## <a name="create-an-xml-web-service"></a>Creazione di un servizio Web XML
  
1. Creare il servizio Web XML.  
  
     Nell'esempio viene creato un servizio Web XML che restituisce i dati, in questo caso un elenco di clienti dal database **Northwind** e riceve un **set** di dati con aggiornamenti ai dati, che il servizio Web XML risolve nell'origine dati originale.  
  
     Il servizio Web XML espone due metodi: **GetCustomers**, per restituire l'elenco dei clienti e **UpdateCustomers**, per risolvere gli aggiornamenti nell'origine dati. Il servizio Web XML viene archiviato in un file sul server Web denominato DataSetSample.asmx. Nel codice seguente viene descritto il contenuto del file DataSetSample.asmx.  
  
    ```vb  
    <% @ WebService Language = "vb" Class = "Sample" %>  
    Imports System  
    Imports System.Data  
    Imports System.Data.SqlClient  
    Imports System.Web.Services  
  
    <WebService(Namespace:="http://microsoft.com/webservices/")> _  
    Public Class Sample  
  
    Public connection As SqlConnection = New SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind")  
  
      <WebMethod( Description := "Returns Northwind Customers", EnableSession := False )> _  
      Public Function GetCustomers() As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
          "SELECT CustomerID, CompanyName FROM Customers", connection)  
  
        Dim custDS As DataSet = New DataSet()  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
        adapter.Fill(custDS, "Customers")  
  
        Return custDS  
      End Function  
  
      <WebMethod( Description := "Updates Northwind Customers", EnableSession := False )> _  
      Public Function UpdateCustomers(custDS As DataSet) As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter()  
  
        adapter.InsertCommand = New SqlCommand( _  
          "INSERT INTO Customers (CustomerID, CompanyName) " & _  
          "Values(@CustomerID, @CompanyName)", connection)  
        adapter.InsertCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.InsertCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        adapter.UpdateCommand = New SqlCommand( _  
          "UPDATE Customers Set CustomerID = @CustomerID, " & _  
          "CompanyName = @CompanyName WHERE CustomerID = " & _  
          @OldCustomerID", connection)  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        Dim parameter As SqlParameter = _  
          adapter.UpdateCommand.Parameters.Add( _  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.DeleteCommand = New SqlCommand( _  
          "DELETE FROM Customers WHERE CustomerID = @CustomerID", _  
          connection)  
        parameter = adapter.DeleteCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.Update(custDS, "Customers")  
  
        Return custDS  
      End Function  
    End Class  
    ```  
  
    ```csharp  
    <% @ WebService Language = "C#" Class = "Sample" %>  
    using System;  
    using System.Data;  
    using System.Data.SqlClient;  
    using System.Web.Services;  
  
    [WebService(Namespace="http://microsoft.com/webservices/")]  
    public class Sample  
    {  
      public SqlConnection connection = new SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind");  
  
      [WebMethod( Description = "Returns Northwind Customers", EnableSession = false )]  
      public DataSet GetCustomers()  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter(  
          "SELECT CustomerID, CompanyName FROM Customers", connection);  
  
        DataSet custDS = new DataSet();  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
        adapter.Fill(custDS, "Customers");  
  
        return custDS;  
      }  
  
      [WebMethod( Description = "Updates Northwind Customers",  
        EnableSession = false )]  
      public DataSet UpdateCustomers(DataSet custDS)  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter();  
  
        adapter.InsertCommand = new SqlCommand(  
          "INSERT INTO Customers (CustomerID, CompanyName) " +  
          "Values(@CustomerID, @CompanyName)", connection);  
        adapter.InsertCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.InsertCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
  
        adapter.UpdateCommand = new SqlCommand(  
          "UPDATE Customers Set CustomerID = @CustomerID, " +  
          "CompanyName = @CompanyName WHERE CustomerID = " +  
          "@OldCustomerID", connection);  
        adapter.UpdateCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.UpdateCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
        SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.DeleteCommand = new SqlCommand(  
        "DELETE FROM Customers WHERE CustomerID = @CustomerID",  
         connection);  
        parameter = adapter.DeleteCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.Update(custDS, "Customers");  
  
        return custDS;  
      }  
    }  
    ```  
  
     In uno scenario tipico, il metodo **UpdateCustomers** viene scritto per intercettare le violazioni della concorrenza ottimistica. Per semplicità, questa opzione non è stata inclusa nell'esempio. Per ulteriori informazioni sulla concorrenza ottimistica, vedere [concorrenza ottimistica](../optimistic-concurrency.md).  
  
2. Creare un proxy del servizio Web XML.  
  
     Un proxy SOAP verrà richiesto dai client del servizio Web XML per l'uso dei metodi esposti. È possibile generare questo proxy usando Visual Studio. Se si imposta un riferimento Web su un servizio Web esistente tramite Visual Studio, tutti i comportamenti descritti in questo passaggio si verificheranno in modo trasparente. Per creare la classe proxy autonomamente, continuare a eseguire i passaggi descritti di seguito. Tuttavia, nella maggior parte dei casi, per creare la classe proxy per l'applicazione client è sufficiente usare Visual Studio.  
  
     Per creare un proxy, è possibile usare lo Strumento del linguaggio di descrizione dei servizi Web (Wsdl.exe). Se, ad esempio, il servizio Web XML viene esposto all'URL `http://myserver/data/DataSetSample.asmx` , eseguire un comando simile al seguente per creare un proxy Visual Basic .NET con uno spazio dei nomi **WebData. DSSample** e archiviarlo nel file Sample. vb.  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     Per creare un proxy C# nel file sample.cs, eseguire il comando seguente.  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     È quindi possibile compilare il proxy come libreria e importarlo nel client del servizio Web XML. Per compilare il codice del proxy di Visual Basic .NET archiviato nel file sample.vb come sample.dll, eseguire il comando seguente.  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     Per compilare il codice del proxy C# archiviato nel file sample.cs come sample.dll, eseguire il comando seguente.  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3. Creare un client del servizio Web XML.  
  
     Se si desidera che in Visual Studio venga generata automaticamente la classe proxy del servizio Web, creare semplicemente il progetto client e, nella finestra di Esplora soluzioni, fare clic con il pulsante destro del mouse sul progetto e quindi scegliere **Aggiungi**  >  **riferimento al servizio**. Nella finestra di dialogo **Aggiungi riferimento al servizio** selezionare **Avanzate**, quindi fare clic su **Aggiungi riferimento Web**. Selezionare il servizio Web dall'elenco dei servizi Web disponibili. potrebbe essere necessario specificare l'indirizzo dell'endpoint del servizio Web se il servizio Web non è disponibile all'interno della soluzione corrente o nel computer corrente. Se si crea autonomamente il proxy del servizio Web XML, come descritto nel passaggio precedente, è possibile importarlo nel codice del client e usare i metodi del servizio Web XML.

     Il codice di esempio seguente importa la libreria proxy, chiama **GetCustomers** per ottenere un elenco di clienti, aggiunge un nuovo cliente e quindi restituisce un **set di dati** con gli aggiornamenti di **UpdateCustomers**.  
  
     L'esempio passa il **set di dati** restituito da **DataSet. GetChanges** a **UpdateCustomers** perché solo le righe modificate devono essere passate a **UpdateCustomers**. **UpdateCustomers** restituisce il **set di dati**risolto, che è quindi possibile **unire** al **set di dati** esistente per incorporare le modifiche risolte e le informazioni sugli errori delle righe dall'aggiornamento. Il codice seguente presuppone che sia stato usato Visual Studio per creare il riferimento Web e che il riferimento Web sia stato rinominato in DsSample nella finestra di dialogo **Aggiungi riferimento Web** .  
  
    ```vb  
    Imports System  
    Imports System.Data  
  
    Public Class Client  
  
      Public Shared Sub Main()  
        Dim proxySample As New DsSample.Sample ()  ' Proxy object.  
        Dim customersDataSet As DataSet = proxySample.GetCustomers()  
        Dim customersTable As DataTable = _  
          customersDataSet.Tables("Customers")  
  
        Dim rowAs DataRow = customersTable.NewRow()  
        row("CustomerID") = "ABCDE"  
        row("CompanyName") = "New Company Name"  
        customersTable.Rows.Add(row)  
  
        Dim updateDataSet As DataSet = _  
          proxySample.UpdateCustomers(customersDataSet.GetChanges())  
  
        customersDataSet.Merge(updateDataSet)  
        customersDataSet.AcceptChanges()  
      End Sub  
    End Class  
    ```  
  
    ```csharp  
    using System;  
    using System.Data;  
  
    public class Client  
    {  
      public static void Main()  
      {  
        Sample proxySample = new DsSample.Sample();  // Proxy object.  
        DataSet customersDataSet = proxySample.GetCustomers();  
        DataTable customersTable = customersDataSet.Tables["Customers"];  
  
        DataRow row = customersTable.NewRow();  
        row["CustomerID"] = "ABCDE";  
        row["CompanyName"] = "New Company Name";  
        customersTable.Rows.Add(row);  
  
        DataSet updateDataSet = new DataSet();  
  
        updateDataSet =
          proxySample.UpdateCustomers(customersDataSet.GetChanges());  
  
        customersDataSet.Merge(updateDataSet);  
        customersDataSet.AcceptChanges();  
      }  
    }  
    ```  
  
     Se si crea la classe proxy autonomamente, invece, è necessario eseguire i seguenti passaggi aggiuntivi. Per compilare l'esempio, fornire la libreria del proxy creata (sample.dll) e le librerie .NET correlate. Per compilare la versione di Visual Basic .NET dell'esempio, archiviata nel file client.vb, eseguire il comando seguente.  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     Per compilare la versione C# dell'esempio, archiviata nel file client.cs, eseguire il comando seguente.  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [ADO.NET](../index.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [DataTables](datatables.md)
- [Popolamento di un dataset da un oggetto DataAdapter](../populating-a-dataset-from-a-dataadapter.md)
- [Aggiornamento di origini dati con DataAdapter](../updating-data-sources-with-dataadapters.md)
- [Parametri DataAdapter](../dataadapter-parameters.md)
- [Strumento del linguaggio di descrizione dei servizi Web (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))
- [Panoramica di ADO.NET](../ado-net-overview.md)
