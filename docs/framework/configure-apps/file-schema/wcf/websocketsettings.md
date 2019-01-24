---
title: '&lt;webSocketSettings&gt;'
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 00c6bc45f06d97d4f95bd6be1515d16141be4e1d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565917"
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="e6054-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="e6054-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="e6054-103">Elemento di configurazione usato per specificare le impostazioni relative a Web Socket.</span><span class="sxs-lookup"><span data-stu-id="e6054-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="e6054-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e6054-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e6054-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="e6054-105">\<bindings></span></span>  
<span data-ttu-id="e6054-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e6054-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6054-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6054-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6054-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e6054-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e6054-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e6054-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6054-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="e6054-110">Attributes</span></span>  
  
|<span data-ttu-id="e6054-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="e6054-111">Attribute</span></span>|<span data-ttu-id="e6054-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6054-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6054-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="e6054-113">createNotificationOnConnection</span></span>|<span data-ttu-id="e6054-114">Specifica se una notifica viene inviata alla connessione.</span><span class="sxs-lookup"><span data-stu-id="e6054-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="e6054-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="e6054-115">disablePayloadMasking</span></span>|<span data-ttu-id="e6054-116">Specifica se il mascheramento di Web Socket è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="e6054-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="e6054-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="e6054-117">keepAliveInterval</span></span>|<span data-ttu-id="e6054-118">Specifica l'intervallo keep-alive.</span><span class="sxs-lookup"><span data-stu-id="e6054-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="e6054-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="e6054-119">maxPendingConnections</span></span>|<span data-ttu-id="e6054-120">Specifica il numero massimo di connessioni in attesa dell'invio nel servizio.</span><span class="sxs-lookup"><span data-stu-id="e6054-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="e6054-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="e6054-121">receiveBufferSize</span></span>|<span data-ttu-id="e6054-122">Specifica le dimensioni del buffer di ricezione.</span><span class="sxs-lookup"><span data-stu-id="e6054-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="e6054-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="e6054-123">sendBufferSize</span></span>|<span data-ttu-id="e6054-124">Specifica le dimensioni del buffer di invio.</span><span class="sxs-lookup"><span data-stu-id="e6054-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="e6054-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="e6054-125">subProtocol</span></span>|<span data-ttu-id="e6054-126">Specifica il sottoprotocollo Web Socket.</span><span class="sxs-lookup"><span data-stu-id="e6054-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="e6054-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="e6054-127">transportUsage</span></span>|<span data-ttu-id="e6054-128">Specifica quando usare Web Sockets.</span><span class="sxs-lookup"><span data-stu-id="e6054-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="e6054-129">transportUsage Attribute</span><span class="sxs-lookup"><span data-stu-id="e6054-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="e6054-130">Valore</span><span class="sxs-lookup"><span data-stu-id="e6054-130">Value</span></span>|<span data-ttu-id="e6054-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6054-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e6054-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="e6054-132">WhenDuplex</span></span>|<span data-ttu-id="e6054-133">Usare il protocollo Web Socket quando il contratto è di tipo duplex.</span><span class="sxs-lookup"><span data-stu-id="e6054-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="e6054-134">Always</span><span class="sxs-lookup"><span data-stu-id="e6054-134">Always</span></span>|<span data-ttu-id="e6054-135">Usare sempre il protocollo Web Socket indipendentemente dal contratto.</span><span class="sxs-lookup"><span data-stu-id="e6054-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="e6054-136">Never</span><span class="sxs-lookup"><span data-stu-id="e6054-136">Never</span></span>|<span data-ttu-id="e6054-137">Non usare mai il protocollo Web Socket.</span><span class="sxs-lookup"><span data-stu-id="e6054-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6054-138">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e6054-138">Child Elements</span></span>  
 <span data-ttu-id="e6054-139">nessuno</span><span class="sxs-lookup"><span data-stu-id="e6054-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6054-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e6054-140">Parent Elements</span></span>  
  
|<span data-ttu-id="e6054-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6054-141">Element</span></span>|<span data-ttu-id="e6054-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6054-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6054-143">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e6054-143">\<netHttpBinding></span></span>|<span data-ttu-id="e6054-144">Specifica NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="e6054-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e6054-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6054-145">Example</span></span>  
 <span data-ttu-id="e6054-146">Nell'esempio seguente viene illustrato come utilizzare il \<webSocketSettings > elemento.</span><span class="sxs-lookup"><span data-stu-id="e6054-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e6054-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6054-147">See also</span></span>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="e6054-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="e6054-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e6054-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="e6054-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e6054-150">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="e6054-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e6054-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="e6054-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
