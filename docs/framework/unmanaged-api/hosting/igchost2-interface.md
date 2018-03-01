---
title: Interfaccia IGCHost2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a616e724d6fb26734fcda48d6a9b39605e0284a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="igchost2-interface"></a><span data-ttu-id="7ded1-102">Interfaccia IGCHost2</span><span class="sxs-lookup"><span data-stu-id="7ded1-102">IGCHost2 Interface</span></span>
<span data-ttu-id="7ded1-103">Fornisce metodi per ottenere informazioni sul sistema di garbage collection e per controllare alcuni aspetti dell'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="7ded1-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ded1-104">Per un nuovo sviluppo, è consigliabile utilizzare il [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) invece di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7ded1-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ded1-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7ded1-105">Methods</span></span>  
  
|<span data-ttu-id="7ded1-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="7ded1-106">Method</span></span>|<span data-ttu-id="7ded1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ded1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ded1-108">Metodo SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="7ded1-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="7ded1-109">Imposta le dimensioni del segmento e la dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="7ded1-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="7ded1-110">Consente di generazione 0 e dei segmenti maggiori `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="7ded1-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ded1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ded1-111">Requirements</span></span>  
 <span data-ttu-id="7ded1-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ded1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ded1-113">**Intestazione:** GCHost. idl, GCHost. H</span><span class="sxs-lookup"><span data-stu-id="7ded1-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="7ded1-114">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7ded1-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ded1-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ded1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ded1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ded1-116">See Also</span></span>  
 [<span data-ttu-id="7ded1-117">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="7ded1-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="7ded1-118">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="7ded1-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="7ded1-119">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="7ded1-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
