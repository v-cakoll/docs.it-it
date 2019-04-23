---
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: b35e2f365e82291d3f8b827850fdebfe8fa2237d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152841"
---
# <a name="netpeertcpbinding"></a><span data-ttu-id="f19df-101">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="f19df-101">\<netPeerTcpBinding></span></span>
<span data-ttu-id="f19df-102">Definisce un'associazione per la messaggistica TCP specifica del canale peer.</span><span class="sxs-lookup"><span data-stu-id="f19df-102">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
 <span data-ttu-id="f19df-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f19df-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f19df-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="f19df-104">\<bindings></span></span>  
<span data-ttu-id="f19df-105">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="f19df-105">\<netPeerTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f19df-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f19df-106">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding name="string"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           listenIPAddress="String"
           maxBufferPoolSize="integer"
           maxReceiveMessageSize="Integer"
           port="Integer">
    <security mode="None/Transport/Message/TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f19df-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f19df-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f19df-108">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f19df-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f19df-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="f19df-109">Attributes</span></span>  
  
|<span data-ttu-id="f19df-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="f19df-110">Attribute</span></span>|<span data-ttu-id="f19df-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f19df-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f19df-112">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="f19df-112">closeTimeout</span></span>|<span data-ttu-id="f19df-113">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="f19df-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="f19df-114">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f19df-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f19df-115">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f19df-115">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="f19df-116">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="f19df-116">listenIPAddress</span></span>|<span data-ttu-id="f19df-117">Stringa che specifica l'indirizzo IP usato dal nodo peer per l'ascolto dei messaggi TCP.</span><span class="sxs-lookup"><span data-stu-id="f19df-117">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="f19df-118">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="f19df-118">The default is `null`.</span></span>|  
|<span data-ttu-id="f19df-119">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="f19df-119">maxBufferPoolSize</span></span>|<span data-ttu-id="f19df-120">Numero intero che specifica la dimensione del pool di buffer massima per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="f19df-120">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="f19df-121">Il valore predefinito è 524.288 byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="f19df-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="f19df-122">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="f19df-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="f19df-123">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="f19df-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="f19df-124">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="f19df-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="f19df-125">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="f19df-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="f19df-126">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="f19df-126">maxReceivedMessageSize</span></span>|<span data-ttu-id="f19df-127">Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="f19df-127">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="f19df-128">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="f19df-128">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="f19df-129">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="f19df-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="f19df-130">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="f19df-130">The default is 65536.</span></span>|  
|<span data-ttu-id="f19df-131">name</span><span class="sxs-lookup"><span data-stu-id="f19df-131">name</span></span>|<span data-ttu-id="f19df-132">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="f19df-132">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="f19df-133">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="f19df-133">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="f19df-134">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="f19df-134">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f19df-135">Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f19df-135">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="f19df-136">openTimeout</span><span class="sxs-lookup"><span data-stu-id="f19df-136">openTimeout</span></span>|<span data-ttu-id="f19df-137">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="f19df-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="f19df-138">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f19df-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f19df-139">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f19df-139">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="f19df-140">porta</span><span class="sxs-lookup"><span data-stu-id="f19df-140">port</span></span>|<span data-ttu-id="f19df-141">Numero intero che specifica la porta dell'interfaccia di rete usata dall'associazione per elaborare i messaggi TCP del canale peer.</span><span class="sxs-lookup"><span data-stu-id="f19df-141">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="f19df-142">Il valore deve essere compreso tra <xref:System.Net.IPEndPoint.MinPort> e <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="f19df-142">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="f19df-143">Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="f19df-143">The default is 0.</span></span>|  
|<span data-ttu-id="f19df-144">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="f19df-144">receiveTimeout</span></span>|<span data-ttu-id="f19df-145">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="f19df-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="f19df-146">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f19df-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f19df-147">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="f19df-147">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="f19df-148">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="f19df-148">sendTimeout</span></span>|<span data-ttu-id="f19df-149">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="f19df-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="f19df-150">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f19df-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f19df-151">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f19df-151">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f19df-152">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f19df-152">Child Elements</span></span>  
  
|<span data-ttu-id="f19df-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="f19df-153">Element</span></span>|<span data-ttu-id="f19df-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f19df-154">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f19df-155">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f19df-155">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="f19df-156">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="f19df-156">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="f19df-157">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="f19df-157">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="f19df-158">\<resolver></span><span class="sxs-lookup"><span data-stu-id="f19df-158">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="f19df-159">Specifica un resolver peer usato dall'associazione per risolvere un ID di rete peer negli indirizzi endpoint dei nodi appartenenti alla rete di peer.</span><span class="sxs-lookup"><span data-stu-id="f19df-159">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[<span data-ttu-id="f19df-160">\<security></span><span class="sxs-lookup"><span data-stu-id="f19df-160">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="f19df-161">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="f19df-161">Defines the security settings for the message.</span></span> <span data-ttu-id="f19df-162">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="f19df-162">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f19df-163">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f19df-163">Parent Elements</span></span>  
  
|<span data-ttu-id="f19df-164">Elemento</span><span class="sxs-lookup"><span data-stu-id="f19df-164">Element</span></span>|<span data-ttu-id="f19df-165">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f19df-165">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f19df-166">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f19df-166">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="f19df-167">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="f19df-167">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f19df-168">Note</span><span class="sxs-lookup"><span data-stu-id="f19df-168">Remarks</span></span>  
 <span data-ttu-id="f19df-169">Questa associazione fornisce il supporto per la creazione di applicazioni peer-to-peer o a più parti usando il trasporto peer su TCP.</span><span class="sxs-lookup"><span data-stu-id="f19df-169">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="f19df-170">Ogni nodo di peer può ospitare più canali del peer definiti con questo tipo di associazione.</span><span class="sxs-lookup"><span data-stu-id="f19df-170">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f19df-171">Esempio</span><span class="sxs-lookup"><span data-stu-id="f19df-171">Example</span></span>  
 <span data-ttu-id="f19df-172">Nell'esempio seguente è dimostrato l'uso dell'associazione NetPeerTcpBinding, il quale fornisce comunicazione a più parti usando un canale peer.</span><span class="sxs-lookup"><span data-stu-id="f19df-172">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="f19df-173">Per uno scenario dettagliato dell'utilizzo di questa associazione, vedere [Net. TCP Peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="f19df-173">For a detailed scenario of using this binding, see [Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netPeerBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 maxBufferSize="1001"
                 maxConnections="123"
                 maxReceiveMessageSize="1000">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="TransportWithMessageCredential">
            <message clientCredentialType="CardSpace" />
          </security>
        </binding>
      </netPeerBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="f19df-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f19df-174">See also</span></span>

- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="f19df-175">Associazioni</span><span class="sxs-lookup"><span data-stu-id="f19df-175">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f19df-176">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="f19df-176">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f19df-177">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="f19df-177">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f19df-178">\<binding></span><span class="sxs-lookup"><span data-stu-id="f19df-178">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- <span data-ttu-id="f19df-179">[Netpeertcp](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f19df-179">[Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span></span>
- [<span data-ttu-id="f19df-180">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="f19df-180">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
