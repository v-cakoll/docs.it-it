---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: a46e9129bd27319abb4d7519444568af622170fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252063"
---
# \<claimType>
<span data-ttu-id="906bb-101">Specifica una singola attestazione facoltativa o obbligatoria per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="906bb-101">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)\  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**  
  
## <a name="syntax"></a><span data-ttu-id="906bb-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="906bb-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="906bb-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="906bb-103">Attributes and Elements</span></span>  
 <span data-ttu-id="906bb-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="906bb-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="906bb-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="906bb-105">Attributes</span></span>  
  
|<span data-ttu-id="906bb-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="906bb-106">Attribute</span></span>|<span data-ttu-id="906bb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="906bb-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="906bb-108">type</span><span class="sxs-lookup"><span data-stu-id="906bb-108">type</span></span>|<span data-ttu-id="906bb-109">Tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="906bb-109">The claim type.</span></span> <span data-ttu-id="906bb-110">In genere un URI.</span><span class="sxs-lookup"><span data-stu-id="906bb-110">Typically a URI.</span></span> <span data-ttu-id="906bb-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="906bb-111">Required.</span></span>|  
|<span data-ttu-id="906bb-112">facoltativo</span><span class="sxs-lookup"><span data-stu-id="906bb-112">optional</span></span>|<span data-ttu-id="906bb-113">Valore booleano che specifica se il tipo di attestazione è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="906bb-113">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="906bb-114">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="906bb-114">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="906bb-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="906bb-115">Child Elements</span></span>  
 <span data-ttu-id="906bb-116">nessuno</span><span class="sxs-lookup"><span data-stu-id="906bb-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="906bb-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="906bb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="906bb-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="906bb-118">Element</span></span>|<span data-ttu-id="906bb-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="906bb-119">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequired>](claimtyperequired.md)|<span data-ttu-id="906bb-120">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="906bb-120">Specifies the set of required claims for incoming security tokens.</span></span>|
