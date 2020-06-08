---
title: Metodo ICorDebugManagedCallback2::ChangeConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
ms.openlocfilehash: 7d209b7c319baff912b3462f8ed5f3f30f127750
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501911"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="7c421-102">Metodo ICorDebugManagedCallback2::ChangeConnection</span><span class="sxs-lookup"><span data-stu-id="7c421-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="7c421-103">Notifica al debugger che è stato modificato il set di attività associato alla connessione specificata.</span><span class="sxs-lookup"><span data-stu-id="7c421-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c421-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c421-104">Syntax</span></span>  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c421-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c421-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="7c421-106">in Puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo contenente la connessione modificata.</span><span class="sxs-lookup"><span data-stu-id="7c421-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="7c421-107">in ID della connessione modificata.</span><span class="sxs-lookup"><span data-stu-id="7c421-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c421-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7c421-108">Remarks</span></span>  
 <span data-ttu-id="7c421-109">Un `ChangeConnection` callback verrà attivato in uno dei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="7c421-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="7c421-110">Quando un debugger si connette a un processo che contiene connessioni.</span><span class="sxs-lookup"><span data-stu-id="7c421-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="7c421-111">In questo caso, il runtime genererà e invierà un evento [ICorDebugManagedCallback2:: CreateConnection](icordebugmanagedcallback2-createconnection-method.md) e un `ChangeConnection` evento per ogni connessione nel processo.</span><span class="sxs-lookup"><span data-stu-id="7c421-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="7c421-112">Un `ChangeConnection` evento viene generato per tutte le connessioni esistenti, indipendentemente dal fatto che il set di attività della connessione sia stato modificato dopo la creazione.</span><span class="sxs-lookup"><span data-stu-id="7c421-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
- <span data-ttu-id="7c421-113">Quando un host chiama [ICLRDebugManager:: SetConnectionTasks](../hosting/iclrdebugmanager-setconnectiontasks-method.md) nell' [API di hosting](../hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="7c421-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
 <span data-ttu-id="7c421-114">Il debugger deve analizzare tutti i thread del processo per individuare le nuove modifiche.</span><span class="sxs-lookup"><span data-stu-id="7c421-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c421-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c421-115">Requirements</span></span>  
 <span data-ttu-id="7c421-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c421-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c421-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c421-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c421-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c421-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c421-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c421-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c421-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c421-120">See also</span></span>

- [<span data-ttu-id="7c421-121">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="7c421-121">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="7c421-122">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="7c421-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
