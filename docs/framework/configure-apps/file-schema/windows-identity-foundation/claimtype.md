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
ms.openlocfilehash: c4ee8833578b082f25c427b13d77072d1954197f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="292a6-102">&lt;claimType&gt;</span><span class="sxs-lookup"><span data-stu-id="292a6-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="292a6-103">Specifica una singola attestazione obbligatorio o facoltativa per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="292a6-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="292a6-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="292a6-104">\<system.identityModel></span></span>  
<span data-ttu-id="292a6-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="292a6-105">\<identityConfiguration></span></span>  
<span data-ttu-id="292a6-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="292a6-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="292a6-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="292a6-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="292a6-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="292a6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="292a6-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="292a6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="292a6-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="292a6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="292a6-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="292a6-111">Attributes</span></span>  
  
|<span data-ttu-id="292a6-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="292a6-112">Attribute</span></span>|<span data-ttu-id="292a6-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="292a6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="292a6-114">tipo</span><span class="sxs-lookup"><span data-stu-id="292a6-114">type</span></span>|<span data-ttu-id="292a6-115">Tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="292a6-115">The claim type.</span></span> <span data-ttu-id="292a6-116">In genere un URI.</span><span class="sxs-lookup"><span data-stu-id="292a6-116">Typically a URI.</span></span> <span data-ttu-id="292a6-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="292a6-117">Required.</span></span>|  
|<span data-ttu-id="292a6-118">facoltativi</span><span class="sxs-lookup"><span data-stu-id="292a6-118">optional</span></span>|<span data-ttu-id="292a6-119">Valore booleano che specifica se il tipo di attestazione è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="292a6-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="292a6-120">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="292a6-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="292a6-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="292a6-121">Child Elements</span></span>  
 <span data-ttu-id="292a6-122">None</span><span class="sxs-lookup"><span data-stu-id="292a6-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="292a6-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="292a6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="292a6-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="292a6-124">Element</span></span>|<span data-ttu-id="292a6-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="292a6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="292a6-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="292a6-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="292a6-127">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="292a6-127">Specifies the set of required claims for incoming security tokens.</span></span>|
