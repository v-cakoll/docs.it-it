---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 85a9112def77fc31c8e4b826454894fe7372b31b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257655"
---
# <a name="nettcp"></a><span data-ttu-id="ffff9-102">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="ffff9-102">\<net.tcp></span></span>
<span data-ttu-id="ffff9-103">Specifica le impostazioni di configurazione per il servizio di condivisione porte NET.TCP, che consente a più processi di condividere la stessa porta TCP.</span><span class="sxs-lookup"><span data-stu-id="ffff9-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="ffff9-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="ffff9-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="ffff9-105">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="ffff9-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffff9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ffff9-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="Integer"
             maxPendingAccepts="Integer"
             maxPendingConnections="Integer"
             receiveTimeout="TimeSpan"
             teredoEnabled="Boolean">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only)-->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="ffff9-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="ffff9-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ffff9-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ffff9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ffff9-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ffff9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ffff9-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="ffff9-110">Attributes</span></span>  
  
|<span data-ttu-id="ffff9-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="ffff9-111">Attribute</span></span>|<span data-ttu-id="ffff9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ffff9-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="ffff9-113">Valore intero che specifica i numero massimo di connessioni in attesa accettate dalla connessione condivisa, ma non sono ancora state inviate ai servizi Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ffff9-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="ffff9-114">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="ffff9-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="ffff9-115">Numero intero che specifica il massimo di thread di accettazione contemporaneamente in attesa sull'endpoint di ascolto per il servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="ffff9-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="ffff9-116">Il valore predefinito è 2.</span><span class="sxs-lookup"><span data-stu-id="ffff9-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="ffff9-117">Numero massimo di connessioni che il listener può tenere in attesa di essere accettate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ffff9-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="ffff9-118">Quando questo valore della quota viene superato, le nuove connessioni in ingresso vengono eliminate anziché restare in attesa di essere accettate.</span><span class="sxs-lookup"><span data-stu-id="ffff9-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="ffff9-119">Le funzionalità di connessione, ad esempio la protezione dei messaggi, possono determinare l'apertura di più connessioni da parte di un client.</span><span class="sxs-lookup"><span data-stu-id="ffff9-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="ffff9-120">Gli amministratori del servizio devono tener conto delle connessioni aggiuntive durante l'impostazione di questo valore della quota.</span><span class="sxs-lookup"><span data-stu-id="ffff9-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="ffff9-121">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="ffff9-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="ffff9-122">`TimeSpan` che specifica il timeout per la lettura dei dati sui frame e per l'esecuzione dell'invio della connessione dalle connessioni sottostanti.</span><span class="sxs-lookup"><span data-stu-id="ffff9-122">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="ffff9-123">L'impostazione predefinita è "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="ffff9-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="ffff9-124">Valore booleano che indica se il servizio di condivisione delle porte utilizza Microsoft Teredo per l'ascolto sulle porte TCP per conto di servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="ffff9-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="ffff9-125">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="ffff9-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ffff9-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ffff9-126">Child Elements</span></span>  
  
|<span data-ttu-id="ffff9-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="ffff9-127">Element</span></span>|<span data-ttu-id="ffff9-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ffff9-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ffff9-129">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="ffff9-129">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="ffff9-130">Una raccolta di elementi di configurazione che contengono un `securityIdentifier` attributo per specificare gli account utente per processi che ospitano servizi WCF e vengono concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="ffff9-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ffff9-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ffff9-131">Parent Elements</span></span>  
  
|<span data-ttu-id="ffff9-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="ffff9-132">Element</span></span>|<span data-ttu-id="ffff9-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ffff9-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ffff9-134">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="ffff9-134">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="ffff9-135">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="ffff9-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffff9-136">Note</span><span class="sxs-lookup"><span data-stu-id="ffff9-136">Remarks</span></span>  
 <span data-ttu-id="ffff9-137">Per altre informazioni sulla condivisione di porte, vedere [condivisione delle porte Net. TCP](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md).</span><span class="sxs-lookup"><span data-stu-id="ffff9-137">For more information on port sharing, see [Net.TCP Port Sharing](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="ffff9-138">Per informazioni su come configurare il servizio di condivisione delle porte, vedere [configurazione del servizio di condivisione porta Net. TCP](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="ffff9-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffff9-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffff9-139">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="ffff9-140">Condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="ffff9-140">Net.TCP Port Sharing</span></span>](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="ffff9-141">Configurazione del servizio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="ffff9-141">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
