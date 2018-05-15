---
title: '&lt;ClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 94f8586a9ca63b8c1f1128cdda4a74ccfe0f5416
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="6fc34-102">&lt;ClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="6fc34-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="6fc34-103">Specifica una singola attestazione obbligatorio o facoltativa per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="6fc34-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="6fc34-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6fc34-104">\<system.identityModel></span></span>  
<span data-ttu-id="6fc34-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6fc34-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6fc34-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="6fc34-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="6fc34-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="6fc34-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fc34-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fc34-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6fc34-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6fc34-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6fc34-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6fc34-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6fc34-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="6fc34-111">Attributes</span></span>  
  
|<span data-ttu-id="6fc34-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="6fc34-112">Attribute</span></span>|<span data-ttu-id="6fc34-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6fc34-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6fc34-114">tipo</span><span class="sxs-lookup"><span data-stu-id="6fc34-114">type</span></span>|<span data-ttu-id="6fc34-115">Tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="6fc34-115">The claim type.</span></span> <span data-ttu-id="6fc34-116">In genere un URI.</span><span class="sxs-lookup"><span data-stu-id="6fc34-116">Typically a URI.</span></span> <span data-ttu-id="6fc34-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6fc34-117">Required.</span></span>|  
|<span data-ttu-id="6fc34-118">facoltativi</span><span class="sxs-lookup"><span data-stu-id="6fc34-118">optional</span></span>|<span data-ttu-id="6fc34-119">Valore booleano che specifica se il tipo di attestazione è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6fc34-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="6fc34-120">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6fc34-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6fc34-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6fc34-121">Child Elements</span></span>  
 <span data-ttu-id="6fc34-122">Nessuno</span><span class="sxs-lookup"><span data-stu-id="6fc34-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6fc34-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6fc34-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6fc34-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="6fc34-124">Element</span></span>|<span data-ttu-id="6fc34-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6fc34-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6fc34-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="6fc34-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="6fc34-127">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="6fc34-127">Specifies the set of required claims for incoming security tokens.</span></span>|
