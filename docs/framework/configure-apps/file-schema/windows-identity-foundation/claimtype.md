---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 4253aec961b812b6893ee201861d2ab38048032a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942873"
---
# <a name="claimtype"></a><span data-ttu-id="9671e-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="9671e-101">\<claimType></span></span>
<span data-ttu-id="9671e-102">Specifica una singola attestazione facoltativa o obbligatoria per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="9671e-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="9671e-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="9671e-103">\<system.identityModel></span></span>  
<span data-ttu-id="9671e-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="9671e-104">\<identityConfiguration></span></span>  
<span data-ttu-id="9671e-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="9671e-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="9671e-106">\<claimType></span><span class="sxs-lookup"><span data-stu-id="9671e-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9671e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9671e-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9671e-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9671e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9671e-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9671e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9671e-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="9671e-110">Attributes</span></span>  
  
|<span data-ttu-id="9671e-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="9671e-111">Attribute</span></span>|<span data-ttu-id="9671e-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="9671e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9671e-113">type</span><span class="sxs-lookup"><span data-stu-id="9671e-113">type</span></span>|<span data-ttu-id="9671e-114">Tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="9671e-114">The claim type.</span></span> <span data-ttu-id="9671e-115">In genere un URI.</span><span class="sxs-lookup"><span data-stu-id="9671e-115">Typically a URI.</span></span> <span data-ttu-id="9671e-116">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="9671e-116">Required.</span></span>|  
|<span data-ttu-id="9671e-117">facoltativi</span><span class="sxs-lookup"><span data-stu-id="9671e-117">optional</span></span>|<span data-ttu-id="9671e-118">Valore booleano che specifica se il tipo di attestazione è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9671e-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="9671e-119">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9671e-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9671e-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9671e-120">Child Elements</span></span>  
 <span data-ttu-id="9671e-121">Nessuna</span><span class="sxs-lookup"><span data-stu-id="9671e-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9671e-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9671e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9671e-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="9671e-123">Element</span></span>|<span data-ttu-id="9671e-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="9671e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9671e-125">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="9671e-125">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="9671e-126">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="9671e-126">Specifies the set of required claims for incoming security tokens.</span></span>|
