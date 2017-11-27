---
title: '&lt;claimTypeRequired&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 89d42cba78eb9758d8b3491fd1bd3b25ef168f9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="cca3f-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="cca3f-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="cca3f-103">Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="cca3f-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="cca3f-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="cca3f-104">\<system.identityModel></span></span>  
<span data-ttu-id="cca3f-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="cca3f-105">\<identityConfiguration></span></span>  
<span data-ttu-id="cca3f-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="cca3f-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cca3f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cca3f-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cca3f-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cca3f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cca3f-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cca3f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cca3f-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="cca3f-110">Attributes</span></span>  
 <span data-ttu-id="cca3f-111">Nessuna</span><span class="sxs-lookup"><span data-stu-id="cca3f-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cca3f-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cca3f-112">Child Elements</span></span>  
  
|<span data-ttu-id="cca3f-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="cca3f-113">Element</span></span>|<span data-ttu-id="cca3f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cca3f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cca3f-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="cca3f-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="cca3f-116">Specifica una singola attestazione obbligatorio o facoltativa per i token di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="cca3f-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cca3f-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cca3f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cca3f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="cca3f-118">Element</span></span>|<span data-ttu-id="cca3f-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cca3f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cca3f-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="cca3f-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="cca3f-121">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="cca3f-121">Specifies service-level identity settings.</span></span>|
