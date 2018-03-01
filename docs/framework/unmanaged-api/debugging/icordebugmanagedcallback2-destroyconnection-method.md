---
title: Metodo ICorDebugManagedCallback2::DestroyConnection
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
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a9d87f3c57e72c567be582ba2ac78589fa2e3357
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="dc6c3-102">Metodo ICorDebugManagedCallback2::DestroyConnection</span><span class="sxs-lookup"><span data-stu-id="dc6c3-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="dc6c3-103">Notifica al debugger che la connessione specificata è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="dc6c3-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc6c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc6c3-104">Syntax</span></span>  
  
```  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dc6c3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dc6c3-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="dc6c3-106">[in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo che contiene la connessione in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="dc6c3-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="dc6c3-107">[in] L'ID della connessione in cui è stato eliminato definitivamente.</span><span class="sxs-lookup"><span data-stu-id="dc6c3-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc6c3-108">Note</span><span class="sxs-lookup"><span data-stu-id="dc6c3-108">Remarks</span></span>  
 <span data-ttu-id="dc6c3-109">Oggetto `DestroyConnection` callback verrà generato quando un host chiama il metodo [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) nel [API di Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="dc6c3-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc6c3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc6c3-110">Requirements</span></span>  
 <span data-ttu-id="dc6c3-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc6c3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc6c3-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="dc6c3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc6c3-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc6c3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc6c3-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc6c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6c3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc6c3-115">See Also</span></span>  
 [<span data-ttu-id="dc6c3-116">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="dc6c3-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="dc6c3-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="dc6c3-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
