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
ms.openlocfilehash: 9da3c0ee081b81411d13dfcf9c8557c6bd4d3448
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437307"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="2b4a8-102">Metodo ICorConfiguration::SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="2b4a8-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="2b4a8-103">Imposta l'interfaccia di callback per la pianificazione di thread per l'attività non è una fase di esecuzione che altrimenti sarebbero bloccati per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="2b4a8-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b4a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b4a8-104">Syntax</span></span>  
  
```  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b4a8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2b4a8-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="2b4a8-106">[in] Un puntatore a un [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) oggetto notifica all'host la sospensione di thread per l'attività non di runtime.</span><span class="sxs-lookup"><span data-stu-id="2b4a8-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b4a8-107">Note</span><span class="sxs-lookup"><span data-stu-id="2b4a8-107">Remarks</span></span>  
 <span data-ttu-id="2b4a8-108">L'host può scegliere all'interno di [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback se ripianificare un thread.</span><span class="sxs-lookup"><span data-stu-id="2b4a8-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b4a8-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2b4a8-109">Requirements</span></span>  
 <span data-ttu-id="2b4a8-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b4a8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b4a8-111">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="2b4a8-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b4a8-112">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2b4a8-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b4a8-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b4a8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b4a8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b4a8-114">See Also</span></span>  
 [<span data-ttu-id="2b4a8-115">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="2b4a8-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
