---
title: Esempio di annunci
ms.date: 03/30/2017
ms.assetid: 954a75e4-9a97-41d6-94fc-43765d4205a9
ms.openlocfilehash: a82056844c9ec8f77bce4b0adec481a025894d1f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43749262"
---
# <a name="announcements-sample"></a><span data-ttu-id="a6be3-102">Esempio di annunci</span><span class="sxs-lookup"><span data-stu-id="a6be3-102">Announcements Sample</span></span>
<span data-ttu-id="a6be3-103">In questo esempio viene illustrato come utilizzare la funzionalità degli annunci della funzionalità di individuazione.</span><span class="sxs-lookup"><span data-stu-id="a6be3-103">This sample shows how to use the Announcement functionality of the Discovery feature.</span></span> <span data-ttu-id="a6be3-104">Gli annunci consentono ai servizi di inviare messaggi di annuncio contenenti i metadati relativi al servizio.</span><span class="sxs-lookup"><span data-stu-id="a6be3-104">Announcements allow services to send out announcement messages that contain metadata about the service.</span></span> <span data-ttu-id="a6be3-105">Per impostazione predefinita, viene inviato un annuncio Hello all'avvio del servizio e un annuncio Bye all'arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="a6be3-105">By default a hello announcement is sent when the service starts up and a bye announcement is sent when the service shuts down.</span></span> <span data-ttu-id="a6be3-106">Questi annunci possono essere trasmessi tramite multicast oppure inviati da punto a punto.</span><span class="sxs-lookup"><span data-stu-id="a6be3-106">These announcements can be multicast or they can be sent point-to-point.</span></span> <span data-ttu-id="a6be3-107">Questo esempio è costituito da due progetti, ovvero il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="a6be3-107">This sample consists of two projects service and client.</span></span>  
  
## <a name="service"></a><span data-ttu-id="a6be3-108">Service</span><span class="sxs-lookup"><span data-stu-id="a6be3-108">Service</span></span>  
 <span data-ttu-id="a6be3-109">Questo progetto contiene un servizio calcolatrice indipendente.</span><span class="sxs-lookup"><span data-stu-id="a6be3-109">This project contains a self-hosted calculator service.</span></span> <span data-ttu-id="a6be3-110">Nel metodo `Main` viene creato un host del servizio a cui viene aggiunto un endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="a6be3-110">In the `Main` method, a service host is created and a service endpoint is added to it.</span></span> <span data-ttu-id="a6be3-111">Successivamente viene creato un oggetto <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="a6be3-111">Next, a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> is created.</span></span> <span data-ttu-id="a6be3-112">Per abilitare gli annunci, è necessario aggiungere un endpoint degli annunci a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="a6be3-112">To enable announcements, an announcement endpoint must be added to the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span> <span data-ttu-id="a6be3-113">In questo caso viene aggiunto un endpoint standard, tramite multicast UDP, come endpoint degli annunci.</span><span class="sxs-lookup"><span data-stu-id="a6be3-113">In this case a standard endpoint, using UDP multicast is added as the announcement endpoint.</span></span> <span data-ttu-id="a6be3-114">In questo modo gli annunci vengono trasmessi su un indirizzo UDP conosciuto.</span><span class="sxs-lookup"><span data-stu-id="a6be3-114">This broadcasts the announcements over a well-known UDP address.</span></span>  
  
```  
Uri baseAddress = new Uri("http://localhost:8000/" + Guid.NewGuid().ToString());  
  
// Create a ServiceHost for the CalculatorService type.  
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))  
{  
     serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new WSHttpBinding(), String.Empty);  
  
     ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();  
  
     // Announce the availability of the service over UDP multicast  
    serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());  
  
    // Make the service discoverable over UDP multicast.  
    serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);                  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    serviceHost.Open();  
    // ...  
}  
```  
  
## <a name="client"></a><span data-ttu-id="a6be3-115">Client</span><span class="sxs-lookup"><span data-stu-id="a6be3-115">Client</span></span>  
 <span data-ttu-id="a6be3-116">In questo progetto si noti che il client ospita un <xref:System.ServiceModel.Discovery.AnnouncementService>.</span><span class="sxs-lookup"><span data-stu-id="a6be3-116">In this project, note that the client hosts an <xref:System.ServiceModel.Discovery.AnnouncementService>.</span></span> <span data-ttu-id="a6be3-117">Due delegati vengono inoltre registrati con gli eventi.</span><span class="sxs-lookup"><span data-stu-id="a6be3-117">Furthermore, two delegates are registered with events.</span></span> <span data-ttu-id="a6be3-118">Questi eventi definiscono il comportamento del client alla ricezione di messaggio online e offline.</span><span class="sxs-lookup"><span data-stu-id="a6be3-118">These events dictate what the client does when online and offline announcements are received.</span></span>  
  
```  
// Create an AnnouncementService instance  
AnnouncementService announcementService = new AnnouncementService();  
  
// Subscribe the announcement events  
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;  
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;  
```  
  
 <span data-ttu-id="a6be3-119">I metodi `OnOnlineEvent` e `OnOfflineEvent` gestiscono rispettivamente i messaggi di annuncio Hello e Bye.</span><span class="sxs-lookup"><span data-stu-id="a6be3-119">The `OnOnlineEvent` and `OnOfflineEvent` methods handle the hello and bye announcement messages respectively.</span></span>  
  
```  
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)  
{  
    Console.WriteLine();              
    Console.WriteLine("Received an online announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);  
PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);  
}  
  
static void OnOfflineEvent(object sender, AnnouncementEventArgs e)  
{  
    Console.WriteLine();  
    Console.WriteLine("Received an offline announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);  
            PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);  
}  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a6be3-120">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="a6be3-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="a6be3-121">In questo esempio utilizza endpoint HTTP e per eseguire questo esempio, corretto elenchi ACL URL devono essere aggiunte vedere [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="a6be3-121">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added see [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) for details.</span></span> <span data-ttu-id="a6be3-122">L'esecuzione del comando seguente con privilegi elevati consente di aggiungere gli elenchi di controllo di accesso appropriati.</span><span class="sxs-lookup"><span data-stu-id="a6be3-122">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="a6be3-123">È possibile che si desideri sostituire il dominio e il nome utente per gli argomenti seguenti quando il comando non funziona nella forma originale.</span><span class="sxs-lookup"><span data-stu-id="a6be3-123">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2.  <span data-ttu-id="a6be3-124">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="a6be3-124">Build the solution.</span></span>  
  
3.  <span data-ttu-id="a6be3-125">Eseguire l'applicazione client.exe.</span><span class="sxs-lookup"><span data-stu-id="a6be3-125">Run the client.exe application.</span></span>  
  
4.  <span data-ttu-id="a6be3-126">Eseguire l'applicazione service.exe.</span><span class="sxs-lookup"><span data-stu-id="a6be3-126">Run the service.exe application.</span></span> <span data-ttu-id="a6be3-127">Si noti che il client riceve un annuncio online.</span><span class="sxs-lookup"><span data-stu-id="a6be3-127">Note the client receives an online announcement.</span></span>  
  
5.  <span data-ttu-id="a6be3-128">Chiudere l'applicazione service.exe.</span><span class="sxs-lookup"><span data-stu-id="a6be3-128">Close the service.exe application.</span></span> <span data-ttu-id="a6be3-129">Si noti che il client riceve un annuncio offline.</span><span class="sxs-lookup"><span data-stu-id="a6be3-129">Note the client receives an offline announcement.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a6be3-130">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a6be3-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a6be3-131">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a6be3-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a6be3-132">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="a6be3-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a6be3-133">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a6be3-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`  
  
## <a name="see-also"></a><span data-ttu-id="a6be3-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6be3-134">See Also</span></span>
