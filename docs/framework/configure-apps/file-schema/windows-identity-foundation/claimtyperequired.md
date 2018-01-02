---
title: '&lt;claimTypeRequired&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 491277e39b29d7c3e0a0d69ec8745b2c6718a91e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="5d826-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="5d826-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="5d826-103">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="5d826-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="5d826-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="5d826-104">\<system.identityModel></span></span>  
<span data-ttu-id="5d826-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5d826-105">\<identityConfiguration></span></span>  
<span data-ttu-id="5d826-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="5d826-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d826-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d826-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d826-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5d826-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5d826-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5d826-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d826-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="5d826-110">Attributes</span></span>  
 <span data-ttu-id="5d826-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="5d826-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5d826-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5d826-112">Child Elements</span></span>  
  
|<span data-ttu-id="5d826-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d826-113">Element</span></span>|<span data-ttu-id="5d826-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d826-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d826-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="5d826-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="5d826-116">Specifica una singola attestazione obbligatorio o facoltativa per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="5d826-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d826-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5d826-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5d826-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d826-118">Element</span></span>|<span data-ttu-id="5d826-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d826-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d826-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5d826-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="5d826-121">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="5d826-121">Specifies service-level identity settings.</span></span>|
