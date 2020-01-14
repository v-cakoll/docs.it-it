---
title: Accesso ai servizi WCF con un'applicazione client Windows Store
ms.date: 03/30/2017
ms.assetid: e2002ef4-5dee-4a54-9d87-03b33d35fc52
ms.openlocfilehash: 77dc5d19bc40dc09148a8d2368c56e522bfafc1a
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938167"
---
# <a name="accessing-wcf-services-with-a-windows-store-client-app"></a><span data-ttu-id="81bdf-102">Accesso ai servizi WCF con un'applicazione client Windows Store</span><span class="sxs-lookup"><span data-stu-id="81bdf-102">Accessing WCF Services with a Windows Store Client App</span></span>
<span data-ttu-id="81bdf-103">In Windows 8 è stato introdotto un nuovo tipo di applicazione denominato applicazioni Windows Store.</span><span class="sxs-lookup"><span data-stu-id="81bdf-103">Windows 8 introduces a new type of application called Windows Store applications.</span></span> <span data-ttu-id="81bdf-104">Queste applicazioni sono progettate in base a un'interfaccia del touchscreen.</span><span class="sxs-lookup"><span data-stu-id="81bdf-104">These applications are designed around a touch screen interface.</span></span> <span data-ttu-id="81bdf-105">.NET Framework 4.5 consente alle applicazioni Windows Store di chiamare i servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="81bdf-105">.NET Framework 4.5 enables Windows Store applications to call WCF services.</span></span>  
  
## <a name="wcf-support-in-windows-store-applications"></a><span data-ttu-id="81bdf-106">Supporto WCF nelle applicazioni Windows Store</span><span class="sxs-lookup"><span data-stu-id="81bdf-106">WCF Support in Windows Store Applications</span></span>  
 <span data-ttu-id="81bdf-107">Un subset di funzionalità WCF è disponibile in un'applicazione Windows Store. Per altre informazioni, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="81bdf-107">A subset of WCF functionality is available from within a Windows Store application, see the following sections for more details.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="81bdf-108">Usare le API di diffusione WinRT anziché quelle esposte da WCF.</span><span class="sxs-lookup"><span data-stu-id="81bdf-108">Use the WinRT syndication APIs instead of those exposed by WCF.</span></span> <span data-ttu-id="81bdf-109">Per altre informazioni, vedere [API di diffusione WinRT](xref:Windows.Web.Syndication)</span><span class="sxs-lookup"><span data-stu-id="81bdf-109">For more information see, [WinRT Syndication API](xref:Windows.Web.Syndication)</span></span>  
  
> [!WARNING]
> <span data-ttu-id="81bdf-110">L'uso di Aggiungi riferimento al servizio per aggiungere il riferimento di un servizio Web a un componente Windows Runtime non è supportato.</span><span class="sxs-lookup"><span data-stu-id="81bdf-110">Using Add Service Reference to add a web service reference to a Windows Runtime Component isn’t supported.</span></span>  
  
### <a name="supported-bindings"></a><span data-ttu-id="81bdf-111">Associazioni supportate</span><span class="sxs-lookup"><span data-stu-id="81bdf-111">Supported Bindings</span></span>  
 <span data-ttu-id="81bdf-112">Nelle applicazioni Windows Store sono supportate le associazioni WCF seguenti:</span><span class="sxs-lookup"><span data-stu-id="81bdf-112">The following WCF bindings are supported in Windows Store Applications:</span></span>  
  
1. <xref:System.ServiceModel.BasicHttpBinding>  
  
2. <xref:System.ServiceModel.NetTcpBinding>  
  
3. <xref:System.ServiceModel.NetHttpBinding>  
  
4. <xref:System.ServiceModel.Channels.CustomBinding>
  
 <span data-ttu-id="81bdf-113">Nelle applicazioni Windows Store sono supportati gli elementi di associazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="81bdf-113">The following binding elements are supported in Windows Store Applications</span></span>  
  
1. <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
2. <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
3. <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
4. <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
5. <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
6. <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
7. <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
8. <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
9. <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="81bdf-114">Sono supportate sia la codifica testo sia quella binaria.</span><span class="sxs-lookup"><span data-stu-id="81bdf-114">Both Text and Binary encodings are supported.</span></span> <span data-ttu-id="81bdf-115">Inoltre, sono supportate tutte le modalità di trasferimento WCF.</span><span class="sxs-lookup"><span data-stu-id="81bdf-115">All WCF transfer modes are supported.</span></span> <span data-ttu-id="81bdf-116">Per altre informazioni, vedere [Streaming Message Transfer](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md).</span><span class="sxs-lookup"><span data-stu-id="81bdf-116">For more information see, [Streaming Message Transfer](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md).</span></span>  
  
### <a name="add-service-reference"></a><span data-ttu-id="81bdf-117">Aggiungi riferimento al servizio</span><span class="sxs-lookup"><span data-stu-id="81bdf-117">Add Service Reference</span></span>  
 <span data-ttu-id="81bdf-118">Per chiamare un servizio WCF da un'applicazione Windows Store, usare la funzionalità Aggiungi riferimento al servizio di Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="81bdf-118">To call a WCF service from a Windows Store application, use the Add Service Reference feature of Visual Studio 2012.</span></span> <span data-ttu-id="81bdf-119">Si noteranno alcune modifiche di tale funzionalità quando eseguita in un'applicazione Windows Store.</span><span class="sxs-lookup"><span data-stu-id="81bdf-119">You will notice a few changes in the functionality of Add Service Reference when done within a Windows Store application.</span></span> <span data-ttu-id="81bdf-120">Innanzitutto non viene generato alcun file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="81bdf-120">First no configuration file is generated.</span></span> <span data-ttu-id="81bdf-121">Nelle applicazioni Windows Store non vengono usati i file di configurazione, pertanto devono essere configurati nel codice.</span><span class="sxs-lookup"><span data-stu-id="81bdf-121">Windows Store applications do not use configuration files, so they must be configured in code.</span></span> <span data-ttu-id="81bdf-122">Questo codice di configurazione è disponibile nel file References.cs generato da Aggiungi riferimento al servizio.</span><span class="sxs-lookup"><span data-stu-id="81bdf-122">This configuration code can be found in the References.cs file generated by Add Service Reference.</span></span> <span data-ttu-id="81bdf-123">Per visualizzare questo file, assicurarsi di selezionare "Mostra tutti i file" in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="81bdf-123">To see this file, make sure to select "Show All Files" in the solution explorer.</span></span> <span data-ttu-id="81bdf-124">Il file si trova nei riferimenti al servizio, quindi nei nodi Reference.svcmap del progetto.</span><span class="sxs-lookup"><span data-stu-id="81bdf-124">The file will be located under the Service References and then Reference.svcmap nodes within the project.</span></span> <span data-ttu-id="81bdf-125">Tutte le operazioni generate per i servizi WCF in un'applicazione Windows Store saranno asincrone mediante il modello asincrono basato su attività.</span><span class="sxs-lookup"><span data-stu-id="81bdf-125">All operations generated for WCF services within a Windows Store application will be asynchronous using the Task-based asynchronous pattern.</span></span> <span data-ttu-id="81bdf-126">Per altre informazioni, vedere [attività asincrone-semplificare la programmazione asincrona con le attività](https://docs.microsoft.com/archive/msdn-magazine/2010/september/async-tasks-simplify-asynchronous-programming-with-tasks).</span><span class="sxs-lookup"><span data-stu-id="81bdf-126">For more information, see [Async Tasks - Simplify Asynchronous Programming with Tasks](https://docs.microsoft.com/archive/msdn-magazine/2010/september/async-tasks-simplify-asynchronous-programming-with-tasks).</span></span>  
  
 <span data-ttu-id="81bdf-127">Poiché la configurazione viene generata nel codice, tutte le modifiche apportate al file Reference.cs verranno sovrascritte ogni volta che il riferimento al servizio viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="81bdf-127">Because configuration is now generated in code, any changes made in the Reference.cs file would be overwritten every time the service reference is updated.</span></span> <span data-ttu-id="81bdf-128">Per risolvere questa situazione, il codice di configurazione viene generato all'interno di un metodo parziale, che è possibile implementare nella classe proxy del client.</span><span class="sxs-lookup"><span data-stu-id="81bdf-128">To remedy this situation the configuration code is generated within a partial method, which you can implement in your client proxy class.</span></span> <span data-ttu-id="81bdf-129">Il metodo parziale viene dichiarato come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="81bdf-129">The partial method is declared as follows:</span></span>  
  
```csharp  
static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,  
            System.ServiceModel.Description.ClientCredentials clientCredentials);  
```  
  
 <span data-ttu-id="81bdf-130">È quindi possibile implementare questo metodo parziale e modificare l'associazione o l'endpoint nella classe proxy del client come segue:</span><span class="sxs-lookup"><span data-stu-id="81bdf-130">You can then implement this partial method and change the binding or endpoint in your client proxy class as follows:</span></span>  
  
```csharp  
public partial class Service1Client : System.ServiceModel.ClientBase<MetroWcfClient.ServiceRefMultiEndpt.IService1>, MetroWcfClient.ServiceRefMultiEndpt.IService1  
    {   
        static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,   
            System.ServiceModel.Description.ClientCredentials clientCredentials)  
        {  
            if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
            }  
            else if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService11.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
                clientCredentials.UserName.UserName = "username1";  
                clientCredentials.UserName.Password = "password";  
            }  
            else if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.NetTcpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.Name = "MyTcpBinding";  
                serviceEndpoint.Address = new System.ServiceModel.EndpointAddress("net.tcp://localhost/tcp");  
            }  
        }  
    }  
```  
  
### <a name="serialization"></a><span data-ttu-id="81bdf-131">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="81bdf-131">Serialization</span></span>  
 <span data-ttu-id="81bdf-132">Nelle applicazioni Windows Store sono supportati i serializzatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="81bdf-132">The following serializers are supported in Windows Store applications:</span></span>  
  
1. <span data-ttu-id="81bdf-133">DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="81bdf-133">DataContractSerializer</span></span>  
  
2. <span data-ttu-id="81bdf-134">DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="81bdf-134">DataContractJsonSerializer</span></span>  
  
3. <span data-ttu-id="81bdf-135">XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="81bdf-135">XmlSerializer</span></span>  
  
> [!WARNING]
> <span data-ttu-id="81bdf-136">XmlDictionaryWriter.Write (DateTime) consente ora di scrivere un oggetto DateTime come stringa.</span><span class="sxs-lookup"><span data-stu-id="81bdf-136">XmlDictionaryWriter.Write(DateTime) now writes the DateTime object as a string.</span></span>  
  
### <a name="security"></a><span data-ttu-id="81bdf-137">Sicurezza -</span><span class="sxs-lookup"><span data-stu-id="81bdf-137">Security</span></span>  

<span data-ttu-id="81bdf-138">Nelle applicazioni Windows Store sono supportate le modalità di sicurezza seguenti:</span><span class="sxs-lookup"><span data-stu-id="81bdf-138">The following security modes are supported in Windows Store applications:</span></span>
  
1. <xref:System.ServiceModel.SecurityMode.None>  
  
2. <xref:System.ServiceModel.SecurityMode.Transport>  
  
3. <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>
  
4. <xref:System.ServiceModel.SecurityMode.Message>
  
<span data-ttu-id="81bdf-139">Nelle applicazioni Windows Store sono supportati i tipi di credenziali client seguenti:</span><span class="sxs-lookup"><span data-stu-id="81bdf-139">The following client credential types are supported in Windows Store applications:</span></span>
  
1. <span data-ttu-id="81bdf-140">nessuna</span><span class="sxs-lookup"><span data-stu-id="81bdf-140">None</span></span>  
  
2. <span data-ttu-id="81bdf-141">Basic</span><span class="sxs-lookup"><span data-stu-id="81bdf-141">Basic</span></span>  
  
3. <span data-ttu-id="81bdf-142">Digest</span><span class="sxs-lookup"><span data-stu-id="81bdf-142">Digest</span></span>  
  
4. <span data-ttu-id="81bdf-143">Negotiate</span><span class="sxs-lookup"><span data-stu-id="81bdf-143">Negotiate</span></span>  
  
5. <span data-ttu-id="81bdf-144">NTLM</span><span class="sxs-lookup"><span data-stu-id="81bdf-144">NTLM</span></span>  
  
6. <span data-ttu-id="81bdf-145">Portale di</span><span class="sxs-lookup"><span data-stu-id="81bdf-145">Windows</span></span>  
  
7. <span data-ttu-id="81bdf-146">Username (sicurezza del messaggio)</span><span class="sxs-lookup"><span data-stu-id="81bdf-146">Username (Message Security)</span></span>  
  
8. <span data-ttu-id="81bdf-147">Windows (sicurezza del trasporto)</span><span class="sxs-lookup"><span data-stu-id="81bdf-147">Windows (Transport Security)</span></span>  
  
 <span data-ttu-id="81bdf-148">Per consentire alle applicazioni Windows Store di accedere e inviare le credenziali di Windows predefinite, è necessario abilitare questa funzionalità nel file Package.appmanifest.</span><span class="sxs-lookup"><span data-stu-id="81bdf-148">In order for Windows Store applications to access and send default Windows credentials, you must enable this functionality within the Package.appmanifest file.</span></span> <span data-ttu-id="81bdf-149">Aprire il file e selezionare la scheda funzionalità e selezionare "credenziali di Windows predefinite".</span><span class="sxs-lookup"><span data-stu-id="81bdf-149">Open this file and select the Capabilities tab and select "Default Windows Credentials".</span></span> <span data-ttu-id="81bdf-150">In questo modo le applicazioni possono connettersi alle risorse Intranet che richiedono le credenziali del dominio.</span><span class="sxs-lookup"><span data-stu-id="81bdf-150">This allows the application to connect to intranet resources that require domain credentials.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="81bdf-151">Affinché le applicazioni Windows Store effettuino chiamate tra computer, è necessario abilitare un'altra funzionalità denominata "rete domestica/aziendale".</span><span class="sxs-lookup"><span data-stu-id="81bdf-151">In order for Windows Store applications to make cross machine calls you must enable another capability called "Home/Work Networking".</span></span> <span data-ttu-id="81bdf-152">Questa impostazione è inoltre presente nel file Package. AppManifest nella scheda funzionalità. Selezionare la casella di controllo rete domestica/aziendale.</span><span class="sxs-lookup"><span data-stu-id="81bdf-152">This setting is also in the Package.appmanifest file under the Capabilities tab. Select the Home/Work Networking checkbox.</span></span> <span data-ttu-id="81bdf-153">In questo modo viene fornito l'accesso in ingresso e in uscita dell'applicazione in uso alle reti delle posizioni affidabili dell'utente come casa e lavoro.</span><span class="sxs-lookup"><span data-stu-id="81bdf-153">This gives your application inbound and outbound access to the networks of the user’s trusted places like home and work.</span></span> <span data-ttu-id="81bdf-154">Le porte critiche in ingresso sono sempre bloccate.</span><span class="sxs-lookup"><span data-stu-id="81bdf-154">Inbound critical ports are always blocked.</span></span> <span data-ttu-id="81bdf-155">Per accedere ai servizi su Internet è inoltre necessario abilitare la funzionalità Internet (client).</span><span class="sxs-lookup"><span data-stu-id="81bdf-155">For accessing services on the internet you must also enable Internet (Client) capability.</span></span>  
  
### <a name="misc"></a><span data-ttu-id="81bdf-156">Vari</span><span class="sxs-lookup"><span data-stu-id="81bdf-156">Misc</span></span>  
 <span data-ttu-id="81bdf-157">L'uso delle classi seguenti è supportato per le applicazioni Windows Store:</span><span class="sxs-lookup"><span data-stu-id="81bdf-157">The use of the following classes is supported for Windows Store Applications:</span></span>  
  
1. <xref:System.ServiceModel.ChannelFactory>  
  
2. <xref:System.ServiceModel.DuplexChannelFactory%601>
  
3. <xref:System.ServiceModel.CallbackBehaviorAttribute>  
  
### <a name="defining-service-contracts"></a><span data-ttu-id="81bdf-158">Definizione dei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="81bdf-158">Defining Service Contracts</span></span>  
 <span data-ttu-id="81bdf-159">Si consiglia di definire solo operazioni del servizio asincrone mediante il modello asincrono basato su attività.</span><span class="sxs-lookup"><span data-stu-id="81bdf-159">We recommend only defining asynchronous service operations using the task-based async pattern.</span></span> <span data-ttu-id="81bdf-160">In questo modo viene garantita la risposta delle applicazioni Windows Store durante la chiamata a un'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="81bdf-160">This ensures Windows Store applications remain responsive while calling a service operation.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="81bdf-161">Sebbene non venga generata alcuna eccezione se si definisce un'operazione sincrona, è consigliabile definire solo le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="81bdf-161">While no exception will be thrown if you define a synchronous operation, it is strongly recommended to only define asynchronous operations.</span></span>  
  
### <a name="calling-wcf-services-from-windows-store-applications"></a><span data-ttu-id="81bdf-162">Chiamata dei servizi WCF da applicazioni Windows Store</span><span class="sxs-lookup"><span data-stu-id="81bdf-162">Calling WCF Services from Windows Store Applications</span></span>  
 <span data-ttu-id="81bdf-163">Come detto in precedenza, tutte le configurazioni devono essere eseguite nel codice nel metodo GetBindingForEndpoint della classe proxy generata.</span><span class="sxs-lookup"><span data-stu-id="81bdf-163">As mentioned before all configuration must be done in code in the GetBindingForEndpoint method in the generated proxy class.</span></span> <span data-ttu-id="81bdf-164">La chiamata di un'operazione del servizio viene effettuata in modo analogo al metodo asincrono basato su attività, come illustrato nel seguente frammento di codice.</span><span class="sxs-lookup"><span data-stu-id="81bdf-164">Calling a service operation is done the same as calling any task-based asynchronous method as shown in the following code snippet.</span></span>  
  
```csharp  
void async SomeMethod()  
{  
    ServiceClient proxy = new ServiceClient();  
    Task<T> results = await proxy.CallAsync(param1, param2);  
    T result = results.Result;  
    if (result.Success)  
    {  
       // Do something with result  
    }  
}  
```  
  
 <span data-ttu-id="81bdf-165">Si noti l'uso della parola chiave async nel metodo con cui si effettua la chiamata asincrona e la parola chiave await quando viene chiamato il metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="81bdf-165">Notice the use of the async keyword on the method making the asynchronous call and the await keyword when calling the asynchronous method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81bdf-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81bdf-166">See also</span></span>

- [<span data-ttu-id="81bdf-167">Blog di WCF in app di Windows Store</span><span class="sxs-lookup"><span data-stu-id="81bdf-167">WCF in Windows Store Apps Blog</span></span>](https://docs.microsoft.com/archive/blogs/piyushjo/wcf-in-windows-8-metro-styled-apps-absolutely-supported)
- [<span data-ttu-id="81bdf-168">Client e sicurezza di Windows Store WCF</span><span class="sxs-lookup"><span data-stu-id="81bdf-168">WCF Windows Store Clients and Security</span></span>](https://docs.microsoft.com/archive/blogs/piyushjo/calling-a-wcf-service-from-a-metro-application-adding-security)
- [<span data-ttu-id="81bdf-169">App di Windows Store e chiamate tra computer</span><span class="sxs-lookup"><span data-stu-id="81bdf-169">Windows Store Apps and Cross Machine Calls</span></span>](https://docs.microsoft.com/archive/blogs/piyushjo/calling-a-wcf-service-from-a-metro-application-cross-machine-scenario)
- [<span data-ttu-id="81bdf-170">Chiamata di un servizio WCF distribuito in Azure da un'app di Windows Store</span><span class="sxs-lookup"><span data-stu-id="81bdf-170">Calling a WCF Service Deployed in Azure from a Windows Store App</span></span>](https://docs.microsoft.com/archive/blogs/piyushjo/calling-a-wcf-service-from-a-metro-application-cross-machine-scenario)
- [<span data-ttu-id="81bdf-171">Programmazione delle funzionalità di sicurezza di WCF</span><span class="sxs-lookup"><span data-stu-id="81bdf-171">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
- [<span data-ttu-id="81bdf-172">Associazioni</span><span class="sxs-lookup"><span data-stu-id="81bdf-172">Bindings</span></span>](../../../../docs/framework/wcf/bindings.md)
