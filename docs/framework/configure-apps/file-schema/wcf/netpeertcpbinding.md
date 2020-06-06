---
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: 921da4d0b010672585a045d58d03182e480a255a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140734"
---
# \<netPeerTcpBinding>
<span data-ttu-id="30c53-101">Definisce un'associazione per la messaggistica TCP specifica del canale peer.</span><span class="sxs-lookup"><span data-stu-id="30c53-101">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netPeerTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="30c53-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30c53-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30c53-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="30c53-103">Attributes and Elements</span></span>  
 <span data-ttu-id="30c53-104">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="30c53-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30c53-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="30c53-105">Attributes</span></span>  
  
|<span data-ttu-id="30c53-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="30c53-106">Attribute</span></span>|<span data-ttu-id="30c53-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30c53-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="30c53-108">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="30c53-108">closeTimeout</span></span>|<span data-ttu-id="30c53-109">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="30c53-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="30c53-110">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="30c53-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="30c53-111">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="30c53-111">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="30c53-112">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="30c53-112">listenIPAddress</span></span>|<span data-ttu-id="30c53-113">Stringa che specifica l'indirizzo IP usato dal nodo peer per l'ascolto dei messaggi TCP.</span><span class="sxs-lookup"><span data-stu-id="30c53-113">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="30c53-114">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="30c53-114">The default is `null`.</span></span>|  
|<span data-ttu-id="30c53-115">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="30c53-115">maxBufferPoolSize</span></span>|<span data-ttu-id="30c53-116">Numero intero che specifica la dimensione del pool di buffer massima per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="30c53-116">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="30c53-117">Il valore predefinito è 524.288 byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="30c53-117">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="30c53-118">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="30c53-118">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="30c53-119">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="30c53-119">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="30c53-120">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="30c53-120">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="30c53-121">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="30c53-121">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="30c53-122">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="30c53-122">maxReceivedMessageSize</span></span>|<span data-ttu-id="30c53-123">Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="30c53-123">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="30c53-124">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="30c53-124">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="30c53-125">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="30c53-125">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="30c53-126">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="30c53-126">The default is 65536.</span></span>|  
|<span data-ttu-id="30c53-127">name</span><span class="sxs-lookup"><span data-stu-id="30c53-127">name</span></span>|<span data-ttu-id="30c53-128">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="30c53-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="30c53-129">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="30c53-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="30c53-130">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="30c53-130">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="30c53-131">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="30c53-131">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="30c53-132">openTimeout</span><span class="sxs-lookup"><span data-stu-id="30c53-132">openTimeout</span></span>|<span data-ttu-id="30c53-133">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="30c53-133">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="30c53-134">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="30c53-134">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="30c53-135">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="30c53-135">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="30c53-136">port</span><span class="sxs-lookup"><span data-stu-id="30c53-136">port</span></span>|<span data-ttu-id="30c53-137">Numero intero che specifica la porta dell'interfaccia di rete usata dall'associazione per elaborare i messaggi TCP del canale peer.</span><span class="sxs-lookup"><span data-stu-id="30c53-137">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="30c53-138">Il valore deve essere compreso tra <xref:System.Net.IPEndPoint.MinPort> e <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="30c53-138">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="30c53-139">Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="30c53-139">The default is 0.</span></span>|  
|<span data-ttu-id="30c53-140">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="30c53-140">receiveTimeout</span></span>|<span data-ttu-id="30c53-141">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="30c53-141">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="30c53-142">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="30c53-142">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="30c53-143">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="30c53-143">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="30c53-144">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="30c53-144">sendTimeout</span></span>|<span data-ttu-id="30c53-145">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="30c53-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="30c53-146">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="30c53-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="30c53-147">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="30c53-147">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30c53-148">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="30c53-148">Child Elements</span></span>  
  
|<span data-ttu-id="30c53-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="30c53-149">Element</span></span>|<span data-ttu-id="30c53-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30c53-150">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="30c53-151">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="30c53-151">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="30c53-152">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="30c53-152">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<resolver>](resolver.md)|<span data-ttu-id="30c53-153">Specifica un resolver peer usato dall'associazione per risolvere un ID di rete peer negli indirizzi endpoint dei nodi appartenenti alla rete di peer.</span><span class="sxs-lookup"><span data-stu-id="30c53-153">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="30c53-154">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="30c53-154">Defines the security settings for the message.</span></span> <span data-ttu-id="30c53-155">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="30c53-155">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="30c53-156">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="30c53-156">Parent Elements</span></span>  
  
|<span data-ttu-id="30c53-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="30c53-157">Element</span></span>|<span data-ttu-id="30c53-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30c53-158">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="30c53-159">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="30c53-159">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30c53-160">Commenti</span><span class="sxs-lookup"><span data-stu-id="30c53-160">Remarks</span></span>  
 <span data-ttu-id="30c53-161">Questa associazione fornisce il supporto per la creazione di applicazioni peer-to-peer o a più parti usando il trasporto peer su TCP.</span><span class="sxs-lookup"><span data-stu-id="30c53-161">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="30c53-162">Ogni nodo di peer può ospitare più canali del peer definiti con questo tipo di associazione.</span><span class="sxs-lookup"><span data-stu-id="30c53-162">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30c53-163">Esempio</span><span class="sxs-lookup"><span data-stu-id="30c53-163">Example</span></span>  
 <span data-ttu-id="30c53-164">Nell'esempio seguente è dimostrato l'uso dell'associazione NetPeerTcpBinding, il quale fornisce comunicazione a più parti usando un canale peer.</span><span class="sxs-lookup"><span data-stu-id="30c53-164">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="30c53-165">Per uno scenario dettagliato dell'uso di questa associazione, vedere [net peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="30c53-165">For a detailed scenario of using this binding, see [Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="30c53-166">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="30c53-166">See also</span></span>

- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="30c53-167">Binding</span><span class="sxs-lookup"><span data-stu-id="30c53-167">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="30c53-168">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="30c53-168">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="30c53-169">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="30c53-169">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- <span data-ttu-id="30c53-170">[NetPeerTCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="30c53-170">[Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span></span>
- [<span data-ttu-id="30c53-171">Rete peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="30c53-171">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
