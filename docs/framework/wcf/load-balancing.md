---
title: Bilanciamento del carico
ms.date: 03/30/2017
helpviewer_keywords:
- load balancing [WCF]
ms.assetid: 148e0168-c08d-4886-8769-776d0953b80f
ms.openlocfilehash: 2a0644ea17db2923f5729feda40f3b2bff364231
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660749"
---
# <a name="load-balancing"></a><span data-ttu-id="87171-102">Bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="87171-102">Load Balancing</span></span>
<span data-ttu-id="87171-103">Un modo per aumentare la capacità delle applicazioni di Windows Communication Foundation (WCF) è a scalabilità orizzontale distribuendole in una farm di server con bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="87171-103">One way to increase the capacity of Windows Communication Foundation (WCF) applications is to scale them out by deploying them into a load-balanced server farm.</span></span> <span data-ttu-id="87171-104">Le applicazioni WCF possono essere con carico bilanciato usando standard il bilanciamento del carico tecniche, tra cui servizi di bilanciamento del carico software, ad esempio Windows Network Load Balancing, nonché di carico basato su hardware appositi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="87171-104">WCF applications can be load balanced using standard load balancing techniques, including software load balancers such as Windows Network Load Balancing as well as hardware-based load balancing appliances.</span></span>  
  
 <span data-ttu-id="87171-105">Le sezioni seguenti illustrano considerazioni per le applicazioni WCF compilate utilizzando varie associazioni fornite dal sistema di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="87171-105">The following sections discuss considerations for load balancing WCF applications built using various system-provided bindings.</span></span>  
  
## <a name="load-balancing-with-the-basic-http-binding"></a><span data-ttu-id="87171-106">Bilanciamento del carico con l'associazione HTTP di base</span><span class="sxs-lookup"><span data-stu-id="87171-106">Load Balancing with the Basic HTTP Binding</span></span>  
 <span data-ttu-id="87171-107">Dalla prospettiva di bilanciamento del carico, le applicazioni WCF che comunicano utilizzando il <xref:System.ServiceModel.BasicHttpBinding> non sono diverse da altri tipi comuni di HTTP traffico di rete (statico contenuto HTML, pagine ASP.NET o servizi Web ASMX).</span><span class="sxs-lookup"><span data-stu-id="87171-107">From the perspective of load balancing, WCF applications that communicate using the <xref:System.ServiceModel.BasicHttpBinding> are no different than other common types of HTTP network traffic (static HTML content, ASP.NET pages, or ASMX Web Services).</span></span> <span data-ttu-id="87171-108">Canali WCF che utilizzano questa associazione sono intrinsecamente senza stati e terminano le connessioni quando il canale viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="87171-108">WCF channels that use this binding are inherently stateless, and terminate their connections when the channel closes.</span></span> <span data-ttu-id="87171-109">Di conseguenza, <xref:System.ServiceModel.BasicHttpBinding> funziona correttamente con le tecniche esistenti di bilanciamento del carico HTTP.</span><span class="sxs-lookup"><span data-stu-id="87171-109">As such, the <xref:System.ServiceModel.BasicHttpBinding> works well with existing HTTP load balancing techniques.</span></span>  
  
 <span data-ttu-id="87171-110">Per impostazione predefinita, <xref:System.ServiceModel.BasicHttpBinding> invia nei messaggi un'intestazione HTTP Connection con un valore `Keep-Alive` che consente ai client di stabilire connessioni permanenti ai servizi che le supportano.</span><span class="sxs-lookup"><span data-stu-id="87171-110">By default, the <xref:System.ServiceModel.BasicHttpBinding> sends a connection HTTP header in messages with a `Keep-Alive` value, which enables clients to establish persistent connections to the services that support them.</span></span> <span data-ttu-id="87171-111">Questa configurazione offre un miglioramento della velocità effettiva poiché le connessioni stabilite in precedenza possono essere riutilizzate per l'invio di messaggi successivi allo stesso server.</span><span class="sxs-lookup"><span data-stu-id="87171-111">This configuration offers enhanced throughput because previously established connections can be reused to send subsequent messages to the same server.</span></span> <span data-ttu-id="87171-112">Il riutilizzo delle connessioni può tuttavia causare una forte associazione dei client a un server specifico all'interno della farm con carico bilanciato, riducendo in questo modo l'efficacia del bilanciamento del carico di tipo round robin.</span><span class="sxs-lookup"><span data-stu-id="87171-112">However, connection reuse may cause clients to become strongly associated to a specific server within the load-balanced farm, which reduces the effectiveness of round-robin load balancing.</span></span> <span data-ttu-id="87171-113">Se questo comportamento è inaccettabile, è possibile disattivare il `Keep-Alive` HTTP nel server utilizzando la proprietà <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> con una classe <xref:System.ServiceModel.Channels.CustomBinding> o una classe <xref:System.ServiceModel.Channels.Binding> definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="87171-113">If this behavior is undesirable, HTTP `Keep-Alive` can be disabled on the server using the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> property with a <xref:System.ServiceModel.Channels.CustomBinding> or user-defined <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="87171-114">Nell'esempio seguente viene illustrato come eseguire questa operazione utilizzando la configurazione.</span><span class="sxs-lookup"><span data-stu-id="87171-114">The following example shows how to do this using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
 <system.serviceModel>  
  <services>  
   <service   
     name="Microsoft.ServiceModel.Samples.CalculatorService"  
     behaviorConfiguration="CalculatorServiceBehavior">  
     <host>  
      <baseAddresses>  
       <add baseAddress="http://localhost:8000/servicemodelsamples/service"/>  
      </baseAddresses>  
     </host>  
    <!-- configure http endpoint, use base address provided by host  
         And the customBinding -->  
     <endpoint address=""  
           binding="customBinding"  
           bindingConfiguration="HttpBinding"   
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
   </service>  
  </services>  
  
  <bindings>  
    <customBinding>  
  
    <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
      <binding name="HttpBinding" keepAliveEnabled="False"/>  
  
    </customBinding>  
  </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="87171-115">Utilizzando la configurazione semplificata introdotta in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], lo stesso comportamento può essere ottenuto utilizzando la configurazione semplificata seguente.</span><span class="sxs-lookup"><span data-stu-id="87171-115">Using the simplified configuration introduced in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], the same behavior can be accomplished using the following simplified configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
 <system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="customBinding" />  
    </protocolMapping>  
    <bindings>  
      <customBinding>  
  
      <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
        <binding keepAliveEnabled="False"/>  
  
      </customBinding>  
    </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="87171-116">Per altre informazioni su endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) (Configurazione semplificata) e [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md) (Configurazione semplificata per servizi WCF).</span><span class="sxs-lookup"><span data-stu-id="87171-116">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="load-balancing-with-the-wshttp-binding-and-the-wsdualhttp-binding"></a><span data-ttu-id="87171-117">Bilanciamento del carico con l'associazione WSHttp e WSDualHttp</span><span class="sxs-lookup"><span data-stu-id="87171-117">Load Balancing with the WSHttp Binding and the WSDualHttp Binding</span></span>  
 <span data-ttu-id="87171-118">Entrambe le classi <xref:System.ServiceModel.WSHttpBinding> e <xref:System.ServiceModel.WSDualHttpBinding> possono essere sottoposte a bilanciamento del carico utilizzando tecniche di bilanciamento del carico HTTP, purché vengano apportate alcune modifiche alla configurazione dell'associazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="87171-118">Both the <xref:System.ServiceModel.WSHttpBinding> and the <xref:System.ServiceModel.WSDualHttpBinding> can be load balanced using HTTP load balancing techniques provided several modifications are made to the default binding configuration.</span></span>  
  
-   <span data-ttu-id="87171-119">Disattivare la definizione del contesto di sicurezza. A tale scopo, impostare la proprietà <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> della classe <xref:System.ServiceModel.WSHttpBinding> su `false`.</span><span class="sxs-lookup"><span data-stu-id="87171-119">Turn off Security Context Establishment: this can be accomplished by the setting the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> property on the <xref:System.ServiceModel.WSHttpBinding> to `false`.</span></span> <span data-ttu-id="87171-120">In alternativa, se sessioni di sicurezza sono necessari, è possibile usare le sessioni di sicurezza con stato, come descritto nel [alle sessioni protette](../../../docs/framework/wcf/feature-details/secure-sessions.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="87171-120">Alternatively, if security sessions are required, it is possible to use stateful security sessions as described in the [Secure Sessions](../../../docs/framework/wcf/feature-details/secure-sessions.md) topic.</span></span> <span data-ttu-id="87171-121">Le sessioni di sicurezza con stato consentono al servizio di rimanere senza stato, poiché lo stato per la sessione di sicurezza viene trasmesso con ogni richiesta come parte del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="87171-121">Stateful security sessions enable the service to remain stateless as all of the state for the security session is transmitted with each request as a part of the protection security token.</span></span> <span data-ttu-id="87171-122">Si noti che per abilitare una sessione di sicurezza con stato, è necessario utilizzare una classe <xref:System.ServiceModel.Channels.CustomBinding> o una classe <xref:System.ServiceModel.Channels.Binding> definita dall'utente, poiché le impostazioni di configurazione necessarie non vengono esposte sulle classi <xref:System.ServiceModel.WSHttpBinding> e <xref:System.ServiceModel.WSDualHttpBinding> fornite dal sistema.</span><span class="sxs-lookup"><span data-stu-id="87171-122">Note that to enable a stateful security session, it is necessary to use a <xref:System.ServiceModel.Channels.CustomBinding> or user-defined <xref:System.ServiceModel.Channels.Binding> as the necessary configuration settings are not exposed on <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.WSDualHttpBinding> that are provided by the system.</span></span>  
  
-   <span data-ttu-id="87171-123">Non utilizzare sessioni affidabili.</span><span class="sxs-lookup"><span data-stu-id="87171-123">Do not use reliable sessions.</span></span> <span data-ttu-id="87171-124">Questa funzionalità è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="87171-124">This feature is off by default.</span></span>  
  
## <a name="load-balancing-the-nettcp-binding"></a><span data-ttu-id="87171-125">Bilanciamento del carico dell'associazione Net.TCP</span><span class="sxs-lookup"><span data-stu-id="87171-125">Load Balancing the Net.TCP Binding</span></span>  
 <span data-ttu-id="87171-126">La classe <xref:System.ServiceModel.NetTcpBinding> può essere sottoposta a bilanciamento del carico utilizzando tecniche di bilanciamento del carico a livello IP.</span><span class="sxs-lookup"><span data-stu-id="87171-126">The <xref:System.ServiceModel.NetTcpBinding> can be load balanced using IP-layer load balancing techniques.</span></span> <span data-ttu-id="87171-127">Tuttavia, per impostazione predefinita, <xref:System.ServiceModel.NetTcpBinding> combina in pool le connessioni TCP per ridurre la latenza delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="87171-127">However, the <xref:System.ServiceModel.NetTcpBinding> pools TCP connections by default to reduce connection latency.</span></span> <span data-ttu-id="87171-128">Si tratta di un'ottimizzazione che interferisce con il meccanismo di base del bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="87171-128">This is an optimization that interferes with the basic mechanism of load balancing.</span></span> <span data-ttu-id="87171-129">Il valore di configurazione principale per ottimizzare <xref:System.ServiceModel.NetTcpBinding> è il timeout di lease, che fa parte delle impostazioni del pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="87171-129">The primary configuration value for optimizing the <xref:System.ServiceModel.NetTcpBinding> is the lease timeout, which is part of the Connection Pool Settings.</span></span> <span data-ttu-id="87171-130">Il pool di connessioni fa in modo che le connessioni client siano associate a server specifici all'interno della farm.</span><span class="sxs-lookup"><span data-stu-id="87171-130">Connection pooling causes client connections to become associated to specific servers within the farm.</span></span> <span data-ttu-id="87171-131">Con l'aumento della durata di tali connessioni (un fattore controllato dall'impostazione del timeout di lease), la distribuzione del carico nei vari server della farm diventa sbilanciata.</span><span class="sxs-lookup"><span data-stu-id="87171-131">As the lifetime of those connections increase (a factor controlled by the lease timeout setting), the load distribution across various servers in the farm becomes unbalanced.</span></span> <span data-ttu-id="87171-132">Di conseguenza, la durata media delle chiamate aumenta.</span><span class="sxs-lookup"><span data-stu-id="87171-132">As a result the average call time increases.</span></span> <span data-ttu-id="87171-133">Quando si utilizza <xref:System.ServiceModel.NetTcpBinding> in scenari con carico bilanciato, considerare una riduzione del timeout di lease predefinito utilizzato dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="87171-133">So when using the <xref:System.ServiceModel.NetTcpBinding> in load-balanced scenarios, consider reducing the default lease timeout used by the binding.</span></span> <span data-ttu-id="87171-134">Un timeout di lease di 30 secondi è un punto di partenza ragionevole per scenari con carico bilanciato, sebbene il valore ottimale dipenda dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87171-134">A 30-second lease timeout is a reasonable starting point for load-balanced scenarios, although the optimal value is application-dependent.</span></span> <span data-ttu-id="87171-135">Per altre informazioni sui timeout di lease del canale e altre quote del trasporto, vedere [le quote dei trasporti](../../../docs/framework/wcf/feature-details/transport-quotas.md).</span><span class="sxs-lookup"><span data-stu-id="87171-135">For more information about the channel lease timeout and other transport quotas, see [Transport Quotas](../../../docs/framework/wcf/feature-details/transport-quotas.md).</span></span>  
  
 <span data-ttu-id="87171-136">Per migliorare le prestazioni in scenari con carico bilanciato, considerare l'utilizzo di <xref:System.ServiceModel.NetTcpSecurity> (<xref:System.ServiceModel.SecurityMode.Transport> o <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>).</span><span class="sxs-lookup"><span data-stu-id="87171-136">For best performance in load-balanced scenarios, consider using <xref:System.ServiceModel.NetTcpSecurity> (either <xref:System.ServiceModel.SecurityMode.Transport> or <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87171-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87171-137">See also</span></span>
- [<span data-ttu-id="87171-138">Procedure consigliate per l'hosting in Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="87171-138">Internet Information Services Hosting Best Practices</span></span>](../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
