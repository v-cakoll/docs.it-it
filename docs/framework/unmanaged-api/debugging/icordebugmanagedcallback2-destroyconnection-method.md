---
title: Metodo ICorDebugManagedCallback2::DestroyConnection
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35ae3a9761798ed9ea42b984f2c6c2cad4e42777
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704102"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="220c6-102">Metodo ICorDebugManagedCallback2::DestroyConnection</span><span class="sxs-lookup"><span data-stu-id="220c6-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="220c6-103">Notifica al debugger che è stata terminata la connessione specificata.</span><span class="sxs-lookup"><span data-stu-id="220c6-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="220c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="220c6-104">Syntax</span></span>  
  
```  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="220c6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="220c6-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="220c6-106">[in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo che contiene la connessione che è stato eliminato definitivamente.</span><span class="sxs-lookup"><span data-stu-id="220c6-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="220c6-107">[in] L'ID della connessione in cui è stato eliminato definitivamente.</span><span class="sxs-lookup"><span data-stu-id="220c6-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="220c6-108">Note</span><span class="sxs-lookup"><span data-stu-id="220c6-108">Remarks</span></span>  
 <span data-ttu-id="220c6-109">Oggetto `DestroyConnection` callback verrà generato quando un host chiama [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) nel [API Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="220c6-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="220c6-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="220c6-110">Requirements</span></span>  
 <span data-ttu-id="220c6-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="220c6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="220c6-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="220c6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="220c6-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="220c6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="220c6-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="220c6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="220c6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="220c6-115">See also</span></span>

- [<span data-ttu-id="220c6-116">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="220c6-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="220c6-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="220c6-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
