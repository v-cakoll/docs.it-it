---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 6bc185572528d4229ee53f1421eaa5bf27b053e6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267235"
---
# <a name="claimtype"></a><span data-ttu-id="48cf7-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="48cf7-101">\<claimType></span></span>
<span data-ttu-id="48cf7-102">Specifica una singola attestazione obbligatorio o facoltativa per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="48cf7-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="48cf7-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="48cf7-103">\<system.identityModel></span></span>  
<span data-ttu-id="48cf7-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="48cf7-104">\<identityConfiguration></span></span>  
<span data-ttu-id="48cf7-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="48cf7-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="48cf7-106">\<claimType></span><span class="sxs-lookup"><span data-stu-id="48cf7-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48cf7-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48cf7-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48cf7-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="48cf7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="48cf7-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="48cf7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48cf7-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="48cf7-110">Attributes</span></span>  
  
|<span data-ttu-id="48cf7-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="48cf7-111">Attribute</span></span>|<span data-ttu-id="48cf7-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48cf7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="48cf7-113">tipo</span><span class="sxs-lookup"><span data-stu-id="48cf7-113">type</span></span>|<span data-ttu-id="48cf7-114">Tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="48cf7-114">The claim type.</span></span> <span data-ttu-id="48cf7-115">In genere un URI.</span><span class="sxs-lookup"><span data-stu-id="48cf7-115">Typically a URI.</span></span> <span data-ttu-id="48cf7-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="48cf7-116">Required.</span></span>|  
|<span data-ttu-id="48cf7-117">facoltativi</span><span class="sxs-lookup"><span data-stu-id="48cf7-117">optional</span></span>|<span data-ttu-id="48cf7-118">Valore booleano che specifica se il tipo di attestazione è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="48cf7-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="48cf7-119">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="48cf7-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48cf7-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="48cf7-120">Child Elements</span></span>  
 <span data-ttu-id="48cf7-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="48cf7-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48cf7-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="48cf7-122">Parent Elements</span></span>  
  
|<span data-ttu-id="48cf7-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="48cf7-123">Element</span></span>|<span data-ttu-id="48cf7-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48cf7-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48cf7-125">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="48cf7-125">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="48cf7-126">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="48cf7-126">Specifies the set of required claims for incoming security tokens.</span></span>|
