---
title: Metodo ICorConfiguration::SetGCThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b50c87efeb8ad2311a75886da677a9dc901bca1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763230"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="9369d-102">Metodo ICorConfiguration::SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="9369d-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="9369d-103">Imposta l'interfaccia di callback per la pianificazione dei thread per le attività non di runtime che verrebbe bloccate in caso contrario, per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="9369d-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9369d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9369d-104">Syntax</span></span>  
  
```  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9369d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9369d-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="9369d-106">[in] Un puntatore a un [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) oggetto che invia una notifica all'host la sospensione di thread per le attività non di runtime.</span><span class="sxs-lookup"><span data-stu-id="9369d-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9369d-107">Note</span><span class="sxs-lookup"><span data-stu-id="9369d-107">Remarks</span></span>  
 <span data-ttu-id="9369d-108">L'host può scegliere all'interno di [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback se si desidera modificare la pianificazione di un thread.</span><span class="sxs-lookup"><span data-stu-id="9369d-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9369d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9369d-109">Requirements</span></span>  
 <span data-ttu-id="9369d-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9369d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9369d-111">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9369d-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9369d-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9369d-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9369d-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9369d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9369d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9369d-114">See also</span></span>

- [<span data-ttu-id="9369d-115">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="9369d-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
