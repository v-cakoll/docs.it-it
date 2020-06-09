---
title: Filtro messaggi personalizzato
ms.date: 03/30/2017
ms.assetid: 98dd0af8-fce6-4255-ac32-42eb547eea67
ms.openlocfilehash: 0e4da0f2283fd537afe3cacdddfb36c327cfd3b4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600044"
---
# <a name="custom-message-filter"></a><span data-ttu-id="a3b34-102">Filtro messaggi personalizzato</span><span class="sxs-lookup"><span data-stu-id="a3b34-102">Custom Message Filter</span></span>
<span data-ttu-id="a3b34-103">In questo esempio viene illustrato come sostituire i filtri messaggi utilizzati da Windows Communication Foundation (WCF) per inviare messaggi agli endpoint.</span><span class="sxs-lookup"><span data-stu-id="a3b34-103">This sample demonstrates how to replace the message filters that Windows Communication Foundation (WCF) uses to dispatch messages to endpoints.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3b34-104">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a3b34-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="a3b34-105">Quando il primo messaggio su un canale arriva al server, il server deve determinare quale degli endpoint associati all'URI (se presenti) deve ricevere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="a3b34-105">When the first message on a channel arrives at the server, the server must determine which (if any) of the endpoints associated with that URI should receive the message.</span></span> <span data-ttu-id="a3b34-106">Questo processo viene controllato dagli oggetti <xref:System.ServiceModel.Dispatcher.MessageFilter> allegati a <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span><span class="sxs-lookup"><span data-stu-id="a3b34-106">This process is controlled by the <xref:System.ServiceModel.Dispatcher.MessageFilter> objects attached to the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span>  
  
 <span data-ttu-id="a3b34-107">Ogni endpoint di un servizio ha un solo <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span><span class="sxs-lookup"><span data-stu-id="a3b34-107">Each endpoint of a service has a single <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span> <span data-ttu-id="a3b34-108">La classe <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> è dotata delle proprietà <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> e <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="a3b34-108">The <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> has both an <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and a <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>.</span></span> <span data-ttu-id="a3b34-109">L'unione di questi due filtri è il filtro messaggi utilizzato per quell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="a3b34-109">The union of these two filters is the message filter used for that endpoint.</span></span>  
  
 <span data-ttu-id="a3b34-110">Per impostazione predefinita, la proprietà <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> per un endpoint corrisponde a qualsiasi messaggio indirizzato a un indirizzo che corrisponde alla classe <xref:System.ServiceModel.EndpointAddress> dell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="a3b34-110">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> for an endpoint matches any message that is addressed to an address that matches the service endpoint's <xref:System.ServiceModel.EndpointAddress>.</span></span> <span data-ttu-id="a3b34-111">Per impostazione predefinita, <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> per un endpoint controlla l'azione del messaggio in arrivo e corrisponde a qualsiasi messaggio con un'azione che corrisponde a una delle azioni delle operazioni del contratto dell'endpoint di servizio ( `IsInitiating` = `true` vengono considerate solo le azioni).</span><span class="sxs-lookup"><span data-stu-id="a3b34-111">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> for an endpoint inspects the action of the incoming message and matches any message with an action that corresponds to one of the actions of the service endpoint contract's operations (only `IsInitiating`=`true` actions are considered).</span></span> <span data-ttu-id="a3b34-112">Di conseguenza, per impostazione predefinita il filtro per un endpoint corrisponde solo se l'intestazione di destinazione del messaggio rappresenta la classe <xref:System.ServiceModel.EndpointAddress> dell'endpoint e l'azione del messaggio corrisponde a una delle azioni dell'operazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="a3b34-112">As a result, by default, the filter for an endpoint only matches if both the message's To header is the <xref:System.ServiceModel.EndpointAddress> of the endpoint and the message's action matches one of the endpoint operation's actions.</span></span>  
  
 <span data-ttu-id="a3b34-113">Questi filtri possono essere modificati utilizzando un comportamento.</span><span class="sxs-lookup"><span data-stu-id="a3b34-113">These filters can be changed using a behavior.</span></span> <span data-ttu-id="a3b34-114">Nell'esempio, il servizio crea un'interfaccia <xref:System.ServiceModel.Description.IEndpointBehavior> che sostituisce le proprietà <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> e <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> nella classe <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:</span><span class="sxs-lookup"><span data-stu-id="a3b34-114">In the sample, the service creates an <xref:System.ServiceModel.Description.IEndpointBehavior> that replaces the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> on the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:</span></span>  
  
```csharp
class FilteringEndpointBehavior : IEndpointBehavior
{
    //...
}
```  
  
 <span data-ttu-id="a3b34-115">Vengono definiti due filtri per l'indirizzo:</span><span class="sxs-lookup"><span data-stu-id="a3b34-115">Two address filters are defined:</span></span>  
  
```csharp
// Matches any message whose To address contains the letter 'e'  
class MatchEAddressFilter : MessageFilter { }
// Matches any message whose To address does not contain the letter 'e'  
class MatchNoEAddressFilter : MessageFilter { }  
```  
  
 <span data-ttu-id="a3b34-116">`FilteringEndpointBehavior` è reso configurabile e consente due variazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="a3b34-116">The `FilteringEndpointBehavior` is made configurable and allows for two different variations.</span></span>  
  
```csharp
public class FilteringEndpointBehaviorExtension : BehaviorExtensionElement { }
```  
  
 <span data-ttu-id="a3b34-117">La variazione 1 corrisponde solo agli indirizzi che contengono una 'e' (ma che sono dotati di qualsiasi azione), mentre la variazione 2 corrisponde solo agli indirizzi a cui manca una 'e':</span><span class="sxs-lookup"><span data-stu-id="a3b34-117">Variation 1 matches only addresses that contain an 'e' (but that have any Action) whereas Variation 2 matches only addresses that lack an 'e':</span></span>  
  
```csharp
if (Variation == 1)  
    return new FilteringEndpointBehavior(  
        new MatchEAddressFilter(), new MatchAllMessageFilter());  
else  
    return new FilteringEndpointBehavior(  
        new MatchNoEAddressFilter(), new MatchAllMessageFilter());  
```  
  
 <span data-ttu-id="a3b34-118">Il servizio registra il nuovo comportamento nel file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="a3b34-118">In the configuration file, the service registers the new behavior:</span></span>  
  
```xml  
<extensions>  
    <behaviorExtensions>  
        <add name="filteringEndpointBehavior" type="Microsoft.ServiceModel.Samples.FilteringEndpointBehaviorExtension, service" />  
    </behaviorExtensions>  
</extensions>
```  
  
 <span data-ttu-id="a3b34-119">Il servizio quindi crea le configurazioni `endpointBehavior` per ogni variazione:</span><span class="sxs-lookup"><span data-stu-id="a3b34-119">Then the service creates `endpointBehavior` configurations for each variation:</span></span>  
  
```xml  
<endpointBehaviors>  
    <behavior name="endpoint1">  
        <filteringEndpointBehavior variation="1" />  
    </behavior>  
    <behavior name="endpoint2">  
        <filteringEndpointBehavior variation="2" />  
    </behavior>  
</endpointBehaviors>  
```  
  
 <span data-ttu-id="a3b34-120">L'endpoint del servizio infine fa riferimento a uno degli elementi `behaviorConfigurations`:</span><span class="sxs-lookup"><span data-stu-id="a3b34-120">Finally, the service's endpoint references one of the `behaviorConfigurations`:</span></span>  
  
```xml  
<endpoint address=""  
        bindingConfiguration="ws"  
        listenUri=""
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IHello"
        behaviorConfiguration="endpoint2" />  
```  
  
 <span data-ttu-id="a3b34-121">L'implementazione dell'applicazione client è semplice: crea due canali sull'URI del servizio passando quel valore come il secondo parametro (`via`) su <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> e invia un solo messaggio su ogni canale, utilizzando però indirizzi endpoint diversi per ognuno.</span><span class="sxs-lookup"><span data-stu-id="a3b34-121">The implementation of the client application is straightforward; it creates two channels to the service's URI (by passing in that value as the second (`via`) parameter to <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> and sends a single message on each channel, but it uses different endpoint addresses for each.</span></span> <span data-ttu-id="a3b34-122">Di conseguenza, i messaggi in uscita dal client hanno designazioni di destinazione diverse e il server risponde appropriatamente, come dimostrato dall'output del client:</span><span class="sxs-lookup"><span data-stu-id="a3b34-122">As a result, the outbound messages from the client have different To designations, and the server responds accordingly, as demonstrated by the client's output:</span></span>  
  
```console  
Sending message to urn:e...  
Exception: The message with To 'urn:e' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher.  Check that the sender and receiver's EndpointAddresses agree.  
  
Sending message to urn:a...  
Hello  
```  
  
 <span data-ttu-id="a3b34-123">La commutazione della variazione nel file di configurazione del server determina lo scambio del filtro e la visualizzazione da parte del client del comportamento contrario (il messaggio a `urn:e` ha esito positivo, mentre il messaggio a `urn:a` ha esito negativo).</span><span class="sxs-lookup"><span data-stu-id="a3b34-123">Switching the variation in the server's configuration file causes the filter to be swapped and the client sees the opposite behavior (the message to `urn:e` succeeds, whereas the message to `urn:a` fails).</span></span>  
  
```xml  
<endpoint address=""  
          bindingConfiguration="ws"  
          listenUri=""
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.IHello"
          behaviorConfiguration="endpoint1" />  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="a3b34-124">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a3b34-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a3b34-125">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a3b34-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a3b34-126">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="a3b34-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a3b34-127">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a3b34-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageFilter`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a3b34-128">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="a3b34-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a3b34-129">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a3b34-129">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="a3b34-130">Per eseguire l'esempio in una configurazione a computer singolo, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a3b34-130">To run the sample in a single-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
3. <span data-ttu-id="a3b34-131">Per eseguire l'esempio in una configurazione tra computer, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md) e modificare la riga seguente in client.cs.</span><span class="sxs-lookup"><span data-stu-id="a3b34-131">To run the sample in a cross-machine configuration, follow the instructions at [Running the Windows Communication Foundation Samples](running-the-samples.md) and change the following line in Client.cs.</span></span>  
  
    ```csharp
    Uri serviceVia = new Uri("http://localhost/ServiceModelSamples/service.svc");  
    ```  
  
     <span data-ttu-id="a3b34-132">Sostituire localhost con il nome del server.</span><span class="sxs-lookup"><span data-stu-id="a3b34-132">Replace localhost with the name of server.</span></span>  
  
    ```csharp
    Uri serviceVia = new Uri("http://servermachinename/ServiceModelSamples/service.svc");  
    ```  
