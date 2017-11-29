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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8e1cf4c4428814361a56b5fd06dcce9e1512c836
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="39ca2-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="39ca2-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="39ca2-103">Contiene una raccolta di elementi di configurazione che specificano account utente per processi che ospitano servizi [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] e ai quali è concesso l'accesso in connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="39ca2-103">Contains a collection of configuration elements that specify user accounts for processes that host [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="39ca2-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="39ca2-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39ca2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39ca2-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39ca2-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="39ca2-106">Attributes and Elements</span></span>  
 <span data-ttu-id="39ca2-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="39ca2-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39ca2-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="39ca2-108">Attributes</span></span>  
 <span data-ttu-id="39ca2-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="39ca2-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39ca2-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="39ca2-110">Child Elements</span></span>  
  
|<span data-ttu-id="39ca2-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="39ca2-111">Attribute</span></span>|<span data-ttu-id="39ca2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39ca2-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="39ca2-113">\<add></span><span class="sxs-lookup"><span data-stu-id="39ca2-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="39ca2-114">Aggiunge un account utente per i processi che ospitano servizi [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] e ai quali è concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="39ca2-114">Adds a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39ca2-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="39ca2-115">Parent Elements</span></span>  
  
|<span data-ttu-id="39ca2-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="39ca2-116">Element</span></span>|<span data-ttu-id="39ca2-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39ca2-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39ca2-118">[\<NET. pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) o [ \<NET. TCP >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="39ca2-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="39ca2-119">Specifica impostazioni di configurazione per i servizi di condivisione Net Pipe o TCP.</span><span class="sxs-lookup"><span data-stu-id="39ca2-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39ca2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39ca2-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
