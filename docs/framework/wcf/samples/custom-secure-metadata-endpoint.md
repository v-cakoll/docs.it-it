---
title: Endpoint di metadati protetto personalizzato
ms.date: 03/30/2017
ms.assetid: 9e369e99-ea4a-49ff-aed2-9fdf61091a48
ms.openlocfilehash: 89f12b4490d556884aaa15dcb102b5ad876707ba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183839"
---
# <a name="custom-secure-metadata-endpoint"></a><span data-ttu-id="931e7-102">Endpoint di metadati protetto personalizzato</span><span class="sxs-lookup"><span data-stu-id="931e7-102">Custom Secure Metadata Endpoint</span></span>
<span data-ttu-id="931e7-103">In questo esempio viene illustrato come implementare un servizio con un endpoint di metadati sicuro che utilizza una delle associazioni di scambio non metadati e come configurare [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) o i client per recuperare i metadati da tale endpoint di metadati.</span><span class="sxs-lookup"><span data-stu-id="931e7-103">This sample demonstrates how to implement a service with a secure metadata endpoint that uses one of the non-metadata exchange bindings, and how to configure [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) or clients to fetch the metadata from such a metadata endpoint.</span></span> <span data-ttu-id="931e7-104">Per l'esposizione di endpoint di metadati sono disponibili due associazioni fornite dal sistema, cioè mexHttpBinding e mexHttpsBinding.</span><span class="sxs-lookup"><span data-stu-id="931e7-104">There are two system-provided bindings available for exposing metadata endpoints: mexHttpBinding and mexHttpsBinding.</span></span> <span data-ttu-id="931e7-105">L'associazione mexHttpBinding viene utilizzata per esporre un endpoint di metadati tramite HTTP in modo non protetto.</span><span class="sxs-lookup"><span data-stu-id="931e7-105">mexHttpBinding is used to expose a metadata endpoint over HTTP in a non-secure manner.</span></span> <span data-ttu-id="931e7-106">L'associazione mexHttpsBinding viene utilizzata per esporre un endpoint di metadati tramite HTTPS in modo protetto.</span><span class="sxs-lookup"><span data-stu-id="931e7-106">mexHttpsBinding is used to expose a metadata endpoint over HTTPS in a secure manner.</span></span> <span data-ttu-id="931e7-107">In questo esempio viene illustrato come esporre un endpoint di metadati protetto tramite <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="931e7-107">This sample illustrates how to expose a secure metadata endpoint using the <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="931e7-108">Procedere in questo modo quando si desidera modificare le impostazioni di sicurezza sull'associazione senza utilizzare HTTPS.</span><span class="sxs-lookup"><span data-stu-id="931e7-108">You would want to do this when you want to change the security settings on the binding, but you do not want to use HTTPS.</span></span> <span data-ttu-id="931e7-109">Se si utilizza mexHttpsBinding, l'endpoint di metadati sarà protetto, ma non sarà in alcun modo possibile modificare le impostazioni dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="931e7-109">If you use the mexHttpsBinding your metadata endpoint will be secure, but there is no way to modify the binding settings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="931e7-110">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="931e7-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="931e7-111">Service</span><span class="sxs-lookup"><span data-stu-id="931e7-111">Service</span></span>  
 <span data-ttu-id="931e7-112">Il servizio di questo esempio è dotato di due endpoint.</span><span class="sxs-lookup"><span data-stu-id="931e7-112">The service in this sample has two endpoints.</span></span> <span data-ttu-id="931e7-113">L'endpoint dell'applicazione invia al contratto `ICalculator` un `WSHttpBinding` con la `ReliableSession` attivata e la sicurezza dei `Message` che utilizza certificati.</span><span class="sxs-lookup"><span data-stu-id="931e7-113">The application endpoint serves the `ICalculator` contract on a `WSHttpBinding` with `ReliableSession` enabled and `Message` security using certificates.</span></span> <span data-ttu-id="931e7-114">L'endpoint di metadati utilizza inoltre `WSHttpBinding`, con le stesse impostazioni di sicurezza ma senza `ReliableSession`.</span><span class="sxs-lookup"><span data-stu-id="931e7-114">The metadata endpoint also uses `WSHttpBinding`, with the same security settings but with no `ReliableSession`.</span></span> <span data-ttu-id="931e7-115">La configurazione pertinente è la seguente:</span><span class="sxs-lookup"><span data-stu-id="931e7-115">Here is the relevant configuration:</span></span>  
  
```xml  
<services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- use base address provided by host -->  
     <endpoint address=""  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding2"  
       contract="Microsoft.ServiceModel.Samples.ICalculator" />  
     <endpoint address="mex"  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding1"  
       contract="IMetadataExchange" />  
     </service>  
 </services>  
 <bindings>  
   <wsHttpBinding>  
     <binding name="Binding1">  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
     <binding name="Binding2">  
       <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
   </wsHttpBinding>  
 </bindings>  
```  
  
 <span data-ttu-id="931e7-116">In molti degli altri esempi, l'endpoint di metadati utilizza il `mexHttpBinding` predefinito, che non è protetto.</span><span class="sxs-lookup"><span data-stu-id="931e7-116">In many of the other samples, the metadata endpoint uses the default `mexHttpBinding`, which is not secure.</span></span> <span data-ttu-id="931e7-117">Qui i metadati sono protetti utilizzando `WSHttpBinding` con sicurezza dei `Message`.</span><span class="sxs-lookup"><span data-stu-id="931e7-117">Here the metadata is secured using `WSHttpBinding` with `Message` security.</span></span> <span data-ttu-id="931e7-118">Affinché i client di metadati possano recuperare questi metadati, è necessario che siano configurati con un'associazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="931e7-118">In order for metadata clients to retrieve this metadata, they must be configured with a matching binding.</span></span> <span data-ttu-id="931e7-119">Nell'esempio viene illustrato l'utilizzo di due di questi client.</span><span class="sxs-lookup"><span data-stu-id="931e7-119">This sample demonstrates two such clients.</span></span>  
  
 <span data-ttu-id="931e7-120">Il primo client utilizza Svcutil.exe per recuperare i metadati e generare il codice del client e la configurazione in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="931e7-120">The first client uses Svcutil.exe to fetch the metadata and generate client code and configuration at design time.</span></span> <span data-ttu-id="931e7-121">Il servizio utilizza un'associazione non predefinita per i metadati, quindi lo strumento Svcutil.exe deve essere specificamente configurato in modo da ottenere i metadati dal servizio che utilizza quell'associazione.</span><span class="sxs-lookup"><span data-stu-id="931e7-121">Because the service uses a non-default binding for the metadata, the Svcutil.exe tool must be specifically configured so that it can get the metadata from the service using that binding.</span></span>  
  
 <span data-ttu-id="931e7-122">Il secondo client utilizza il `MetadataResolver` per recuperare dinamicamente i metadati per un contratto noto e richiamare quindi le operazioni sul client generato dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="931e7-122">The second client uses the `MetadataResolver` to dynamically fetch the metadata for a known contract and then invoke operations on the dynamically generated client.</span></span>  
  
## <a name="svcutil-client"></a><span data-ttu-id="931e7-123">Client Svcutil</span><span class="sxs-lookup"><span data-stu-id="931e7-123">Svcutil client</span></span>  
 <span data-ttu-id="931e7-124">Quando si utilizza l'associazione predefinita per ospitare l'endpoint `IMetadataExchange`, è possibile eseguire Svcutil.exe con l'indirizzo di quell'endpoint:</span><span class="sxs-lookup"><span data-stu-id="931e7-124">When using the default binding to host your `IMetadataExchange` endpoint, you can run Svcutil.exe with the address of that endpoint:</span></span>  
  
```console  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="931e7-125">e funziona.</span><span class="sxs-lookup"><span data-stu-id="931e7-125">and it works.</span></span> <span data-ttu-id="931e7-126">Ma in questo esempio, il server utilizza un endpoint non predefinito per ospitare i metadati.</span><span class="sxs-lookup"><span data-stu-id="931e7-126">But in this sample, the server uses a non-default endpoint to host the metadata.</span></span> <span data-ttu-id="931e7-127">È quindi necessario richiedere a Svcutil.exe di utilizzare l'associazione corretta.</span><span class="sxs-lookup"><span data-stu-id="931e7-127">So Svcutil.exe must be instructed to use the correct binding.</span></span> <span data-ttu-id="931e7-128">Questa operazione può essere eseguita utilizzando un file Svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="931e7-128">This can be done using a Svcutil.exe.config file.</span></span>  
  
 <span data-ttu-id="931e7-129">Il file Svcutil.exe.config sembra un file di configurazione client normale.</span><span class="sxs-lookup"><span data-stu-id="931e7-129">The Svcutil.exe.config file looks like a normal client configuration file.</span></span> <span data-ttu-id="931e7-130">Le uniche differenze sono il nome e il contratto dell'endpoint:</span><span class="sxs-lookup"><span data-stu-id="931e7-130">The only unusual aspects are the client endpoint name and contract:</span></span>  
  
```xml  
<endpoint name="http"  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"  
          behaviorConfiguration="ClientCertificateBehavior"  
          contract="IMetadataExchange" />  
```  
  
 <span data-ttu-id="931e7-131">Il nome dell'endpoint deve essere il nome dello schema dell'indirizzo in cui vengono ospitati i metadati e il contratto dell'endpoint deve essere `IMetadataExchange`.</span><span class="sxs-lookup"><span data-stu-id="931e7-131">The endpoint name must be the name of the scheme of the address where the metadata is hosted and the endpoint contract must be `IMetadataExchange`.</span></span> <span data-ttu-id="931e7-132">In questo modo, quando viene eseguito Svcutil.exe con una riga di comando simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="931e7-132">Thus, when Svcutil.exe is run with a command-line such as the following:</span></span>  
  
```console  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="931e7-133">viene cercato l'endpoint denominato "http" e il contratto `IMetadataExchange` per configurare l'associazione e il comportamento dello scambio di comunicazione con l'endpoint di metadati.</span><span class="sxs-lookup"><span data-stu-id="931e7-133">it looks for the endpoint named "http" and contract `IMetadataExchange` to configure the binding and behavior of the communication exchange with the metadata endpoint.</span></span> <span data-ttu-id="931e7-134">Il resto del file Svcutil.exe.config nell'esempio specifica la configurazione di associazione e le credenziali del comportamento per fare corrispondere la configurazione del server all'endpoint di metadati.</span><span class="sxs-lookup"><span data-stu-id="931e7-134">The rest of the Svcutil.exe.config file in the sample specifies the binding configuration and behavior credentials to match the server's configuration of the metadata endpoint.</span></span>  
  
 <span data-ttu-id="931e7-135">Perché Svcutil.exe selezioni la configurazione in Svcutil.exe.config, Svcutil.exe deve trovarsi nella stessa directory del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="931e7-135">In order for Svcutil.exe to pick up the configuration in Svcutil.exe.config, Svcutil.exe must be in the same directory as the configuration file.</span></span> <span data-ttu-id="931e7-136">Di conseguenza, è necessario copiare Svcutil.exe dal percorso di installazione alla directory che contiene il file Svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="931e7-136">As a result, you must copy Svcutil.exe from its install location to the directory that contains the Svcutil.exe.config file.</span></span> <span data-ttu-id="931e7-137">Da tale directory, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="931e7-137">Then from that directory, run the following command:</span></span>  
  
```console  
.\svcutil.exe http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="931e7-138">Il leader ". \\" assicura che venga eseguita la copia di Svcutil.exe in questa directory (quella con un file Svcutil.exe.config corrispondente).</span><span class="sxs-lookup"><span data-stu-id="931e7-138">The leading ".\\" ensures that the copy of Svcutil.exe in this directory (the one which has a corresponding Svcutil.exe.config) is run.</span></span>  
  
## <a name="metadataresolver-client"></a><span data-ttu-id="931e7-139">Client di MetadataResolver</span><span class="sxs-lookup"><span data-stu-id="931e7-139">MetadataResolver client</span></span>  
 <span data-ttu-id="931e7-140">Se il client conosce il contratto e come comunicare con i metadati in fase di progettazione, può scoprire dinamicamente l'associazione e indirizzo degli endpoint dell'applicazione utilizzando `MetadataResolver`.</span><span class="sxs-lookup"><span data-stu-id="931e7-140">If the client knows the contract and how to talk to the metadata at design time, the client can dynamically find out the binding and address of application endpoints using the `MetadataResolver`.</span></span> <span data-ttu-id="931e7-141">In questo esempio di client viene illustrata questa operazione, oltre a come configurare l'associazione e le credenziali utilizzate dal `MetadataResolver` creando e configurando un `MetadataExchangeClient`.</span><span class="sxs-lookup"><span data-stu-id="931e7-141">This sample client demonstrates this, showing how to configure the binding and credentials used by `MetadataResolver` by creating and configuring a `MetadataExchangeClient`.</span></span>  
  
 <span data-ttu-id="931e7-142">Le stesse informazioni sull'associazione e sul certificato visualizzate in Svcutil.exe.config possono essere specificate in modo imperativo nel `MetadataExchangeClient`:</span><span class="sxs-lookup"><span data-stu-id="931e7-142">The same binding and certificate information that appeared in Svcutil.exe.config can be specified imperatively on the `MetadataExchangeClient`:</span></span>  
  
```csharp  
// Specify the Metadata Exchange binding and its security mode  
WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
// Create a MetadataExchangeClient for retrieving metadata, and set the // certificate details  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
mexClient.SoapCredentials.ClientCertificate.SetCertificate(    StoreLocation.CurrentUser, StoreName.My,  
    X509FindType.FindBySubjectName, "client.com");  
mexClient.SoapCredentials.ServiceCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(    StoreLocation.CurrentUser, StoreName.TrustedPeople,  
    X509FindType.FindBySubjectName, "localhost");  
```  
  
 <span data-ttu-id="931e7-143">Una volta configurato il `mexClient`, è possibile enumerare i contratti desiderati e utilizzare `MetadataResolver` per recuperare un elenco di endpoint con quei contratti:</span><span class="sxs-lookup"><span data-stu-id="931e7-143">With the `mexClient` configured, we can enumerate the contracts we are interested in, and use `MetadataResolver` to fetch a list of endpoints with those contracts:</span></span>  
  
```csharp  
// The contract we want to fetch metadata for  
Collection<ContractDescription> contracts = new Collection<ContractDescription>();  
ContractDescription contract = ContractDescription.GetContract(typeof(ICalculator));  
contracts.Add(contract);  
// Find endpoints for that contract  
EndpointAddress mexAddress = new EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
ServiceEndpointCollection endpoints = MetadataResolver.Resolve(contracts, mexAddress, mexClient);  
```  
  
 <span data-ttu-id="931e7-144">Infine, è possibile utilizzare le informazioni da quegli endpoint per inizializzare l'associazione e l'indirizzo di una `ChannelFactory` utilizzata per creare canali per comunicare con gli endpoint dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="931e7-144">Finally we can use the information from those endpoints to initialize the binding and address of a `ChannelFactory` used to create channels to communicate with the application endpoints.</span></span>  
  
```csharp  
ChannelFactory<ICalculator> cf = new ChannelFactory<ICalculator>(endpoint.Binding, endpoint.Address);  
```  
  
 <span data-ttu-id="931e7-145">Il punto importante di questo esempio di client è di dimostrare che, se si utilizza `MetadataResolver` ed è necessario specificare associazioni o comportamenti personalizzati per la comunicazione di scambio di metadati, è possibile utilizzare un `MetadataExchangeClient` per specificare quelle impostazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="931e7-145">The key point of this sample client is to demonstrate that, if you are using `MetadataResolver`, and you must specify custom bindings or behaviors for the metadata exchange communication, you can use a `MetadataExchangeClient` to specify those custom settings.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="931e7-146">Per impostare e compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="931e7-146">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="931e7-147">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="931e7-147">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="931e7-148">Per compilare la soluzione, seguire le istruzioni in [Compilazione di Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="931e7-148">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="931e7-149">Per eseguire l'esempio sullo stesso computer</span><span class="sxs-lookup"><span data-stu-id="931e7-149">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="931e7-150">Eseguire Setup.bat dalla cartella di installazione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="931e7-150">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="931e7-151">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="931e7-151">This installs all the certificates required for running the sample.</span></span> <span data-ttu-id="931e7-152">Si noti che Setup.bat utilizza lo strumento FindPrivateKey.exe, che viene installato eseguendo setupCertTool.bat dalla procedura di [installazione monouso per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="931e7-152">Note that Setup.bat uses the FindPrivateKey.exe tool, which is installed by running setupCertTool.bat from [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="931e7-153">Eseguire l'applicazione client da \MetadataResolverClient\bin o \SvcutilClient\bin.</span><span class="sxs-lookup"><span data-stu-id="931e7-153">Run the client application from \MetadataResolverClient\bin or \SvcutilClient\bin.</span></span> <span data-ttu-id="931e7-154">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="931e7-154">Client activity is displayed on the client console application.</span></span>  
  
3. <span data-ttu-id="931e7-155">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="931e7-155">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
4. <span data-ttu-id="931e7-156">Rimuovere i certificati eseguendo Cleanup.bat una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="931e7-156">Remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="931e7-157">Negli altri esempi relativi alla sicurezza vengono usati gli stessi certificati.</span><span class="sxs-lookup"><span data-stu-id="931e7-157">Other security samples use the same certificates.</span></span>  
  
#### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="931e7-158">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="931e7-158">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="931e7-159">Eseguire `setup.bat service` sul server.</span><span class="sxs-lookup"><span data-stu-id="931e7-159">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="931e7-160">In `setup.bat` esecuzione `service` con l'argomento crea un certificato del servizio con il nome di dominio completo del computer e lo esporta in un file denominato Service.cer.</span><span class="sxs-lookup"><span data-stu-id="931e7-160">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
2. <span data-ttu-id="931e7-161">Modificare Web.config sul server per riflettere il nome del nuovo certificato,</span><span class="sxs-lookup"><span data-stu-id="931e7-161">On the server, edit Web.config to reflect the new certificate name.</span></span> <span data-ttu-id="931e7-162">Ovvero, modificare `findValue` l'attributo nell'elemento [ \<>serviceCertificate](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) in nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="931e7-162">That is, change the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) element to the fully-qualified domain name of the machine.</span></span>  
  
3. <span data-ttu-id="931e7-163">Copiare il file Service.cer dalla directory del servizio alla directory del client sul computer client.</span><span class="sxs-lookup"><span data-stu-id="931e7-163">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
4. <span data-ttu-id="931e7-164">Eseguire `setup.bat client` sul client.</span><span class="sxs-lookup"><span data-stu-id="931e7-164">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="931e7-165">`setup.bat` L'esecuzione `client` con l'argomento crea un certificato client denominato Client.com ed esporta il certificato client in un file denominato Client.cer.</span><span class="sxs-lookup"><span data-stu-id="931e7-165">Running `setup.bat` with the `client` argument creates a client certificate named Client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
5. <span data-ttu-id="931e7-166">Nel file App.config del `MetadataResolverClient` sul computer client, modificare il valore dell'indirizzo dell'endpoint mex in modo che corrisponda al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="931e7-166">In the App.config file of the `MetadataResolverClient` on the client machine, change the address value of the mex endpoint to match the new address of your service.</span></span> <span data-ttu-id="931e7-167">Tale operazione viene eseguita sostituendo localhost con il nome di dominio completo del server.</span><span class="sxs-lookup"><span data-stu-id="931e7-167">You do this by replacing localhost with the fully-qualified domain name of the server.</span></span> <span data-ttu-id="931e7-168">Modificare inoltre l'occorrenza di "localhost" nel file metadataResolverClient.cs al nuovo nome del certificato del servizio (il nome di dominio completo del server).</span><span class="sxs-lookup"><span data-stu-id="931e7-168">Also change the occurrence of "localhost" in the metadataResolverClient.cs file to the new service certificate name (the fully-qualified domain name of the server).</span></span> <span data-ttu-id="931e7-169">Eseguire la stessa operazione per il file App.config del progetto SvcutilClient.</span><span class="sxs-lookup"><span data-stu-id="931e7-169">Do the same thing for the App.config of the SvcutilClient project.</span></span>  
  
6. <span data-ttu-id="931e7-170">Copiare il file Client.cer dalla directory del client nella directory del servizio sul server.</span><span class="sxs-lookup"><span data-stu-id="931e7-170">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
7. <span data-ttu-id="931e7-171">Eseguire `ImportServiceCert.bat` sul client.</span><span class="sxs-lookup"><span data-stu-id="931e7-171">On the client, run `ImportServiceCert.bat`.</span></span> <span data-ttu-id="931e7-172">In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="931e7-172">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
8. <span data-ttu-id="931e7-173">Eseguire `ImportClientCert.bat` sul server. In questo modo il certificato client viene importato dal file Client.cer nell'archivio LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="931e7-173">On the server, run `ImportClientCert.bat`, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
9. <span data-ttu-id="931e7-174">Compilare il progetto di servizio in Visual Studio sul computer server e selezionare la pagina della Guida in un browser Web per verificare che sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="931e7-174">On the service machine, build the service project in Visual Studio and select the help page in a web browser to verify that it is running.</span></span>  
  
10. <span data-ttu-id="931e7-175">Eseguire MetadataResolverClient o SvcutilClient da VS sul computer client.</span><span class="sxs-lookup"><span data-stu-id="931e7-175">On the client machine, run the MetadataResolverClient or the SvcutilClient from VS.</span></span>  
  
    1. <span data-ttu-id="931e7-176">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="931e7-176">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="931e7-177">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="931e7-177">To clean up after the sample</span></span>  
  
- <span data-ttu-id="931e7-178">Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="931e7-178">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="931e7-179">Questo script non rimuove i certificati del servizio su un client quando si esegue questo esempio tra più computer.</span><span class="sxs-lookup"><span data-stu-id="931e7-179">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="931e7-180">Se sono stati eseguiti esempi di Windows Communication Foundation (WCF) che usano i certificati tra computer, assicurarsi di cancellare i certificati del servizio installati nell'archivio CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="931e7-180">If you have run Windows Communication Foundation (WCF) samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="931e7-181">A tale scopo, utilizzare il comando seguente: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`.</span><span class="sxs-lookup"><span data-stu-id="931e7-181">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`.</span></span> <span data-ttu-id="931e7-182">Ad esempio `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="931e7-182">For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="931e7-183">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="931e7-183">The samples may already be installed on your machine.</span></span> <span data-ttu-id="931e7-184">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="931e7-184">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="931e7-185">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="931e7-185">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="931e7-186">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="931e7-186">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Metadata\CustomMexEndpoint`  
