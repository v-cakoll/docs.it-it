---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 1c40c5e4b4a24a3c1bbd6e096f12b7b044331c88
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252055"
---
# <a name="claimtyperequired"></a><span data-ttu-id="0db90-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="0db90-101">\<claimTypeRequired></span></span>
<span data-ttu-id="0db90-102">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="0db90-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
<span data-ttu-id="0db90-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0db90-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0db90-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="0db90-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="0db90-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="0db90-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="0db90-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> claimTypeRequired**</span><span class="sxs-lookup"><span data-stu-id="0db90-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0db90-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0db90-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0db90-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0db90-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0db90-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0db90-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0db90-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="0db90-110">Attributes</span></span>  
 <span data-ttu-id="0db90-111">Nessuna</span><span class="sxs-lookup"><span data-stu-id="0db90-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0db90-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0db90-112">Child Elements</span></span>  
  
|<span data-ttu-id="0db90-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="0db90-113">Element</span></span>|<span data-ttu-id="0db90-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0db90-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0db90-115">\<claimType></span><span class="sxs-lookup"><span data-stu-id="0db90-115">\<claimType></span></span>](claimtype.md)|<span data-ttu-id="0db90-116">Specifica una singola attestazione facoltativa o obbligatoria per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="0db90-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0db90-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0db90-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0db90-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="0db90-118">Element</span></span>|<span data-ttu-id="0db90-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0db90-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0db90-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="0db90-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="0db90-121">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="0db90-121">Specifies service-level identity settings.</span></span>|
