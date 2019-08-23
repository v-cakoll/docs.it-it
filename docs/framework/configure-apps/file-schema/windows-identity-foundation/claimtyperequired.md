---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 85f3954514fa8b532311b1fbfc34f32ebefa4099
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942820"
---
# <a name="claimtyperequired"></a><span data-ttu-id="f39fa-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="f39fa-101">\<claimTypeRequired></span></span>
<span data-ttu-id="f39fa-102">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="f39fa-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="f39fa-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f39fa-103">\<system.identityModel></span></span>  
<span data-ttu-id="f39fa-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f39fa-104">\<identityConfiguration></span></span>  
<span data-ttu-id="f39fa-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="f39fa-105">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f39fa-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f39fa-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f39fa-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f39fa-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f39fa-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f39fa-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f39fa-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="f39fa-109">Attributes</span></span>  
 <span data-ttu-id="f39fa-110">Nessuna</span><span class="sxs-lookup"><span data-stu-id="f39fa-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f39fa-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f39fa-111">Child Elements</span></span>  
  
|<span data-ttu-id="f39fa-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="f39fa-112">Element</span></span>|<span data-ttu-id="f39fa-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f39fa-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f39fa-114">\<claimType></span><span class="sxs-lookup"><span data-stu-id="f39fa-114">\<claimType></span></span>](claimtype.md)|<span data-ttu-id="f39fa-115">Specifica una singola attestazione facoltativa o obbligatoria per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="f39fa-115">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f39fa-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f39fa-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f39fa-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="f39fa-117">Element</span></span>|<span data-ttu-id="f39fa-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f39fa-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f39fa-119">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f39fa-119">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="f39fa-120">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="f39fa-120">Specifies service-level identity settings.</span></span>|
