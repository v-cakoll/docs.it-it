---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: f9def3004b116afdc629de136cdfe0b0eb6e75c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102622"
---
# <a name="allowaccounts"></a><span data-ttu-id="31154-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="31154-101">\<allowAccounts></span></span>
<span data-ttu-id="31154-102">Contiene una raccolta di elementi di configurazione che specificano utente account per processi che ospitano servizi Windows Communication Foundation (WCF) e concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="31154-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="31154-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="31154-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31154-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31154-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31154-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="31154-105">Attributes and Elements</span></span>  
 <span data-ttu-id="31154-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="31154-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31154-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="31154-107">Attributes</span></span>  
 <span data-ttu-id="31154-108">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="31154-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="31154-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="31154-109">Child Elements</span></span>  
  
|<span data-ttu-id="31154-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="31154-110">Attribute</span></span>|<span data-ttu-id="31154-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31154-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="31154-112">\<add></span><span class="sxs-lookup"><span data-stu-id="31154-112">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="31154-113">Aggiunge un account utente per processi che ospitano servizi WCF e vengono concesso l'accesso al servizio di condivisione</span><span class="sxs-lookup"><span data-stu-id="31154-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="31154-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="31154-114">Parent Elements</span></span>  
  
|<span data-ttu-id="31154-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="31154-115">Element</span></span>|<span data-ttu-id="31154-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31154-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31154-117">[\<NET. pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) oppure [ \<NET. TCP >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="31154-117">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="31154-118">Specifica impostazioni di configurazione per i servizi di condivisione Net Pipe o TCP.</span><span class="sxs-lookup"><span data-stu-id="31154-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31154-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31154-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
