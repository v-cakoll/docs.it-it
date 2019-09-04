---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: a46e9129bd27319abb4d7519444568af622170fc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252063"
---
# <a name="claimtype"></a><span data-ttu-id="76815-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="76815-101">\<claimType></span></span>
<span data-ttu-id="76815-102">Specifica una singola attestazione facoltativa o obbligatoria per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="76815-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
<span data-ttu-id="76815-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="76815-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="76815-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="76815-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="76815-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="76815-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="76815-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> claimTypeRequired**](claimtyperequired.md)</span><span class="sxs-lookup"><span data-stu-id="76815-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)</span></span>\  
<span data-ttu-id="76815-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> claimType**</span><span class="sxs-lookup"><span data-stu-id="76815-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76815-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76815-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76815-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="76815-109">Attributes and Elements</span></span>  
 <span data-ttu-id="76815-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="76815-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76815-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="76815-111">Attributes</span></span>  
  
|<span data-ttu-id="76815-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="76815-112">Attribute</span></span>|<span data-ttu-id="76815-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="76815-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76815-114">type</span><span class="sxs-lookup"><span data-stu-id="76815-114">type</span></span>|<span data-ttu-id="76815-115">Tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="76815-115">The claim type.</span></span> <span data-ttu-id="76815-116">In genere un URI.</span><span class="sxs-lookup"><span data-stu-id="76815-116">Typically a URI.</span></span> <span data-ttu-id="76815-117">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="76815-117">Required.</span></span>|  
|<span data-ttu-id="76815-118">facoltativi</span><span class="sxs-lookup"><span data-stu-id="76815-118">optional</span></span>|<span data-ttu-id="76815-119">Valore booleano che specifica se il tipo di attestazione è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="76815-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="76815-120">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="76815-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76815-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="76815-121">Child Elements</span></span>  
 <span data-ttu-id="76815-122">Nessuna</span><span class="sxs-lookup"><span data-stu-id="76815-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76815-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="76815-123">Parent Elements</span></span>  
  
|<span data-ttu-id="76815-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="76815-124">Element</span></span>|<span data-ttu-id="76815-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76815-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76815-126">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="76815-126">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="76815-127">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="76815-127">Specifies the set of required claims for incoming security tokens.</span></span>|
