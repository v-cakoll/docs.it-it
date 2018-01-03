---
title: Metodo ICorDebugController::EnumerateThreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.EnumerateThreads
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61d96aa6c8ae4a50c3afbcd84033244208e2444d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="2263e-102">Metodo ICorDebugController::EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="2263e-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="2263e-103">Ottiene un enumeratore per i thread gestiti attivi nel processo.</span><span class="sxs-lookup"><span data-stu-id="2263e-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2263e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2263e-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2263e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2263e-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="2263e-106">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugThreadEnum" che rappresenta un enumeratore per tutti i thread gestiti attivi nel processo.</span><span class="sxs-lookup"><span data-stu-id="2263e-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2263e-107">Note</span><span class="sxs-lookup"><span data-stu-id="2263e-107">Remarks</span></span>  
 <span data-ttu-id="2263e-108">Un thread viene considerato attivo dopo il [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback viene inviato e prima di [:: ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback sia stato inviato .</span><span class="sxs-lookup"><span data-stu-id="2263e-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="2263e-109">Un thread gestito può non avere necessariamente frame gestiti nel relativo stack.</span><span class="sxs-lookup"><span data-stu-id="2263e-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="2263e-110">I thread possono essere enumerati anche prima che il [ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="2263e-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="2263e-111">L'enumerazione naturalmente sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="2263e-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2263e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2263e-112">Requirements</span></span>  
 <span data-ttu-id="2263e-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2263e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2263e-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="2263e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2263e-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2263e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2263e-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2263e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2263e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2263e-117">See Also</span></span>  
 
