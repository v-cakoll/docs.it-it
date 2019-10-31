---
title: Metodo ICorDebugManagedCallback2::CreateConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.CreateConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type:
- apiref
ms.openlocfilehash: d83ad530c8a61c2bfc38fb46ad2a33ef8d5077d3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130584"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="fc1ed-102">Metodo ICorDebugManagedCallback2::CreateConnection</span><span class="sxs-lookup"><span data-stu-id="fc1ed-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="fc1ed-103">Notifica al debugger che è stata creata una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="fc1ed-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc1ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc1ed-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc1ed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc1ed-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="fc1ed-106">in Puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo in cui è stata creata la connessione</span><span class="sxs-lookup"><span data-stu-id="fc1ed-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="fc1ed-107">in ID della nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="fc1ed-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="fc1ed-108">in Puntatore al nome della nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="fc1ed-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc1ed-109">Note</span><span class="sxs-lookup"><span data-stu-id="fc1ed-109">Remarks</span></span>  
 <span data-ttu-id="fc1ed-110">Un callback `CreateConnection` verrà attivato in uno dei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="fc1ed-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="fc1ed-111">Quando un debugger si connette a un processo che contiene connessioni.</span><span class="sxs-lookup"><span data-stu-id="fc1ed-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="fc1ed-112">In questo caso, il runtime genererà e invierà un evento `CreateConnection` e un evento [ICorDebugManagedCallback2:: ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) per ogni connessione nel processo.</span><span class="sxs-lookup"><span data-stu-id="fc1ed-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
- <span data-ttu-id="fc1ed-113">Quando un host chiama [ICLRDebugManager:: BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) nell' [API di hosting](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="fc1ed-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc1ed-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc1ed-114">Requirements</span></span>  
 <span data-ttu-id="fc1ed-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc1ed-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc1ed-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc1ed-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc1ed-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc1ed-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc1ed-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc1ed-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc1ed-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc1ed-119">See also</span></span>

- [<span data-ttu-id="fc1ed-120">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="fc1ed-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="fc1ed-121">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="fc1ed-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
