---
title: Cenni preliminari sulla creazione di endpoint
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], overview
ms.assetid: f4dce0fb-6f54-47e6-8054-86d7f574b91c
ms.openlocfilehash: 46ca6294d68537e86a319b55d8c11e3ae0084738
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="endpoint-creation-overview"></a><span data-ttu-id="01bbf-102">Cenni preliminari sulla creazione di endpoint</span><span class="sxs-lookup"><span data-stu-id="01bbf-102">Endpoint Creation Overview</span></span>
<span data-ttu-id="01bbf-103">Tutte le comunicazioni con un servizio Windows Communication Foundation (WCF) viene eseguita mediante il *endpoint* del servizio.</span><span class="sxs-lookup"><span data-stu-id="01bbf-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="01bbf-104">Gli endpoint forniscono ai client l'accesso alle funzionalità che offre un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="01bbf-104">Endpoints provide the clients access to the functionality that a WCF service offers.</span></span> <span data-ttu-id="01bbf-105">Questa sezione descrive la struttura di un endpoint e viene illustrato come definire un endpoint nella configurazione e nel codice.</span><span class="sxs-lookup"><span data-stu-id="01bbf-105">This section describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="01bbf-106">Struttura di un endpoint</span><span class="sxs-lookup"><span data-stu-id="01bbf-106">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="01bbf-107">Ogni endpoint contiene un indirizzo che indica dove individuare l'endpoint, un'associazione che specifica in che modo un client può comunicare con l'endpoint e un contratto che identifica i metodi disponibili.</span><span class="sxs-lookup"><span data-stu-id="01bbf-107">Each endpoint contains an address that indicates where to find the endpoint, a binding that specifies how a client can communicate with the endpoint, and a contract that identifies the methods available.</span></span>  
  
-   <span data-ttu-id="01bbf-108">**Indirizzo**.</span><span class="sxs-lookup"><span data-stu-id="01bbf-108">**Address**.</span></span> <span data-ttu-id="01bbf-109">L'indirizzo identifica in modo univoco l'endpoint e comunica ai potenziali utenti l'ubicazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="01bbf-109">The address uniquely identifies the endpoint and tells potential consumers where the service is located.</span></span> <span data-ttu-id="01bbf-110">È rappresentato nel modello a oggetti WCF per il <xref:System.ServiceModel.EndpointAddress> indirizzo, che contiene un URI (Uniform Resource Identifier) e proprietà dell'indirizzo che includono un'identità, alcuni elementi di Web Services Description Language (WSDL) e una raccolta di facoltativo intestazioni.</span><span class="sxs-lookup"><span data-stu-id="01bbf-110">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> address, which contains a Uniform Resource Identifier (URI) and address properties that include an identity, some Web Services Description Language (WSDL) elements, and a collection of optional headers.</span></span> <span data-ttu-id="01bbf-111">Le intestazioni facoltative forniscono dettagli aggiuntivi sull'indirizzo per identificare o interagire con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="01bbf-111">The optional headers provide additional detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="01bbf-112">Per altre informazioni, vedere [specificando un indirizzo Endpoint](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="01bbf-112">For more information, see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
-   <span data-ttu-id="01bbf-113">**Associazione**.</span><span class="sxs-lookup"><span data-stu-id="01bbf-113">**Binding**.</span></span> <span data-ttu-id="01bbf-114">L'associazione specifica la modalità di comunicazione con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="01bbf-114">The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="01bbf-115">L'associazione specifica in che modo l'endpoint comunica con il mondo, incluso il protocollo di trasporto da usare (ad esempio, TCP o HTTP), il tipo di codifica da usare per i messaggi (ad esempio, testo o binaria) e i requisiti di sicurezza necessari (ad esempio, Secure Sockets Layer [SSL] o sicurezza dei messaggi SOAP).</span><span class="sxs-lookup"><span data-stu-id="01bbf-115">The binding specifies how the endpoint communicates with the world, including which transport protocol to use (for example, TCP or HTTP), which encoding to use for the messages (for example, text or binary), and which security requirements are necessary (for example, Secure Sockets Layer [SSL] or SOAP message security).</span></span> <span data-ttu-id="01bbf-116">Per altre informazioni, vedere [usando le associazioni per configurare servizi e client](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="01bbf-116">For more information, see [Using Bindings to Configure Services and Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span></span>  
  
-   <span data-ttu-id="01bbf-117">**Contratto di servizio**.</span><span class="sxs-lookup"><span data-stu-id="01bbf-117">**Service contract**.</span></span> <span data-ttu-id="01bbf-118">Il contratto di servizio delinea la funzionalità che l'endpoint espone al client.</span><span class="sxs-lookup"><span data-stu-id="01bbf-118">The service contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="01bbf-119">Un contratto specifica le operazioni che un client può richiamare, il modulo del messaggio e il tipo di parametri o dati di input necessari per chiamare l'operazione e il tipo di elaborazione o messaggio di risposta che il client può aspettarsi.</span><span class="sxs-lookup"><span data-stu-id="01bbf-119">A contract specifies the operations that a client can call, the form of the message and the type of input parameters or data required to call the operation, and the kind of processing or response message the client can expect.</span></span> <span data-ttu-id="01bbf-120">Tre tipi di contratti di base corrispondono a modelli di scambio dei messaggi (MEP, Message Exchange Pattern) di base: datagramma (unidirezionale), request/reply e duplex (bidirezionale).</span><span class="sxs-lookup"><span data-stu-id="01bbf-120">Three basic types of contracts correspond to basic message exchange patterns (MEPs): datagram (one-way), request/reply, and duplex (bidirectional).</span></span> <span data-ttu-id="01bbf-121">Il contratto di servizio può inoltre usare contratti dati e contratti di messaggio per richiedere tipi di dati e formati di messaggio specifici al momento dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="01bbf-121">The service contract can also employ data and message contracts to require specific data types and message formats when being accessed.</span></span> <span data-ttu-id="01bbf-122">Per ulteriori informazioni su come definire un contratto di servizio, vedere [progettazione contratti di servizio](../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="01bbf-122">For more information about how to define a service contract, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span> <span data-ttu-id="01bbf-123">Per ricevere messaggi dal servizio in un modello di scambio dei messaggi (MEP) duplex, è possibile che un client debba implementare un contratto definito dal servizio, detto contratto di callback.</span><span class="sxs-lookup"><span data-stu-id="01bbf-123">Note that a client may also be required to implement a service-defined contract, called a callback contract, to receive messages from the service in a duplex MEP.</span></span> <span data-ttu-id="01bbf-124">Per ulteriori informazioni, vedere [servizi Duplex](../../../docs/framework/wcf/feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="01bbf-124">For more information, see [Duplex Services](../../../docs/framework/wcf/feature-details/duplex-services.md).</span></span>  
  
 <span data-ttu-id="01bbf-125">L'endpoint per un servizio può essere specificato in modo imperativo mediante l'uso di codice oppure in modo dichiarativo mediante la configurazione.</span><span class="sxs-lookup"><span data-stu-id="01bbf-125">The endpoint for a service can be specified either imperatively by using code or declaratively through configuration.</span></span> <span data-ttu-id="01bbf-126">Se non è specificato alcun endpoint, il runtime ne fornisce di predefiniti aggiungendone uno per ogni indirizzo di base per ciascun contratto di servizio implementato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="01bbf-126">If no endpoints are specified then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="01bbf-127">In genere definire endpoint nel codice non è pratico in quanto le associazioni e gli indirizzi di un servizio distribuito sono solitamente diversi da quelli usati durante lo sviluppo del servizio.</span><span class="sxs-lookup"><span data-stu-id="01bbf-127">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="01bbf-128">In genere è più pratico definire endpoint di servizio mediante la configurazione piuttosto che mediante codice.</span><span class="sxs-lookup"><span data-stu-id="01bbf-128">Generally, it is more practical to define service endpoints using configuration rather than code.</span></span> <span data-ttu-id="01bbf-129">Se le informazioni sull'associazione e sull'indirizzo non vengono incluse nel codice, tali dati possono essere modificati senza dover compilare e distribuire nuovamente l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="01bbf-129">Keeping the binding and addressing information out of the code allows them to change without having to recompile and redeploy the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01bbf-130">Quando si aggiunge un endpoint di servizio che esegue la rappresentazione, è necessario usare uno dei metodi <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> o il metodo <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> per caricare correttamente il contratto in un nuovo oggetto <xref:System.ServiceModel.Description.ServiceDescription>.</span><span class="sxs-lookup"><span data-stu-id="01bbf-130">When adding a service endpoint that performs impersonation, you must either use one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods or the <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> method to properly load the contract into a new <xref:System.ServiceModel.Description.ServiceDescription> object.</span></span>  
  
## <a name="defining-endpoints-in-code"></a><span data-ttu-id="01bbf-131">Definizione di endpoint nel codice</span><span class="sxs-lookup"><span data-stu-id="01bbf-131">Defining Endpoints in Code</span></span>  
 <span data-ttu-id="01bbf-132">Nell'esempio riportato di seguito viene illustrato come specificare un endpoint nel codice.</span><span class="sxs-lookup"><span data-stu-id="01bbf-132">The following example illustrates how to specify an endpoint in code with the following:</span></span>  
  
-   <span data-ttu-id="01bbf-133">Definire un contratto per un `IEcho` tipo di servizio che accetta un nome e l'istruzione echo con la risposta "Hello \<nome >!".</span><span class="sxs-lookup"><span data-stu-id="01bbf-133">Define a contract for an `IEcho` type of service that accepts someone's name and echo with the response "Hello \<name>!".</span></span>  
  
-   <span data-ttu-id="01bbf-134">Implementare un servizio `Echo` del tipo definito dal contratto `IEcho`.</span><span class="sxs-lookup"><span data-stu-id="01bbf-134">Implement an `Echo` service of the type defined by the `IEcho` contract.</span></span>  
  
-   <span data-ttu-id="01bbf-135">Specificare l'indirizzo di endpoint http://localhost:8000/Echo per il servizio.</span><span class="sxs-lookup"><span data-stu-id="01bbf-135">Specify an endpoint address of http://localhost:8000/Echo for the service.</span></span>  
  
-   <span data-ttu-id="01bbf-136">Configurare il servizio `Echo` usando un'associazione <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="01bbf-136">Configure the `Echo` service using a <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   public interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   class Echo : IEcho  
   {  
      public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      public static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Use a predefined WSHttpBinding to configure the service.  
          WSHttpBinding binding = new WSHttpBinding();  
  
          // Add the endpoint for this service to the service host.  
          serviceHost.AddServiceEndpoint(  
             typeof(IEcho),   
             binding,   
             echoUri  
           );  
  
          // Open the service host to run it.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Create a ServiceHost for the Echo service.  
Dim svcHost As ServiceHost = New ServiceHost(GetType(HelloWorld), echoUri)  
  
' Use a predefined WSHttpBinding to configure the service.  
Dim binding As New WSHttpBinding()  
  
' Add the endpoint for this service to the service host.  
serviceHost.AddServiceEndpoint(GetType(IEcho), binding, echoUri)  
  
' Open the service host to run it.  
serviceHost.Open()  
```  
  
> [!NOTE]
>  <span data-ttu-id="01bbf-137">L'host del servizio viene creato con un indirizzo di base. Il resto dell'indirizzo, relativo all'indirizzo di base, viene quindi specificato come parte di un endpoint.</span><span class="sxs-lookup"><span data-stu-id="01bbf-137">The service host is created with a base address and then the rest of the address, relative to the base address, is specified as part of an endpoint.</span></span> <span data-ttu-id="01bbf-138">Questo partizionamento dell'indirizzo consente a più endpoint di essere definiti in modo più appropriato per i servizi presenti in un host.</span><span class="sxs-lookup"><span data-stu-id="01bbf-138">This partitioning of the address allows multiple endpoints to be defined more conveniently for services at a host.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01bbf-139">Le proprietà di <xref:System.ServiceModel.Description.ServiceDescription> nell'applicazione del servizio non devono essere modificate dopo la chiamata al metodo <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> su <xref:System.ServiceModel.ServiceHostBase>.</span><span class="sxs-lookup"><span data-stu-id="01bbf-139">Properties of <xref:System.ServiceModel.Description.ServiceDescription> in the service application must not be modified subsequent to the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method on <xref:System.ServiceModel.ServiceHostBase>.</span></span> <span data-ttu-id="01bbf-140">Se vengono modificati dopo questo punto, alcuni membri, ad esempio la proprietà <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> e i metodi `AddServiceEndpoint` su <xref:System.ServiceModel.ServiceHostBase> e <xref:System.ServiceModel.ServiceHost>, generano un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="01bbf-140">Some members, such as the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property and the `AddServiceEndpoint` methods on <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.ServiceHost>, throw an exception if modified past that point.</span></span> <span data-ttu-id="01bbf-141">Altri consentono la modifica, ma il risultato è indefinito.</span><span class="sxs-lookup"><span data-stu-id="01bbf-141">Others permit you to modify them, but the result is undefined.</span></span>  
>   
>  <span data-ttu-id="01bbf-142">Analogamente, sul client i valori <xref:System.ServiceModel.Description.ServiceEndpoint> non devono essere modificati dopo la chiamata a <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> su <xref:System.ServiceModel.ChannelFactory>.</span><span class="sxs-lookup"><span data-stu-id="01bbf-142">Similarly, on the client the <xref:System.ServiceModel.Description.ServiceEndpoint> values must not be modified after the call to <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> on the <xref:System.ServiceModel.ChannelFactory>.</span></span> <span data-ttu-id="01bbf-143">Se viene modificata dopo questo punto, la proprietà <xref:System.ServiceModel.ChannelFactory.Credentials%2A> genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="01bbf-143">The <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property throws an exception if modified past that point.</span></span> <span data-ttu-id="01bbf-144">Gli altri valori della descrizione client possono essere modificati senza errore, ma il risultato è indefinito.</span><span class="sxs-lookup"><span data-stu-id="01bbf-144">The other client description values can be modified without error, but the result is undefined.</span></span>  
>   
>  <span data-ttu-id="01bbf-145">Per il servizio o per il client, è consigliabile modificare la descrizione prima di chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="01bbf-145">Whether for the service or client, it is recommended that you modify the description prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>  
  
## <a name="defining-endpoints-in-configuration"></a><span data-ttu-id="01bbf-146">Definizione di endpoint nella configurazione</span><span class="sxs-lookup"><span data-stu-id="01bbf-146">Defining Endpoints in Configuration</span></span>  
 <span data-ttu-id="01bbf-147">Durante la creazione di un'applicazione è spesso necessario rimettere le decisioni all'amministratore che distribuisce l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="01bbf-147">When creating an application, you often want to defer decisions to the administrator who is deploying the application.</span></span> <span data-ttu-id="01bbf-148">Spesso non è possibile prevedere, ad esempio, quale sarà l'indirizzo (URI) di un servizio.</span><span class="sxs-lookup"><span data-stu-id="01bbf-148">For example, there is often no way of knowing in advance what a service address (a URI) will be.</span></span> <span data-ttu-id="01bbf-149">Anziché inserire un indirizzo nel codice, è preferibile consentire che questa operazione venga eseguita da un amministratore dopo la creazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="01bbf-149">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="01bbf-150">Questa flessibilità viene realizzata attraverso la configurazione.</span><span class="sxs-lookup"><span data-stu-id="01bbf-150">This flexibility is accomplished through configuration.</span></span> <span data-ttu-id="01bbf-151">Per informazioni dettagliate, vedere [configurazione dei servizi](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="01bbf-151">For details, see [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01bbf-152">Utilizzare il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con il `/config:` *filename*`[,`*filename* `]` passa a Consente di creare rapidamente i file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="01bbf-152">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config:`*filename*`[,`*filename*`]` switch to quickly create configuration files.</span></span>  
  
## <a name="using-default-endpoints"></a><span data-ttu-id="01bbf-153">Uso di endpoint predefiniti</span><span class="sxs-lookup"><span data-stu-id="01bbf-153">Using Default Endpoints</span></span>  
 <span data-ttu-id="01bbf-154">Se non è specificato alcun endpoint nel codice o nella configurazione, il runtime ne fornisce di predefiniti aggiungendone uno per ogni indirizzo di base per ciascun contratto di servizio implementato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="01bbf-154">If no endpoints are specified in code or in configuration then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="01bbf-155">L'indirizzo di base può essere specificato nel codice o nella configurazione e gli endpoint predefiniti vengono aggiunti quando viene chiamato <xref:System.ServiceModel.ICommunicationObject.Open> in <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="01bbf-155">The base address can be specified in code or in configuration, and the default endpoints are added when <xref:System.ServiceModel.ICommunicationObject.Open> is called on the <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="01bbf-156">Questo esempio è identico a quello della sezione precedente, ma poiché non è stato specificato alcun endpoint, vengono aggiunti gli endpoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="01bbf-156">This example is the same example from the previous section, but since no endpoints are specified, the default endpoints are added.</span></span>  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   Interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   Class Echo : IEcho  
   {  
      Public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Open the service host to run it. Default endpoints  
          // are added when the service is opened.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Open the service host to run it. Default endpoints  
' are added when the service is opened.  
serviceHost.Open()  
```  
  
 <span data-ttu-id="01bbf-157">Se vengono forniti endpoint in modo esplicito, è comunque possibile aggiungere gli endpoint predefiniti chiamando <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> su <xref:System.ServiceModel.ServiceHost> prima di chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="01bbf-157">If endpoints are explicitly provided, the default endpoints can still be added by calling <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> on the <xref:System.ServiceModel.ServiceHost> before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="01bbf-158">Per ulteriori informazioni sugli endpoint predefiniti, vedere [configurazione semplificata](../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="01bbf-158">For more information about default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01bbf-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01bbf-159">See Also</span></span>  
 [<span data-ttu-id="01bbf-160">Implementazione dei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="01bbf-160">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
