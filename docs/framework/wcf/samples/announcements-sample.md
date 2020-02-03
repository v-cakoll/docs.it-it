---
title: Esempio di annunci
ms.date: 03/30/2017
ms.assetid: 954a75e4-9a97-41d6-94fc-43765d4205a9
ms.openlocfilehash: c3824fb0dc7ab4169c309d1a5154127d6bc3b78f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747007"
---
# <a name="announcements-sample"></a>Esempio di annunci

In questo esempio viene illustrato come utilizzare la funzionalità degli annunci della funzionalità di individuazione. Gli annunci consentono ai servizi di inviare messaggi di annuncio contenenti i metadati relativi al servizio. Per impostazione predefinita, viene inviato un annuncio Hello all'avvio del servizio e un annuncio Bye all'arresto del servizio. Questi annunci possono essere trasmessi tramite multicast oppure inviati da punto a punto. Questo esempio è costituito da due progetti, ovvero il servizio e il client.

## <a name="service"></a>Service

Questo progetto contiene un servizio calcolatrice indipendente. Nel metodo `Main` viene creato un host del servizio a cui viene aggiunto un endpoint del servizio. Successivamente viene creato un oggetto <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>. Per abilitare gli annunci, è necessario aggiungere un endpoint degli annunci a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>. In questo caso viene aggiunto un endpoint standard, tramite multicast UDP, come endpoint degli annunci. In questo modo gli annunci vengono trasmessi su un indirizzo UDP conosciuto.

```csharp
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

## <a name="client"></a>Client

In questo progetto si noti che il client ospita un <xref:System.ServiceModel.Discovery.AnnouncementService>. Due delegati vengono inoltre registrati con gli eventi. Questi eventi definiscono il comportamento del client alla ricezione di messaggio online e offline.

```csharp
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();

// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
```

I metodi `OnOnlineEvent` e `OnOfflineEvent` gestiscono rispettivamente i messaggi di annuncio Hello e Bye.

```csharp
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

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Questo esempio usa endpoint HTTP e per eseguirlo è necessario aggiungere elenchi di controllo di accesso (ACL) agli URL appropriati. Per ulteriori informazioni, vedere [configurazione di http e HTTPS](../feature-details/configuring-http-and-https.md). L'esecuzione del comando seguente con privilegi elevati consente di aggiungere gli elenchi di controllo di accesso appropriati. È possibile che si desideri sostituire il dominio e il nome utente per gli argomenti seguenti quando il comando non funziona nella forma originale. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. Compila la soluzione.

3. Eseguire l'applicazione client.exe.

4. Eseguire l'applicazione service.exe. Si noti che il client riceve un annuncio online.

5. Chiudere l'applicazione service.exe. Si noti che il client riceve un annuncio offline.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`
