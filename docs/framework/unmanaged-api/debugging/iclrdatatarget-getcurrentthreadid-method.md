---
title: Metodo ICLRDataTarget::GetCurrentThreadID
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc4ba4f87cd53e12baa0a7cf8b853db0e948201f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500387"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="3ff13-102">Metodo ICLRDataTarget::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="3ff13-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="3ff13-103">Ottiene l'identificatore del sistema operativo per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="3ff13-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ff13-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ff13-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ff13-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3ff13-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="3ff13-106">[out] Un puntatore all'identificatore del sistema operativo del thread corrente per il processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3ff13-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ff13-107">Note</span><span class="sxs-lookup"><span data-stu-id="3ff13-107">Remarks</span></span>  
 <span data-ttu-id="3ff13-108">Se nessun thread corrente per il processo di destinazione, il `GetCurrentThreadID` metodo potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="3ff13-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ff13-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ff13-109">Requirements</span></span>  
 <span data-ttu-id="3ff13-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ff13-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ff13-111">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="3ff13-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3ff13-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ff13-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ff13-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ff13-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff13-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ff13-114">See also</span></span>
- [<span data-ttu-id="3ff13-115">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="3ff13-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
