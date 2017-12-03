---
title: '&lt;NET. pipe&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 918ee745e12a339b71f228f3f79b366335d7824d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltnetpipegt"></a><span data-ttu-id="8b4a0-102">&lt;NET. pipe&gt;</span><span class="sxs-lookup"><span data-stu-id="8b4a0-102">&lt;net.pipe&gt;</span></span>
<span data-ttu-id="8b4a0-103">Specifica impostazioni di configurazione per Named Pipe Activation Service, che gestisce la durata della connessione named pipe, nonché le richieste di attivazione che arrivano sulle named pipe.</span><span class="sxs-lookup"><span data-stu-id="8b4a0-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
 <span data-ttu-id="8b4a0-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="8b4a0-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="8b4a0-105">\<NET. pipe ></span><span class="sxs-lookup"><span data-stu-id="8b4a0-105">\<net.pipe></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b4a0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b4a0-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.pipe maxPendingAccepts="Integer"  
                    maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan">  
          <allowAccounts>  
             // LocalSystem account  
             <add securityIdentifier="S-1-5-18"/>  
             // LocalService account  
             <add securityIdentifier="S-1-5-19"/>  
             // Administrators account  
             <add securityIdentifier="S-1-5-20"/>  
             // Network Service account  
             <add securityIdentifier="S-1-5-32-544" />  
             // IIS_IUSRS account (Vista only)  
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.pipe>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="8b4a0-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="8b4a0-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b4a0-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8b4a0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8b4a0-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8b4a0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b4a0-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="8b4a0-110">Attributes</span></span>  
  
|<span data-ttu-id="8b4a0-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="8b4a0-111">Attribute</span></span>|<span data-ttu-id="8b4a0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b4a0-112">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="8b4a0-113">Numero intero che specifica il massimo di thread di accettazione contemporaneamente in attesa sull'endpoint di ascolto per il servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="8b4a0-113">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="8b4a0-114">Il valore predefinito è 2.</span><span class="sxs-lookup"><span data-stu-id="8b4a0-114">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="8b4a0-115">Numero intero che specifica il numero massimo di connessioni che possono rimanere in attesa di invio.</span><span class="sxs-lookup"><span data-stu-id="8b4a0-115">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="8b4a0-116">Il valore predefinito è 100.</span><span class="sxs-lookup"><span data-stu-id="8b4a0-116">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="8b4a0-117">`TimeSpan` che specifica il timeout per la lettura dei dati sui frame e per l'esecuzione dell'invio della connessione dalle connessioni sottostanti.</span><span class="sxs-lookup"><span data-stu-id="8b4a0-117">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="8b4a0-118">L'impostazione predefinita è "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="8b4a0-118">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b4a0-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8b4a0-119">Child Elements</span></span>  
  
|<span data-ttu-id="8b4a0-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="8b4a0-120">Element</span></span>|<span data-ttu-id="8b4a0-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b4a0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b4a0-122">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="8b4a0-122">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="8b4a0-123">Raccolta di elementi di configurazione che contiene un attributo `securityIdentifier` per specificare account utente per processi che ospitano servizi [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] e ai quali è concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="8b4a0-123">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8b4a0-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8b4a0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8b4a0-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="8b4a0-125">Element</span></span>|<span data-ttu-id="8b4a0-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b4a0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b4a0-127">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="8b4a0-127">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="8b4a0-128">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="8b4a0-128">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b4a0-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b4a0-129">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
