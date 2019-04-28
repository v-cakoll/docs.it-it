---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 1101d021f3c7436c4f45a22a48e50f6d1553f753
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769746"
---
# <a name="websocketsettings"></a><span data-ttu-id="d91d0-101">\<webSocketSettings></span><span class="sxs-lookup"><span data-stu-id="d91d0-101">\<webSocketSettings></span></span>
<span data-ttu-id="d91d0-102">Elemento di configurazione usato per specificare le impostazioni relative a Web Socket.</span><span class="sxs-lookup"><span data-stu-id="d91d0-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="d91d0-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d91d0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d91d0-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="d91d0-104">\<bindings></span></span>  
<span data-ttu-id="d91d0-105">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d91d0-105">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d91d0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d91d0-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d91d0-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d91d0-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d91d0-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d91d0-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d91d0-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="d91d0-109">Attributes</span></span>  
  
|<span data-ttu-id="d91d0-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="d91d0-110">Attribute</span></span>|<span data-ttu-id="d91d0-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d91d0-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d91d0-112">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="d91d0-112">createNotificationOnConnection</span></span>|<span data-ttu-id="d91d0-113">Specifica se una notifica viene inviata alla connessione.</span><span class="sxs-lookup"><span data-stu-id="d91d0-113">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="d91d0-114">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="d91d0-114">disablePayloadMasking</span></span>|<span data-ttu-id="d91d0-115">Specifica se il mascheramento di Web Socket è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="d91d0-115">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="d91d0-116">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="d91d0-116">keepAliveInterval</span></span>|<span data-ttu-id="d91d0-117">Specifica l'intervallo keep-alive.</span><span class="sxs-lookup"><span data-stu-id="d91d0-117">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="d91d0-118">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="d91d0-118">maxPendingConnections</span></span>|<span data-ttu-id="d91d0-119">Specifica il numero massimo di connessioni in attesa dell'invio nel servizio.</span><span class="sxs-lookup"><span data-stu-id="d91d0-119">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="d91d0-120">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="d91d0-120">receiveBufferSize</span></span>|<span data-ttu-id="d91d0-121">Specifica le dimensioni del buffer di ricezione.</span><span class="sxs-lookup"><span data-stu-id="d91d0-121">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="d91d0-122">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="d91d0-122">sendBufferSize</span></span>|<span data-ttu-id="d91d0-123">Specifica le dimensioni del buffer di invio.</span><span class="sxs-lookup"><span data-stu-id="d91d0-123">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="d91d0-124">subProtocol</span><span class="sxs-lookup"><span data-stu-id="d91d0-124">subProtocol</span></span>|<span data-ttu-id="d91d0-125">Specifica il sottoprotocollo Web Socket.</span><span class="sxs-lookup"><span data-stu-id="d91d0-125">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="d91d0-126">transportUsage</span><span class="sxs-lookup"><span data-stu-id="d91d0-126">transportUsage</span></span>|<span data-ttu-id="d91d0-127">Specifica quando usare Web Sockets.</span><span class="sxs-lookup"><span data-stu-id="d91d0-127">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="d91d0-128">transportUsage Attribute</span><span class="sxs-lookup"><span data-stu-id="d91d0-128">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="d91d0-129">Value</span><span class="sxs-lookup"><span data-stu-id="d91d0-129">Value</span></span>|<span data-ttu-id="d91d0-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d91d0-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d91d0-131">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="d91d0-131">WhenDuplex</span></span>|<span data-ttu-id="d91d0-132">Usare il protocollo Web Socket quando il contratto è di tipo duplex.</span><span class="sxs-lookup"><span data-stu-id="d91d0-132">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="d91d0-133">Always</span><span class="sxs-lookup"><span data-stu-id="d91d0-133">Always</span></span>|<span data-ttu-id="d91d0-134">Usare sempre il protocollo Web Socket indipendentemente dal contratto.</span><span class="sxs-lookup"><span data-stu-id="d91d0-134">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="d91d0-135">Never</span><span class="sxs-lookup"><span data-stu-id="d91d0-135">Never</span></span>|<span data-ttu-id="d91d0-136">Non usare mai il protocollo Web Socket.</span><span class="sxs-lookup"><span data-stu-id="d91d0-136">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d91d0-137">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d91d0-137">Child Elements</span></span>  
 <span data-ttu-id="d91d0-138">nessuno</span><span class="sxs-lookup"><span data-stu-id="d91d0-138">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d91d0-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d91d0-139">Parent Elements</span></span>  
  
|<span data-ttu-id="d91d0-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="d91d0-140">Element</span></span>|<span data-ttu-id="d91d0-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d91d0-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d91d0-142">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d91d0-142">\<netHttpBinding></span></span>|<span data-ttu-id="d91d0-143">Specifica NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d91d0-143">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d91d0-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="d91d0-144">Example</span></span>  
 <span data-ttu-id="d91d0-145">Nell'esempio seguente viene illustrato come utilizzare il \<webSocketSettings > elemento.</span><span class="sxs-lookup"><span data-stu-id="d91d0-145">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d91d0-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d91d0-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="d91d0-147">Associazioni</span><span class="sxs-lookup"><span data-stu-id="d91d0-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d91d0-148">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="d91d0-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d91d0-149">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="d91d0-149">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d91d0-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="d91d0-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
