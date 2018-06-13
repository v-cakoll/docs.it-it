---
title: '&lt;claimTypeRequired&gt;'
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6fb600aac46b3ee5cb54fa904d35ac7b7ed90719
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754954"
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="fb0ae-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="fb0ae-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="fb0ae-103">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="fb0ae-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="fb0ae-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="fb0ae-104">\<system.identityModel></span></span>  
<span data-ttu-id="fb0ae-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="fb0ae-105">\<identityConfiguration></span></span>  
<span data-ttu-id="fb0ae-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="fb0ae-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb0ae-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb0ae-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb0ae-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fb0ae-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fb0ae-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fb0ae-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb0ae-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="fb0ae-110">Attributes</span></span>  
 <span data-ttu-id="fb0ae-111">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fb0ae-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fb0ae-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fb0ae-112">Child Elements</span></span>  
  
|<span data-ttu-id="fb0ae-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb0ae-113">Element</span></span>|<span data-ttu-id="fb0ae-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb0ae-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb0ae-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="fb0ae-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="fb0ae-116">Specifica una singola attestazione obbligatorio o facoltativa per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="fb0ae-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fb0ae-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fb0ae-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fb0ae-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb0ae-118">Element</span></span>|<span data-ttu-id="fb0ae-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb0ae-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb0ae-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="fb0ae-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="fb0ae-121">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="fb0ae-121">Specifies service-level identity settings.</span></span>|
