---
title: '&lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c1c4630e6191dbbe02688a4e4a9db9e18b8d36d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508418"
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="b758b-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="b758b-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="b758b-103">Contiene una raccolta di elementi di configurazione che specificano utente account per processi che ospitano servizi Windows Communication Foundation (WCF) e concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="b758b-103">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="b758b-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="b758b-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b758b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b758b-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b758b-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b758b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b758b-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b758b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b758b-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="b758b-108">Attributes</span></span>  
 <span data-ttu-id="b758b-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b758b-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b758b-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b758b-110">Child Elements</span></span>  
  
|<span data-ttu-id="b758b-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="b758b-111">Attribute</span></span>|<span data-ttu-id="b758b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b758b-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="b758b-113">\<add></span><span class="sxs-lookup"><span data-stu-id="b758b-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="b758b-114">Aggiunge un account utente per processi che ospitano servizi WCF e vengono concesso l'accesso al servizio di condivisione</span><span class="sxs-lookup"><span data-stu-id="b758b-114">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b758b-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b758b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b758b-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b758b-116">Element</span></span>|<span data-ttu-id="b758b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b758b-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b758b-118">[\<NET. pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) oppure [ \<NET. TCP >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="b758b-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="b758b-119">Specifica impostazioni di configurazione per i servizi di condivisione Net Pipe o TCP.</span><span class="sxs-lookup"><span data-stu-id="b758b-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b758b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b758b-120">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
