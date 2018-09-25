---
title: '&lt;claimTypeRequired&gt;'
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: df4494de6b76943849db2bedef8f43ad894b6bd1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084228"
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="332b3-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="332b3-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="332b3-103">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="332b3-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="332b3-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="332b3-104">\<system.identityModel></span></span>  
<span data-ttu-id="332b3-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="332b3-105">\<identityConfiguration></span></span>  
<span data-ttu-id="332b3-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="332b3-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="332b3-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="332b3-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="332b3-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="332b3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="332b3-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="332b3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="332b3-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="332b3-110">Attributes</span></span>  
 <span data-ttu-id="332b3-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="332b3-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="332b3-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="332b3-112">Child Elements</span></span>  
  
|<span data-ttu-id="332b3-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="332b3-113">Element</span></span>|<span data-ttu-id="332b3-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="332b3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="332b3-115">\<tipo di attestazione ></span><span class="sxs-lookup"><span data-stu-id="332b3-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="332b3-116">Specifica una singola attestazione obbligatorio o facoltativa per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="332b3-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="332b3-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="332b3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="332b3-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="332b3-118">Element</span></span>|<span data-ttu-id="332b3-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="332b3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="332b3-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="332b3-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="332b3-121">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="332b3-121">Specifies service-level identity settings.</span></span>|
