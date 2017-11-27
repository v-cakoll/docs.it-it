---
title: Accesso ai servizi tramite client WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
caps.latest.revision: "36"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6154309f24ea0eda062b7108ae280175d3ad97e1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="accessing-services-using-a-wcf-client"></a><span data-ttu-id="fce26-102">Accesso ai servizi tramite client WCF</span><span class="sxs-lookup"><span data-stu-id="fce26-102">Accessing Services Using a WCF Client</span></span>
<span data-ttu-id="fce26-103">Dopo aver creato un servizio, il passaggio successivo consiste nel creare un proxy client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fce26-103">After you create a service, the next step is to create a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client proxy.</span></span> <span data-ttu-id="fce26-104">Un'applicazione client usa il proxy client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] per comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="fce26-104">A client application uses the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client proxy to communicate with the service.</span></span> <span data-ttu-id="fce26-105">Le applicazioni client importano di norma i metadati di un servizio per generare il codice client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] che può essere usato per richiamare il servizio.</span><span class="sxs-lookup"><span data-stu-id="fce26-105">Client applications usually import a service's metadata to generate [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client code that can be used to invoke the service.</span></span>  
  
 <span data-ttu-id="fce26-106">I passaggi di base per la creazione di un client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="fce26-106">The basic steps for creating a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client include the following:</span></span>  
  
1.  <span data-ttu-id="fce26-107">Compilare il codice del servizio.</span><span class="sxs-lookup"><span data-stu-id="fce26-107">Compile the service code.</span></span>  
  
2.  <span data-ttu-id="fce26-108">Generare il proxy client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fce26-108">Generate the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client proxy.</span></span>  
  
3.  <span data-ttu-id="fce26-109">Creare un'istanza del proxy client WCF.</span><span class="sxs-lookup"><span data-stu-id="fce26-109">Instantiate the WCF client proxy.</span></span>  
  
 <span data-ttu-id="fce26-110">Il proxy client WCF può essere generato manualmente utilizzando Service Model Metadata Utility Tool (SvcUtil.exe) per ulteriori informazioni, vedere [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fce26-110">The WCF client proxy can be generated manually by using the Service Model Metadata Utility Tool (SvcUtil.exe) for more information see, [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="fce26-111">Il proxy client WCF può essere generato anche in Visual Studio usando la funzionalità Aggiungi riferimento al servizio.</span><span class="sxs-lookup"><span data-stu-id="fce26-111">The WCF client proxy can also be generated within Visual Studio using the Add Service Reference  feature.</span></span> <span data-ttu-id="fce26-112">Per generare il proxy client WCF usando l'uno o l'altro metodo, è necessario che il servizio sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fce26-112">To generate the WCF client proxy using either method the service must be running.</span></span> <span data-ttu-id="fce26-113">Se il servizio è self-hosted, è necessario eseguire l'host.</span><span class="sxs-lookup"><span data-stu-id="fce26-113">If the service is self-hosted you must run the host.</span></span> <span data-ttu-id="fce26-114">Se il servizio è ospitato in IIS/WAS, non è necessario effettuare nessun'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="fce26-114">If the service is hosted in IIS/WAS you do not need to do anything else.</span></span>  
  
## <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="fce26-115">Strumento ServiceModel Metadata Utility Tool</span><span class="sxs-lookup"><span data-stu-id="fce26-115">ServiceModel Metadata Utility Tool</span></span>  
 <span data-ttu-id="fce26-116">Il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) è uno strumento da riga di comando per la generazione di codice dai metadati.</span><span class="sxs-lookup"><span data-stu-id="fce26-116">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) is a command-line tool for generating code from metadata.</span></span> <span data-ttu-id="fce26-117">Di seguito è riportato un esempio di utilizzo di un comando Svcutil.exe di base.</span><span class="sxs-lookup"><span data-stu-id="fce26-117">The following use is an example of a basic Svcutil.exe command.</span></span>  
  
```  
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
```  
  
 <span data-ttu-id="fce26-118">In alternativa, è possibile usare Svcutil.exe con file WSDL (Web Services Description Language) e XSD (XML Schema Definition) sul file system.</span><span class="sxs-lookup"><span data-stu-id="fce26-118">Alternatively, you can use Svcutil.exe with Web Services Description Language (WSDL) and XML Schema definition language (XSD) files on the file system.</span></span>  
  
```  
Svcutil.exe <list of WSDL and XSD files on file system>  
```  
  
 <span data-ttu-id="fce26-119">Il risultato è un file di codice che contiene il codice client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] che l'applicazione client può usare per richiamare il servizio.</span><span class="sxs-lookup"><span data-stu-id="fce26-119">The result is a code file that contains [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client code that the client application can use to invoke the service.</span></span>  
  
 <span data-ttu-id="fce26-120">È inoltre possibile usare lo strumento per generare file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fce26-120">You can also use the tool to generate configuration files.</span></span>  
  
```  
Svcutil.exe <file1 [,file2]>  
```  
  
 <span data-ttu-id="fce26-121">Se viene fornito un solo nome file, si tratta del nome del file di output.</span><span class="sxs-lookup"><span data-stu-id="fce26-121">If only one file name is given, that is the name of the output file.</span></span> <span data-ttu-id="fce26-122">Se vengono forniti due nomi file, il primo indica un file di configurazione di input il cui contenuto viene unito con la configurazione generata e scritto nel secondo file.</span><span class="sxs-lookup"><span data-stu-id="fce26-122">If two file names are given, then the first file is an input configuration file whose contents are merged with the generated configuration and written out into the second file.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="fce26-123">la configurazione, vedere [la configurazione di associazioni per servizi](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="fce26-123"> configuration, see [Configuring Bindings for Services](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fce26-124">Le richieste di metadati non protette generano rischi esattamente come qualsiasi richiesta di rete non protetta. Se non si è certi dell'identità dell'endpoint con cui si sta comunicando, le informazioni recuperate potrebbero essere metadati provenienti da un servizio dannoso.</span><span class="sxs-lookup"><span data-stu-id="fce26-124">Unsecured metadata requests pose certain risks in the same way that any unsecured network request does: If you are not certain that the endpoint you are communicating with is who it says it is, the information you retrieve might be metadata from a malicious service.</span></span>  
  
## <a name="add-service-reference-in-visual-studio"></a><span data-ttu-id="fce26-125">Aggiungi riferimento al servizio in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fce26-125">Add Service Reference in Visual Studio</span></span>  
 <span data-ttu-id="fce26-126">Con il servizio in esecuzione, a destra fare clic sul progetto che conterrà il proxy client WCF e selezionare **Aggiungi riferimento al servizio**.</span><span class="sxs-lookup"><span data-stu-id="fce26-126">With the service running, right click the project that will contain the WCF client proxy and select **Add Service Reference**.</span></span> <span data-ttu-id="fce26-127">Nel **Aggiungi finestra di dialogo riferimento servizio** digitare l'URL per il servizio che si desidera chiamare e fare clic su di **passare** pulsante.</span><span class="sxs-lookup"><span data-stu-id="fce26-127">In the **Add Service Reference Dialog** type in the URL to the service you want to call and click the **Go** button.</span></span> <span data-ttu-id="fce26-128">Nella finestra di dialogo viene visualizzato un elenco dei servizi disponibili all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="fce26-128">The dialog will display a list of services available at the address you specify.</span></span> <span data-ttu-id="fce26-129">Fare doppio clic sul servizio per visualizzare i contratti e operazioni disponibili, specificare uno spazio dei nomi per il codice generato e scegliere il **OK** pulsante.</span><span class="sxs-lookup"><span data-stu-id="fce26-129">Double click the service to see the contracts and operations available, specify a namespace for the generated code and click the **OK** button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fce26-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="fce26-130">Example</span></span>  
 <span data-ttu-id="fce26-131">Nell'esempio di codice seguente viene illustrato un contratto di servizio creato per un servizio.</span><span class="sxs-lookup"><span data-stu-id="fce26-131">The following code example shows a service contract created for a service.</span></span>  
  
```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    // Other methods are not shown here.
}
```
  
```vb
' Define a service contract.
<ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
Public Interface ICalculator
    <OperationContract()>  _
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
    ' Other methods are not shown here.
End Interface
```
  
 <span data-ttu-id="fce26-132">Lo strumento ServiceModel Metadata Utility Tool e la funzionalità Aggiungi il riferimento al servizio in Visual Studio generano la seguente classe client di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fce26-132">The ServiceModel Metadata utility tool and Add Service Reference in Visual Studio generates the following [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client class.</span></span> <span data-ttu-id="fce26-133">La classe eredita dalla classe generica <xref:System.ServiceModel.ClientBase%601> e implementa l'interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="fce26-133">The class inherits from the generic <xref:System.ServiceModel.ClientBase%601> class and implements the `ICalculator` interface.</span></span> <span data-ttu-id="fce26-134">Lo strumento genera anche l'interfaccia `ICalculator` (procedure non illustrata di seguito).</span><span class="sxs-lookup"><span data-stu-id="fce26-134">The tool also generates the `ICalculator` interface (not shown here).</span></span>  
  
```csharp
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator
{
    public CalculatorClient()
    {}

    public CalculatorClient(string endpointConfigurationName) :
            base(endpointConfigurationName)
    {}

    public CalculatorClient(string endpointConfigurationName, string remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(string endpointConfigurationName,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(System.ServiceModel.Channels.Binding binding,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(binding, remoteAddress)
    {}

    public double Add(double n1, double n2)
    {
        return base.Channel.Add(n1, n2);
    }
}
```  
  
```vb  
Partial Public Class CalculatorClient
    Inherits System.ServiceModel.ClientBase(Of ICalculator)
    Implements ICalculator

    Public Sub New()
        MyBase.New
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String)
        MyBase.New(endpointConfigurationName)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String, ByVal remoteAddress As String)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal binding As System.ServiceModel.Channels.Binding,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(binding, remoteAddress)
    End Sub

    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        Implements ICalculator.Add
        Return MyBase.Channel.Add(n1, n2)
    End Function
End Class
```
  
## <a name="using-the-wcf-client"></a><span data-ttu-id="fce26-135">Utilizzo del client WCF</span><span class="sxs-lookup"><span data-stu-id="fce26-135">Using the WCF Client</span></span>  
 <span data-ttu-id="fce26-136">Per usare il client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], creare un'istanza del client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e quindi chiamarne i metodi, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="fce26-136">To use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client, create an instance of the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client, and then call its methods, as shown in the following code.</span></span>  
  
```csharp
// Create a client object with the given client endpoint configuration.
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = calcClient.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```
  
```vb
' Create a client object with the given client endpoint configuration.
Dim calcClient As CalculatorClient = _
New CalculatorClient("CalculatorEndpoint")

' Call the Add service operation.
Dim value1 As Double = 100.00D
Dim value2 As Double = 15.99D
Dim result As Double = calcClient.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)
```
  
## <a name="debugging-exceptions-thrown-by-a-client"></a><span data-ttu-id="fce26-137">Debug delle eccezioni generate da un client</span><span class="sxs-lookup"><span data-stu-id="fce26-137">Debugging Exceptions Thrown by a Client</span></span>  
 <span data-ttu-id="fce26-138">Molte eccezioni generate da un client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] vengono provocate da un'eccezione nel servizio.</span><span class="sxs-lookup"><span data-stu-id="fce26-138">Many exceptions thrown by a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client are caused by an exception on the service.</span></span> <span data-ttu-id="fce26-139">Di seguito ne vengono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="fce26-139">Some examples of this are:</span></span>  
  
-   <span data-ttu-id="fce26-140"><xref:System.Net.Sockets.SocketException>: connessione esistente chiusa forzatamente dall'host remoto.</span><span class="sxs-lookup"><span data-stu-id="fce26-140"><xref:System.Net.Sockets.SocketException>: An existing connection was forcibly closed by the remote host.</span></span>  
  
-   <span data-ttu-id="fce26-141"><xref:System.ServiceModel.CommunicationException>: connessione sottostante chiusa in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="fce26-141"><xref:System.ServiceModel.CommunicationException>: The underlying connection was closed unexpectedly.</span></span>  
  
-   <span data-ttu-id="fce26-142"><xref:System.ServiceModel.CommunicationObjectAbortedException>: connessione socket interrotta.</span><span class="sxs-lookup"><span data-stu-id="fce26-142"><xref:System.ServiceModel.CommunicationObjectAbortedException>: The socket connection was aborted.</span></span> <span data-ttu-id="fce26-143">Questo problema può essere causato da un errore durante l'elaborazione del messaggio, da un timeout di ricezione superato dall'host remoto o da un problema della risorsa di rete sottostante.</span><span class="sxs-lookup"><span data-stu-id="fce26-143">This could be caused by an error processing your message, a receive time-out being exceeded by the remote host, or an underlying network resource issue.</span></span>  
  
 <span data-ttu-id="fce26-144">Quando si verificano questi tipi di eccezioni, il modo migliore per risolvere il problema è attivare la traccia sul lato servizio e individuare l'eccezione che si è verificata.</span><span class="sxs-lookup"><span data-stu-id="fce26-144">When these types of exceptions occur, the best way to solve the problem is to turn on tracing on the service side and determine what exception occurred there.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="fce26-145">la traccia, vedere [traccia](../../../docs/framework/wcf/diagnostics/tracing/index.md) e [utilizzando opzioni di traccia per risolvere i problemi dell'applicazione](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span><span class="sxs-lookup"><span data-stu-id="fce26-145"> tracing, see [Tracing](../../../docs/framework/wcf/diagnostics/tracing/index.md) and [Using Tracing to Troubleshoot Your Application](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fce26-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fce26-146">See Also</span></span>  
 [<span data-ttu-id="fce26-147">Procedura: Creare un client</span><span class="sxs-lookup"><span data-stu-id="fce26-147">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="fce26-148">Procedura: accedere ai servizi con un contratto Duplex</span><span class="sxs-lookup"><span data-stu-id="fce26-148">How to: Access Services with a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [<span data-ttu-id="fce26-149">Procedura: chiamare operazioni del servizio in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="fce26-149">How to: Call Service Operations Asynchronously</span></span>](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)  
 [<span data-ttu-id="fce26-150">Procedura: accedere ai servizi con unidirezionale e contratti Request / Reply</span><span class="sxs-lookup"><span data-stu-id="fce26-150">How to: Access Services with One-Way and Request-Reply Contracts</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)  
 [<span data-ttu-id="fce26-151">Procedura: accedere a WSE 3.0 Service</span><span class="sxs-lookup"><span data-stu-id="fce26-151">How to: Access a WSE 3.0 Service</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)  
 [<span data-ttu-id="fce26-152">Informazioni sul codice Client generato</span><span class="sxs-lookup"><span data-stu-id="fce26-152">Understanding Generated Client Code</span></span>](../../../docs/framework/wcf/feature-details/understanding-generated-client-code.md)  
 [<span data-ttu-id="fce26-153">Procedura: migliorare l'avvio del tempo di applicazioni Client WCF usando XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="fce26-153">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)  
 [<span data-ttu-id="fce26-154">Specifica del comportamento in fase di esecuzione dei client</span><span class="sxs-lookup"><span data-stu-id="fce26-154">Specifying Client Run-Time Behavior</span></span>](../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [<span data-ttu-id="fce26-155">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="fce26-155">Configuring Client Behaviors</span></span>](../../../docs/framework/wcf/configuring-client-behaviors.md)
