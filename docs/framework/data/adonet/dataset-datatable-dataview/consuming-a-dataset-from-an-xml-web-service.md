---
title: Utilizzo di un dataset da un servizio Web XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: d7328949e3eb4822b1a645bb5f0c1866f01ecb0a
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389740"
---
# <a name="consume-a-dataset-from-an-xml-web-service"></a><span data-ttu-id="442fc-102">Usare un DataSet da un servizio Web XMLConsume a DataSet from an XML web service</span><span class="sxs-lookup"><span data-stu-id="442fc-102">Consume a DataSet from an XML web service</span></span>

<span data-ttu-id="442fc-103">Il <xref:System.Data.DataSet> è stato progettato con una struttura disconnessa, in parte per facilitare il trasporto di dati su Internet.</span><span class="sxs-lookup"><span data-stu-id="442fc-103">The <xref:System.Data.DataSet> was architected with a disconnected design, in part to facilitate the convenient transport of data over the Internet.</span></span> <span data-ttu-id="442fc-104">Il **DataSet** è "serializzabile" in quanto può essere specificato come input o output da servizi Web XML senza alcuna codifica aggiuntiva necessaria per trasmettere il contenuto del **DataSet** da un servizio Web XML a un client e viceversa.</span><span class="sxs-lookup"><span data-stu-id="442fc-104">The **DataSet** is "serializable" in that it can be specified as an input to or output from XML Web services without any additional coding required to stream the contents of the **DataSet** from an XML Web service to a client and back.</span></span> <span data-ttu-id="442fc-105">Il **DataSet** viene convertito in modo implicito in un flusso XML utilizzando il formato DiffGram, inviato in rete e quindi ricostruito dal flusso XML come **DataSet** sul lato ricevente.</span><span class="sxs-lookup"><span data-stu-id="442fc-105">The **DataSet** is implicitly converted to an XML stream using the DiffGram format, sent over the network, and then reconstructed from the XML stream as a **DataSet** on the receiving end.</span></span> <span data-ttu-id="442fc-106">Si tratta quindi di un metodo molto semplice e flessibile per la trasmissione e la restituzione di dati relazionali tramite i servizi Web XML.</span><span class="sxs-lookup"><span data-stu-id="442fc-106">This gives you a very simple and flexible method for transmitting and returning relational data using XML Web services.</span></span> <span data-ttu-id="442fc-107">Per ulteriori informazioni sul formato DiffGram, vedere [DiffGrams](diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="442fc-107">For more information about the DiffGram format, see [DiffGrams](diffgrams.md).</span></span>  
  
 <span data-ttu-id="442fc-108">Nell'esempio seguente viene illustrato come creare un client e un servizio Web XML che utilizzano il **DataSet** per trasportare dati relazionali (inclusi i dati modificati) e risolvere eventuali aggiornamenti nell'origine dati originale.</span><span class="sxs-lookup"><span data-stu-id="442fc-108">The following example shows how to create an XML Web service and client that use the **DataSet** to transport relational data (including modified data) and resolve any updates back to the original data source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="442fc-109">Nella creazione di un servizio Web XML si consiglia di tenere sempre presenti le implicazioni inerenti la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="442fc-109">We recommend that you always consider security implications when creating an XML Web service.</span></span> <span data-ttu-id="442fc-110">Per informazioni sulla protezione di un servizio Web XML, vedere [Protezione dei servizi Web XML creati utilizzando ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="442fc-110">For information on securing an XML Web service, see [Securing XML Web Services Created Using ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).</span></span>  
  
## <a name="create-an-xml-web-service"></a><span data-ttu-id="442fc-111">Creare un servizio Web XMLCreate an XML web service</span><span class="sxs-lookup"><span data-stu-id="442fc-111">Create an XML web service</span></span>
  
1. <span data-ttu-id="442fc-112">Creare il servizio Web XML.</span><span class="sxs-lookup"><span data-stu-id="442fc-112">Create the XML Web service.</span></span>  
  
     <span data-ttu-id="442fc-113">Nell'esempio viene creato un servizio Web XML che restituisce dati, in questo caso un elenco di clienti del database **Northwind,** e riceve un **DataSet** con aggiornamenti ai dati, che il servizio Web XML risolve nuovamente nell'origine dati originale.</span><span class="sxs-lookup"><span data-stu-id="442fc-113">In the example, an XML Web service is created that returns data, in this case a list of customers from the **Northwind** database, and receives a **DataSet** with updates to the data, which the XML Web service resolves back to the original data source.</span></span>  
  
     <span data-ttu-id="442fc-114">Il servizio Web XML espone due metodi: **GetCustomers**, per restituire l'elenco dei clienti, e **UpdateCustomers**, per risolvere gli aggiornamenti nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="442fc-114">The XML Web service exposes two methods: **GetCustomers**, to return the list of customers, and **UpdateCustomers**, to resolve updates back to the data source.</span></span> <span data-ttu-id="442fc-115">Il servizio Web XML viene archiviato in un file sul server Web denominato DataSetSample.asmx.</span><span class="sxs-lookup"><span data-stu-id="442fc-115">The XML Web service is stored in a file on the Web server called DataSetSample.asmx.</span></span> <span data-ttu-id="442fc-116">Nel codice seguente viene descritto il contenuto del file DataSetSample.asmx.</span><span class="sxs-lookup"><span data-stu-id="442fc-116">The following code outlines the contents of DataSetSample.asmx.</span></span>  
  
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
  
     <span data-ttu-id="442fc-117">In uno scenario tipico, il **UpdateCustomers** metodo verrebbe scritto per rilevare le violazioni della concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="442fc-117">In a typical scenario, the **UpdateCustomers** method would be written to catch optimistic concurrency violations.</span></span> <span data-ttu-id="442fc-118">Per semplicità, questa opzione non è stata inclusa nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="442fc-118">For simplicity, the example does not include this.</span></span> <span data-ttu-id="442fc-119">Per ulteriori informazioni sulla concorrenza ottimistica, vedere [Concorrenza ottimistica](../optimistic-concurrency.md).</span><span class="sxs-lookup"><span data-stu-id="442fc-119">For more information about optimistic concurrency, see [Optimistic Concurrency](../optimistic-concurrency.md).</span></span>  
  
2. <span data-ttu-id="442fc-120">Creare un proxy del servizio Web XML.</span><span class="sxs-lookup"><span data-stu-id="442fc-120">Create an XML Web service proxy.</span></span>  
  
     <span data-ttu-id="442fc-121">Un proxy SOAP verrà richiesto dai client del servizio Web XML per l'uso dei metodi esposti.</span><span class="sxs-lookup"><span data-stu-id="442fc-121">Clients of the XML Web service require a SOAP proxy in order to consume the exposed methods.</span></span> <span data-ttu-id="442fc-122">È possibile generare questo proxy usando Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="442fc-122">You can have Visual Studio generate this proxy for you.</span></span> <span data-ttu-id="442fc-123">Se si imposta un riferimento Web su un servizio Web esistente tramite Visual Studio, tutti i comportamenti descritti in questo passaggio si verificheranno in modo trasparente.</span><span class="sxs-lookup"><span data-stu-id="442fc-123">By setting a Web reference to an existing Web service from within Visual Studio, all the behavior described in this step occurs transparently.</span></span> <span data-ttu-id="442fc-124">Per creare la classe proxy autonomamente, continuare a eseguire i passaggi descritti di seguito.</span><span class="sxs-lookup"><span data-stu-id="442fc-124">If you want to create the proxy class yourself, continue with this discussion.</span></span> <span data-ttu-id="442fc-125">Tuttavia, nella maggior parte dei casi, per creare la classe proxy per l'applicazione client è sufficiente usare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="442fc-125">In most circumstances, however, using Visual Studio to create the proxy class for the client application is sufficient.</span></span>  
  
     <span data-ttu-id="442fc-126">Per creare un proxy, è possibile usare lo Strumento del linguaggio di descrizione dei servizi Web (Wsdl.exe).</span><span class="sxs-lookup"><span data-stu-id="442fc-126">A proxy can be created using the Web Services Description Language Tool.</span></span> <span data-ttu-id="442fc-127">Ad esempio, se il servizio Web `http://myserver/data/DataSetSample.asmx`XML è esposto all'URL , eseguire un comando simile al seguente per creare un proxy di Visual Basic .NET con uno spazio dei nomi **WebData.DSSample** e archiviarlo nel file sample.vb.</span><span class="sxs-lookup"><span data-stu-id="442fc-127">For example, if the XML Web service is exposed at the URL `http://myserver/data/DataSetSample.asmx`, issue a command such as the following to create a Visual Basic .NET proxy with a namespace of **WebData.DSSample** and store it in the file sample.vb.</span></span>  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="442fc-128">Per creare un proxy C# nel file sample.cs, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="442fc-128">To create a C# proxy in the file sample.cs, issue the following command.</span></span>  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="442fc-129">È quindi possibile compilare il proxy come libreria e importarlo nel client del servizio Web XML.</span><span class="sxs-lookup"><span data-stu-id="442fc-129">The proxy can then be compiled as a library and imported into the XML Web service client.</span></span> <span data-ttu-id="442fc-130">Per compilare il codice del proxy di Visual Basic .NET archiviato nel file sample.vb come sample.dll, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="442fc-130">To compile the Visual Basic .NET proxy code stored in sample.vb as sample.dll, issue the following command.</span></span>  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     <span data-ttu-id="442fc-131">Per compilare il codice del proxy C# archiviato nel file sample.cs come sample.dll, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="442fc-131">To compile the C# proxy code stored in sample.cs as sample.dll, issue the following command.</span></span>  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3. <span data-ttu-id="442fc-132">Creare un client del servizio Web XML.</span><span class="sxs-lookup"><span data-stu-id="442fc-132">Create an XML Web service client.</span></span>  
  
     <span data-ttu-id="442fc-133">Se si desidera che Visual Studio generi automaticamente la classe proxy del servizio Web, è sufficiente creare il progetto client e, nella finestra Esplora soluzioni, fare clic con il pulsante destro del mouse sul progetto e quindi **scegliere Aggiungi** > riferimento al**servizio**.</span><span class="sxs-lookup"><span data-stu-id="442fc-133">If you want to have Visual Studio generate the Web service proxy class for you, simply create the client project, and, in the Solution Explorer window, right-click the project, and then select **Add** > **Service Reference**.</span></span> <span data-ttu-id="442fc-134">Nella finestra di dialogo **Aggiungi riferimento** al servizio selezionare **Avanzate**, quindi Aggiungi **riferimento Web**.</span><span class="sxs-lookup"><span data-stu-id="442fc-134">In the **Add Service Reference** dialog box, select **Advanced**, and then select **Add Web Reference**.</span></span> <span data-ttu-id="442fc-135">Selezionare il servizio Web dall'elenco dei servizi Web disponibili (potrebbe essere necessario fornire l'indirizzo dell'endpoint del servizio Web se il servizio Web non è disponibile all'interno della soluzione corrente o nel computer corrente).</span><span class="sxs-lookup"><span data-stu-id="442fc-135">Select the Web service from the list of available Web services (this may require supplying the address of the Web service endpoint if the Web service isn't available within the current solution or on the current computer).</span></span> <span data-ttu-id="442fc-136">Se si crea autonomamente il proxy del servizio Web XML, come descritto nel passaggio precedente, è possibile importarlo nel codice del client e usare i metodi del servizio Web XML.</span><span class="sxs-lookup"><span data-stu-id="442fc-136">If you create the XML Web service proxy yourself (as described in the previous step), you can import it into your client code and consume the XML Web service methods.</span></span>

     <span data-ttu-id="442fc-137">Il codice di esempio seguente importa la libreria proxy, chiama **GetCustomers** per ottenere un elenco di clienti, aggiunge un nuovo cliente e quindi restituisce un **DataSet** con gli aggiornamenti a **UpdateCustomers**.</span><span class="sxs-lookup"><span data-stu-id="442fc-137">The following sample code imports the proxy library, calls **GetCustomers** to get a list of customers, adds a new customer, and then returns a **DataSet** with the updates to **UpdateCustomers**.</span></span>  
  
     <span data-ttu-id="442fc-138">Nell'esempio viene passato il **DataSet** restituito da **DataSet.GetChanges** a **UpdateCustomers** perché solo le righe modificate devono essere passate a **UpdateCustomers**.</span><span class="sxs-lookup"><span data-stu-id="442fc-138">The example passes the **DataSet** returned by **DataSet.GetChanges** to **UpdateCustomers** because only modified rows need to be passed to **UpdateCustomers**.</span></span> <span data-ttu-id="442fc-139">**UpdateCustomers** restituisce il **DataSet**risolto , che è quindi possibile **unire** nel **DataSet** esistente per incorporare le modifiche risolte e le eventuali informazioni sugli errori di riga dall'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="442fc-139">**UpdateCustomers** returns the resolved **DataSet**, which you can then **Merge** into the existing **DataSet** to incorporate the resolved changes and any row error information from the update.</span></span> <span data-ttu-id="442fc-140">Nel codice riportato di seguito si presuppone che sia stato utilizzato Visual Studio per creare il riferimento Web e che il riferimento Web sia stato rinominato In DsSample nella finestra di dialogo **Aggiungi riferimento Web.**</span><span class="sxs-lookup"><span data-stu-id="442fc-140">The following code assumes that you have used Visual Studio to create the Web reference, and that you have renamed the Web reference to DsSample in the **Add Web Reference** dialog box.</span></span>  
  
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
  
     <span data-ttu-id="442fc-141">Se si crea la classe proxy autonomamente, invece, è necessario eseguire i seguenti passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="442fc-141">If you decide to create the proxy class yourself, you must take the following extra steps.</span></span> <span data-ttu-id="442fc-142">Per compilare l'esempio, fornire la libreria del proxy creata (sample.dll) e le librerie .NET correlate.</span><span class="sxs-lookup"><span data-stu-id="442fc-142">To compile the sample, supply the proxy library that was created (sample.dll) and the related .NET libraries.</span></span> <span data-ttu-id="442fc-143">Per compilare la versione di Visual Basic .NET dell'esempio, archiviata nel file client.vb, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="442fc-143">To compile the Visual Basic .NET version of the sample, stored in the file client.vb, issue the following command.</span></span>  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     <span data-ttu-id="442fc-144">Per compilare la versione C# dell'esempio, archiviata nel file client.cs, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="442fc-144">To compile the C# version of the sample, stored in the file client.cs, issue the following command.</span></span>  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="442fc-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="442fc-145">See also</span></span>

- [<span data-ttu-id="442fc-146">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="442fc-146">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="442fc-147">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="442fc-147">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="442fc-148">DataTable</span><span class="sxs-lookup"><span data-stu-id="442fc-148">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="442fc-149">Popolamento di un set di dati da un oggetto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="442fc-149">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="442fc-150">Aggiornamento di origini dati con DataAdapter</span><span class="sxs-lookup"><span data-stu-id="442fc-150">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="442fc-151">Parametri DataAdapter</span><span class="sxs-lookup"><span data-stu-id="442fc-151">DataAdapter Parameters</span></span>](../dataadapter-parameters.md)
- <span data-ttu-id="442fc-152">[Strumento del linguaggio di descrizione dei servizi Web (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="442fc-152">[Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span></span>
- [<span data-ttu-id="442fc-153">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="442fc-153">ADO.NET Overview</span></span>](../ado-net-overview.md)
