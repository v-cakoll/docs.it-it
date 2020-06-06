---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 4a3a17655f5469fe84c0b684ebdac9848bbfba84
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397689"
---
# \<net.tcp>
<span data-ttu-id="575f8-102">Specifica le impostazioni di configurazione per il servizio di condivisione porte NET.TCP, che consente a più processi di condividere la stessa porta TCP.</span><span class="sxs-lookup"><span data-stu-id="575f8-102">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.tcp>**  
  
## <a name="syntax"></a><span data-ttu-id="575f8-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="575f8-103">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="575f8-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="575f8-104">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="575f8-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="575f8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="575f8-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="575f8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="575f8-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="575f8-107">Attributes</span></span>  
  
|<span data-ttu-id="575f8-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="575f8-108">Attribute</span></span>|<span data-ttu-id="575f8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="575f8-109">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="575f8-110">Numero intero che specifica il numero massimo di connessioni in attesa accettate dalla connessione condivisa, ma che non sono ancora state inviate ai servizi Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="575f8-110">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="575f8-111">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="575f8-111">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="575f8-112">Numero intero che specifica il massimo di thread di accettazione contemporaneamente in attesa sull'endpoint di ascolto per il servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="575f8-112">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="575f8-113">Il valore predefinito è 2.</span><span class="sxs-lookup"><span data-stu-id="575f8-113">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="575f8-114">Numero massimo di connessioni che il listener può tenere in attesa di essere accettate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="575f8-114">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="575f8-115">Quando questo valore della quota viene superato, le nuove connessioni in ingresso vengono eliminate anziché restare in attesa di essere accettate.</span><span class="sxs-lookup"><span data-stu-id="575f8-115">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="575f8-116">Le funzionalità di connessione, ad esempio la protezione dei messaggi, possono determinare l'apertura di più connessioni da parte di un client.</span><span class="sxs-lookup"><span data-stu-id="575f8-116">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="575f8-117">Gli amministratori del servizio devono tener conto delle connessioni aggiuntive durante l'impostazione di questo valore della quota.</span><span class="sxs-lookup"><span data-stu-id="575f8-117">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="575f8-118">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="575f8-118">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="575f8-119"><xref:System.TimeSpan> che specifica il timeout per la lettura dei dati sui frame e per l'esecuzione dell'invio della connessione dalle connessioni sottostanti.</span><span class="sxs-lookup"><span data-stu-id="575f8-119">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="575f8-120">L'impostazione predefinita è "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="575f8-120">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="575f8-121">Valore booleano che indica se il servizio di condivisione delle porte utilizza il servizio Microsoft Teredo per l'ascolto sulle porte TCP per conto dei servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="575f8-121">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="575f8-122">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="575f8-122">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="575f8-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="575f8-123">Child Elements</span></span>  
  
|<span data-ttu-id="575f8-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="575f8-124">Element</span></span>|<span data-ttu-id="575f8-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="575f8-125">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="575f8-126">Raccolta di elementi di configurazione che contengono un `securityIdentifier` attributo per specificare gli account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="575f8-126">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="575f8-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="575f8-127">Parent Elements</span></span>  
  
|<span data-ttu-id="575f8-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="575f8-128">Element</span></span>|<span data-ttu-id="575f8-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="575f8-129">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="575f8-130">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="575f8-130">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="575f8-131">Commenti</span><span class="sxs-lookup"><span data-stu-id="575f8-131">Remarks</span></span>  
 <span data-ttu-id="575f8-132">Per ulteriori informazioni sulla condivisione delle porte, vedere la pagina relativa alla [condivisione delle porte net. TCP](../../../wcf/feature-details/net-tcp-port-sharing.md).</span><span class="sxs-lookup"><span data-stu-id="575f8-132">For more information on port sharing, see [Net.TCP Port Sharing](../../../wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="575f8-133">Per informazioni su come configurare il servizio di condivisione delle porte, vedere [configurazione del servizio di condivisione porte net. TCP](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="575f8-133">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="575f8-134">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="575f8-134">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="575f8-135">Condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="575f8-135">Net.TCP Port Sharing</span></span>](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="575f8-136">Configurazione del servizio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="575f8-136">Configuring the Net.TCP Port Sharing Service</span></span>](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
