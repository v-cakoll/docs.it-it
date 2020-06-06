---
title: <discoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
ms.openlocfilehash: 32b14f8fb3235040a51455f2099a403c8312c699
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855402"
---
# \<discoveryEndpoint>

<span data-ttu-id="f3663-101">Questo elemento di configurazione definisce un endpoint standard con un contratto di individuazione fisso.</span><span class="sxs-lookup"><span data-stu-id="f3663-101">This configuration element defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="f3663-102">Quando viene aggiunto alla configurazione del servizio, specifica la posizione di ascolto dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="f3663-102">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="f3663-103">Quando viene aggiunto alla configurazione del client, specifica la posizione di invio delle query di individuazione.</span><span class="sxs-lookup"><span data-stu-id="f3663-103">When added to the client configuration it specifies where to send the discovery queries.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="f3663-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3663-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3663-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f3663-105">Attributes and elements</span></span>

<span data-ttu-id="f3663-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f3663-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3663-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f3663-107">Attributes</span></span>

| <span data-ttu-id="f3663-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="f3663-108">Attribute</span></span>        | <span data-ttu-id="f3663-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3663-109">Description</span></span> |  
| ---------------- | ----------- |  
| <span data-ttu-id="f3663-110">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="f3663-110">discoveryMode</span></span>    | <span data-ttu-id="f3663-111">Stringa che specifica la modalità del protocollo di individuazione.</span><span class="sxs-lookup"><span data-stu-id="f3663-111">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="f3663-112">I valori validi sono "Adhoc" e "Managed".</span><span class="sxs-lookup"><span data-stu-id="f3663-112">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="f3663-113">Nella modalità gestita il protocollo si basa su un proxy di individuazione che viene usato come un repository di servizi individuabili.</span><span class="sxs-lookup"><span data-stu-id="f3663-113">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="f3663-114">Con la modalità Adhoc è necessario che il protocollo utilizzi il meccanismo multicast UDP per l'individuazione dei servizi disponibili.</span><span class="sxs-lookup"><span data-stu-id="f3663-114">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="f3663-115">Per ulteriori informazioni sulla proprietà, vedere <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A> .</span><span class="sxs-lookup"><span data-stu-id="f3663-115">For more information on the property, see <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span></span> |  
| <span data-ttu-id="f3663-116">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="f3663-116">discoveryVersion</span></span> | <span data-ttu-id="f3663-117">Stringa che specifica una delle due versioni del protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="f3663-117">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="f3663-118">I valori validi sono WSDiscovery11 e WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="f3663-118">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="f3663-119">Questo valore è di tipo <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="f3663-119">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span> |  
| <span data-ttu-id="f3663-120">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="f3663-120">maxResponseDelay</span></span> | <span data-ttu-id="f3663-121">Valore TimeSpan che specifica il valore massimo per il tempo di attesa del protocollo di individuazione prima dell'invio di determinati messaggi, ad esempio Probe Match o Resolve Match.</span><span class="sxs-lookup"><span data-stu-id="f3663-121">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="f3663-122">Se tutti i messaggi ProbeMatch vengono inviati contemporaneamente, potrebbero verificarsi problemi di rete.</span><span class="sxs-lookup"><span data-stu-id="f3663-122">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="f3663-123">Per evitare questo problema, i messaggi ProbeMatch vengono inviati con un ritardo casuale tra ogni ProbeMatch.</span><span class="sxs-lookup"><span data-stu-id="f3663-123">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="f3663-124">Il ritardo casuale è compreso nell'intervallo tra 0 e il valore impostato da questo attributo.</span><span class="sxs-lookup"><span data-stu-id="f3663-124">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="f3663-125">Se questo attributo viene impostato su 0, i messaggi ProbeMatch vengono inviati in un ciclo breve senza alcun ritardo.</span><span class="sxs-lookup"><span data-stu-id="f3663-125">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="f3663-126">In caso contrario, i messaggi ProbeMatch vengono inviati con un ritardo casuale, in modo che il tempo totale richiesto per l'invio di tutti i messaggi ProbeMatch non superi il valore di maxResponseDelay.</span><span class="sxs-lookup"><span data-stu-id="f3663-126">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="f3663-127">Questo valore è importante solo per i servizi e non viene usato dai client.</span><span class="sxs-lookup"><span data-stu-id="f3663-127">This value is only relevant for services, it is not used by clients.</span></span> |  
| `name`           | <span data-ttu-id="f3663-128">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="f3663-128">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="f3663-129">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="f3663-129">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span> |  
  
### <a name="child-elements"></a><span data-ttu-id="f3663-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f3663-130">Child elements</span></span>

<span data-ttu-id="f3663-131">No.</span><span class="sxs-lookup"><span data-stu-id="f3663-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3663-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f3663-132">Parent elements</span></span>

| <span data-ttu-id="f3663-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3663-133">Element</span></span> | <span data-ttu-id="f3663-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3663-134">Description</span></span> |  
| ------- | ----------- |  
| [\<standardEndpoints>](standardendpoints.md) | <span data-ttu-id="f3663-135">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="f3663-135">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span> |  
  
## <a name="example"></a><span data-ttu-id="f3663-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="f3663-136">Example</span></span>

<span data-ttu-id="f3663-137">Nell'esempio seguente viene illustrato un servizio in ascolto dei messaggi di individuazione su un trasporto multicast di rete peer.</span><span class="sxs-lookup"><span data-stu-id="f3663-137">The following example demonstrates a service listening on the discovery messages over a peer net multicast transport.</span></span> <span data-ttu-id="f3663-138">Nell'esempio viene specificata in modo esplicito la versione WS-Discovery aprile 2005.</span><span class="sxs-lookup"><span data-stu-id="f3663-138">The example explicitly specifies WS-Discovery April 2005 version.</span></span>  
  
<span data-ttu-id="f3663-139">La configurazione dell'endpoint standard viene definita in base al servizio e non può essere condivisa nel servizio.</span><span class="sxs-lookup"><span data-stu-id="f3663-139">The standard endpoint configuration is defined per service and cannot be shared across the service.</span></span> <span data-ttu-id="f3663-140">Affinché lo stesso endpoint di individuazione possa essere usato da un altro servizio, la stessa configurazione dovrà essere aggiunta alla sezione di tale servizio.</span><span class="sxs-lookup"><span data-stu-id="f3663-140">If another service would like to have the same discovery endpoint, the same configuration needs to be added to that service’s section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f3663-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3663-141">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
