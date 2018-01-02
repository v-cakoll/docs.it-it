---
title: '&lt;claimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ae572ff3a8a2335a4259bdce2af5f6922fb0596f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="699e5-102">&lt;claimType&gt;</span><span class="sxs-lookup"><span data-stu-id="699e5-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="699e5-103">Specifica una singola attestazione obbligatorio o facoltativa per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="699e5-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="699e5-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="699e5-104">\<system.identityModel></span></span>  
<span data-ttu-id="699e5-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="699e5-105">\<identityConfiguration></span></span>  
<span data-ttu-id="699e5-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="699e5-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="699e5-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="699e5-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="699e5-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="699e5-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="699e5-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="699e5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="699e5-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="699e5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="699e5-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="699e5-111">Attributes</span></span>  
  
|<span data-ttu-id="699e5-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="699e5-112">Attribute</span></span>|<span data-ttu-id="699e5-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="699e5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="699e5-114">tipo</span><span class="sxs-lookup"><span data-stu-id="699e5-114">type</span></span>|<span data-ttu-id="699e5-115">Tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="699e5-115">The claim type.</span></span> <span data-ttu-id="699e5-116">In genere un URI.</span><span class="sxs-lookup"><span data-stu-id="699e5-116">Typically a URI.</span></span> <span data-ttu-id="699e5-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="699e5-117">Required.</span></span>|  
|<span data-ttu-id="699e5-118">facoltativi</span><span class="sxs-lookup"><span data-stu-id="699e5-118">optional</span></span>|<span data-ttu-id="699e5-119">Valore booleano che specifica se il tipo di attestazione è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="699e5-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="699e5-120">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="699e5-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="699e5-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="699e5-121">Child Elements</span></span>  
 <span data-ttu-id="699e5-122">None</span><span class="sxs-lookup"><span data-stu-id="699e5-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="699e5-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="699e5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="699e5-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="699e5-124">Element</span></span>|<span data-ttu-id="699e5-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="699e5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="699e5-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="699e5-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="699e5-127">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="699e5-127">Specifies the set of required claims for incoming security tokens.</span></span>|
