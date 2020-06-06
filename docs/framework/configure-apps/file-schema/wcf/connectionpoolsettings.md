---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 842173c7bd9673a1e08c93d5ed650a42b9d979e5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400474"
---
# \<connectionPoolSettings>
<span data-ttu-id="bb5c8-101">Specifica impostazioni aggiuntive del pool di connessioni per un'associazione con named pipe.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-101">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedPipeTransport>**](namedpipetransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="bb5c8-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb5c8-102">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb5c8-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bb5c8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="bb5c8-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb5c8-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="bb5c8-105">Attributes</span></span>  
  
|<span data-ttu-id="bb5c8-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="bb5c8-106">Attribute</span></span>|<span data-ttu-id="bb5c8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb5c8-107">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="bb5c8-108">Stringa che definisce il nome del pool di connessioni usato per canali in uscita.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-108">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="bb5c8-109">In modalità di invio nel flusso, le connessioni non sono condivise, pertanto il pool di connessioni è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-109">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="bb5c8-110">Il valore predefinito è una stringa "default".</span><span class="sxs-lookup"><span data-stu-id="bb5c8-110">The default is a "default" string.</span></span> <span data-ttu-id="bb5c8-111">È possibile modificare questo valore per isolare le connessioni per un particolare client in gruppi separati.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-111">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="bb5c8-112">Elemento <xref:System.TimeSpan> positivo che specifica il periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-112">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="bb5c8-113">L'impostazione predefinita è 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-113">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="bb5c8-114">Numero intero positivo che specifica il numero massimo di connessioni a un endpoint remoto iniziate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-114">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="bb5c8-115">Le connessioni in eccesso vengono messe in coda finché il numero di connessioni non risulta inferiore al limite consentito.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-115">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="bb5c8-116">`idleTimeout` limita il periodo di tempo entro il quale le connessioni rimangono in coda prima che venga generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-116">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="bb5c8-117">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-117">The default is 10.</span></span><br /><br /> <span data-ttu-id="bb5c8-118">Questo attributo limita il numero di connessioni attive simultanee dal client a un particolare endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-118">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="bb5c8-119">Se questo valore viene superato a causa di un numero maggiore di connessioni client attive, può risultare che il servizio non risponda al client.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-119">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="bb5c8-120">In questo caso, il valore deve essere regolato in modo da superare il numero massimo di connessioni client simultanee previste a un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-120">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb5c8-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bb5c8-121">Child Elements</span></span>  
 <span data-ttu-id="bb5c8-122">No.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb5c8-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bb5c8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bb5c8-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb5c8-124">Element</span></span>|<span data-ttu-id="bb5c8-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb5c8-125">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="bb5c8-126">Definisce un trasporto che fa in modo che un canale trasferisca messaggi usando named pipe.</span><span class="sxs-lookup"><span data-stu-id="bb5c8-126">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb5c8-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="bb5c8-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="bb5c8-128">Trasporti</span><span class="sxs-lookup"><span data-stu-id="bb5c8-128">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="bb5c8-129">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="bb5c8-129">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="bb5c8-130">Binding</span><span class="sxs-lookup"><span data-stu-id="bb5c8-130">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="bb5c8-131">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="bb5c8-131">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="bb5c8-132">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="bb5c8-132">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
