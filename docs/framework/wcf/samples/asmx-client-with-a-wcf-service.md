---
title: Client ASMX con un servizio WCF
ms.date: 03/30/2017
ms.assetid: 3ea381ee-ac7d-4d62-8c6c-12dc3650879f
ms.openlocfilehash: 93a881e486d82183fc42c524f3d83527c649516d
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
ms.locfileid: "33805129"
---
# <a name="asmx-client-with-a-wcf-service"></a><span data-ttu-id="4ea7e-102">Client ASMX con un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="4ea7e-102">ASMX Client with a WCF Service</span></span>
<span data-ttu-id="4ea7e-103">In questo esempio viene illustrato come creare un servizio utilizzando Windows Communication Foundation (WCF) e quindi accedere al servizio da un client non WCF, ad esempio un client ASMX.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-103">This sample demonstrates how to create a service using Windows Communication Foundation (WCF) and then access the service from a non-WCF client, such as an ASMX client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ea7e-104">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="4ea7e-105">Questo esempio è costituito da un programma di console client (.exe) e da una libreria di servizi (.dll) ospitati da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="4ea7e-105">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="4ea7e-106">Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-106">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="4ea7e-107">Il contratto viene definito dall'interfaccia `ICalculator` che espone operazioni matematiche (`Add`, `Subtract`, `Multiply` e `Divide`).</span><span class="sxs-lookup"><span data-stu-id="4ea7e-107">The contract is defined by the `ICalculator` interface, which exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="4ea7e-108">Il client ASMX esegue richieste sincrone a un'operazione matematica e il servizio risponde fornendo il risultato.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-108">The ASMX client makes synchronous requests to a math operation and the service replies with the result.</span></span>  
  
 <span data-ttu-id="4ea7e-109">Il servizio implementa un contratto `ICalculator`, come definito nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-109">The service implements an `ICalculator` contract as defined in the following code.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="4ea7e-110"><xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Xml.Serialization.XmlSerializer> eseguono il mapping dei tipi CLR a una rappresentazione XML.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-110">The <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Xml.Serialization.XmlSerializer> map CLR types to an XML representation.</span></span> <span data-ttu-id="4ea7e-111"><xref:System.Runtime.Serialization.DataContractSerializer> interpreta alcune rappresentazioni XML in modo diverso da XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-111">The <xref:System.Runtime.Serialization.DataContractSerializer> interprets some XML representations differently than XmlSerializer.</span></span> <span data-ttu-id="4ea7e-112">Generatori proxy non WCF, ad esempio Wsdl.exe, generano un'interfaccia più efficace quando viene utilizzata XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-112">Non-WCF proxy generators, such as Wsdl.exe, generate a more usable interface when the XmlSerializer is being used.</span></span> <span data-ttu-id="4ea7e-113">Il <xref:System.ServiceModel.XmlSerializerFormatAttribute> è collegato il `ICalculator` interfaccia, per garantire che venga utilizzato XmlSerializer per il mapping dei tipi CLR in XML.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-113">The <xref:System.ServiceModel.XmlSerializerFormatAttribute> is applied to the `ICalculator` interface, to ensure that the XmlSerializer is used for mapping CLR types to XML.</span></span> <span data-ttu-id="4ea7e-114">L'implementazione del servizio calcola e restituisce il risultato appropriato.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-114">The service implementation calculates and returns the appropriate result.</span></span>  
  
 <span data-ttu-id="4ea7e-115">Il servizio espone un solo endpoint per comunicare con il servizio che viene definito mediante un file di configurazione (Web.config).</span><span class="sxs-lookup"><span data-stu-id="4ea7e-115">The service exposes a single endpoint for communicating with the service, defined using a configuration file (Web.config).</span></span> <span data-ttu-id="4ea7e-116">L'endpoint è costituito da un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-116">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="4ea7e-117">Il servizio espone l'endpoint dell'indirizzo di base fornito dall'host IIS.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-117">The service exposes the endpoint at the base address provided by the Internet Information Services (IIS) host.</span></span> <span data-ttu-id="4ea7e-118">L'attributo `binding` è impostato su basicHttpBinding  per fornire la comunicazione HTTP mediante SOAP 1.1, che è conforme a WS-BasicProfile 1.1, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-118">The `binding` attribute is set to basicHttpBinding that provides HTTP communications using SOAP 1.1, which is compliant with WS-I BasicProfile 1.1 as shown in the following sample configuration.</span></span>  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc.  -->  
    <endpoint address=""  
              binding="basicHttpBinding"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </service>  
</services>  
```  
  
 <span data-ttu-id="4ea7e-119">Il client ASMX comunica con il servizio WCF utilizzando un proxy tipizzato generato dall'utilità di Web Services Description Language (WSDL) (Wsdl.exe).</span><span class="sxs-lookup"><span data-stu-id="4ea7e-119">The ASMX client communicates with the WCF service using a typed proxy that is generated by the Web Services Description Language (WSDL) utility (Wsdl.exe).</span></span> <span data-ttu-id="4ea7e-120">Il proxy tipizzato è contenuto nel file generatedClient.cs.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-120">The typed proxy is contained in the file generatedClient.cs.</span></span> <span data-ttu-id="4ea7e-121">L'utilità WSDL recupera i metadati per il servizio specificato e genera un proxy tipizzato che può essere utilizzato da un client per comunicare.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-121">The WSDL utility retrieves metadata for the specified service and generates a typed proxy for use by a client to communicate.</span></span> <span data-ttu-id="4ea7e-122">Per impostazione predefinita, il framework non espone metadati.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-122">By default, the framework does not expose any metadata.</span></span> <span data-ttu-id="4ea7e-123">Per esporre i metadati necessari per generare il proxy, è necessario aggiungere un [ \<serviceMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) e impostare il relativo `httpGetEnabled` attributo `True` come illustrato nella configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-123">To expose the metadata required to generate the proxy, you must add a [\<serviceMetadata>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) and set its `httpGetEnabled` attribute to `True` as shown in the following configuration.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- Setting httpGetEnabled to True on the serviceMetadata  
           behavior exposes the service's wsdl at <base address>?wsdl :  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="4ea7e-124">Eseguire il comando seguente da un prompt dei comandi nella directory del client per generare il proxy tipizzato.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-124">Run the following command from a command prompt in the client directory to generate the typed proxy.</span></span>  
  
```console  
wsdl /n:Microsoft.ServiceModel.Samples /o:generatedClient.cs /urlkey:CalculatorServiceAddress http://localhost/servicemodelsamples/service.svc?wsdl  
```  
  
 <span data-ttu-id="4ea7e-125">Utilizzando il proxy tipizzato generato, il client può accedere a uno specifico endpoint del servizio configurando l'indirizzo appropriato.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-125">By using the generated typed proxy, the client can access a given service endpoint by configuring the appropriate address.</span></span> <span data-ttu-id="4ea7e-126">Il client utilizza un file di configurazione (App.config) per specificare l'endpoint con il quale comunicare.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-126">The client uses a configuration file (App.config) to specify the endpoint to communicate with.</span></span>  
  
```xml  
<appSettings>  
  <add key="CalculatorServiceAddress"   
       value="http://localhost/ServiceModelSamples/service.svc"/>  
</appSettings>  
```  
  
 <span data-ttu-id="4ea7e-127">L'implementazione client costruisce un'istanza del proxy tipizzato per iniziare a comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-127">The client implementation constructs an instance of the typed proxy to begin communicating with the service.</span></span>  
  
```  
// Create a client to the CalculatorService.  
using (CalculatorService client = new CalculatorService())  
{  
    // Call the Add service operation.  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation.  
    value1 = 145.00D;  
    value2 = 76.54D;  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Multiply service operation.  
    value1 = 9.00D;  
    value2 = 81.25D;  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    value1 = 22.00D;  
    value2 = 7.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
}  
  
Console.WriteLine();  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
```  
  
 <span data-ttu-id="4ea7e-128">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="4ea7e-129">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-129">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4ea7e-130">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="4ea7e-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4ea7e-131">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4ea7e-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="4ea7e-132">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4ea7e-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="4ea7e-133">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4ea7e-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ea7e-134">Per ulteriori informazioni sul passaggio e restituzione di dati complessi tipi, vedere: [Data Binding in un Client di Windows Form](../../../../docs/framework/wcf/samples/data-binding-in-a-windows-forms-client.md), [Data Binding in un Client Windows Presentation Foundation](../../../../docs/framework/wcf/samples/data-binding-in-a-wpf-client.md), e [dati Associazione in un Client ASP.NET](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md)</span><span class="sxs-lookup"><span data-stu-id="4ea7e-134">For more information about passing and returning complex data types see: [Data Binding in a Windows Forms Client](../../../../docs/framework/wcf/samples/data-binding-in-a-windows-forms-client.md), [Data Binding in a Windows Presentation Foundation Client](../../../../docs/framework/wcf/samples/data-binding-in-a-wpf-client.md), and [Data Binding in an ASP.NET Client](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4ea7e-135">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4ea7e-136">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4ea7e-137">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4ea7e-138">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="4ea7e-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\ASMX`  
  
## <a name="see-also"></a><span data-ttu-id="4ea7e-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ea7e-139">See Also</span></span>
