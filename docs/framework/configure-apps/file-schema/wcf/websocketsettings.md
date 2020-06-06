---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: fa87a1b0961425d6a9bc84769bef6e87cbc2ce96
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732562"
---
# \<webSocketSettings>
<span data-ttu-id="498f9-101">Elemento di configurazione usato per specificare le impostazioni relative a Web Socket.</span><span class="sxs-lookup"><span data-stu-id="498f9-101">A configuration element used to specify Web Socket settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="498f9-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="498f9-102">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="498f9-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="498f9-103">Attributes and Elements</span></span>  
 <span data-ttu-id="498f9-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="498f9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="498f9-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="498f9-105">Attributes</span></span>  
  
|<span data-ttu-id="498f9-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="498f9-106">Attribute</span></span>|<span data-ttu-id="498f9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="498f9-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="498f9-108">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="498f9-108">createNotificationOnConnection</span></span>|<span data-ttu-id="498f9-109">Specifica se una notifica viene inviata alla connessione.</span><span class="sxs-lookup"><span data-stu-id="498f9-109">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="498f9-110">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="498f9-110">disablePayloadMasking</span></span>|<span data-ttu-id="498f9-111">Specifica se il mascheramento di Web Socket è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="498f9-111">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="498f9-112">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="498f9-112">keepAliveInterval</span></span>|<span data-ttu-id="498f9-113">Specifica l'intervallo keep-alive.</span><span class="sxs-lookup"><span data-stu-id="498f9-113">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="498f9-114">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="498f9-114">maxPendingConnections</span></span>|<span data-ttu-id="498f9-115">Specifica il numero massimo di connessioni in attesa dell'invio nel servizio.</span><span class="sxs-lookup"><span data-stu-id="498f9-115">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="498f9-116">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="498f9-116">receiveBufferSize</span></span>|<span data-ttu-id="498f9-117">Specifica le dimensioni del buffer di ricezione.</span><span class="sxs-lookup"><span data-stu-id="498f9-117">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="498f9-118">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="498f9-118">sendBufferSize</span></span>|<span data-ttu-id="498f9-119">Specifica le dimensioni del buffer di invio.</span><span class="sxs-lookup"><span data-stu-id="498f9-119">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="498f9-120">subProtocol</span><span class="sxs-lookup"><span data-stu-id="498f9-120">subProtocol</span></span>|<span data-ttu-id="498f9-121">Specifica il sottoprotocollo Web Socket.</span><span class="sxs-lookup"><span data-stu-id="498f9-121">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="498f9-122">transportUsage</span><span class="sxs-lookup"><span data-stu-id="498f9-122">transportUsage</span></span>|<span data-ttu-id="498f9-123">Specifica quando usare Web Sockets.</span><span class="sxs-lookup"><span data-stu-id="498f9-123">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="498f9-124">transportUsage Attribute</span><span class="sxs-lookup"><span data-stu-id="498f9-124">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="498f9-125">Valore</span><span class="sxs-lookup"><span data-stu-id="498f9-125">Value</span></span>|<span data-ttu-id="498f9-126">Description</span><span class="sxs-lookup"><span data-stu-id="498f9-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="498f9-127">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="498f9-127">WhenDuplex</span></span>|<span data-ttu-id="498f9-128">Usare il protocollo Web Socket quando il contratto è di tipo duplex.</span><span class="sxs-lookup"><span data-stu-id="498f9-128">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="498f9-129">Sempre</span><span class="sxs-lookup"><span data-stu-id="498f9-129">Always</span></span>|<span data-ttu-id="498f9-130">Usare sempre il protocollo Web Socket indipendentemente dal contratto.</span><span class="sxs-lookup"><span data-stu-id="498f9-130">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="498f9-131">Mai</span><span class="sxs-lookup"><span data-stu-id="498f9-131">Never</span></span>|<span data-ttu-id="498f9-132">Non usare mai il protocollo Web Socket.</span><span class="sxs-lookup"><span data-stu-id="498f9-132">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="498f9-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="498f9-133">Child Elements</span></span>  
 <span data-ttu-id="498f9-134">nessuno</span><span class="sxs-lookup"><span data-stu-id="498f9-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="498f9-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="498f9-135">Parent Elements</span></span>  
  
|<span data-ttu-id="498f9-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="498f9-136">Element</span></span>|<span data-ttu-id="498f9-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="498f9-137">Description</span></span>|  
|-------------|-----------------|  
|\<netHttpBinding>|<span data-ttu-id="498f9-138">Specifica NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="498f9-138">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="498f9-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="498f9-139">Example</span></span>  
 <span data-ttu-id="498f9-140">L'esempio seguente illustra come usare l'elemento \<webSocketSettings>.</span><span class="sxs-lookup"><span data-stu-id="498f9-140">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="498f9-141">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="498f9-141">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="498f9-142">Binding</span><span class="sxs-lookup"><span data-stu-id="498f9-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="498f9-143">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="498f9-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="498f9-144">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="498f9-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
