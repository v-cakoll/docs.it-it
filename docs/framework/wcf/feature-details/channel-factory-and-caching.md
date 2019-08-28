---
title: Channel factory e memorizzazione nella cache
ms.date: 03/30/2017
ms.assetid: 954f030e-091c-4c0e-a7a2-10f9a6b1f529
ms.openlocfilehash: 98b77071204e2c2f98609e6c5bb1ca84a896dd58
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040206"
---
# <a name="channel-factory-and-caching"></a><span data-ttu-id="c87dc-102">Channel factory e memorizzazione nella cache</span><span class="sxs-lookup"><span data-stu-id="c87dc-102">Channel Factory and Caching</span></span>

<span data-ttu-id="c87dc-103">Le applicazioni client WCF utilizzano la classe <xref:System.ServiceModel.ChannelFactory%601> per creare un canale di comunicazione con un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="c87dc-103">WCF client applications use the <xref:System.ServiceModel.ChannelFactory%601> class to create a communication channel with a WCF service.</span></span>  <span data-ttu-id="c87dc-104">La creazione di istanze dell'oggetto <xref:System.ServiceModel.ChannelFactory%601> comporta un sovraccarico perché include le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="c87dc-104">Creating <xref:System.ServiceModel.ChannelFactory%601> instances incurs some overhead because it involves the following operations:</span></span>

- <span data-ttu-id="c87dc-105">Costruzione dell'albero <xref:System.ServiceModel.Description.ContractDescription></span><span class="sxs-lookup"><span data-stu-id="c87dc-105">Constructing the <xref:System.ServiceModel.Description.ContractDescription> tree</span></span>

- <span data-ttu-id="c87dc-106">Reflection di tutti i tipi CLR obbligatori</span><span class="sxs-lookup"><span data-stu-id="c87dc-106">Reflecting all of the required CLR types</span></span>

- <span data-ttu-id="c87dc-107">Costruzione dello stack dei canali</span><span class="sxs-lookup"><span data-stu-id="c87dc-107">Constructing the channel stack</span></span>

- <span data-ttu-id="c87dc-108">Eliminazione di risorse</span><span class="sxs-lookup"><span data-stu-id="c87dc-108">Disposing of resources</span></span>

<span data-ttu-id="c87dc-109">Per ridurre il sovraccarico, WCF può memorizzare le channel factory nella cache quando si utilizza un proxy client WCF.</span><span class="sxs-lookup"><span data-stu-id="c87dc-109">To help minimize this overhead, WCF can cache channel factories when you are using a WCF client proxy.</span></span>

> [!TIP]
> <span data-ttu-id="c87dc-110">Si dispone di un controllo diretto sulla creazione della channel factory quando si utilizza direttamente la classe <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="c87dc-110">You have direct control over channel factory creation when you use the <xref:System.ServiceModel.ChannelFactory%601> class directly.</span></span>

<span data-ttu-id="c87dc-111">I proxy client WCF generati con [lo strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) sono <xref:System.ServiceModel.ClientBase%601>derivati da.</span><span class="sxs-lookup"><span data-stu-id="c87dc-111">WCF client proxies generated with [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) are derived from <xref:System.ServiceModel.ClientBase%601>.</span></span> <span data-ttu-id="c87dc-112"><xref:System.ServiceModel.ClientBase%601> definisce una proprietà <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> statica che definisce il comportamento di memorizzazione nella cache della channel factory.</span><span class="sxs-lookup"><span data-stu-id="c87dc-112"><xref:System.ServiceModel.ClientBase%601> defines a static <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property that defines channel factory caching behavior.</span></span> <span data-ttu-id="c87dc-113">Le impostazioni della cache vengono effettuate per un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="c87dc-113">Cache settings are made for a specific type.</span></span> <span data-ttu-id="c87dc-114">Ad esempio, l' `ClientBase<ITest>.CacheSettings` impostazione di su uno dei valori definiti di seguito influirà solo su proxy/ClientBase di `ITest`tipo.</span><span class="sxs-lookup"><span data-stu-id="c87dc-114">For example, setting  `ClientBase<ITest>.CacheSettings` to one of the values defined below will affect only those proxy/ClientBase of type `ITest`.</span></span> <span data-ttu-id="c87dc-115">L'impostazione della cache per un oggetto <xref:System.ServiceModel.ClientBase%601> particolare non è più modificabile non appena viene creata la prima istanza di proxy/ClientBase.</span><span class="sxs-lookup"><span data-stu-id="c87dc-115">The cache setting for a particular <xref:System.ServiceModel.ClientBase%601> is immutable as soon as the first proxy/ClientBase instance is created.</span></span>

## <a name="specifying-caching-behavior"></a><span data-ttu-id="c87dc-116">Specifica del comportamento di memorizzazione nella cache</span><span class="sxs-lookup"><span data-stu-id="c87dc-116">Specifying Caching Behavior</span></span>

<span data-ttu-id="c87dc-117">Il comportamento di memorizzazione nella cache viene specificato impostando la proprietà <xref:System.ServiceModel.ClientBase%601.CacheSetting> su uno dei seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="c87dc-117">Caching behavior is specified by setting the <xref:System.ServiceModel.ClientBase%601.CacheSetting> property to one of the following values.</span></span>

|<span data-ttu-id="c87dc-118">Valore di impostazione della cache</span><span class="sxs-lookup"><span data-stu-id="c87dc-118">Cache Setting Value</span></span>|<span data-ttu-id="c87dc-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c87dc-119">Description</span></span>|
|-------------------------|-----------------|
|<xref:System.ServiceModel.CacheSetting.AlwaysOn>|<span data-ttu-id="c87dc-120">Tutte le istanze di <xref:System.ServiceModel.ClientBase%601> nel dominio applicazione possono partecipare alla memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="c87dc-120">All instances of <xref:System.ServiceModel.ClientBase%601> within the app-domain can participate in caching.</span></span> <span data-ttu-id="c87dc-121">Lo sviluppatore ha stabilito che non esistono implicazioni negative sulla sicurezza relativamente alla memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="c87dc-121">The developer has determined that there are no adverse security implications to caching.</span></span> <span data-ttu-id="c87dc-122">La memorizzazione nella cache non verrà disattivata anche se si accede a proprietà con <xref:System.ServiceModel.ClientBase%601> distinzione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c87dc-122">Caching will not be turned off even if "security-sensitive" properties on <xref:System.ServiceModel.ClientBase%601> are accessed.</span></span> <span data-ttu-id="c87dc-123">Le proprietà "sensibili per la sicurezza" <xref:System.ServiceModel.ClientBase%601> di <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>sono <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> , <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A>e.</span><span class="sxs-lookup"><span data-stu-id="c87dc-123">The "security-sensitive" properties of <xref:System.ServiceModel.ClientBase%601> are <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>, <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> and <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A>.</span></span>|
|<xref:System.ServiceModel.CacheSetting.Default>|<span data-ttu-id="c87dc-124">Solo le istanze di <xref:System.ServiceModel.ClientBase%601> create da endpoint definiti nei file di configurazione partecipano alla memorizzazione nella cache nel dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="c87dc-124">Only instances of <xref:System.ServiceModel.ClientBase%601> created from endpoints defined in configuration files participate in caching within the app-domain.</span></span> <span data-ttu-id="c87dc-125">Tutte le istanze di <xref:System.ServiceModel.ClientBase%601> create a livello di codice all'interno del dominio applicazione non prenderanno parte alla memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="c87dc-125">Any instances of <xref:System.ServiceModel.ClientBase%601> created programmatically within that app-domain will not participate in caching.</span></span> <span data-ttu-id="c87dc-126">Inoltre, la memorizzazione nella cache verrà disabilitata per un' <xref:System.ServiceModel.ClientBase%601> istanza di una volta che viene eseguito l'accesso a una qualsiasi delle proprietà "sensibili per la sicurezza".</span><span class="sxs-lookup"><span data-stu-id="c87dc-126">Also, caching will be disabled for an instance of <xref:System.ServiceModel.ClientBase%601> once any of its "security-sensitive" properties is accessed.</span></span>|
|<xref:System.ServiceModel.CacheSetting.AlwaysOff>|<span data-ttu-id="c87dc-127">La memorizzazione nella cache è disabilitata per tutte le istanze di <xref:System.ServiceModel.ClientBase%601> di un tipo specifico all'interno del dominio applicazione in questione.</span><span class="sxs-lookup"><span data-stu-id="c87dc-127">Caching is turned off for all instances of <xref:System.ServiceModel.ClientBase%601> of a particular type within the app-domain in question.</span></span>|

<span data-ttu-id="c87dc-128">Nei frammenti di codice riportati di seguito viene illustrato come utilizzare la proprietà <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A>.</span><span class="sxs-lookup"><span data-stu-id="c87dc-128">The following code snippets illustrate how to use the <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property.</span></span>

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

<span data-ttu-id="c87dc-129">Nel codice precedente, tutte le istanze di `TestClient` utilizzeranno la stessa channel factory.</span><span class="sxs-lookup"><span data-stu-id="c87dc-129">In the above code, all instances of `TestClient` will use the same channel factory.</span></span>

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

<span data-ttu-id="c87dc-130">Nell'esempio precedente, tutte le istanze di `TestClient` utilizzano la stessa channel factory, eccetto l'istanza numero 4.</span><span class="sxs-lookup"><span data-stu-id="c87dc-130">In the example above, all instances of `TestClient` would use the same channel factory except instance #4.</span></span> <span data-ttu-id="c87dc-131">L'istanza numero 4 utilizza una channel factory creata in modo specifico per il relativo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="c87dc-131">Instance #4 would use a channel factory that is created specifically for its use.</span></span> <span data-ttu-id="c87dc-132">Questa impostazione viene utilizzata per scenari in cui un endpoint particolare necessita di impostazioni di sicurezza diverse dagli altri endpoint dello stesso tipo di channel factory, in questo caso `ITest`.</span><span class="sxs-lookup"><span data-stu-id="c87dc-132">This setting would work for scenarios where a particular endpoint needs different security settings from the other endpoints of the same channel factory type (in this case `ITest`).</span></span>

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

<span data-ttu-id="c87dc-133">Nell'esempio precedente, tutte le istanze di `TestClient` utilizzano channel factory diverse.</span><span class="sxs-lookup"><span data-stu-id="c87dc-133">In the example above, all instances of `TestClient` would use different channel factories.</span></span> <span data-ttu-id="c87dc-134">Ciò è utile quando ogni endpoint presenta requisiti di sicurezza diversi e la memorizzazione nella cache non è appropriata.</span><span class="sxs-lookup"><span data-stu-id="c87dc-134">This is useful when each endpoint has different security requirements and it makes no sense to cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="c87dc-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c87dc-135">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601>
- [<span data-ttu-id="c87dc-136">Creazione di client</span><span class="sxs-lookup"><span data-stu-id="c87dc-136">Building Clients</span></span>](../../../../docs/framework/wcf/building-clients.md)
- [<span data-ttu-id="c87dc-137">Client</span><span class="sxs-lookup"><span data-stu-id="c87dc-137">Clients</span></span>](../../../../docs/framework/wcf/feature-details/clients.md)
- [<span data-ttu-id="c87dc-138">Accesso ai servizi tramite client WCF</span><span class="sxs-lookup"><span data-stu-id="c87dc-138">Accessing Services Using a WCF Client</span></span>](../../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="c87dc-139">Procedura: Usare ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="c87dc-139">How to: Use the ChannelFactory</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
