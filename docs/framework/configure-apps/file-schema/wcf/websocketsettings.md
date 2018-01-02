---
title: '&lt;webSocketSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ee0f555fc1e3412032e0a7dda3a747bbfef6f4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="a2d9e-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="a2d9e-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="a2d9e-103">Elemento di configurazione usato per specificare le impostazioni relative a Web Socket.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="a2d9e-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a2d9e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a2d9e-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="a2d9e-105">\<bindings></span></span>  
<span data-ttu-id="a2d9e-106">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a2d9e-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2d9e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2d9e-107">Syntax</span></span>  
  
```xml  
<netHttpBinding>  
  <binding>   
    <webSocketSettings createNotificationOnConnection="boolean" 
                       disablePayloadMasking="boolean" 
                       keepAliveInterval="TimeSpan" 
                       maxPendingConnections="Integer" 
                       receiveBufferSize="Integer" 
                       sendBufferSize="Integer" 
                       subProtocol="String" 
                       transportUsage="WhenDuplex/Always/Never"/>
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2d9e-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a2d9e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a2d9e-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2d9e-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="a2d9e-110">Attributes</span></span>  
  
|<span data-ttu-id="a2d9e-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="a2d9e-111">Attribute</span></span>|<span data-ttu-id="a2d9e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2d9e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a2d9e-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="a2d9e-113">createNotificationOnConnection</span></span>|<span data-ttu-id="a2d9e-114">Specifica se una notifica viene inviata alla connessione.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="a2d9e-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="a2d9e-115">disablePayloadMasking</span></span>|<span data-ttu-id="a2d9e-116">Specifica se il mascheramento di Web Socket è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="a2d9e-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="a2d9e-117">keepAliveInterval</span></span>|<span data-ttu-id="a2d9e-118">Specifica l'intervallo keep-alive.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="a2d9e-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="a2d9e-119">maxPendingConnections</span></span>|<span data-ttu-id="a2d9e-120">Specifica il numero massimo di connessioni in attesa dell'invio nel servizio.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="a2d9e-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="a2d9e-121">receiveBufferSize</span></span>|<span data-ttu-id="a2d9e-122">Specifica le dimensioni del buffer di ricezione.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="a2d9e-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="a2d9e-123">sendBufferSize</span></span>|<span data-ttu-id="a2d9e-124">Specifica le dimensioni del buffer di invio.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="a2d9e-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="a2d9e-125">subProtocol</span></span>|<span data-ttu-id="a2d9e-126">Specifica il sottoprotocollo Web Socket.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="a2d9e-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="a2d9e-127">transportUsage</span></span>|<span data-ttu-id="a2d9e-128">Specifica quando usare Web Sockets.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="a2d9e-129">transportUsage Attribute</span><span class="sxs-lookup"><span data-stu-id="a2d9e-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="a2d9e-130">Valore</span><span class="sxs-lookup"><span data-stu-id="a2d9e-130">Value</span></span>|<span data-ttu-id="a2d9e-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2d9e-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a2d9e-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="a2d9e-132">WhenDuplex</span></span>|<span data-ttu-id="a2d9e-133">Usare il protocollo Web Socket quando il contratto è di tipo duplex.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="a2d9e-134">Always</span><span class="sxs-lookup"><span data-stu-id="a2d9e-134">Always</span></span>|<span data-ttu-id="a2d9e-135">Usare sempre il protocollo Web Socket indipendentemente dal contratto.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="a2d9e-136">Never</span><span class="sxs-lookup"><span data-stu-id="a2d9e-136">Never</span></span>|<span data-ttu-id="a2d9e-137">Non usare mai il protocollo Web Socket.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2d9e-138">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a2d9e-138">Child Elements</span></span>  
 <span data-ttu-id="a2d9e-139">None</span><span class="sxs-lookup"><span data-stu-id="a2d9e-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2d9e-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a2d9e-140">Parent Elements</span></span>  
  
|<span data-ttu-id="a2d9e-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="a2d9e-141">Element</span></span>|<span data-ttu-id="a2d9e-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2d9e-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a2d9e-143">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a2d9e-143">\<netHttpBinding></span></span>|<span data-ttu-id="a2d9e-144">Specifica NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a2d9e-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a2d9e-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2d9e-145">Example</span></span>  
 <span data-ttu-id="a2d9e-146">Nell'esempio seguente viene illustrato come utilizzare il \<webSocketSettings > elemento.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>  
        <binding>  
          <webSocketSettings createNotificationOnConnection="true"  
                              disablePayloadMasking="false  
                              keepAliveInterval="00:10:00"  
                              maxPendingConnections="100"  
                              receiveBufferSize="1000"  
                              sendBufferSize="1000"  
                              subProtocol="Soap"  
                              transportUsage="WhenDuplex/Always/Never"/>  
  
        </binding>  
      </netHttpBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2d9e-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2d9e-147">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="a2d9e-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="a2d9e-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a2d9e-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="a2d9e-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a2d9e-150">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="a2d9e-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a2d9e-151">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="a2d9e-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
