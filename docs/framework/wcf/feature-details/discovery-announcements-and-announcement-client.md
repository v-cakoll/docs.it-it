---
title: Annunci di individuazione e client annunci
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 426c6437-f8d2-4968-b23a-18afd671aa4b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a6da9c2e251a6592bb0af039d552d02e7e4fd3fd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="discovery-announcements-and-announcement-client"></a><span data-ttu-id="8fe4a-102">Annunci di individuazione e client annunci</span><span class="sxs-lookup"><span data-stu-id="8fe4a-102">Discovery Announcements and Announcement Client</span></span>
<span data-ttu-id="8fe4a-103">La funzionalità di individuazione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consente ai componenti di annunciare la propria disponibilità.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-103">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] discovery feature enables components to announce their availability.</span></span> <span data-ttu-id="8fe4a-104">Se viene configurato a tale scopo, un servizio invia annunci Hello e Bye.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-104">If configured to do so, a service sends Hello and Bye announcements.</span></span> <span data-ttu-id="8fe4a-105">I client o altri componenti possono attendere tali messaggi dell'annuncio ed eseguire azioni su di loro.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-105">Clients or other components can listen for such announcement messages and act on them.</span></span> <span data-ttu-id="8fe4a-106">In questo modo viene fornito un metodo alternativo che consente ai client di essere consapevoli della presenza di servizi.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-106">This provides an alternative method for clients to be aware of services.</span></span> <span data-ttu-id="8fe4a-107">La funzionalità degli annunci può essere utilizzata per vari scopi. Se ad esempio i servizi entrano ed escono periodicamente da una rete, gli annunci possono costituire un'alternativa migliore rispetto alla ricerca di servizi.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-107">Announcement functionality has several uses, for example, if the services enter and leave a network frequently, announcements may be a better alternative than searching for services.</span></span> <span data-ttu-id="8fe4a-108">Con questo approccio, il traffico di rete è ridotto e il client è in grado di sapere se un servizio è presente o assente contestualmente alla ricezione degli annunci.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-108">With this approach, the network traffic is reduced and the client can learn about the presence or departure of the service as soon as announcements are received.</span></span>  
  
## <a name="discovery-announcements"></a><span data-ttu-id="8fe4a-109">Annunci di individuazione</span><span class="sxs-lookup"><span data-stu-id="8fe4a-109">Discovery Announcements</span></span>  
 <span data-ttu-id="8fe4a-110">Se un servizio configurato per gli annunci si unisce a una rete e diviene individuabile, invia un messaggio Hello che annuncia la propria disponibilità ai client in ascolto.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-110">When a service configured for announcements joins a network and becomes discoverable, it sends a Hello message announcing its availability to listening clients.</span></span> <span data-ttu-id="8fe4a-111">Il messaggio contiene le informazioni relative all'individuazione sul servizio, ad esempio il contratto, l'indirizzo endpoint e gli ambiti associati.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-111">The message contains discovery related information about the service, such as its contract, endpoint address and associated scopes.</span></span> <span data-ttu-id="8fe4a-112">È possibile specificare la destinazione dell'invio del messaggio di annuncio con la classe <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-112">You can specify where the announcement message is sent with the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> class.</span></span> <span data-ttu-id="8fe4a-113">Se l'endpoint annunci è un elemento <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>, Hello e Bye sono multicast, mentre se l'endpoint annunci è unicast, i messaggi vengono inviati direttamente all'endpoint specificato.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-113">If the announcement endpoint is a <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> then the Hello and Bye are multicast appropriately, or if the announcement endpoint is unicast, the messages are sent directly to the specified endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fe4a-114">Gli annunci vengono inviati quando l'host del servizio viene aperto e chiuso.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-114">Announcements are sent when the service host opens and closes.</span></span> <span data-ttu-id="8fe4a-115">Se queste chiamate non vengono completate in modo corretto, è possibile che il messaggio dell'annuncio non venga inviato. Se ad esempio si verificano errori nel servizio, il messaggio di annuncio Bye non viene inviato.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-115">If these calls do not finish properly the announcement message may not be sent out. For example if the service faults, then the Bye announcement message is not sent.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="8fe4a-116">È possibile personalizzare la funzionalità di annunci, con la possibilità di inviare annunci in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-116">You can customize the announcement functionality, allowing you to send announcements whenever you choose.</span></span>  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="8fe4a-117"> definisce <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> e <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> come endpoint standard per consentire a servizi e client di inviare facilmente annunci Hello e Bye.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-117"> defines the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> and <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> as standard endpoints to allow services and clients to easily send Hello and Bye announcements.</span></span>  
  
### <a name="announcements-on-the-service"></a><span data-ttu-id="8fe4a-118">Annunci sul servizio</span><span class="sxs-lookup"><span data-stu-id="8fe4a-118">Announcements on the Service</span></span>  
 <span data-ttu-id="8fe4a-119">Per configurare l'invio di annunci da parte del servizio, aggiungere un <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> con un endpoint annunci.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-119">To configure the service to send announcements, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> with an announcement endpoint.</span></span> <span data-ttu-id="8fe4a-120">Nell'esempio seguente viene mostrato come aggiungere a livello di codice questo comportamento all'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-120">The following example shows how to programmatically add this behavior to the service host.</span></span> <span data-ttu-id="8fe4a-121">In questo esempio viene utilizzato `UdpAnnouncementEndpoint`, che implica che gli annunci vengono inviati in multicast a un percorso specificato dallo specifico endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-121">This example uses the `UdpAnnouncementEndpoint`, which implies that the announcements are multicast to a location specified by that standard endpoint.</span></span>  
  
```  
ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());
serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
```  
  
 <span data-ttu-id="8fe4a-122">È inoltre possibile configurare il comportamento nel file di configurazione, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-122">The behavior can be configured in the configuration file as well, as shown in the following example.</span></span>  
  
```xml  
<services>
  <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">
    <!--Add Discovery Endpoint-->
    <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorBehavior">
      <!--Add Discovery behavior-->
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
 <span data-ttu-id="8fe4a-123">Negli esempi precedenti viene configurato un servizio per inviare messaggi di annuncio in modo automatico.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-123">The preceding examples configure a service to automatically send announcement messages.</span></span> <span data-ttu-id="8fe4a-124">È inoltre possibile inviare messaggi di annuncio in modo esplicito tramite la classe <xref:System.ServiceModel.Discovery.AnnouncementClient>.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-124">You can also send announcement messages explicitly by using the <xref:System.ServiceModel.Discovery.AnnouncementClient> class.</span></span>  
  
### <a name="announcements-on-the-client"></a><span data-ttu-id="8fe4a-125">Annunci sul client</span><span class="sxs-lookup"><span data-stu-id="8fe4a-125">Announcements on the Client</span></span>  
 <span data-ttu-id="8fe4a-126">Un'applicazione client deve ospitare un servizio annunci per rispondere ai messaggi Hello e Bye ed eseguire la sottoscrizione agli eventi <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> e <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived>.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-126">A client application must host an announcement service to respond to the Hello and Bye messages and subscribe to the <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> and <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived> events.</span></span> <span data-ttu-id="8fe4a-127">Nell'esempio seguente viene illustrato come effettuare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-127">The following example shows how to do this.</span></span>  
  
```  
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();
  
// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
  
// Create ServiceHost for the AnnouncementService
using (ServiceHost announcementServiceHost = new ServiceHost(announcementService))
{  
    // Listen for the announcements sent over UDP multicast
    announcementServiceHost.AddServiceEndpoint(new UdpAnnouncementEndpoint());
    announcementServiceHost.Open();
  
    Console.WriteLine("Press <ENTER> to terminate.");
    Console.ReadLine();
}  
```  
  
 <span data-ttu-id="8fe4a-128">Alla ricezione di un messaggio Hello o Bye è possibile accedere ai metadati di individuazione di endpoint tramite <xref:System.ServiceModel.Discovery.AnnouncementEventArgs>, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8fe4a-128">When a Hello or Bye message is received, you can access the endpoint discovery metadata through <xref:System.ServiceModel.Discovery.AnnouncementEventArgs> as shown in the following example.</span></span>  
  
```  
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine("Received an online announcement from {0}", 
e.EndpointDiscoveryMetadata.Address);
}

static void OnOfflineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine("Received an offline announcement from {0}", 
e.EndpointDiscoveryMetadata.Address);
}
```
