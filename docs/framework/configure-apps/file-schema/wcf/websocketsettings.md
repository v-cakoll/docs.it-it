---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: fa87a1b0961425d6a9bc84769bef6e87cbc2ce96
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732562"
---
# <a name="websocketsettings"></a><span data-ttu-id="02416-101">\<webSocketSettings ></span><span class="sxs-lookup"><span data-stu-id="02416-101">\<webSocketSettings></span></span>
<span data-ttu-id="02416-102">Elemento di configurazione usato per specificare le impostazioni relative a Web Socket.</span><span class="sxs-lookup"><span data-stu-id="02416-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="02416-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="02416-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="02416-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="02416-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="02416-105">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="02416-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="02416-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**NetHttpBinding**](nethttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="02416-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="02416-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="02416-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="02416-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<webSocketSettings >**</span><span class="sxs-lookup"><span data-stu-id="02416-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02416-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02416-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02416-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="02416-110">Attributes and Elements</span></span>  
 <span data-ttu-id="02416-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="02416-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02416-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="02416-112">Attributes</span></span>  
  
|<span data-ttu-id="02416-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="02416-113">Attribute</span></span>|<span data-ttu-id="02416-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02416-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02416-115">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="02416-115">createNotificationOnConnection</span></span>|<span data-ttu-id="02416-116">Specifica se una notifica viene inviata alla connessione.</span><span class="sxs-lookup"><span data-stu-id="02416-116">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="02416-117">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="02416-117">disablePayloadMasking</span></span>|<span data-ttu-id="02416-118">Specifica se il mascheramento di Web Socket è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="02416-118">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="02416-119">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="02416-119">keepAliveInterval</span></span>|<span data-ttu-id="02416-120">Specifica l'intervallo keep-alive.</span><span class="sxs-lookup"><span data-stu-id="02416-120">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="02416-121">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="02416-121">maxPendingConnections</span></span>|<span data-ttu-id="02416-122">Specifica il numero massimo di connessioni in attesa dell'invio nel servizio.</span><span class="sxs-lookup"><span data-stu-id="02416-122">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="02416-123">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="02416-123">receiveBufferSize</span></span>|<span data-ttu-id="02416-124">Specifica le dimensioni del buffer di ricezione.</span><span class="sxs-lookup"><span data-stu-id="02416-124">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="02416-125">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="02416-125">sendBufferSize</span></span>|<span data-ttu-id="02416-126">Specifica le dimensioni del buffer di invio.</span><span class="sxs-lookup"><span data-stu-id="02416-126">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="02416-127">subProtocol</span><span class="sxs-lookup"><span data-stu-id="02416-127">subProtocol</span></span>|<span data-ttu-id="02416-128">Specifica il sottoprotocollo Web Socket.</span><span class="sxs-lookup"><span data-stu-id="02416-128">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="02416-129">transportUsage</span><span class="sxs-lookup"><span data-stu-id="02416-129">transportUsage</span></span>|<span data-ttu-id="02416-130">Specifica quando usare Web Sockets.</span><span class="sxs-lookup"><span data-stu-id="02416-130">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="02416-131">transportUsage Attribute</span><span class="sxs-lookup"><span data-stu-id="02416-131">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="02416-132">Value</span><span class="sxs-lookup"><span data-stu-id="02416-132">Value</span></span>|<span data-ttu-id="02416-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02416-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02416-134">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="02416-134">WhenDuplex</span></span>|<span data-ttu-id="02416-135">Usare il protocollo Web Socket quando il contratto è di tipo duplex.</span><span class="sxs-lookup"><span data-stu-id="02416-135">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="02416-136">Always</span><span class="sxs-lookup"><span data-stu-id="02416-136">Always</span></span>|<span data-ttu-id="02416-137">Usare sempre il protocollo Web Socket indipendentemente dal contratto.</span><span class="sxs-lookup"><span data-stu-id="02416-137">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="02416-138">Never</span><span class="sxs-lookup"><span data-stu-id="02416-138">Never</span></span>|<span data-ttu-id="02416-139">Non usare mai il protocollo Web Socket.</span><span class="sxs-lookup"><span data-stu-id="02416-139">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02416-140">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="02416-140">Child Elements</span></span>  
 <span data-ttu-id="02416-141">Nessuno</span><span class="sxs-lookup"><span data-stu-id="02416-141">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02416-142">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="02416-142">Parent Elements</span></span>  
  
|<span data-ttu-id="02416-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="02416-143">Element</span></span>|<span data-ttu-id="02416-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02416-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02416-145">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="02416-145">\<netHttpBinding></span></span>|<span data-ttu-id="02416-146">Specifica NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="02416-146">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="02416-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="02416-147">Example</span></span>  
 <span data-ttu-id="02416-148">Nell'esempio seguente viene illustrato come utilizzare l'elemento \<> webSocketSettings.</span><span class="sxs-lookup"><span data-stu-id="02416-148">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="02416-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02416-149">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="02416-150">Associazioni</span><span class="sxs-lookup"><span data-stu-id="02416-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="02416-151">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="02416-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="02416-152">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="02416-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="02416-153">\<binding ></span><span class="sxs-lookup"><span data-stu-id="02416-153">\<binding></span></span>](bindings.md)
