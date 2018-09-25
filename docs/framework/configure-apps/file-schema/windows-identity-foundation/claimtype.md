---
title: '&lt;Tipo di attestazione&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 805377565b6e835fd9ffba915a003bc56529a3b6
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084215"
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="c38f8-102">&lt;Tipo di attestazione&gt;</span><span class="sxs-lookup"><span data-stu-id="c38f8-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="c38f8-103">Specifica una singola attestazione obbligatorio o facoltativa per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="c38f8-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="c38f8-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c38f8-104">\<system.identityModel></span></span>  
<span data-ttu-id="c38f8-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c38f8-105">\<identityConfiguration></span></span>  
<span data-ttu-id="c38f8-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="c38f8-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="c38f8-107">\<tipo di attestazione ></span><span class="sxs-lookup"><span data-stu-id="c38f8-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c38f8-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c38f8-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c38f8-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c38f8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c38f8-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c38f8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c38f8-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="c38f8-111">Attributes</span></span>  
  
|<span data-ttu-id="c38f8-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="c38f8-112">Attribute</span></span>|<span data-ttu-id="c38f8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c38f8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c38f8-114">tipo</span><span class="sxs-lookup"><span data-stu-id="c38f8-114">type</span></span>|<span data-ttu-id="c38f8-115">Tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="c38f8-115">The claim type.</span></span> <span data-ttu-id="c38f8-116">In genere un URI.</span><span class="sxs-lookup"><span data-stu-id="c38f8-116">Typically a URI.</span></span> <span data-ttu-id="c38f8-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c38f8-117">Required.</span></span>|  
|<span data-ttu-id="c38f8-118">facoltativi</span><span class="sxs-lookup"><span data-stu-id="c38f8-118">optional</span></span>|<span data-ttu-id="c38f8-119">Valore booleano che specifica se il tipo di attestazione è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c38f8-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="c38f8-120">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c38f8-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c38f8-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c38f8-121">Child Elements</span></span>  
 <span data-ttu-id="c38f8-122">nessuno</span><span class="sxs-lookup"><span data-stu-id="c38f8-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c38f8-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c38f8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c38f8-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c38f8-124">Element</span></span>|<span data-ttu-id="c38f8-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c38f8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c38f8-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="c38f8-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="c38f8-127">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="c38f8-127">Specifies the set of required claims for incoming security tokens.</span></span>|
