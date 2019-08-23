---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 5c9dbec13dd0d71ba1b92ea971d067540013b6f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940312"
---
# <a name="websocketsettings"></a><span data-ttu-id="05849-101">\<webSocketSettings></span><span class="sxs-lookup"><span data-stu-id="05849-101">\<webSocketSettings></span></span>
<span data-ttu-id="05849-102">Elemento di configurazione usato per specificare le impostazioni relative a Web Socket.</span><span class="sxs-lookup"><span data-stu-id="05849-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="05849-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="05849-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="05849-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="05849-104">\<bindings></span></span>  
<span data-ttu-id="05849-105">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="05849-105">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05849-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05849-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05849-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="05849-107">Attributes and Elements</span></span>  
 <span data-ttu-id="05849-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="05849-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05849-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="05849-109">Attributes</span></span>  
  
|<span data-ttu-id="05849-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="05849-110">Attribute</span></span>|<span data-ttu-id="05849-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05849-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="05849-112">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="05849-112">createNotificationOnConnection</span></span>|<span data-ttu-id="05849-113">Specifica se una notifica viene inviata alla connessione.</span><span class="sxs-lookup"><span data-stu-id="05849-113">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="05849-114">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="05849-114">disablePayloadMasking</span></span>|<span data-ttu-id="05849-115">Specifica se il mascheramento di Web Socket è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="05849-115">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="05849-116">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="05849-116">keepAliveInterval</span></span>|<span data-ttu-id="05849-117">Specifica l'intervallo keep-alive.</span><span class="sxs-lookup"><span data-stu-id="05849-117">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="05849-118">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="05849-118">maxPendingConnections</span></span>|<span data-ttu-id="05849-119">Specifica il numero massimo di connessioni in attesa dell'invio nel servizio.</span><span class="sxs-lookup"><span data-stu-id="05849-119">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="05849-120">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="05849-120">receiveBufferSize</span></span>|<span data-ttu-id="05849-121">Specifica le dimensioni del buffer di ricezione.</span><span class="sxs-lookup"><span data-stu-id="05849-121">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="05849-122">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="05849-122">sendBufferSize</span></span>|<span data-ttu-id="05849-123">Specifica le dimensioni del buffer di invio.</span><span class="sxs-lookup"><span data-stu-id="05849-123">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="05849-124">subProtocol</span><span class="sxs-lookup"><span data-stu-id="05849-124">subProtocol</span></span>|<span data-ttu-id="05849-125">Specifica il sottoprotocollo Web Socket.</span><span class="sxs-lookup"><span data-stu-id="05849-125">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="05849-126">transportUsage</span><span class="sxs-lookup"><span data-stu-id="05849-126">transportUsage</span></span>|<span data-ttu-id="05849-127">Specifica quando usare Web Sockets.</span><span class="sxs-lookup"><span data-stu-id="05849-127">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="05849-128">transportUsage Attribute</span><span class="sxs-lookup"><span data-stu-id="05849-128">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="05849-129">Value</span><span class="sxs-lookup"><span data-stu-id="05849-129">Value</span></span>|<span data-ttu-id="05849-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05849-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="05849-131">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="05849-131">WhenDuplex</span></span>|<span data-ttu-id="05849-132">Usare il protocollo Web Socket quando il contratto è di tipo duplex.</span><span class="sxs-lookup"><span data-stu-id="05849-132">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="05849-133">Always</span><span class="sxs-lookup"><span data-stu-id="05849-133">Always</span></span>|<span data-ttu-id="05849-134">Usare sempre il protocollo Web Socket indipendentemente dal contratto.</span><span class="sxs-lookup"><span data-stu-id="05849-134">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="05849-135">Never</span><span class="sxs-lookup"><span data-stu-id="05849-135">Never</span></span>|<span data-ttu-id="05849-136">Non usare mai il protocollo Web Socket.</span><span class="sxs-lookup"><span data-stu-id="05849-136">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05849-137">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="05849-137">Child Elements</span></span>  
 <span data-ttu-id="05849-138">Nessuna</span><span class="sxs-lookup"><span data-stu-id="05849-138">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05849-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="05849-139">Parent Elements</span></span>  
  
|<span data-ttu-id="05849-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="05849-140">Element</span></span>|<span data-ttu-id="05849-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05849-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="05849-142">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="05849-142">\<netHttpBinding></span></span>|<span data-ttu-id="05849-143">Specifica NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="05849-143">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="05849-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="05849-144">Example</span></span>  
 <span data-ttu-id="05849-145">Nell'esempio seguente viene illustrato come utilizzare l' \<elemento webSocketSettings >.</span><span class="sxs-lookup"><span data-stu-id="05849-145">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="05849-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05849-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="05849-147">Associazioni</span><span class="sxs-lookup"><span data-stu-id="05849-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="05849-148">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="05849-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="05849-149">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="05849-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="05849-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="05849-150">\<binding></span></span>](../../../misc/binding.md)
