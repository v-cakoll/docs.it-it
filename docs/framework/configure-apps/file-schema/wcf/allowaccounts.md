---
title: '&lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 61310d530cfec2862fb64155777cd0e88132f748
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145939"
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="cfb2e-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="cfb2e-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="cfb2e-103">Contiene una raccolta di elementi di configurazione che specificano utente account per processi che ospitano servizi Windows Communication Foundation (WCF) e concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="cfb2e-103">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="cfb2e-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="cfb2e-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfb2e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfb2e-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfb2e-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cfb2e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="cfb2e-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cfb2e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfb2e-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="cfb2e-108">Attributes</span></span>  
 <span data-ttu-id="cfb2e-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cfb2e-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cfb2e-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cfb2e-110">Child Elements</span></span>  
  
|<span data-ttu-id="cfb2e-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="cfb2e-111">Attribute</span></span>|<span data-ttu-id="cfb2e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfb2e-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="cfb2e-113">\<add></span><span class="sxs-lookup"><span data-stu-id="cfb2e-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="cfb2e-114">Aggiunge un account utente per processi che ospitano servizi WCF e vengono concesso l'accesso al servizio di condivisione</span><span class="sxs-lookup"><span data-stu-id="cfb2e-114">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cfb2e-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cfb2e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="cfb2e-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfb2e-116">Element</span></span>|<span data-ttu-id="cfb2e-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfb2e-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cfb2e-118">[\<NET. pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) oppure [ \<NET. TCP >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="cfb2e-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="cfb2e-119">Specifica impostazioni di configurazione per i servizi di condivisione Net Pipe o TCP.</span><span class="sxs-lookup"><span data-stu-id="cfb2e-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cfb2e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfb2e-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
