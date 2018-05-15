---
title: '&lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: bbfe0d5d531cf61c01f95d0e82ce0f894031d6f3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="e3665-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="e3665-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="e3665-103">Contiene una raccolta di elementi di configurazione che specificano utente account per i processi che ospitano servizi Windows Communication Foundation (WCF) e viene concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="e3665-103">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="e3665-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="e3665-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3665-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3665-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3665-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e3665-106">Attributes and Elements</span></span>  
 <span data-ttu-id="e3665-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e3665-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3665-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="e3665-108">Attributes</span></span>  
 <span data-ttu-id="e3665-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e3665-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e3665-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e3665-110">Child Elements</span></span>  
  
|<span data-ttu-id="e3665-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="e3665-111">Attribute</span></span>|<span data-ttu-id="e3665-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3665-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="e3665-113">\<add></span><span class="sxs-lookup"><span data-stu-id="e3665-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="e3665-114">Aggiunge un account utente per i processi che ospitano servizi [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] e ai quali è concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="e3665-114">Adds a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3665-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e3665-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e3665-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3665-116">Element</span></span>|<span data-ttu-id="e3665-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3665-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3665-118">[\<NET. pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) oppure [ \<NET. TCP >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="e3665-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="e3665-119">Specifica impostazioni di configurazione per i servizi di condivisione Net Pipe o TCP.</span><span class="sxs-lookup"><span data-stu-id="e3665-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3665-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3665-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
