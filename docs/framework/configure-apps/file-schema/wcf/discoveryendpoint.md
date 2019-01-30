---
title: <discoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
ms.openlocfilehash: d1a3371872f5587a682b8242c29b71808508ca3d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274783"
---
# <a name="discoveryendpoint"></a><span data-ttu-id="935a8-101">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="935a8-101">\<discoveryEndpoint></span></span>

<span data-ttu-id="935a8-102">Questo elemento di configurazione definisce un endpoint standard con un contratto di individuazione fisso.</span><span class="sxs-lookup"><span data-stu-id="935a8-102">This configuration element defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="935a8-103">Quando viene aggiunto alla configurazione del servizio, specifica la posizione di ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="935a8-103">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="935a8-104">Quando viene aggiunto alla configurazione del client, specifica la posizione di invio delle query di individuazione.</span><span class="sxs-lookup"><span data-stu-id="935a8-104">When added to the client configuration it specifies where to send the discovery queries.</span></span>  
  
<span data-ttu-id="935a8-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="935a8-105">\<system.serviceModel></span></span>  
<span data-ttu-id="935a8-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="935a8-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="935a8-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="935a8-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="935a8-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="935a8-108">Attributes and elements</span></span>

<span data-ttu-id="935a8-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="935a8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="935a8-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="935a8-110">Attributes</span></span>

| <span data-ttu-id="935a8-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="935a8-111">Attribute</span></span>        | <span data-ttu-id="935a8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="935a8-112">Description</span></span> |  
| ---------------- | ----------- |  
| <span data-ttu-id="935a8-113">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="935a8-113">discoveryMode</span></span>    | <span data-ttu-id="935a8-114">Stringa che specifica la modalità del protocollo di individuazione.</span><span class="sxs-lookup"><span data-stu-id="935a8-114">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="935a8-115">I valori validi sono "Adhoc" e "Managed".</span><span class="sxs-lookup"><span data-stu-id="935a8-115">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="935a8-116">Nella modalità gestita il protocollo si basa su un proxy di individuazione che viene usato come un repository di servizi individuabili.</span><span class="sxs-lookup"><span data-stu-id="935a8-116">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="935a8-117">Con la modalità Adhoc è necessario che il protocollo utilizzi il meccanismo multicast UDP per l'individuazione dei servizi disponibili.</span><span class="sxs-lookup"><span data-stu-id="935a8-117">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="935a8-118">Per altre informazioni sulla proprietà, vedere <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="935a8-118">For more information on the property, see <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span></span> |  
| <span data-ttu-id="935a8-119">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="935a8-119">discoveryVersion</span></span> | <span data-ttu-id="935a8-120">Stringa che specifica una delle due versioni del protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="935a8-120">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="935a8-121">I valori validi sono WSDiscovery11 e WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="935a8-121">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="935a8-122">Questo valore è di tipo <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="935a8-122">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span> |  
| <span data-ttu-id="935a8-123">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="935a8-123">maxResponseDelay</span></span> | <span data-ttu-id="935a8-124">Valore TimeSpan che specifica il valore massimo per il tempo di attesa del protocollo di individuazione prima dell'invio di determinati messaggi, ad esempio Probe Match o Resolve Match.</span><span class="sxs-lookup"><span data-stu-id="935a8-124">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="935a8-125">Se tutti i messaggi ProbeMatch vengono inviati contemporaneamente, potrebbero verificarsi problemi di rete.</span><span class="sxs-lookup"><span data-stu-id="935a8-125">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="935a8-126">Per evitare questo problema, i messaggi ProbeMatch vengono inviati con un ritardo casuale tra ogni ProbeMatch.</span><span class="sxs-lookup"><span data-stu-id="935a8-126">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="935a8-127">Il ritardo casuale è compreso nell'intervallo tra 0 e il valore impostato da questo attributo.</span><span class="sxs-lookup"><span data-stu-id="935a8-127">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="935a8-128">Se questo attributo viene impostato su 0, i messaggi ProbeMatch vengono inviati in un ciclo breve senza alcun ritardo.</span><span class="sxs-lookup"><span data-stu-id="935a8-128">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="935a8-129">In caso contrario, i messaggi ProbeMatch vengono inviati con un ritardo casuale, in modo che il tempo totale richiesto per l'invio di tutti i messaggi ProbeMatch non superi il valore di maxResponseDelay.</span><span class="sxs-lookup"><span data-stu-id="935a8-129">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="935a8-130">Questo valore è importante solo per i servizi e non viene usato dai client.</span><span class="sxs-lookup"><span data-stu-id="935a8-130">This value is only relevant for services, it is not used by clients.</span></span> |  
| `name`           | <span data-ttu-id="935a8-131">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="935a8-131">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="935a8-132">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="935a8-132">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span> |  
  
### <a name="child-elements"></a><span data-ttu-id="935a8-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="935a8-133">Child elements</span></span>

<span data-ttu-id="935a8-134">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="935a8-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="935a8-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="935a8-135">Parent elements</span></span>

| <span data-ttu-id="935a8-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="935a8-136">Element</span></span> | <span data-ttu-id="935a8-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="935a8-137">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="935a8-138">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="935a8-138">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md) | <span data-ttu-id="935a8-139">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="935a8-139">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span> |  
  
## <a name="example"></a><span data-ttu-id="935a8-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="935a8-140">Example</span></span>

<span data-ttu-id="935a8-141">Nell'esempio seguente viene illustrato un servizio in ascolto dei messaggi di individuazione su un trasporto multicast di rete peer.</span><span class="sxs-lookup"><span data-stu-id="935a8-141">The following example demonstrates a service listening on the discovery messages over a peer net multicast transport.</span></span> <span data-ttu-id="935a8-142">Nell'esempio viene specificata in modo esplicito la versione WS-Discovery aprile 2005.</span><span class="sxs-lookup"><span data-stu-id="935a8-142">The example explicitly specifies WS-Discovery April 2005 version.</span></span>  
  
<span data-ttu-id="935a8-143">La configurazione dell'endpoint standard viene definita in base al servizio e non può essere condivisa nel servizio.</span><span class="sxs-lookup"><span data-stu-id="935a8-143">The standard endpoint configuration is defined per service and cannot be shared across the service.</span></span> <span data-ttu-id="935a8-144">Affinché lo stesso endpoint di individuazione possa essere usato da un altro servizio, la stessa configurazione dovrà essere aggiunta alla sezione di tale servizio.</span><span class="sxs-lookup"><span data-stu-id="935a8-144">If another service would like to have the same discovery endpoint, the same configuration needs to be added to that service’s section.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="peerNetDiscovery"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              kind="discoveryEndpoint"
              endpointConfiguration="peerTcpDiscoveryEndpointConfiguration"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  </service>
</services>
<standardEndpoints>
  <discoveryEndpoint>
    <standardEndpoint name="peerTcpDiscoveryEndpointConfiguration"
                      version="WSDiscoveryApril2005" />
  </discoveryEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="935a8-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="935a8-145">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
