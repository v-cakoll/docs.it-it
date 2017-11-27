---
title: '&lt;NET. TCP&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6cd220b07c2d8f9a24591fc6e9614099e8460139
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltnettcpgt"></a><span data-ttu-id="402c2-102">&lt;NET. TCP&gt;</span><span class="sxs-lookup"><span data-stu-id="402c2-102">&lt;net.tcp&gt;</span></span>
<span data-ttu-id="402c2-103">Specifica le impostazioni di configurazione per il servizio di condivisione porte NET.TCP, che consente a più processi di condividere la stessa porta TCP.</span><span class="sxs-lookup"><span data-stu-id="402c2-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="402c2-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="402c2-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="402c2-105">\<NET ></span><span class="sxs-lookup"><span data-stu-id="402c2-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="402c2-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="402c2-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="402c2-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="402c2-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="402c2-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="402c2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="402c2-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="402c2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="402c2-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="402c2-110">Attributes</span></span>  
  
|<span data-ttu-id="402c2-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="402c2-111">Attribute</span></span>|<span data-ttu-id="402c2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="402c2-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="402c2-113">Numero intero che specifica la quantità massima di connessioni in attesa accettate dalla connessione condivisa, ma che non sono ancora state inviate ai servizi [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="402c2-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span> <span data-ttu-id="402c2-114">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="402c2-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="402c2-115">Numero intero che specifica il massimo di thread di accettazione contemporaneamente in attesa sull'endpoint di ascolto per il servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="402c2-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="402c2-116">Il valore predefinito è 2.</span><span class="sxs-lookup"><span data-stu-id="402c2-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="402c2-117">Numero massimo di connessioni che il listener può tenere in attesa di essere accettate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="402c2-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="402c2-118">Quando questo valore della quota viene superato, le nuove connessioni in ingresso vengono eliminate anziché restare in attesa di essere accettate.</span><span class="sxs-lookup"><span data-stu-id="402c2-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="402c2-119">Le funzionalità di connessione, ad esempio la protezione dei messaggi, possono determinare l'apertura di più connessioni da parte di un client.</span><span class="sxs-lookup"><span data-stu-id="402c2-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="402c2-120">Gli amministratori del servizio devono tener conto delle connessioni aggiuntive durante l'impostazione di questo valore della quota.</span><span class="sxs-lookup"><span data-stu-id="402c2-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="402c2-121">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="402c2-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="402c2-122">`TimeSpan` che specifica il timeout per la lettura dei dati sui frame e per l'esecuzione dell'invio della connessione dalle connessioni sottostanti.</span><span class="sxs-lookup"><span data-stu-id="402c2-122">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="402c2-123">L'impostazione predefinita è "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="402c2-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="402c2-124">Valore booleano che indica se il servizio di condivisione delle porte usa il servizio Microsoft Teredo per l'ascolto sulle porte TCP per conto dei servizi [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="402c2-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="402c2-125">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="402c2-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="402c2-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="402c2-126">Child Elements</span></span>  
  
|<span data-ttu-id="402c2-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="402c2-127">Element</span></span>|<span data-ttu-id="402c2-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="402c2-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="402c2-129">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="402c2-129">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="402c2-130">Raccolta di elementi di configurazione che contiene un attributo `securityIdentifier` per specificare account utente per processi che ospitano servizi [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] e ai quali è concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="402c2-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="402c2-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="402c2-131">Parent Elements</span></span>  
  
|<span data-ttu-id="402c2-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="402c2-132">Element</span></span>|<span data-ttu-id="402c2-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="402c2-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="402c2-134">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="402c2-134">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="402c2-135">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="402c2-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="402c2-136">Note</span><span class="sxs-lookup"><span data-stu-id="402c2-136">Remarks</span></span>  
 <span data-ttu-id="402c2-137">Per ulteriori informazioni sulla condivisione delle porte, vedere [condivisione porta Net. TCP](http://msdn.microsoft.com/en-us/f13692ee-a179-4439-ae72-50db9534eded).</span><span class="sxs-lookup"><span data-stu-id="402c2-137">For more information on port sharing, see [Net.TCP Port Sharing](http://msdn.microsoft.com/en-us/f13692ee-a179-4439-ae72-50db9534eded).</span></span> <span data-ttu-id="402c2-138">Per comprendere come configurare il servizio di condivisione delle porte, vedere [la configurazione del servizio di condivisione porta Net. TCP](http://msdn.microsoft.com/en-us/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).</span><span class="sxs-lookup"><span data-stu-id="402c2-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/en-us/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="402c2-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="402c2-139">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [<span data-ttu-id="402c2-140">Condivisione porta Net. TCP</span><span class="sxs-lookup"><span data-stu-id="402c2-140">Net.TCP Port Sharing</span></span>](http://msdn.microsoft.com/en-us/f13692ee-a179-4439-ae72-50db9534eded)  
 [<span data-ttu-id="402c2-141">Configurare il servizio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="402c2-141">Configuring the Net.TCP Port Sharing Service</span></span>](http://msdn.microsoft.com/en-us/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)
