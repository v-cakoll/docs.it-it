---
title: Interfaccia IAppDomainBinding
ms.date: 03/30/2017
api_name:
- IAppDomainBinding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainBinding
helpviewer_keywords:
- IAppDomainBinding interface [.NET Framework hosting]
ms.assetid: 368881ab-c4ea-4731-bf22-c596aac7c66c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6761ff204d299bc2db84e2e80d988306125a110
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430821"
---
# <a name="iappdomainbinding-interface"></a><span data-ttu-id="89f66-102">Interfaccia IAppDomainBinding</span><span class="sxs-lookup"><span data-stu-id="89f66-102">IAppDomainBinding Interface</span></span>
<span data-ttu-id="89f66-103">Fornisce un metodo che viene chiamato da common language runtime (CLR) per notificare all'applicazione host che è stato creato un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="89f66-103">Provides a method that is called by the common language runtime (CLR) to notify the host application that an application domain has been created.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="89f66-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="89f66-104">Methods</span></span>  
  
|<span data-ttu-id="89f66-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="89f66-105">Method</span></span>|<span data-ttu-id="89f66-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89f66-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="89f66-107">Metodo OnAppDomain</span><span class="sxs-lookup"><span data-stu-id="89f66-107">OnAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-onappdomain-method.md)|<span data-ttu-id="89f66-108">Chiamato da common language runtime (CLR) per notificare all'host che è stato creato un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="89f66-108">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="89f66-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89f66-109">Requirements</span></span>  
 <span data-ttu-id="89f66-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89f66-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89f66-111">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="89f66-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89f66-112">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="89f66-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89f66-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89f66-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f66-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89f66-114">See Also</span></span>  
 [<span data-ttu-id="89f66-115">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="89f66-115">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
