---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: eafaf253e27db632f17acfce4445a07d18b109aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778456"
---
# <a name="claimtyperequired"></a><span data-ttu-id="2b25e-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="2b25e-101">\<claimTypeRequired></span></span>
<span data-ttu-id="2b25e-102">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="2b25e-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="2b25e-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="2b25e-103">\<system.identityModel></span></span>  
<span data-ttu-id="2b25e-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="2b25e-104">\<identityConfiguration></span></span>  
<span data-ttu-id="2b25e-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="2b25e-105">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b25e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b25e-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b25e-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2b25e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2b25e-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2b25e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b25e-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="2b25e-109">Attributes</span></span>  
 <span data-ttu-id="2b25e-110">nessuno</span><span class="sxs-lookup"><span data-stu-id="2b25e-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2b25e-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2b25e-111">Child Elements</span></span>  
  
|<span data-ttu-id="2b25e-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b25e-112">Element</span></span>|<span data-ttu-id="2b25e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b25e-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b25e-114">\<claimType></span><span class="sxs-lookup"><span data-stu-id="2b25e-114">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="2b25e-115">Specifica una singola attestazione obbligatorio o facoltativa per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="2b25e-115">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b25e-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2b25e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="2b25e-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b25e-117">Element</span></span>|<span data-ttu-id="2b25e-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b25e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b25e-119">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="2b25e-119">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="2b25e-120">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="2b25e-120">Specifies service-level identity settings.</span></span>|
