---
title: Metodo ICorDebugManagedCallback2::ChangeConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.ChangeConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c62859cb6a3e61af9670834db169410cecb6787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="d4f8f-102">Metodo ICorDebugManagedCallback2::ChangeConnection</span><span class="sxs-lookup"><span data-stu-id="d4f8f-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="d4f8f-103">Notifica al debugger che il set di attività associata alla connessione specificata è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="d4f8f-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f8f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4f8f-104">Syntax</span></span>  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4f8f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4f8f-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="d4f8f-106">[in] Un puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo che contiene la connessione modificata.</span><span class="sxs-lookup"><span data-stu-id="d4f8f-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="d4f8f-107">[in] L'ID di connessione modificata.</span><span class="sxs-lookup"><span data-stu-id="d4f8f-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4f8f-108">Note</span><span class="sxs-lookup"><span data-stu-id="d4f8f-108">Remarks</span></span>  
 <span data-ttu-id="d4f8f-109">Oggetto `ChangeConnection` callback verrà generato in uno dei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="d4f8f-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="d4f8f-110">Quando un debugger si connette a un processo che contiene le connessioni.</span><span class="sxs-lookup"><span data-stu-id="d4f8f-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="d4f8f-111">In questo caso, il runtime generare e inviare un [ICorDebugManagedCallback2:: CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) evento e un `ChangeConnection` evento per ogni connessione del processo.</span><span class="sxs-lookup"><span data-stu-id="d4f8f-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="d4f8f-112">Oggetto `ChangeConnection` evento viene generato per ogni connessione esistente, indipendentemente dal fatto che set della connessione di attività è stato modificato rispetto alla creazione.</span><span class="sxs-lookup"><span data-stu-id="d4f8f-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
-   <span data-ttu-id="d4f8f-113">Quando un host chiama [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) nel [API di Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="d4f8f-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
 <span data-ttu-id="d4f8f-114">Il debugger deve eseguire l'analisi di tutti i thread del processo per rendere effettive le nuove modifiche.</span><span class="sxs-lookup"><span data-stu-id="d4f8f-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4f8f-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4f8f-115">Requirements</span></span>  
 <span data-ttu-id="d4f8f-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4f8f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4f8f-117">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="d4f8f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4f8f-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4f8f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4f8f-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4f8f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f8f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4f8f-120">See Also</span></span>  
 [<span data-ttu-id="d4f8f-121">ICorDebugManagedCallback2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d4f8f-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="d4f8f-122">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d4f8f-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
