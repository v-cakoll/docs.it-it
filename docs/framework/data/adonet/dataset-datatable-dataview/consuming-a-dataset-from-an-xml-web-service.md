---
title: Utilizzo di un dataset da un servizio Web XML
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
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e46783c627657f1185e93b4ddbb7f996df064250
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="consuming-a-dataset-from-an-xml-web-service"></a>Utilizzo di un dataset da un servizio Web XML
Il <xref:System.Data.DataSet> è stato progettato con una struttura disconnessa, in parte per facilitare il trasporto di dati su Internet. Il **DataSet** è "serializzabile" in quanto può essere specificato come un input o output da servizi Web XML senza scrivere codice aggiuntivo necessario per il contenuto del flusso di **DataSet** da un servizio Web XML per un client e viceversa. Il **set di dati** viene convertito implicitamente in un flusso XML utilizzando il formato DiffGram, inviati in rete e ricreato dal flusso XML come un **DataSet** all'estremità ricevente. Si tratta quindi di un metodo molto semplice e flessibile per la trasmissione e la restituzione di dati relazionali tramite i servizi Web XML. Per ulteriori informazioni sul formato DiffGram, vedere [DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).  
  
 Nell'esempio seguente viene illustrato come creare un servizio Web XML e un client che utilizzano il **DataSet** per il trasporto di dati relazionali (inclusi i dati modificati) e risolvere eventuali aggiornamenti fino all'origine dei dati.  
  
> [!NOTE]
>  Nella creazione di un servizio Web XML si consiglia di tenere sempre presenti le implicazioni inerenti la sicurezza. Per informazioni sulla protezione di un servizio Web XML, vedere [protezione dei servizi Web XML creati tramite ASP.NET](http://msdn.microsoft.com/en-us/354b2ab1-2782-4542-b32a-dc560178b90c).  
  
### <a name="to-create-an-xml-web-service-that-returns-and-consumes-a-dataset"></a>Per creare un servizio Web XML che restituisca e utilizzi un DataSet  
  
1.  Creare il servizio Web XML.  
  
     Nell'esempio viene creato un servizio Web XML che restituisce dati, in questo caso un elenco di clienti il **Northwind** database e riceve un **DataSet** con gli aggiornamenti dei dati, che il servizio Web XML risolve l'origine dati originale.  
  
     Il servizio Web XML espone due metodi: **GetCustomers**, per restituire l'elenco di clienti e **UpdateCustomers**, per risolvere gli aggiornamenti dell'origine dati. Il servizio Web XML viene archiviato in un file sul server Web denominato DataSetSample.asmx. Nel codice seguente viene descritto il contenuto del file DataSetSample.asmx.  
  
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
  
     In uno scenario tipico, il **UpdateCustomers** metodo verrebbe scritto per rilevare eventuali violazioni alla concorrenza ottimistica. Per semplicità, questa opzione non è stata inclusa nell'esempio. Per ulteriori informazioni sulla concorrenza ottimistica, vedere [la concorrenza ottimistica](../../../../../docs/framework/data/adonet/optimistic-concurrency.md).  
  
2.  Creare un proxy del servizio Web XML.  
  
     Un proxy SOAP verrà richiesto dai client del servizio Web XML per l'uso dei metodi esposti. È possibile generare questo proxy usando Visual Studio. Se si imposta un riferimento Web su un servizio Web esistente tramite Visual Studio, tutti i comportamenti descritti in questo passaggio si verificheranno in modo trasparente. Per creare la classe proxy autonomamente, continuare a eseguire i passaggi descritti di seguito. Tuttavia, nella maggior parte dei casi, per creare la classe proxy per l'applicazione client è sufficiente usare Visual Studio.  
  
     Per creare un proxy, è possibile usare lo Strumento del linguaggio di descrizione dei servizi Web (Wsdl.exe). Ad esempio, se il servizio Web XML viene esposto l'URL http://myserver/data/DataSetSample.asmx, inviare un comando analogo al seguente per creare un proxy di Visual Basic .NET con spazio dei nomi **WebData. DSSample** e archiviarlo nel file Sample. vb.  
  
    ```  
    wsdl /l:VB /out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     Per creare un proxy C# nel file sample.cs, eseguire il comando seguente.  
  
    ```  
    wsdl /l:CS /out:sample.cs http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     È quindi possibile compilare il proxy come libreria e importarlo nel client del servizio Web XML. Per compilare il codice del proxy di Visual Basic .NET archiviato nel file sample.vb come sample.dll, eseguire il comando seguente.  
  
    ```  
    vbc /t:library /out:sample.dll sample.vb /r:System.dll /r:System.Web.Services.dll /r:System.Data.dll /r:System.Xml.dll  
    ```  
  
     Per compilare il codice del proxy C# archiviato nel file sample.cs come sample.dll, eseguire il comando seguente.  
  
    ```  
    csc /t:library /out:sample.dll sample.cs /r:System.dll /r:System.Web.Services.dll /r:System.Data.dll /r:System.Xml.dll  
    ```  
  
3.  Creare un client del servizio Web XML.  
  
     Se si desidera generare automaticamente la classe proxy del servizio Web di Visual Studio, è sufficiente creare il progetto client e, nella finestra Esplora soluzioni, fare clic sul progetto, fare clic su **Aggiungi riferimento Web**e il servizio Web da selezionare l'elenco dei servizi Web disponibili (può essere necessario fornire l'indirizzo dell'endpoint del servizio Web, se il servizio Web non è disponibile all'interno della soluzione corrente o nel computer corrente.) Se si crea autonomamente il proxy del servizio Web XML, come descritto nel passaggio precedente, è possibile importarlo nel codice del client e usare i metodi del servizio Web XML. Esempio di codice seguente importa la libreria del proxy, le chiamate **GetCustomers** per ottenere un elenco di clienti, aggiunge un nuovo cliente e quindi restituisce un **set di dati** con gli aggiornamenti a **UpdateCustomers** .  
  
     Si noti che nell'esempio viene passato il **DataSet** restituito da **DataSet. GetChanges** a **UpdateCustomers** perché solo le righe modificate devono essere passati a  **UpdateCustomers**. **UpdateCustomers** restituisce l'oggetto risolto **DataSet**, che è possibile quindi **Merge** in esistente **DataSet** per incorporare le modifiche risolte e eventuali informazioni sugli errori di riga provenienti dall'aggiornamento. Il codice seguente si presuppone che si usa Visual Studio per creare il riferimento Web e che sia stato rinominato come DsSample nel riferimento Web il **Aggiungi riferimento Web** la finestra di dialogo.  
  
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
  
    ```  
    vbc client.vb /r:sample.dll /r:System.dll /r:System.Data.dll /r:System.Xml.dll /r:System.Web.Services.dll  
    ```  
  
     Per compilare la versione C# dell'esempio, archiviata nel file client.cs, eseguire il comando seguente.  
  
    ```  
    csc client.cs /r:sample.dll /r:System.dll /r:System.Data.dll /r:System.Xml.dll /r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Popolamento di un set di dati da un oggetto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [Aggiornamento di origini dati con DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [Parametri DataAdapter](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 [Web Services Description Language Tool (Wsdl.exe)](http://msdn.microsoft.com/en-us/b9210348-8bc2-4367-8c91-d1a04b403e88)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
