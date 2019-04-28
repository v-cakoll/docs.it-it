---
title: Channel factory e memorizzazione nella cache
ms.date: 03/30/2017
ms.assetid: 954f030e-091c-4c0e-a7a2-10f9a6b1f529
ms.openlocfilehash: 3914ba74337bd959558348c191a897c79a32da52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784306"
---
# <a name="channel-factory-and-caching"></a><span data-ttu-id="f1ec8-102">Channel factory e memorizzazione nella cache</span><span class="sxs-lookup"><span data-stu-id="f1ec8-102">Channel Factory and Caching</span></span>
<span data-ttu-id="f1ec8-103">Le applicazioni client WCF utilizzano la classe <xref:System.ServiceModel.ChannelFactory%601> per creare un canale di comunicazione con un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-103">WCF client applications use the <xref:System.ServiceModel.ChannelFactory%601> class to create a communication channel with a WCF service.</span></span>  <span data-ttu-id="f1ec8-104">La creazione di istanze dell'oggetto <xref:System.ServiceModel.ChannelFactory%601> comporta un sovraccarico perché include le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="f1ec8-104">Creating <xref:System.ServiceModel.ChannelFactory%601> instances incurs some overhead because it involves the following operations:</span></span>  
  
- <span data-ttu-id="f1ec8-105">Costruzione dell'albero <xref:System.ServiceModel.Description.ContractDescription></span><span class="sxs-lookup"><span data-stu-id="f1ec8-105">Constructing the <xref:System.ServiceModel.Description.ContractDescription> tree</span></span>  
  
- <span data-ttu-id="f1ec8-106">Reflection di tutti i tipi CLR obbligatori</span><span class="sxs-lookup"><span data-stu-id="f1ec8-106">Reflecting all of the required CLR types</span></span>  
  
- <span data-ttu-id="f1ec8-107">Costruzione dello stack dei canali</span><span class="sxs-lookup"><span data-stu-id="f1ec8-107">Constructing the channel stack</span></span>  
  
- <span data-ttu-id="f1ec8-108">Eliminazione di risorse</span><span class="sxs-lookup"><span data-stu-id="f1ec8-108">Disposing of resources</span></span>  
  
 <span data-ttu-id="f1ec8-109">Per ridurre il sovraccarico, WCF può memorizzare le channel factory nella cache quando si utilizza un proxy client WCF.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-109">To help minimize this overhead, WCF can cache channel factories when you are using a WCF client proxy.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="f1ec8-110">Si dispone di un controllo diretto sulla creazione della channel factory quando si utilizza direttamente la classe <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-110">You have direct control over channel factory creation when you use the <xref:System.ServiceModel.ChannelFactory%601> class directly.</span></span>  
  
 <span data-ttu-id="f1ec8-111">Proxy client WCF generati con [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) derivano dalla <xref:System.ServiceModel.ClientBase%601>.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-111">WCF client proxies generated with [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) are derived from <xref:System.ServiceModel.ClientBase%601>.</span></span> <span data-ttu-id="f1ec8-112"><xref:System.ServiceModel.ClientBase%601> definisce una proprietà <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> statica che definisce il comportamento di memorizzazione nella cache della channel factory.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-112"><xref:System.ServiceModel.ClientBase%601> defines a static <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property that defines channel factory caching behavior.</span></span> <span data-ttu-id="f1ec8-113">Le impostazioni della cache vengono effettuate per un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-113">Cache settings are made for a specific type.</span></span> <span data-ttu-id="f1ec8-114">Ad esempio, impostando `ClientBase<ITest>.CacheSettings` a uno dei valori definiti di seguito influirà solo quei proxy a/ClientBase di tipo `ITest`.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-114">For example, setting  `ClientBase<ITest>.CacheSettings` to one of the values defined below will affect only those proxy/ClientBase of type `ITest`.</span></span> <span data-ttu-id="f1ec8-115">L'impostazione della cache per un oggetto <xref:System.ServiceModel.ClientBase%601> particolare non è più modificabile non appena viene creata la prima istanza di proxy/ClientBase.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-115">The cache setting for a particular <xref:System.ServiceModel.ClientBase%601> is immutable as soon as the first proxy/ClientBase instance is created.</span></span>  
  
## <a name="specifying-caching-behavior"></a><span data-ttu-id="f1ec8-116">Specifica del comportamento di memorizzazione nella cache</span><span class="sxs-lookup"><span data-stu-id="f1ec8-116">Specifying Caching Behavior</span></span>  
 <span data-ttu-id="f1ec8-117">Il comportamento di memorizzazione nella cache viene specificato impostando la proprietà <xref:System.ServiceModel.ClientBase%601.CacheSetting> su uno dei seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-117">Caching behavior is specified by setting the <xref:System.ServiceModel.ClientBase%601.CacheSetting> property to one of the following values.</span></span>  
  
|<span data-ttu-id="f1ec8-118">Valore di impostazione della cache</span><span class="sxs-lookup"><span data-stu-id="f1ec8-118">Cache Setting Value</span></span>|<span data-ttu-id="f1ec8-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1ec8-119">Description</span></span>|  
|-------------------------|-----------------|  
|<xref:System.ServiceModel.CacheSetting.AlwaysOn>|<span data-ttu-id="f1ec8-120">Tutte le istanze di <xref:System.ServiceModel.ClientBase%601> nel dominio applicazione possono partecipare alla memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-120">All instances of <xref:System.ServiceModel.ClientBase%601> within the app-domain can participate in caching.</span></span> <span data-ttu-id="f1ec8-121">Lo sviluppatore ha stabilito che non esistono implicazioni negative sulla sicurezza relativamente alla memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-121">The developer has determined that there are no adverse security implications to caching.</span></span> <span data-ttu-id="f1ec8-122">La memorizzazione nella cache verrà non attivata off anche se "protezione" le proprietà <xref:System.ServiceModel.ClientBase%601> sono accessibili.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-122">Caching will not be turned off even if "security-sensitive" properties on <xref:System.ServiceModel.ClientBase%601> are accessed.</span></span> <span data-ttu-id="f1ec8-123">La proprietà "sensibili alla sicurezza" del <xref:System.ServiceModel.ClientBase%601> vengono <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>, <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> e <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A>.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-123">The "security-sensitive" properties of <xref:System.ServiceModel.ClientBase%601> are <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>, <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> and <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A>.</span></span>|  
|<xref:System.ServiceModel.CacheSetting.Default>|<span data-ttu-id="f1ec8-124">Solo le istanze di <xref:System.ServiceModel.ClientBase%601> create da endpoint definiti nei file di configurazione partecipano alla memorizzazione nella cache nel dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-124">Only instances of <xref:System.ServiceModel.ClientBase%601> created from endpoints defined in configuration files participate in caching within the app-domain.</span></span> <span data-ttu-id="f1ec8-125">Tutte le istanze di <xref:System.ServiceModel.ClientBase%601> create a livello di codice all'interno del dominio applicazione non prenderanno parte alla memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-125">Any instances of <xref:System.ServiceModel.ClientBase%601> created programmatically within that app-domain will not participate in caching.</span></span> <span data-ttu-id="f1ec8-126">Inoltre, la memorizzazione nella cache verrà disabilitata per un'istanza di <xref:System.ServiceModel.ClientBase%601> una volta che si accede a nessuna delle sue proprietà "sensibili alla sicurezza".</span><span class="sxs-lookup"><span data-stu-id="f1ec8-126">Also, caching will be disabled for an instance of <xref:System.ServiceModel.ClientBase%601> once any of its "security-sensitive" properties is accessed.</span></span>|  
|<xref:System.ServiceModel.CacheSetting.AlwaysOff>|<span data-ttu-id="f1ec8-127">La memorizzazione nella cache è disabilitata per tutte le istanze di <xref:System.ServiceModel.ClientBase%601> di un tipo specifico all'interno del dominio applicazione in questione.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-127">Caching is turned off for all instances of <xref:System.ServiceModel.ClientBase%601> of a particular type within the app-domain in question.</span></span>|  
  
 <span data-ttu-id="f1ec8-128">Nei frammenti di codice riportati di seguito viene illustrato come utilizzare la proprietà <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A>.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-128">The following code snippets illustrate how to use the <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property.</span></span>  
  
```csharp  
class Program   
{   
   static void Main(string[] args)   
   {   
      ClientBase<ITest>.CacheSettings = CacheSettings.AlwaysOn;   
      foreach (string msg in messages)   
      {   
         using (TestClient proxy = new TestClient (new BasicHttpBinding(), new EndpointAddress(address)))   
         {   
            // ...  
            proxy.Test(msg);   
            // ...  
         }   
      }   
   }   
}  
// Generated by SvcUtil.exe     
public partial class TestClient : System.ServiceModel.ClientBase, ITest { }  
```  
  
 <span data-ttu-id="f1ec8-129">Nel codice precedente, tutte le istanze di `TestClient` utilizzeranno la stessa channel factory.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-129">In the above code, all instances of `TestClient` will use the same channel factory.</span></span>  
  
```csharp  
class Program   
{   
   static void Main(string[] args)   
   {   
      ClientBase.CacheSettings = CacheSettings.Default;   
      int i = 1;   
      foreach (string msg in messages)   
      {   
         using (TestClient proxy = new TestClient ("MyEndpoint", new EndpointAddress(address)))   
         {   
            if (i == 4)   
            {   
               ServiceEndpoint endpoint = proxy.Endpoint;   
               ... // use endpoint in some way   
            }   
            proxy.Test(msg);   
         }   
         i++;   
   }   
}   
  
// Generated by SvcUtil.exe     
public partial class TestClient : System.ServiceModel.ClientBase, ITest {}  
```  
  
 <span data-ttu-id="f1ec8-130">Nell'esempio precedente, tutte le istanze di `TestClient` utilizzano la stessa channel factory, eccetto l'istanza numero 4.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-130">In the example above, all instances of `TestClient` would use the same channel factory except instance #4.</span></span> <span data-ttu-id="f1ec8-131">L'istanza numero 4 utilizza una channel factory creata in modo specifico per il relativo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-131">Instance #4 would use a channel factory that is created specifically for its use.</span></span> <span data-ttu-id="f1ec8-132">Questa impostazione viene utilizzata per scenari in cui un endpoint particolare necessita di impostazioni di sicurezza diverse dagli altri endpoint dello stesso tipo di channel factory, in questo caso `ITest`.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-132">This setting would work for scenarios where a particular endpoint needs different security settings from the other endpoints of the same channel factory type (in this case `ITest`).</span></span>  
  
```csharp  
class Program   
{   
   static void Main(string[] args)   
   {   
      ClientBase.CacheSettings = CacheSettings.AlwaysOff;   
      foreach (string msg in messages)   
      {   
         using (TestClient proxy = new TestClient ("MyEndpoint", new EndpointAddress(address)))   
         {   
            proxy.Test(msg);   
         }           
      }   
   }  
}  
  
// Generated by SvcUtil.exe   
public partial class TestClient : System.ServiceModel.ClientBase, ITest {}  
```  
  
 <span data-ttu-id="f1ec8-133">Nell'esempio precedente, tutte le istanze di `TestClient` utilizzano channel factory diverse.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-133">In the example above, all instances of `TestClient` would use different channel factories.</span></span> <span data-ttu-id="f1ec8-134">Ciò è utile quando ogni endpoint presenta requisiti di sicurezza diversi e la memorizzazione nella cache non è appropriata.</span><span class="sxs-lookup"><span data-stu-id="f1ec8-134">This is useful when each endpoint has different security requirements and it makes no sense to cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ec8-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1ec8-135">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601>
- [<span data-ttu-id="f1ec8-136">Creazione di client</span><span class="sxs-lookup"><span data-stu-id="f1ec8-136">Building Clients</span></span>](../../../../docs/framework/wcf/building-clients.md)
- [<span data-ttu-id="f1ec8-137">Client</span><span class="sxs-lookup"><span data-stu-id="f1ec8-137">Clients</span></span>](../../../../docs/framework/wcf/feature-details/clients.md)
- [<span data-ttu-id="f1ec8-138">Accesso ai servizi tramite client WCF</span><span class="sxs-lookup"><span data-stu-id="f1ec8-138">Accessing Services Using a WCF Client</span></span>](../../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="f1ec8-139">Procedura: Usare ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="f1ec8-139">How to: Use the ChannelFactory</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
