---
title: Migrazione da .NET Remoting a WCF
ms.date: 03/30/2017
ms.assetid: 16902a42-ef80-40e9-8c4c-90e61ddfdfe5
ms.openlocfilehash: 6041cd9ac066d932811cc489222c8cbf03debb75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509140"
---
# <a name="migrating-from-net-remoting-to-wcf"></a><span data-ttu-id="02a73-102">Migrazione da .NET Remoting a WCF</span><span class="sxs-lookup"><span data-stu-id="02a73-102">Migrating from .NET Remoting to WCF</span></span>
<span data-ttu-id="02a73-103">In questo articolo viene descritto come eseguire la migrazione di un'applicazione che usa Servizi remoti .NET per l'uso di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="02a73-103">This article describes how to migrate an application that uses .NET Remoting to use Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="02a73-104">Vengono confrontati concetti simili tra questi prodotti e quindi viene descritto come realizzare diversi scenari comuni di Servizi remoti .NET in WCF.</span><span class="sxs-lookup"><span data-stu-id="02a73-104">It compares similar concepts between these products and then describes how to accomplish several common Remoting scenarios in WCF.</span></span>  
  
 <span data-ttu-id="02a73-105">Servizi remoti .NET è un prodotto legacy supportato solo per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="02a73-105">.NET Remoting is a legacy product that is supported only for backward compatibility.</span></span> <span data-ttu-id="02a73-106">Non è sicuro in ambienti ad attendibilità mista poiché non è in grado di mantenere livelli di attendibilità distinti tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="02a73-106">It is not secure across mixed-trust environments because it cannot maintain the separate trust levels between client and server.</span></span> <span data-ttu-id="02a73-107">Ad esempio, è consigliabile non esporre mai un endpoint Servizi remoti .NET a Internet o a client non attendibili.</span><span class="sxs-lookup"><span data-stu-id="02a73-107">For example, you should never expose a .NET Remoting endpoint to the Internet or to untrusted clients.</span></span> <span data-ttu-id="02a73-108">Si consiglia di eseguire la migrazione delle applicazioni Servizi remoti .NET esistenti a tecnologie più recenti e sicure.</span><span class="sxs-lookup"><span data-stu-id="02a73-108">We recommend existing Remoting applications be migrated to newer and more secure technologies.</span></span> <span data-ttu-id="02a73-109">Se la progettazione dell'applicazione usa solo HTTP ed è RESTful, è consigliabile l'API Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="02a73-109">If the application’s design uses only HTTP and is RESTful, we recommend ASP.NET Web API.</span></span> <span data-ttu-id="02a73-110">Per altre informazioni, vedere l'API Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="02a73-110">For more information, see ASP.NET Web API.</span></span> <span data-ttu-id="02a73-111">Se l'applicazione è basata su SOAP o richiede protocolli diversi da HTTP, come ad esempio TCP, è consigliabile WCF.</span><span class="sxs-lookup"><span data-stu-id="02a73-111">If the application is based on SOAP or requires non-Http protocols such as TCP, we recommend WCF.</span></span>  

## <a name="comparing-net-remoting-to-wcf"></a><span data-ttu-id="02a73-112">Confronto tra Servizi remoti .NET e WCF</span><span class="sxs-lookup"><span data-stu-id="02a73-112">Comparing .NET Remoting to WCF</span></span>  
 <span data-ttu-id="02a73-113">In questa sezione vengono confrontati i componenti di base di Servizi remoti .NET con gli equivalenti di WCF.</span><span class="sxs-lookup"><span data-stu-id="02a73-113">This section compares the basic building blocks of .NET Remoting with their WCF equivalents.</span></span> <span data-ttu-id="02a73-114">Questi componenti di base verranno usati in un secondo momento per creare alcuni scenari client-server comuni in WCF. Nella tabella seguente sono riepilogate le principali analogie e differenze tra Servizi remoti .NET e WCF.</span><span class="sxs-lookup"><span data-stu-id="02a73-114">We will use these building blocks later to create some common client-server scenarios in WCF.The following chart summarizes the main similarities and differences between .NET Remoting and WCF.</span></span>  
  
||<span data-ttu-id="02a73-115">Servizi remoti .NET</span><span class="sxs-lookup"><span data-stu-id="02a73-115">.NET Remoting</span></span>|<span data-ttu-id="02a73-116">WCF</span><span class="sxs-lookup"><span data-stu-id="02a73-116">WCF</span></span>|  
|-|-------------------|---------|  
|<span data-ttu-id="02a73-117">Tipo di server</span><span class="sxs-lookup"><span data-stu-id="02a73-117">Server type</span></span>|<span data-ttu-id="02a73-118">Sottoclasse MarshalByRefObject</span><span class="sxs-lookup"><span data-stu-id="02a73-118">Subclass MarshalByRefObject</span></span>|<span data-ttu-id="02a73-119">Contrassegno con l'attributo [ServiceContract]</span><span class="sxs-lookup"><span data-stu-id="02a73-119">Mark with [ServiceContract] attribute</span></span>|  
|<span data-ttu-id="02a73-120">Operazioni di servizio</span><span class="sxs-lookup"><span data-stu-id="02a73-120">Service operations</span></span>|<span data-ttu-id="02a73-121">Metodi pubblici nel tipo di server</span><span class="sxs-lookup"><span data-stu-id="02a73-121">Public methods on server type</span></span>|<span data-ttu-id="02a73-122">Contrassegno con l'attributo [OperationContract]</span><span class="sxs-lookup"><span data-stu-id="02a73-122">Mark with [OperationContract] attribute</span></span>|  
|<span data-ttu-id="02a73-123">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="02a73-123">Serialization</span></span>|<span data-ttu-id="02a73-124">ISerializable o [Serializable]</span><span class="sxs-lookup"><span data-stu-id="02a73-124">ISerializable or [Serializable]</span></span>|<span data-ttu-id="02a73-125">DataContractSerializer o XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="02a73-125">DataContractSerializer or XmlSerializer</span></span>|  
|<span data-ttu-id="02a73-126">Oggetti passati</span><span class="sxs-lookup"><span data-stu-id="02a73-126">Objects passed</span></span>|<span data-ttu-id="02a73-127">In base al valore o in base al riferimento</span><span class="sxs-lookup"><span data-stu-id="02a73-127">By-value or by-reference</span></span>|<span data-ttu-id="02a73-128">Solo in base al valore</span><span class="sxs-lookup"><span data-stu-id="02a73-128">By-value only</span></span>|  
|<span data-ttu-id="02a73-129">Errori/eccezioni</span><span class="sxs-lookup"><span data-stu-id="02a73-129">Errors/exceptions</span></span>|<span data-ttu-id="02a73-130">Qualsiasi eccezione serializzabile</span><span class="sxs-lookup"><span data-stu-id="02a73-130">Any serializable exception</span></span>|<span data-ttu-id="02a73-131">FaultContract\<TDetail></span><span class="sxs-lookup"><span data-stu-id="02a73-131">FaultContract\<TDetail></span></span>|  
|<span data-ttu-id="02a73-132">Oggetti proxy client</span><span class="sxs-lookup"><span data-stu-id="02a73-132">Client proxy objects</span></span>|<span data-ttu-id="02a73-133">Proxy trasparenti fortemente tipizzati vengono creati automaticamente da MarshalByRefObjects</span><span class="sxs-lookup"><span data-stu-id="02a73-133">Strongly typed transparent proxies are created automatically from MarshalByRefObjects</span></span>|<span data-ttu-id="02a73-134">Proxy fortemente tipizzati vengono generati su richiesta usando ChannelFactory\<TChannel ></span><span class="sxs-lookup"><span data-stu-id="02a73-134">Strongly typed proxies are generated on-demand using ChannelFactory\<TChannel></span></span>|  
|<span data-ttu-id="02a73-135">Piattaforma richiesta</span><span class="sxs-lookup"><span data-stu-id="02a73-135">Platform required</span></span>|<span data-ttu-id="02a73-136">Sia il client che il server devono usare un sistema operativo Microsoft e .NET</span><span class="sxs-lookup"><span data-stu-id="02a73-136">Both client and server must use Microsoft OS and .NET</span></span>|<span data-ttu-id="02a73-137">Multipiattaforma</span><span class="sxs-lookup"><span data-stu-id="02a73-137">Cross-platform</span></span>|  
|<span data-ttu-id="02a73-138">Formato dei messaggi</span><span class="sxs-lookup"><span data-stu-id="02a73-138">Message format</span></span>|<span data-ttu-id="02a73-139">Private</span><span class="sxs-lookup"><span data-stu-id="02a73-139">Private</span></span>|<span data-ttu-id="02a73-140">Standard di settore (SOAP, WS-\* e così via)</span><span class="sxs-lookup"><span data-stu-id="02a73-140">Industry standards (SOAP, WS-\*, etc.)</span></span>|  
  
### <a name="server-implementation-comparison"></a><span data-ttu-id="02a73-141">Confronto dell'implementazione server</span><span class="sxs-lookup"><span data-stu-id="02a73-141">Server Implementation Comparison</span></span>  
  
#### <a name="creating-a-server-in-net-remoting"></a><span data-ttu-id="02a73-142">Creazione di un server in Servizi remoti .NET</span><span class="sxs-lookup"><span data-stu-id="02a73-142">Creating a Server in .NET Remoting</span></span>  
 <span data-ttu-id="02a73-143">I tipi di server di Servizi remoti .NET devono derivare da MarshalByRefObject e definire i metodi che il client può chiamare, nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="02a73-143">.NET Remoting server types must derive from MarshalByRefObject and define methods the client can call, like the following:</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="02a73-144">I metodi pubblici di questo tipo di server diventano il contratto pubblico disponibile per i client.</span><span class="sxs-lookup"><span data-stu-id="02a73-144">The public methods of this server type become the public contract available to clients.</span></span>  <span data-ttu-id="02a73-145">Non vi è alcuna separazione tra l'interfaccia pubblica del server e la relativa implementazione: un solo tipo le gestisce entrambe.</span><span class="sxs-lookup"><span data-stu-id="02a73-145">There is no separation between the server’s public interface and its implementation – one type handles both.</span></span>  
  
 <span data-ttu-id="02a73-146">Dopo aver definito il tipo di server, questo può essere reso disponibile ai client, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="02a73-146">Once the server type has been defined, it can be made available to clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel(8080);  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingConfiguration.RegisterWellKnownServiceType(  
    typeof(RemotingServer),   
    "RemotingServer",   
    WellKnownObjectMode.Singleton);  
Console.WriteLine("RemotingServer is running.  Press ENTER to terminate...");  
Console.ReadLine();  
```  
  
 <span data-ttu-id="02a73-147">Esistono diversi modi per rendere disponibile il tipo di Servizi remoti .NET come server, incluso l'uso di file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="02a73-147">There are many ways to make the Remoting type available as a server, including using configuration files.</span></span> <span data-ttu-id="02a73-148">Questo è solo un esempio.</span><span class="sxs-lookup"><span data-stu-id="02a73-148">This is just one example.</span></span>  
  
#### <a name="creating-a-server-in-wcf"></a><span data-ttu-id="02a73-149">Creazione di un server in WCF</span><span class="sxs-lookup"><span data-stu-id="02a73-149">Creating a Server in WCF</span></span>  
 <span data-ttu-id="02a73-150">Il passaggio equivalente in WCF prevede la creazione di due tipi: il "contratto di servizio" pubblico e l'implementazione concreta.</span><span class="sxs-lookup"><span data-stu-id="02a73-150">The equivalent step in WCF involves creating two types -- the public "service contract" and the concrete implementation.</span></span> <span data-ttu-id="02a73-151">Il primo viene dichiarato come un'interfaccia contrassegnata con [ServiceContract].</span><span class="sxs-lookup"><span data-stu-id="02a73-151">The first is declared as an interface marked with [ServiceContract].</span></span> <span data-ttu-id="02a73-152">I metodi disponibili per i client sono contrassegnati con [OperationContract]:</span><span class="sxs-lookup"><span data-stu-id="02a73-152">Methods available to clients are marked with [OperationContract]:</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="02a73-153">L'implementazione del server è definita in una classe concreta distinta, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="02a73-153">The server’s implementation is defined in a separate concrete class, like in the following example:</span></span>  
  
```csharp
public class WCFServer : IWCFServer  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="02a73-154">Dopo aver definito questi tipi, il server WCF può essere reso disponibile ai client, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="02a73-154">Once these types have been defined, the WCF server can be made available to clients, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
Uri baseAddress = new Uri("net.tcp://localhost:8000/wcfserver");  
  
using (ServiceHost serviceHost = new ServiceHost(typeof(WCFServer), baseAddress))  
{  
    serviceHost.AddServiceEndpoint(typeof(IWCFServer), binding, baseAddress);  
    serviceHost.Open();  
  
    Console.WriteLine(String.Format("The WCF server is ready at {0}.",  
                                    baseAddress));  
    Console.WriteLine("Press <ENTER> to terminate service...");  
    Console.WriteLine();  
    Console.ReadLine();  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="02a73-155">Viene usato TCP in entrambi gli esempi per mantenerli quanto più simili possibile.</span><span class="sxs-lookup"><span data-stu-id="02a73-155">TCP is used in both examples to keep them as similar as possible.</span></span> <span data-ttu-id="02a73-156">Per esempi relativi all'uso di HTTP, fare riferimento alle procedure dettagliate per gli scenari, disponibili più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="02a73-156">Refer to the scenario walk-throughs later in this topic for examples using HTTP.</span></span>  
  
 <span data-ttu-id="02a73-157">Esistono diversi modi per configurare e ospitare servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="02a73-157">There are many ways to configure and to host WCF services.</span></span> <span data-ttu-id="02a73-158">Questo è solo un esempio, basato su un approccio "self-hosted".</span><span class="sxs-lookup"><span data-stu-id="02a73-158">This is just one example, known as "self-hosted".</span></span> <span data-ttu-id="02a73-159">Per altre informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="02a73-159">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="02a73-160">Procedura: Definire un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="02a73-160">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)  
  
-   [<span data-ttu-id="02a73-161">Configurazione dei servizi tramite file di configurazione</span><span class="sxs-lookup"><span data-stu-id="02a73-161">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)  
  
-   [<span data-ttu-id="02a73-162">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="02a73-162">Hosting Services</span></span>](hosting-services.md)  
  
### <a name="client-implementation-comparison"></a><span data-ttu-id="02a73-163">Confronto dell'implementazione client</span><span class="sxs-lookup"><span data-stu-id="02a73-163">Client Implementation Comparison</span></span>  
  
#### <a name="creating-a-client-in-net-remoting"></a><span data-ttu-id="02a73-164">Creazione di un client in Servizi remoti .NET</span><span class="sxs-lookup"><span data-stu-id="02a73-164">Creating a Client in .NET Remoting</span></span>  
 <span data-ttu-id="02a73-165">Una volta che è stato reso disponibile un oggetto server Servizi remoti .NET, questo può essere usato dai client, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="02a73-165">Once a .NET Remoting server object has been made available, it can be consumed by clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel();  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingServer server = (RemotingServer)Activator.GetObject(  
                            typeof(RemotingServer),   
                            "tcp://localhost:8080/RemotingServer");  
  
RemotingCustomer customer = server.GetCustomer(42);  
Console.WriteLine(String.Format("Customer {0} {1} received.",   
                                 customer.FirstName, customer.LastName));  
```  
  
 <span data-ttu-id="02a73-166">L'istanza RemotingServer restituita da Activator.GetObject() è denominata "proxy trasparente".</span><span class="sxs-lookup"><span data-stu-id="02a73-166">The RemotingServer instance returned from Activator.GetObject() is known as a "transparent proxy."</span></span> <span data-ttu-id="02a73-167">Implementa l'API pubblica per il tipo RemotingServer sul client, ma tutti i metodi chiamano l'oggetto server in esecuzione in un altro processo o computer.</span><span class="sxs-lookup"><span data-stu-id="02a73-167">It implements the public API for the RemotingServer type on the client, but all the methods call the server object running in a different process or machine.</span></span>  
  
#### <a name="creating-a-client-in-wcf"></a><span data-ttu-id="02a73-168">Creazione di un client in WCF</span><span class="sxs-lookup"><span data-stu-id="02a73-168">Creating a Client in WCF</span></span>  
 <span data-ttu-id="02a73-169">Il passaggio equivalente in WCF prevede l'uso di una channel factory per creare il proxy in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="02a73-169">The equivalent step in WCF involves using a channel factory to create the proxy explicitly.</span></span> <span data-ttu-id="02a73-170">Analogamente a Servizi remoti .NET, l'oggetto proxy può essere usato per richiamare operazioni sul server, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="02a73-170">Like Remoting, the proxy object can be used to invoke operations on the server, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
String url = "net.tcp://localhost:8000/wcfserver";  
EndpointAddress address = new EndpointAddress(url);  
ChannelFactory<IWCFServer> channelFactory =   
    new ChannelFactory<IWCFServer>(binding, address);  
IWCFServer server = channelFactory.CreateChannel();  
  
Customer customer = server.GetCustomer(42);  
Console.WriteLine(String.Format("  Customer {0} {1} received.",  
                    customer.FirstName, customer.LastName));  
```  
  
 <span data-ttu-id="02a73-171">In questo esempio viene illustrata la programmazione a livello di canale perché è molto simile all'esempio relativo a Servizi remoti .NET.</span><span class="sxs-lookup"><span data-stu-id="02a73-171">This example shows programming at the channel level because it is most similar to the Remoting example.</span></span> <span data-ttu-id="02a73-172">È inoltre disponibile il **Aggiungi riferimento al servizio** approccio in Visual Studio che genera codice per semplificare la programmazione lato client.</span><span class="sxs-lookup"><span data-stu-id="02a73-172">Also available is the **Add Service Reference** approach in Visual Studio that generates code to simplify client programming.</span></span> <span data-ttu-id="02a73-173">Per altre informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="02a73-173">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="02a73-174">Programmazione a livello di canale client</span><span class="sxs-lookup"><span data-stu-id="02a73-174">Client Channel-Level Programming</span></span>](./extending/client-channel-level-programming.md)  
  
-   [<span data-ttu-id="02a73-175">Procedura: aggiungere, aggiornare o rimuovere un riferimento al servizio</span><span class="sxs-lookup"><span data-stu-id="02a73-175">How to: Add, Update, or Remove a Service Reference</span></span>](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)  
  
### <a name="serialization-usage"></a><span data-ttu-id="02a73-176">Uso della serializzazione</span><span class="sxs-lookup"><span data-stu-id="02a73-176">Serialization Usage</span></span>  
 <span data-ttu-id="02a73-177">Sia Servizi remoti .NET che WCF usano la serializzazione per l'invio di oggetti tra il client e il server, ma vi sono tre importanti differenze:</span><span class="sxs-lookup"><span data-stu-id="02a73-177">Both .NET Remoting and WCF use serialization to send objects between client and server, but they differ in these important ways:</span></span>  
  
1.  <span data-ttu-id="02a73-178">Vengono usati serializzatori e convenzioni differenti per indicare gli elementi da serializzare.</span><span class="sxs-lookup"><span data-stu-id="02a73-178">They use different serializers and conventions to indicate what to serialize.</span></span>  
  
2.  <span data-ttu-id="02a73-179">Servizi remoti .NET supporta la serializzazione "in base al riferimento", che consente l'accesso a proprietà o metodi su un livello per l'esecuzione di codice su un altro livello, ovvero attraverso i limiti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="02a73-179">.NET Remoting supports "by reference" serialization that allows method or property access on one tier to execute code on the other tier, which is across security boundaries.</span></span> <span data-ttu-id="02a73-180">Questa funzionalità espone vulnerabilità di sicurezza e rappresenta uno dei motivi principali per cui gli endpoint Servizi remoti .NET non devono mai essere esposti a client non attendibili.</span><span class="sxs-lookup"><span data-stu-id="02a73-180">This capability exposes security vulnerabilities and is one of the main reasons why Remoting endpoints should never be exposed to untrusted clients.</span></span>  
  
3.  <span data-ttu-id="02a73-181">La serializzazione usata da Servizi remoti .NET è di tipo opt-out (vengono esclusi in modo esplicito gli elementi da non serializzare), mentre la serializzazione di WCF è di tipo opt-in (vengono contrassegnati in modo esplicito i membri da serializzare).</span><span class="sxs-lookup"><span data-stu-id="02a73-181">Serialization used by Remoting is opt-out (explicitly exclude what not to serialize) and WCF serialization is opt-in (explicitly mark which members to serialize).</span></span>  
  
#### <a name="serialization-in-net-remoting"></a><span data-ttu-id="02a73-182">Serializzazione in Servizi remoti .NET</span><span class="sxs-lookup"><span data-stu-id="02a73-182">Serialization in .NET Remoting</span></span>  
 <span data-ttu-id="02a73-183">Servizi remoti .NET supporta due modi per serializzare e deserializzare gli oggetti tra client e server:</span><span class="sxs-lookup"><span data-stu-id="02a73-183">.NET Remoting supports two ways to serialize and deserialize objects between the client and server:</span></span>  
  
-   <span data-ttu-id="02a73-184">*Per valore* : i valori dell'oggetto vengono serializzati attraverso i limiti del livello e viene creata una nuova istanza dell'oggetto su un altro livello.</span><span class="sxs-lookup"><span data-stu-id="02a73-184">*By value* – the values of the object are serialized across tier boundaries, and a new instance of that object is created on the other tier.</span></span> <span data-ttu-id="02a73-185">Tutte le chiamate a metodi o proprietà della nuova istanza sono in esecuzione solo in locale e non influiscono sull'oggetto o sul livello originale.</span><span class="sxs-lookup"><span data-stu-id="02a73-185">Any calls to methods or properties of that new instance execute only locally and do not affect the original object or tier.</span></span>  
  
-   <span data-ttu-id="02a73-186">*Per riferimento* – una speciale "riferimento all'oggetto" viene serializzata attraverso i limiti del livello.</span><span class="sxs-lookup"><span data-stu-id="02a73-186">*By reference* – a special "object reference" is serialized across tier boundaries.</span></span> <span data-ttu-id="02a73-187">Quando un livello interagisce con metodi o proprietà di tale oggetto, comunica con l'oggetto originale nel livello originale.</span><span class="sxs-lookup"><span data-stu-id="02a73-187">When one tier interacts with methods or properties of that object, it communicates back to the original object on the original tier.</span></span> <span data-ttu-id="02a73-188">Il flusso degli oggetti in base al riferimento può avvenire in entrambe le direzioni: dal server al client o dal client al server.</span><span class="sxs-lookup"><span data-stu-id="02a73-188">By-reference objects can flow in either direction – server to client, or client to server.</span></span>  
  
 <span data-ttu-id="02a73-189">I tipi in base al valore in Servizi remoti .NET sono contrassegnati con l'attributo [Serializable] o implementano ISerializable, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="02a73-189">By-value types in Remoting are marked with the [Serializable] attribute or implement ISerializable, like in the following example:</span></span>  
  
```csharp
[Serializable]  
public class RemotingCustomer  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="02a73-190">I tipi in base al riferimento derivano dalla classe MarshalByRefObject, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="02a73-190">By-reference types derive from the MarshalByRefObject class, like in the following example:</span></span>  
  
```csharp
public class RemotingCustomerReference : MarshalByRefObject  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="02a73-191">È estremamente importante comprendere le implicazioni degli oggetti in base al riferimento di Servizi remoti .NET.</span><span class="sxs-lookup"><span data-stu-id="02a73-191">It is extremely important to understand the implications of Remoting’s by-reference objects.</span></span> <span data-ttu-id="02a73-192">Se un livello (client o server) invia un oggetto in base al riferimento all'altro livello, tutte le chiamate di metodi vengono eseguite nel livello proprietario dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="02a73-192">If either tier (client or server) sends a by-reference object to the other tier, all method calls execute back on the tier owning the object.</span></span> <span data-ttu-id="02a73-193">Ad esempio, un client che esegue la chiamata di metodi su un oggetto in base al riferimento restituito dal server eseguirà il codice sul server.</span><span class="sxs-lookup"><span data-stu-id="02a73-193">For example, a client calling methods on a by-reference object returned by the server will execute code on the server.</span></span> <span data-ttu-id="02a73-194">Analogamente, un server che esegue la chiamata di metodi su un oggetto in base al riferimento fornito dal client eseguirà il codice sul client.</span><span class="sxs-lookup"><span data-stu-id="02a73-194">Similarly, a server calling methods on a by-reference object provided by the client will execute code back on the client.</span></span> <span data-ttu-id="02a73-195">Per questo motivo, l'uso di Servizi remoti .NET è consigliabile solo all'interno di ambienti completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="02a73-195">For this reason, the use of .NET Remoting is recommended only within fully-trusted environments.</span></span> <span data-ttu-id="02a73-196">L'esposizione di un endpoint Servizi remoti .NET pubblico a client non attendibili renderà vulnerabile agli attacchi un server Servizi remoti .NET.</span><span class="sxs-lookup"><span data-stu-id="02a73-196">Exposing a public .NET Remoting endpoint to untrusted clients will make a Remoting server vulnerable to attack.</span></span>  
  
#### <a name="serialization-in-wcf"></a><span data-ttu-id="02a73-197">Serializzazione in WCF</span><span class="sxs-lookup"><span data-stu-id="02a73-197">Serialization in WCF</span></span>  
 <span data-ttu-id="02a73-198">WCF supporta solo la serializzazione in base al valore.</span><span class="sxs-lookup"><span data-stu-id="02a73-198">WCF supports only by-value serialization.</span></span> <span data-ttu-id="02a73-199">Il modo più comune per definire un tipo per lo scambio tra client e server è simile a quello riportato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="02a73-199">The most common way to define a type to exchange between client and server is like in the following example:</span></span>  
  
```csharp
[DataContract]  
public class WCFCustomer  
{  
    [DataMember]  
    public string FirstName { get; set; }  
  
    [DataMember]  
    public string LastName { get; set; }  
  
    [DataMember]  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="02a73-200">L'attributo [DataContract] identifica questo tipo come serializzabile e deserializzabile tra client e server.</span><span class="sxs-lookup"><span data-stu-id="02a73-200">The [DataContract] attribute identifies this type as one that can be serialized and deserialized between client and server.</span></span> <span data-ttu-id="02a73-201">L'attributo [DataMember] identifica le singole proprietà o i singoli campi da serializzare.</span><span class="sxs-lookup"><span data-stu-id="02a73-201">The [DataMember] attribute identifies the individual properties or fields to serialize.</span></span>  
  
 <span data-ttu-id="02a73-202">Quando WCF invia un oggetto tra i livelli, serializza solo i valori e crea una nuova istanza dell'oggetto nell'altro livello.</span><span class="sxs-lookup"><span data-stu-id="02a73-202">When WCF sends an object across tiers, it serializes only the values and creates a new instance of the object on the other tier.</span></span> <span data-ttu-id="02a73-203">Tutte le interazioni con i valori dell'oggetto avvengono solo in locale: non comunicano con l'altro livello come nel caso degli oggetti in base al riferimento di Servizi remoti .NET.</span><span class="sxs-lookup"><span data-stu-id="02a73-203">Any interactions with the values of the object occur only locally – they do not communicate with the other tier the way .NET Remoting by-reference objects do.</span></span> <span data-ttu-id="02a73-204">Per altre informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="02a73-204">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="02a73-205">Serializzazione e deserializzazione</span><span class="sxs-lookup"><span data-stu-id="02a73-205">Serialization and Deserialization</span></span>](./feature-details/serialization-and-deserialization.md)  
  
-   [<span data-ttu-id="02a73-206">Serializzazione in Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="02a73-206">Serialization in Windows Communication Foundation</span></span>](http://msdn.microsoft.com/magazine/cc163569.aspx)  
  
### <a name="exception-handling-capabilities"></a><span data-ttu-id="02a73-207">Funzionalità di gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="02a73-207">Exception Handling Capabilities</span></span>  
  
#### <a name="exceptions-in-net-remoting"></a><span data-ttu-id="02a73-208">Eccezioni in Servizi remoti .NET</span><span class="sxs-lookup"><span data-stu-id="02a73-208">Exceptions in .NET Remoting</span></span>  
 <span data-ttu-id="02a73-209">Le eccezioni generate da un server Servizi remoti .NET vengono serializzate, inviate al client e generate in locale sul client come qualsiasi altra eccezione.</span><span class="sxs-lookup"><span data-stu-id="02a73-209">Exceptions thrown by a Remoting server are serialized, sent to the client, and thrown locally on the client like any other exception.</span></span> <span data-ttu-id="02a73-210">È possibile creare eccezioni personalizzate assegnando una sottoclasse al tipo Exception e contrassegnandolo con [Serializable].</span><span class="sxs-lookup"><span data-stu-id="02a73-210">Custom exceptions can be created by sub-classing the Exception type and marking it with [Serializable].</span></span>   <span data-ttu-id="02a73-211">La maggior parte delle eccezioni del framework sono già contrassegnate in questo modo, pertanto possono essere generate dal server, serializzate e generate nuovamente sul client.</span><span class="sxs-lookup"><span data-stu-id="02a73-211">Most framework exceptions are already marked in this way, allowing most to be thrown by the server, serialized, and re-thrown on the client.</span></span> <span data-ttu-id="02a73-212">Benché questa progettazione sia utile in fase di sviluppo, è possibile che informazioni sul lato server vengano inavvertitamente rivelate al client.</span><span class="sxs-lookup"><span data-stu-id="02a73-212">Though this design is convenient during development, server-side information can inadvertently be disclosed to the client.</span></span> <span data-ttu-id="02a73-213">Questo è uno dei diversi motivi per cui Servizi remoti .NET deve essere usato solo in ambienti completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="02a73-213">This is one of many reasons Remoting should be used only in fully-trusted environments.</span></span>  
  
#### <a name="exceptions-and-faults-in-wcf"></a><span data-ttu-id="02a73-214">Eccezioni ed errori in WCF</span><span class="sxs-lookup"><span data-stu-id="02a73-214">Exceptions and Faults in WCF</span></span>  
 <span data-ttu-id="02a73-215">WCF non consente la restituzione di tipi di eccezione arbitrari dal server al client, poiché ciò potrebbe causare la divulgazione accidentale di informazioni.</span><span class="sxs-lookup"><span data-stu-id="02a73-215">WCF does not allow arbitrary exception types to be returned from the server to the client because it could lead to inadvertent information disclosure.</span></span> <span data-ttu-id="02a73-216">Se un'operazione del servizio genera un'eccezione imprevista, questo determina la generazione di una FaultException generica sul client.</span><span class="sxs-lookup"><span data-stu-id="02a73-216">If a service operation throws an unexpected exception, it causes a general purpose FaultException to be thrown on the client.</span></span> <span data-ttu-id="02a73-217">Tale eccezione non include informazioni sul motivo del problema o sulla posizione in cui si è verificato e per alcune applicazioni è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="02a73-217">This exception does not carry any information why or where the problem occurred, and for some applications this is sufficient.</span></span> <span data-ttu-id="02a73-218">Le applicazioni che devono comunicare al client informazioni più dettagliate sugli errori possono eseguire questa operazione definendo un contratto di errore.</span><span class="sxs-lookup"><span data-stu-id="02a73-218">Applications that need to communicate richer error information to the client do this by defining a fault contract.</span></span>  
  
 <span data-ttu-id="02a73-219">A tale scopo, creare innanzitutto un tipo [DataContract] per fornire le informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="02a73-219">To do this, first create a [DataContract] type to carry the fault information.</span></span>  
  
```csharp
[DataContract]  
public class CustomerServiceFault  
{  
    [DataMember]  
    public string ErrorMessage { get; set; }  
  
    [DataMember]  
    public int CustomerId {get;set;}  
}  
```  
  
 <span data-ttu-id="02a73-220">Specificare il contratto di errore da usare per ogni operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="02a73-220">Specify the fault contract to use for each service operation.</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    [FaultContract(typeof(CustomerServiceFault))]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="02a73-221">Il server segnala le condizioni di errore generando una FaultException.</span><span class="sxs-lookup"><span data-stu-id="02a73-221">The server reports error conditions by throwing a FaultException.</span></span>  
  
```csharp
throw new FaultException<CustomerServiceFault>(  
    new CustomerServiceFault() {   
        CustomerId = customerId,   
        ErrorMessage = "Illegal customer Id"   
    });  
```  
  
 <span data-ttu-id="02a73-222">Ogni volta che il client effettua una richiesta al server, può intercettare gli errori come normali eccezioni.</span><span class="sxs-lookup"><span data-stu-id="02a73-222">And whenever the client makes a request to the server, it can catch faults as normal exceptions.</span></span>  
  
```csharp
try  
{  
    Customer customer = server.GetCustomer(-1);  
}  
catch (FaultException<CustomerServiceFault> fault)  
{  
    Console.WriteLine(String.Format("Fault received: {0}",  
    fault.Detail.ErrorMessage));  
}  
```  
  
 <span data-ttu-id="02a73-223">Per altre informazioni sui contratti di errore, vedere <xref:System.ServiceModel.FaultException>.</span><span class="sxs-lookup"><span data-stu-id="02a73-223">For more information about fault contracts, see <xref:System.ServiceModel.FaultException>.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="02a73-224">Considerazioni sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="02a73-224">Security Considerations</span></span>  
  
#### <a name="security-in-net-remoting"></a><span data-ttu-id="02a73-225">Sicurezza in Servizi remoti .NET</span><span class="sxs-lookup"><span data-stu-id="02a73-225">Security in .NET Remoting</span></span>  
 <span data-ttu-id="02a73-226">Alcuni canali di Servizi remoti .NET supportano funzionalità di sicurezza quali l'autenticazione e la crittografia a livello di canale (IPC e TCP).</span><span class="sxs-lookup"><span data-stu-id="02a73-226">Some .NET Remoting channels support security features such as authentication and encryption at the channel layer (IPC and TCP).</span></span> <span data-ttu-id="02a73-227">Il canale HTTP si basa su Internet Information Services (IIS) sia per l'autenticazione che per la crittografia.</span><span class="sxs-lookup"><span data-stu-id="02a73-227">The HTTP channel relies on Internet Information Services (IIS) for both authentication and encryption.</span></span> <span data-ttu-id="02a73-228">Nonostante questo supporto, è necessario considerare Servizi remoti .NET un protocollo di comunicazione non sicuro e usarlo solo all'interno di ambienti completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="02a73-228">Despite this support, you should consider .NET Remoting an unsecure communication protocol and use it only within fully-trusted environments.</span></span> <span data-ttu-id="02a73-229">Non esporre mai un endpoint Servizi remoti .NET pubblico a Internet o a client non attendibili.</span><span class="sxs-lookup"><span data-stu-id="02a73-229">Never expose a public Remoting endpoint to the Internet or untrusted clients.</span></span>  
  
#### <a name="security-in-wcf"></a><span data-ttu-id="02a73-230">Sicurezza in WCF</span><span class="sxs-lookup"><span data-stu-id="02a73-230">Security in WCF</span></span>  
 <span data-ttu-id="02a73-231">WCF è stato progettato tenendo conto della sicurezza, in parte per risolvere i tipi di vulnerabilità che sono presenti in Servizi remoti .NET.</span><span class="sxs-lookup"><span data-stu-id="02a73-231">WCF was designed with security in mind, in part to address the kinds of vulnerabilities found in .NET Remoting.</span></span> <span data-ttu-id="02a73-232">WCF garantisce la sicurezza sia a livello di trasporto che di messaggi e offre numerose opzioni per l'autenticazione, l'autorizzazione, la crittografia e così via.</span><span class="sxs-lookup"><span data-stu-id="02a73-232">WCF offers security at both the transport and message level, and offers many options for authentication, authorization, encryption, and so on.</span></span> <span data-ttu-id="02a73-233">Per altre informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="02a73-233">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="02a73-234">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="02a73-234">Security</span></span>](./feature-details/security.md)  
  
-   [<span data-ttu-id="02a73-235">Materiale sussidiario sulla sicurezza WCF</span><span class="sxs-lookup"><span data-stu-id="02a73-235">WCF Security Guidance</span></span>](./feature-details/security-guidance-and-best-practices.md)  
  
## <a name="migrating-to-wcf"></a><span data-ttu-id="02a73-236">Migrazione a WCF</span><span class="sxs-lookup"><span data-stu-id="02a73-236">Migrating to WCF</span></span>  
  
### <a name="why-migrate-from-remoting-to-wcf"></a><span data-ttu-id="02a73-237">Perché eseguire la migrazione da Servizi remoti .NET a WCF?</span><span class="sxs-lookup"><span data-stu-id="02a73-237">Why Migrate from Remoting to WCF?</span></span>  
  
-   <span data-ttu-id="02a73-238">**Servizi remoti .NET è un prodotto legacy.**</span><span class="sxs-lookup"><span data-stu-id="02a73-238">**.NET Remoting is a legacy product.**</span></span> <span data-ttu-id="02a73-239">Come descritto in [.NET Remoting](http://msdn.microsoft.com/library/vstudio/72x4h507\(v=vs.100\).aspx), viene considerato un prodotto legacy e non è consigliato per nuove attività di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="02a73-239">As described in [.NET Remoting](http://msdn.microsoft.com/library/vstudio/72x4h507\(v=vs.100\).aspx), it is considered a legacy product and is not recommended for new development.</span></span> <span data-ttu-id="02a73-240">Per le applicazioni nuove ed esistenti sono consigliati WCF o l'API Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="02a73-240">WCF or ASP.NET Web API are recommended for new and existing applications.</span></span>  
  
-   <span data-ttu-id="02a73-241">**WCF Usa standard multipiattaforma.**</span><span class="sxs-lookup"><span data-stu-id="02a73-241">**WCF uses cross-platform standards.**</span></span> <span data-ttu-id="02a73-242">WCF è stato progettato tenendo conto dell'interoperabilità tra le piattaforme e supporta numerosi standard di settore (SOAP, WS-Security, WS-Trust e così via).</span><span class="sxs-lookup"><span data-stu-id="02a73-242">WCF was designed with cross-platform interoperability in mind and supports many industry standards (SOAP, WS-Security, WS-Trust, etc.).</span></span> <span data-ttu-id="02a73-243">Un servizio WCF può interagire con client in esecuzione in sistemi operativi diversi da Windows.</span><span class="sxs-lookup"><span data-stu-id="02a73-243">A WCF service can interoperate with clients running on operating systems other than Windows.</span></span> <span data-ttu-id="02a73-244">Servizi remoti .NET è stato progettato principalmente per gli ambienti in cui sia le applicazioni client che quelle server vengono eseguite tramite .NET Framework in un sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="02a73-244">Remoting was designed primarily for environments where both the server and client applications run using the .NET framework on a Windows operating system.</span></span>  
  
-   <span data-ttu-id="02a73-245">**WCF dispone di sicurezza incorporati.**</span><span class="sxs-lookup"><span data-stu-id="02a73-245">**WCF has built-in security.**</span></span> <span data-ttu-id="02a73-246">WCF è stato progettato prestando particolare attenzione alla sicurezza e offre numerose opzioni per l'autenticazione, la sicurezza a livello di trasporto, la sicurezza a livello di messaggi e così via. Servizi remoti .NET è stato progettato per semplificare l'interoperabilità tra le applicazioni, ma non per garantire la sicurezza in ambienti non attendibili.</span><span class="sxs-lookup"><span data-stu-id="02a73-246">WCF was designed with security in mind and offers many options for authentication, transport level security, message level security, etc. Remoting was designed to make it easy for applications to interoperate but was not designed to be secure in non-trusted environments.</span></span> <span data-ttu-id="02a73-247">WCF è stato progettato per l'uso sia in ambienti attendibili che non attendibili.</span><span class="sxs-lookup"><span data-stu-id="02a73-247">WCF was designed to work in both trusted and non-trusted environments.</span></span>  
  
### <a name="migration-recommendations"></a><span data-ttu-id="02a73-248">Suggerimenti sulla migrazione</span><span class="sxs-lookup"><span data-stu-id="02a73-248">Migration Recommendations</span></span>  
 <span data-ttu-id="02a73-249">Di seguito sono riportate le procedure consigliate per la migrazione da Servizi remoti .NET a WCF:</span><span class="sxs-lookup"><span data-stu-id="02a73-249">The following are the recommended steps to migrate from .NET Remoting to WCF:</span></span>  
  
-   <span data-ttu-id="02a73-250">**Creare il contratto di servizio.**</span><span class="sxs-lookup"><span data-stu-id="02a73-250">**Create the service contract.**</span></span> <span data-ttu-id="02a73-251">Definire i tipi di interfaccia di servizio e contrassegnarli con l'attributo [ServiceContract]. Contrassegnare tutti i metodi che i client saranno autorizzati a chiamare con [OperationContract].</span><span class="sxs-lookup"><span data-stu-id="02a73-251">Define your service interface types, and mark them with the [ServiceContract] attribute.Mark all the methods the clients will be allowed to call with [OperationContract].</span></span>  
  
-   <span data-ttu-id="02a73-252">**Creare il contratto dati.**</span><span class="sxs-lookup"><span data-stu-id="02a73-252">**Create the data contract.**</span></span> <span data-ttu-id="02a73-253">Definire i tipi di dati che verranno scambiati tra il server e il client e contrassegnarli con l'attributo [DataContract].</span><span class="sxs-lookup"><span data-stu-id="02a73-253">Define the data types that will be exchanged between server and client, and mark them with the [DataContract] attribute.</span></span> <span data-ttu-id="02a73-254">Contrassegnare tutti i campi e le proprietà che il client sarà autorizzato a usare con [DataMember].</span><span class="sxs-lookup"><span data-stu-id="02a73-254">Mark all the fields and properties the client will be allowed to use with [DataMember].</span></span>  
  
-   <span data-ttu-id="02a73-255">**Creare il contratto di errore (facoltativo).**</span><span class="sxs-lookup"><span data-stu-id="02a73-255">**Create the fault contract (optional).**</span></span> <span data-ttu-id="02a73-256">Creare i tipi che verranno scambiati tra il server e il client quando si verificano errori.</span><span class="sxs-lookup"><span data-stu-id="02a73-256">Create the types that will be exchanged between server and client when errors are encountered.</span></span> <span data-ttu-id="02a73-257">Contrassegnare questi tipi con [DataContract] e [DataMember] per renderli serializzabili.</span><span class="sxs-lookup"><span data-stu-id="02a73-257">Mark these types with [DataContract] and [DataMember] to make them serializable.</span></span> <span data-ttu-id="02a73-258">Contrassegnare inoltre con [FaultContract] tutte le operazioni di servizio contrassegnate con [OperationContract] per indicare quali errori possono restituire.</span><span class="sxs-lookup"><span data-stu-id="02a73-258">For all service operations you marked with [OperationContract], also mark them with [FaultContract] to indicate which errors they may return.</span></span>  
  
-   <span data-ttu-id="02a73-259">**Configurare e ospitare il servizio.**</span><span class="sxs-lookup"><span data-stu-id="02a73-259">**Configure and host the service.**</span></span> <span data-ttu-id="02a73-260">Dopo aver creato il contratto di servizio, il passaggio successivo consiste nel configurare un'associazione per esporre il servizio in un endpoint.</span><span class="sxs-lookup"><span data-stu-id="02a73-260">Once the service contract has been created, the next step is to configure a binding to expose the service at an endpoint.</span></span> <span data-ttu-id="02a73-261">Per ulteriori informazioni, vedere [endpoint: indirizzi, associazioni e contratti](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="02a73-261">For more information, see [Endpoints: Addresses, Bindings, and Contracts](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span></span>  
  
 <span data-ttu-id="02a73-262">Una volta che è stata eseguita la migrazione a WCF di un'applicazione Servizi remoti .NET, è comunque importante rimuovere le dipendenze da Servizi remoti .NET.</span><span class="sxs-lookup"><span data-stu-id="02a73-262">Once a Remoting application has been migrated to WCF, it is still important to remove dependencies on .NET Remoting.</span></span> <span data-ttu-id="02a73-263">Questo garantisce che eventuali vulnerabilità di Servizi remoti .NET vengano rimosse dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="02a73-263">This ensures that any Remoting vulnerabilities are removed from the application.</span></span> <span data-ttu-id="02a73-264">Tali passaggi sono:</span><span class="sxs-lookup"><span data-stu-id="02a73-264">These steps include the following:</span></span>  
  
-   <span data-ttu-id="02a73-265">**Interrompere l'uso di MarshalByRefObject.**</span><span class="sxs-lookup"><span data-stu-id="02a73-265">**Discontinue use of MarshalByRefObject.**</span></span> <span data-ttu-id="02a73-266">Il tipo MarshalByRefObject esiste solo per Servizi remoti .NET e non viene usato da WCF.</span><span class="sxs-lookup"><span data-stu-id="02a73-266">The MarshalByRefObject type exists only for Remoting and is not used by WCF.</span></span> <span data-ttu-id="02a73-267">Tutti i tipi di applicazioni che usano la sottoclasse MarshalByRefObject devono essere rimossi o modificati.</span><span class="sxs-lookup"><span data-stu-id="02a73-267">Any application types that sub-class MarshalByRefObject should be removed or changed.</span></span> <span data-ttu-id="02a73-268">Il tipo MarshalByRefObject esiste solo per Servizi remoti .NET e non viene usato da WCF.</span><span class="sxs-lookup"><span data-stu-id="02a73-268">The MarshalByRefObject type exists only for Remoting and is not used by WCF.</span></span> <span data-ttu-id="02a73-269">Tutti i tipi di applicazioni che usano la sottoclasse MarshalByRefObject devono essere rimossi o modificati.</span><span class="sxs-lookup"><span data-stu-id="02a73-269">Any application types that sub-class MarshalByRefObject should be removed or changed.</span></span>  
  
-   <span data-ttu-id="02a73-270">**Interrompere l'uso di [Serializable] e ISerializable.**</span><span class="sxs-lookup"><span data-stu-id="02a73-270">**Discontinue use of [Serializable] and ISerializable.**</span></span> <span data-ttu-id="02a73-271">L'attributo [Serializable] e l'interfaccia ISerializable erano originariamente concepiti per la serializzazione di tipi all'interno di ambienti attendibili e vengono usati da Servizi remoti .NET.</span><span class="sxs-lookup"><span data-stu-id="02a73-271">The [Serializable] attribute and ISerializable interface were originally designed to serialize types within trusted environments, and they are used by Remoting.</span></span> <span data-ttu-id="02a73-272">La serializzazione di WCF si basa sui tipi contrassegnati con [DataContract] e [DataMember].</span><span class="sxs-lookup"><span data-stu-id="02a73-272">WCF serialization relies on types being marked with [DataContract] and [DataMember].</span></span> <span data-ttu-id="02a73-273">I tipi di dati usati da un'applicazione devono essere modificati in modo da usare [DataContract] invece di ISerializable o [Serializable].</span><span class="sxs-lookup"><span data-stu-id="02a73-273">Data types used by an application should be modified to use [DataContract] and not to use ISerializable or [Serializable].</span></span> <span data-ttu-id="02a73-274">L'attributo [Serializable] e l'interfaccia ISerializable erano originariamente concepiti per la serializzazione di tipi all'interno di ambienti attendibili e vengono usati da Servizi remoti .NET.</span><span class="sxs-lookup"><span data-stu-id="02a73-274">The [Serializable] attribute and ISerializable interface were originally designed to serialize types within trusted environments, and they are used by Remoting.</span></span> <span data-ttu-id="02a73-275">La serializzazione di WCF si basa sui tipi contrassegnati con [DataContract] e [DataMember].</span><span class="sxs-lookup"><span data-stu-id="02a73-275">WCF serialization relies on types being marked with [DataContract] and [DataMember].</span></span> <span data-ttu-id="02a73-276">I tipi di dati usati da un'applicazione devono essere modificati in modo da usare [DataContract] invece di ISerializable o [Serializable].</span><span class="sxs-lookup"><span data-stu-id="02a73-276">Data types used by an application should be modified to use [DataContract] and not to use ISerializable or [Serializable].</span></span>  
  
### <a name="migration-scenarios"></a><span data-ttu-id="02a73-277">Scenari di migrazione</span><span class="sxs-lookup"><span data-stu-id="02a73-277">Migration Scenarios</span></span>  
 <span data-ttu-id="02a73-278">Verrà ora descritto come realizzare in WCF i seguenti scenari comuni di Servizi remoti .NET:</span><span class="sxs-lookup"><span data-stu-id="02a73-278">Now let’s see how to accomplish the following common Remoting scenarios in WCF:</span></span>  
  
1.  <span data-ttu-id="02a73-279">Il server restituisce al client un oggetto in base al valore</span><span class="sxs-lookup"><span data-stu-id="02a73-279">Server returns an object by-value to the client</span></span>  
  
2.  <span data-ttu-id="02a73-280">Il server restituisce al client un oggetto in base al riferimento</span><span class="sxs-lookup"><span data-stu-id="02a73-280">Server returns an object by-reference to the client</span></span>  
  
3.  <span data-ttu-id="02a73-281">Il client invia al server un oggetto in base al valore</span><span class="sxs-lookup"><span data-stu-id="02a73-281">Client sends an object by-value to the server</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02a73-282">L'invio di un oggetto in base al riferimento dal client al server non è consentito in WCF.</span><span class="sxs-lookup"><span data-stu-id="02a73-282">Sending an object by-reference from the client to the server is not allowed in WCF.</span></span>  
  
 <span data-ttu-id="02a73-283">Ai fini dei presenti scenari, si presuppone che le interfacce di base per Servizi remoti .NET siano analoghe a quelle illustrate nel seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="02a73-283">When reading through these scenarios, assume our baseline interfaces for .NET Remoting look like the following example.</span></span> <span data-ttu-id="02a73-284">L'implementazione di Servizi remoti .NET non è importante in questo caso, perché si vuole solo illustrare come usare WCF per implementare una funzionalità equivalente.</span><span class="sxs-lookup"><span data-stu-id="02a73-284">The .NET Remoting implementation is not important here because we want to illustrate only how to use WCF to implement equivalent functionality.</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    // Demonstrates server returning object by-value  
    public Customer GetCustomer(int customerId) {…}  
  
    // Demonstrates server returning object by-reference  
    public CustomerReference GetCustomerReference(int customerId) {…}  
  
    // Demonstrates client passing object to server by-value  
    public bool UpdateCustomer(Customer customer) {…}  
}  
```  
  
#### <a name="scenario-1-service-returns-an-object-by-value"></a><span data-ttu-id="02a73-285">Scenario 1: il server restituisce un oggetto in base al valore</span><span class="sxs-lookup"><span data-stu-id="02a73-285">Scenario 1: Service Returns an Object by Value</span></span>  
 <span data-ttu-id="02a73-286">In questo scenario viene illustrato un server che restituisce al client un oggetto in base al valore.</span><span class="sxs-lookup"><span data-stu-id="02a73-286">This scenario demonstrates a server returning an object to the client by value.</span></span> <span data-ttu-id="02a73-287">Poiché WCF restituisce sempre gli oggetti dal server in base al valore, la procedura seguente descrive semplicemente come compilare un normale servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="02a73-287">WCF always returns objects from the server by value, so the following steps simply describe how to build a normal WCF service.</span></span>  
  
1.  <span data-ttu-id="02a73-288">Per iniziare, definire un'interfaccia pubblica per il servizio WCF e contrassegnarla con l'attributo [ServiceContract].</span><span class="sxs-lookup"><span data-stu-id="02a73-288">Start by defining a public interface for the WCF service and mark it with the [ServiceContract] attribute.</span></span> <span data-ttu-id="02a73-289">Viene usato [OperationContract] per identificare i metodi sul lato server che verranno chiamati dal client.</span><span class="sxs-lookup"><span data-stu-id="02a73-289">We use [OperationContract] to identify the server-side methods our client will call.</span></span>  
  
   ```csharp
   [ServiceContract]  
   public interface ICustomerService  
   {  
       [OperationContract]  
       Customer GetCustomer(int customerId);  
  
       [OperationContract]  
       bool UpdateCustomer(Customer customer);  
   }  
   ```  
  
2.  <span data-ttu-id="02a73-290">Il passaggio successivo consiste nel creare il contratto dati per questo servizio.</span><span class="sxs-lookup"><span data-stu-id="02a73-290">The next step is to create the data contract for this service.</span></span> <span data-ttu-id="02a73-291">Tale operazione viene eseguita creando classi (non interfacce) contrassegnate con l'attributo [DataContract].</span><span class="sxs-lookup"><span data-stu-id="02a73-291">We do this by creating classes (not interfaces) marked with the [DataContract] attribute.</span></span> <span data-ttu-id="02a73-292">Le singole proprietà o i singoli campi che devono essere visibili sia per il client che per il server sono contrassegnati con [DataMember].</span><span class="sxs-lookup"><span data-stu-id="02a73-292">The individual properties or fields we want visible to both client and server are marked with [DataMember].</span></span> <span data-ttu-id="02a73-293">Se si vuole che i tipi derivati siano consentiti, è necessario usare l'attributo [KnownType] per identificarli.</span><span class="sxs-lookup"><span data-stu-id="02a73-293">If we want derived types to be allowed, we must use the [KnownType] attribute to identify them.</span></span> <span data-ttu-id="02a73-294">Gli unici tipi di cui WCF consentirà la serializzazione o la deserializzazione per questo servizio sono quelli nell'interfaccia del servizio e questi "tipi noti".</span><span class="sxs-lookup"><span data-stu-id="02a73-294">The only types WCF will allow to be serialized or deserialized for this service are those in the service interface and these "known types".</span></span> <span data-ttu-id="02a73-295">Ogni tentativo di scambiare qualsiasi altro tipo non incluso in questo elenco verrà rifiutato.</span><span class="sxs-lookup"><span data-stu-id="02a73-295">Attempting to exchange any other type not in this list will be rejected.</span></span>  
  
   ```csharp
   [DataContract]  
   [KnownType(typeof(PremiumCustomer))]  
   public class Customer  
   {  
       [DataMember]  
       public string FirstName { get; set; }  
  
       [DataMember]  
       public string LastName { get; set; }  
  
       [DataMember]  
       public int CustomerId { get; set; }  
   }  
  
   [DataContract]  
   public class PremiumCustomer : Customer   
   {  
       [DataMember]  
       public int AccountId { get; set; }  
   }  
   ```  
  
3.  <span data-ttu-id="02a73-296">È quindi necessario fornire l'implementazione per l'interfaccia del servizio.</span><span class="sxs-lookup"><span data-stu-id="02a73-296">Next, we provide the implementation for the service interface.</span></span>  
  
   ```csharp  
   public class CustomerService : ICustomerService  
   {  
       public Customer GetCustomer(int customerId)  
       {  
           // read from database  
       }  
  
       public bool UpdateCustomer(Customer customer)  
       {  
           // write to database  
       }  
   }  
   ```  
  
4.  <span data-ttu-id="02a73-297">Per eseguire il servizio WCF, è necessario dichiarare un endpoint che esponga tale interfaccia del servizio in un URL specifico tramite un'associazione WCF specifica.</span><span class="sxs-lookup"><span data-stu-id="02a73-297">To run the WCF service, we need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="02a73-298">Questa operazione viene in genere eseguita aggiungendo le sezioni seguenti al file web.config del progetto server.</span><span class="sxs-lookup"><span data-stu-id="02a73-298">This is typically done by adding the following sections to the server project’s web.config file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
5.  <span data-ttu-id="02a73-299">Il servizio WCF può quindi essere avviato con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="02a73-299">The WCF service can then be started with the following code:</span></span>  
  
   ```csharp
   ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
       customerServiceHost.Open();  
   ```  
  
     <span data-ttu-id="02a73-300">Quando questo ServiceHost viene avviato, usa il file web.config per stabilire il contratto, l'associazione e l'endpoint appropriati.</span><span class="sxs-lookup"><span data-stu-id="02a73-300">When this ServiceHost is started, it uses the web.config file to establish the proper contract, binding and endpoint.</span></span> <span data-ttu-id="02a73-301">Per ulteriori informazioni sui file di configurazione, vedere [la configurazione di servizi tramite file di configurazione](./configuring-services-using-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="02a73-301">For more information about configuration files, see [Configuring Services Using Configuration Files](./configuring-services-using-configuration-files.md).</span></span> <span data-ttu-id="02a73-302">Questo tipo di avvio del server è noto come self-hosting.</span><span class="sxs-lookup"><span data-stu-id="02a73-302">This style of starting the server is known as self-hosting.</span></span> <span data-ttu-id="02a73-303">Per ulteriori informazioni sulle altre opzioni di hosting dei servizi WCF, vedere [servizi di Hosting](./hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="02a73-303">To learn more about other choices for hosting WCF services, see [Hosting Services](./hosting-services.md).</span></span>  
  
6.  <span data-ttu-id="02a73-304">Il file app.config del progetto client deve dichiarare le informazioni di associazione corrispondenti per l'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="02a73-304">The client project’s app.config must declare matching binding information for the service’s endpoint.</span></span> <span data-ttu-id="02a73-305">Il modo più semplice per eseguire questa operazione in Visual Studio consiste nell'utilizzare **Aggiungi riferimento al servizio**, che aggiorna automaticamente il file app. config.</span><span class="sxs-lookup"><span data-stu-id="02a73-305">The easiest way to do this in Visual Studio is to use **Add Service Reference**, which will automatically update the app.config file.</span></span> <span data-ttu-id="02a73-306">In alternativa, è possibile apportare le stesse modifiche manualmente.</span><span class="sxs-lookup"><span data-stu-id="02a73-306">Alternatively, these same changes can be added manually.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="02a73-307">Per ulteriori informazioni sull'utilizzo **Aggiungi riferimento al servizio**, vedere [procedura: aggiungere, aggiornare o rimuovere un riferimento al servizio](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span><span class="sxs-lookup"><span data-stu-id="02a73-307">For more information about using **Add Service Reference**, see [How to: Add, Update, or Remove a Service Reference](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span></span>  
  
7.  <span data-ttu-id="02a73-308">A questo punto è possibile chiamare il servizio WCF dal client.</span><span class="sxs-lookup"><span data-stu-id="02a73-308">Now we can call the WCF service from the client.</span></span> <span data-ttu-id="02a73-309">È possibile eseguire tale operazione creando una channel factory per il servizio, richiedendole un canale e chiamando direttamente il metodo desiderato su tale canale.</span><span class="sxs-lookup"><span data-stu-id="02a73-309">We do this by creating a channel factory for that service, asking it for a channel, and directly calling the method we want on that channel.</span></span> <span data-ttu-id="02a73-310">Ciò è possibile perché il canale implementa l'interfaccia del servizio e gestisce automaticamente la logica di richiesta/risposta sottostante.</span><span class="sxs-lookup"><span data-stu-id="02a73-310">We can do this because the channel implements the service’s interface and handles the underlying request/reply logic for us.</span></span> <span data-ttu-id="02a73-311">Il valore restituito dalla chiamata del metodo è la copia deserializzata della risposta del server.</span><span class="sxs-lookup"><span data-stu-id="02a73-311">The return value from that method call is the deserialized copy of the server’s response.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   Customer customer = service.GetCustomer(42);  
   Console.WriteLine(String.Format("  Customer {0} {1} received.",  
           customer.FirstName, customer.LastName));  
   ```  
  
 <span data-ttu-id="02a73-312">Gli oggetti restituiti da WCF dal server al client sono sempre in base al valore.</span><span class="sxs-lookup"><span data-stu-id="02a73-312">Objects returned by WCF from the server to the client are always by value.</span></span> <span data-ttu-id="02a73-313">Gli oggetti sono copie deserializzate dei dati inviati dal server.</span><span class="sxs-lookup"><span data-stu-id="02a73-313">The objects are deserialized copies of the data sent by the server.</span></span> <span data-ttu-id="02a73-314">Il client può chiamare metodi su queste copie locali senza rischiare di richiamare codice server tramite callback.</span><span class="sxs-lookup"><span data-stu-id="02a73-314">The client can call methods on these local copies without any danger of invoking server code through callbacks.</span></span>  
  
#### <a name="scenario-2-server-returns-an-object-by-reference"></a><span data-ttu-id="02a73-315">Scenario 2: il server restituisce un oggetto in base al riferimento</span><span class="sxs-lookup"><span data-stu-id="02a73-315">Scenario 2: Server Returns an Object By Reference</span></span>  
 <span data-ttu-id="02a73-316">In questo scenario viene illustrato un server che fornisce al client un oggetto in base al riferimento.</span><span class="sxs-lookup"><span data-stu-id="02a73-316">This scenario demonstrates the server providing an object to the client by reference.</span></span> <span data-ttu-id="02a73-317">In Servizi remoti .NET questa operazione viene gestita automaticamente per qualsiasi tipo derivato da MarshalByRefObject, che è serializzato in base al riferimento.</span><span class="sxs-lookup"><span data-stu-id="02a73-317">In .NET Remoting, this is handled automatically for any type derived from MarshalByRefObject, which is serialized by-reference.</span></span> <span data-ttu-id="02a73-318">Un esempio di questo scenario consiste nel consentire a più client di disporre di oggetti con sessione indipendenti sul lato server.</span><span class="sxs-lookup"><span data-stu-id="02a73-318">An example of this scenario is allowing multiple clients to have independent sessionful server-side objects.</span></span> <span data-ttu-id="02a73-319">Come accennato in precedenza, gli oggetti restituiti da un servizio WCF sono sempre in base al valore, pertanto non esiste un equivalente diretto di un oggetto in base al riferimento. Tuttavia, è possibile ottenere un risultato analogo a una semantica in base al riferimento usando un oggetto <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="02a73-319">As previously mentioned, objects returned by a WCF service are always by value, so there is no direct equivalent of a by-reference object, but it is possible to achieve something similar to by-reference semantics using an <xref:System.ServiceModel.EndpointAddress10> object.</span></span> <span data-ttu-id="02a73-320">Questo è un oggetto serializzabile in base al valore che può essere usato dal client per ottenere un oggetto in base al riferimento con sessione sul server.</span><span class="sxs-lookup"><span data-stu-id="02a73-320">This is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span> <span data-ttu-id="02a73-321">Ciò rende possibile lo scenario relativo a più client con oggetti con sessione indipendenti sul lato server.</span><span class="sxs-lookup"><span data-stu-id="02a73-321">This enables the scenario of having multiple clients with independent sessionful server-side objects.</span></span>  
  
1.  <span data-ttu-id="02a73-322">Innanzitutto, è necessario definire un contratto di servizio WCF che corrisponde all'oggetto con sessione stesso.</span><span class="sxs-lookup"><span data-stu-id="02a73-322">First, we need to define a WCF service contract that corresponds to the sessionful object itself.</span></span>  
  
   ```csharp
   [ServiceContract(SessionMode = SessionMode.Allowed)]  
       public interface ISessionBoundObject  
       {  
           [OperationContract]  
           string GetCurrentValue();  
  
           [OperationContract]  
           void SetCurrentValue(string value);  
       }  
   ```  
  
    > [!TIP]
    >  <span data-ttu-id="02a73-323">Si noti che l'oggetto con sessione è contrassegnato con [ServiceContract], che lo rende una normale interfaccia del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="02a73-323">Notice that the sessionful object is marked with [ServiceContract], making it a normal WCF service interface.</span></span> <span data-ttu-id="02a73-324">L'impostazione della proprietà SessionMode indica che sarà un servizio con sessione.</span><span class="sxs-lookup"><span data-stu-id="02a73-324">Setting the SessionMode property indicates it will be a sessionful service.</span></span> <span data-ttu-id="02a73-325">In WCF una sessione è un modo per correlare più messaggi inviati tra due endpoint.</span><span class="sxs-lookup"><span data-stu-id="02a73-325">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span> <span data-ttu-id="02a73-326">Ciò significa che, una volta che un client ottiene una connessione al servizio, verrà stabilita una sessione tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="02a73-326">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span> <span data-ttu-id="02a73-327">Il client userà una singola istanza univoca dell'oggetto sul lato server per tutte le proprie interazioni all'interno di questa singola sessione.</span><span class="sxs-lookup"><span data-stu-id="02a73-327">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span>  
  
2.  <span data-ttu-id="02a73-328">È quindi necessario fornire l'implementazione di questa interfaccia del servizio.</span><span class="sxs-lookup"><span data-stu-id="02a73-328">Next, we need to provide the implementation of this service interface.</span></span> <span data-ttu-id="02a73-329">Denotandola con [ServiceBehavior] e impostando InstanceContextMode, è possibile indicare a WCF che si vuole usare un'istanza univoca di questo tipo per ciascuna sessione.</span><span class="sxs-lookup"><span data-stu-id="02a73-329">By denoting it with [ServiceBehavior] and setting the InstanceContextMode, we tell WCF we want to use a unique instance of this type for an each session.</span></span>  
  
   ```csharp
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
       public class MySessionBoundObject : ISessionBoundObject  
       {  
           private string _value;  
  
           public string GetCurrentValue()  
           {  
               return _value;  
           }  
  
           public void SetCurrentValue(string val)  
           {  
               _value = val;  
           }  
  
       }  
   ```  
  
3.  <span data-ttu-id="02a73-330">A questo punto è necessario un modo per ottenere un'istanza di questo oggetto con sessione.</span><span class="sxs-lookup"><span data-stu-id="02a73-330">Now we need a way to obtain an instance of this sessionful object.</span></span> <span data-ttu-id="02a73-331">A tale scopo, è possibile creare un'altra interfaccia di servizio WCF che restituisce un oggetto EndpointAddress10.</span><span class="sxs-lookup"><span data-stu-id="02a73-331">We do this by creating another WCF service interface that returns an EndpointAddress10 object.</span></span> <span data-ttu-id="02a73-332">Si tratta di una forma serializzabile di un endpoint che il client può usare per creare l'oggetto con sessione.</span><span class="sxs-lookup"><span data-stu-id="02a73-332">This is a serializable form of an endpoint that the client can use to create the sessionful object.</span></span>  
  
   ```csharp
   [ServiceContract]  
       public interface ISessionBoundFactory  
       {  
           [OperationContract]  
           EndpointAddress10 GetInstanceAddress();  
       }  
   ```  
  
     <span data-ttu-id="02a73-333">È quindi possibile implementare il servizio WCF:</span><span class="sxs-lookup"><span data-stu-id="02a73-333">And we implement this WCF service:</span></span>  
  
   ```csharp
   public class SessionBoundFactory : ISessionBoundFactory  
       {  
           public static ChannelFactory<ISessionBoundObject> _factory =   
               new ChannelFactory<ISessionBoundObject>("sessionbound");  
 
           public SessionBoundFactory()  
           {  
           }  
  
           public EndpointAddress10 GetInstanceAddress()  
           {  
               IClientChannel channel = (IClientChannel)_factory.CreateChannel();  
               return EndpointAddress10.FromEndpointAddress(channel.RemoteAddress);  
           }  
       }  
   ```  
  
     <span data-ttu-id="02a73-334">Questa implementazione mantiene una channel factory singleton per creare oggetti con sessione.</span><span class="sxs-lookup"><span data-stu-id="02a73-334">This implementation maintains a singleton channel factory to create sessionful objects.</span></span> <span data-ttu-id="02a73-335">Quando viene chiamato GetInstanceAddress(), questo crea un canale e un oggetto EndpointAddress10 che fa riferimento in modo efficace all'indirizzo remoto associato a questo canale.</span><span class="sxs-lookup"><span data-stu-id="02a73-335">When GetInstanceAddress() is called, it creates a channel and creates an EndpointAddress10 object that effectively points to the remote address associated with this channel.</span></span> <span data-ttu-id="02a73-336">EndpointAddress10 è semplicemente un tipo di dati che può essere restituito al client in base al valore.</span><span class="sxs-lookup"><span data-stu-id="02a73-336">EndpointAddress10 is simply a data type that can be returned to the client by-value.</span></span>  
  
4.  <span data-ttu-id="02a73-337">È necessario modificare il file di configurazione del server eseguendo le due operazioni seguenti, come illustrato nell'esempio riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="02a73-337">We need to modify the server’s configuration file by doing the following two things as shown in the example below:</span></span>  
  
    1.  <span data-ttu-id="02a73-338">Dichiarare un \<client > sezione che descrive l'endpoint per l'oggetto con sessione.</span><span class="sxs-lookup"><span data-stu-id="02a73-338">Declare a \<client> section that describes the endpoint for the sessionful object.</span></span> <span data-ttu-id="02a73-339">Questa operazione è necessaria perché il server opera anche come client in questa situazione.</span><span class="sxs-lookup"><span data-stu-id="02a73-339">This is necessary because the server also acts as a client in this situation.</span></span>  
  
    2.  <span data-ttu-id="02a73-340">Dichiarare gli endpoint per la factory e l'oggetto con sessione.</span><span class="sxs-lookup"><span data-stu-id="02a73-340">Declare endpoints for the factory and sessionful object.</span></span> <span data-ttu-id="02a73-341">Ciò è necessario per consentire al client di comunicare con gli endpoint del servizio per acquisire l'EndpointAddress10 e per creare il canale con sessione.</span><span class="sxs-lookup"><span data-stu-id="02a73-341">This is necessary to allow the client to communicate with the service endpoints to acquire the EndpointAddress10 and to create the sessionful channel.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
         <client>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
        </client>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
          <service name="Server.MySessionBoundObject">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundObject"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundObject" />  
          </service>  
          <service name="Server.SessionBoundFactory">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundFactory"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundFactory" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="02a73-342">È quindi possibile avviare questi servizi:</span><span class="sxs-lookup"><span data-stu-id="02a73-342">And then we can start these services:</span></span>  
  
   ```csharp
   ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
   factoryHost.Open();  
  
   ServiceHost sessionHost = new ServiceHost(typeof(MySessionBoundObject));  
   sessionHost.Open();  
   ```  
  
5.  <span data-ttu-id="02a73-343">Il client può essere configurato dichiarando questi stessi endpoint nel file app.config del progetto.</span><span class="sxs-lookup"><span data-stu-id="02a73-343">We configure the client by declaring these same endpoints in its project’s app.config file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
          <endpoint name="factory"  
                    address="net.tcp://localhost:8081/SessionBoundFactory"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundFactory"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
6.  <span data-ttu-id="02a73-344">Per creare e usare questo oggetto con sessione, il client deve eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02a73-344">In order to create and use this sessionful object, the client must do the following steps:</span></span>  
  
    1.  <span data-ttu-id="02a73-345">Creare un canale per il servizio ISessionBoundFactory.</span><span class="sxs-lookup"><span data-stu-id="02a73-345">Create a channel to the ISessionBoundFactory service.</span></span>  
  
    2.  <span data-ttu-id="02a73-346">Usare tale canale per richiamare il servizio in modo da ottenere un EndpointAddress10.</span><span class="sxs-lookup"><span data-stu-id="02a73-346">Use that channel to invoke that service to obtain an EndpointAddress10.</span></span>  
  
    3.  <span data-ttu-id="02a73-347">Usare l'EndpointAddress10 per creare un canale in modo da ottenere un oggetto con sessione.</span><span class="sxs-lookup"><span data-stu-id="02a73-347">Use the EndpointAddress10 to create a channel to obtain a sessionful object.</span></span>  
  
    4.  <span data-ttu-id="02a73-348">Interagire con l'oggetto con sessione per verificare che rimanga la stessa istanza fra diverse chiamate.</span><span class="sxs-lookup"><span data-stu-id="02a73-348">Interact with the sessionful object to demonstrate it remains the same instance across multiple calls.</span></span>  
  
   ```csharp
   ChannelFactory<ISessionBoundFactory> channelFactory =   
       new ChannelFactory<ISessionBoundFactory>("factory");  
   ISessionBoundFactory sessionFactory = channelFactory.CreateChannel();  
  
   EndpointAddress10 address1 = sessionFactory.GetInstanceAddress();  
   EndpointAddress10 address2 = sessionFactory.GetInstanceAddress();  
  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory1 =   
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),   
                                               address1.ToEndpointAddress());  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory2 =   
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),   
                                               address2.ToEndpointAddress());  
  
   ISessionBoundObject sessionInstance1 = sessionObjectFactory1.CreateChannel();  
   ISessionBoundObject sessionInstance2 = sessionObjectFactory2.CreateChannel();  
  
   sessionInstance1.SetCurrentValue("Hello");  
   sessionInstance2.SetCurrentValue("World");  
  
   if (sessionInstance1.GetCurrentValue() == "Hello" &&  
       sessionInstance2.GetCurrentValue() == "World")  
   {  
       Console.WriteLine("sessionful server object works as expected");  
   }  
   ```  
  
 <span data-ttu-id="02a73-349">WCF restituisce sempre oggetti in base al valore, ma è possibile supportare l'equivalente di una semantica in base al riferimento mediante l'uso di EndpointAddress10.</span><span class="sxs-lookup"><span data-stu-id="02a73-349">WCF always returns objects by value, but it is possible to support the equivalent of by-reference semantics through the use of EndpointAddress10.</span></span> <span data-ttu-id="02a73-350">Ciò consente al client di richiedere un'istanza del servizio WCF con sessione, dopodiché può interagire con tale istanza come qualsiasi altro servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="02a73-350">This permits the client to request a sessionful WCF service instance, after which it can interact with it like any other WCF service.</span></span>  
  
#### <a name="scenario-3-client-sends-server-a-by-value-instance"></a><span data-ttu-id="02a73-351">Scenario 3: il client invia al server un'istanza in base al valore</span><span class="sxs-lookup"><span data-stu-id="02a73-351">Scenario 3: Client Sends Server a By-Value Instance</span></span>  
 <span data-ttu-id="02a73-352">In questo scenario viene illustrato un client che invia al server un'istanza di oggetto non primitiva in base al valore.</span><span class="sxs-lookup"><span data-stu-id="02a73-352">This scenario demonstrates the client sending a non-primitive object instance to the server by value.</span></span> <span data-ttu-id="02a73-353">Poiché WCF invia solo oggetti in base al valore, in questo scenario viene illustrato il normale uso di WCF.</span><span class="sxs-lookup"><span data-stu-id="02a73-353">Because WCF only sends objects by value, this scenario demonstrates normal WCF usage.</span></span>  
  
1.  <span data-ttu-id="02a73-354">Usare lo stesso servizio WCF dello scenario 1.</span><span class="sxs-lookup"><span data-stu-id="02a73-354">Use the same WCF Service from Scenario 1.</span></span>  
  
2.  <span data-ttu-id="02a73-355">Usare il client per creare un nuovo oggetto in base al valore (Customer), creare un canale per comunicare con il servizio ICustomerService e inviare l'oggetto a tale canale.</span><span class="sxs-lookup"><span data-stu-id="02a73-355">Use the client to create a new by-value object (Customer), create a channel to communicate with the ICustomerService service, and send the object to it.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   PremiumCustomer customer = new PremiumCustomer {   
   FirstName = "Bob",   
   LastName = "Jones",   
   CustomerId = 43,   
   AccountId = 99};  
   bool success = service.UpdateCustomer(customer);  
   Console.WriteLine(String.Format("  Server returned {0}.", success));  
   ```  
  
     <span data-ttu-id="02a73-356">L'oggetto Customer verrà serializzato e inviato al server, dove sarà deserializzato in una nuova copia di tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="02a73-356">The customer object will be serialized, and sent to the server, where it is deserialized into a new copy of that object.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02a73-357">Questo codice illustra inoltre l'invio di un tipo derivato (PremiumCustomer).</span><span class="sxs-lookup"><span data-stu-id="02a73-357">This code also illustrates sending a derived type (PremiumCustomer).</span></span> <span data-ttu-id="02a73-358">L'interfaccia del servizio prevede un oggetto Customer, ma l'attributo [KnownType] nella classe Customer indicava che anche PremiumCustomer era consentito.</span><span class="sxs-lookup"><span data-stu-id="02a73-358">The service interface expects a Customer object, but the [KnownType] attribute on the Customer class indicated PremiumCustomer was also allowed.</span></span> <span data-ttu-id="02a73-359">In WCF qualunque tentativo di serializzare o deserializzare qualsiasi altro tipo tramite questa interfaccia di servizio non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="02a73-359">WCF will fail any attempt to serialize or deserialize any other type through this service interface.</span></span>  
  
 <span data-ttu-id="02a73-360">I normali scambi di dati in WCF sono in base al valore.</span><span class="sxs-lookup"><span data-stu-id="02a73-360">Normal WCF exchanges of data are by value.</span></span> <span data-ttu-id="02a73-361">Ciò garantisce che la chiamata di metodi su uno di questi oggetti di dati venga eseguita solo in locale: non verrà richiamato codice su un altro livello.</span><span class="sxs-lookup"><span data-stu-id="02a73-361">This guarantees that invoking methods on one of these data objects executes only locally – it will not invoke code on the other tier.</span></span> <span data-ttu-id="02a73-362">Sebbene sia possibile ottenere un risultato simile oggetti in base al riferimento restituiti *da* server, non è possibile che un client di passare un oggetto in base al riferimento *per* il server.</span><span class="sxs-lookup"><span data-stu-id="02a73-362">While it is possible to achieve something like by-reference objects returned *from* the server, it is not possible for a client to pass a by-reference object *to* the server.</span></span> <span data-ttu-id="02a73-363">Uno scenario che richiede una conversazione tra il client e il server può essere realizzato in WCF usando un servizio duplex.</span><span class="sxs-lookup"><span data-stu-id="02a73-363">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span> <span data-ttu-id="02a73-364">Per ulteriori informazioni, vedere [servizi Duplex](./feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="02a73-364">For more information, see [Duplex Services](./feature-details/duplex-services.md).</span></span>  
  
## <a name="summary"></a><span data-ttu-id="02a73-365">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="02a73-365">Summary</span></span>  
 <span data-ttu-id="02a73-366">Servizi remoti .NET è un framework di comunicazione destinato all'uso solo all'interno di ambienti completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="02a73-366">.NET Remoting is a communication framework intended to be used only within fully-trusted environments.</span></span> <span data-ttu-id="02a73-367">Si tratta di un prodotto legacy e supportato solo per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="02a73-367">It is a legacy product and supported only for backward compatibility.</span></span> <span data-ttu-id="02a73-368">Non deve essere usato per creare nuove applicazioni.</span><span class="sxs-lookup"><span data-stu-id="02a73-368">It should not be used to build new applications.</span></span> <span data-ttu-id="02a73-369">Al contrario, WCF è stato progettato prestando particolare attenzione alla sicurezza ed è consigliato per le applicazioni nuove ed esistenti.</span><span class="sxs-lookup"><span data-stu-id="02a73-369">Conversely, WCF was designed with security in mind and is recommended for new and existing applications.</span></span> <span data-ttu-id="02a73-370">Microsoft consiglia di eseguire la migrazione delle applicazioni Servizi remoti .NET esistenti per l'uso di WCF o dell'API Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="02a73-370">Microsoft recommends that existing Remoting applications be migrated to use WCF or ASP.NET Web API instead.</span></span>