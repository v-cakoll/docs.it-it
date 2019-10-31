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
ms.openlocfilehash: f43ee6d9a3832fca1766ec27c9f02d1aab2f5b8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127765"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="28a4c-102">Metodo ICorConfiguration::SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="28a4c-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="28a4c-103">Imposta l'interfaccia di callback per la pianificazione di thread per le attività non di runtime che altrimenti verrebbero bloccate per un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="28a4c-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28a4c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28a4c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28a4c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="28a4c-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="28a4c-106">in Puntatore a un oggetto [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) che notifica all'host la sospensione dei thread per le attività non in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="28a4c-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28a4c-107">Note</span><span class="sxs-lookup"><span data-stu-id="28a4c-107">Remarks</span></span>  
 <span data-ttu-id="28a4c-108">L'host può scegliere all'interno del callback [IGCThreadControl:: ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) se ripianificare un thread.</span><span class="sxs-lookup"><span data-stu-id="28a4c-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28a4c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28a4c-109">Requirements</span></span>  
 <span data-ttu-id="28a4c-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28a4c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28a4c-111">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="28a4c-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28a4c-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="28a4c-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28a4c-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28a4c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a4c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28a4c-114">See also</span></span>

- [<span data-ttu-id="28a4c-115">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="28a4c-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
