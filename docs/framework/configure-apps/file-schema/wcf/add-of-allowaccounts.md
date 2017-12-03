---
title: '&lt;add&gt; di &lt;allowAccounts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 09ab06bb94249e79743335da1a360f6b668b1d86
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltallowaccountsgt"></a><span data-ttu-id="f7880-102">&lt;add&gt; di &lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="f7880-102">&lt;add&gt; of &lt;allowAccounts&gt;</span></span>
<span data-ttu-id="f7880-103">Specifica un account utente per processi che ospitano servizi [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] e ai quali è concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="f7880-103">Specifies a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="f7880-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="f7880-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7880-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7880-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7880-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f7880-106">Attributes and Elements</span></span>  
 <span data-ttu-id="f7880-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f7880-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7880-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="f7880-108">Attributes</span></span>  
  
|<span data-ttu-id="f7880-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="f7880-109">Attribute</span></span>|<span data-ttu-id="f7880-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7880-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7880-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="f7880-111">securityIdentifier</span></span>|<span data-ttu-id="f7880-112">Stringa che specifica un identificatore univoco usato per identificare un account utente.</span><span class="sxs-lookup"><span data-stu-id="f7880-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="f7880-113">I valori predefiniti sono LocalSystem, Administrators, NS, LS e IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="f7880-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7880-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f7880-114">Child Elements</span></span>  
 <span data-ttu-id="f7880-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f7880-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7880-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f7880-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f7880-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7880-117">Element</span></span>|<span data-ttu-id="f7880-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7880-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7880-119">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="f7880-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="f7880-120">Raccolta di elementi di configurazione che contiene un attributo `securityIdentifier` per specificare account utente per processi che ospitano servizi [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] e ai quali è concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="f7880-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f7880-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="f7880-121">Example</span></span>  
 <span data-ttu-id="f7880-122">Nell'esempio di configurazione seguente i cinque identificatori predefiniti per gli account utente vengono aggiunti a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="f7880-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
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
```  
  
## <a name="see-also"></a><span data-ttu-id="f7880-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7880-123">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
