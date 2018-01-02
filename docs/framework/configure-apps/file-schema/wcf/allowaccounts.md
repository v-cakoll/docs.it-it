---
title: '&lt;allowAccounts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a1716aa77808b2a9f8f3ca903dabf81b21b8f709
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="602c9-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="602c9-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="602c9-103">Contiene una raccolta di elementi di configurazione che specificano account utente per processi che ospitano servizi [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] e ai quali è concesso l'accesso in connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="602c9-103">Contains a collection of configuration elements that specify user accounts for processes that host [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="602c9-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="602c9-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="602c9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="602c9-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="602c9-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="602c9-106">Attributes and Elements</span></span>  
 <span data-ttu-id="602c9-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="602c9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="602c9-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="602c9-108">Attributes</span></span>  
 <span data-ttu-id="602c9-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="602c9-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="602c9-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="602c9-110">Child Elements</span></span>  
  
|<span data-ttu-id="602c9-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="602c9-111">Attribute</span></span>|<span data-ttu-id="602c9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="602c9-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="602c9-113">\<add></span><span class="sxs-lookup"><span data-stu-id="602c9-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="602c9-114">Aggiunge un account utente per i processi che ospitano servizi [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] e ai quali è concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="602c9-114">Adds a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="602c9-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="602c9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="602c9-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="602c9-116">Element</span></span>|<span data-ttu-id="602c9-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="602c9-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="602c9-118">[\<NET. pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) o [ \<NET. TCP >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="602c9-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="602c9-119">Specifica impostazioni di configurazione per i servizi di condivisione Net Pipe o TCP.</span><span class="sxs-lookup"><span data-stu-id="602c9-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="602c9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="602c9-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
