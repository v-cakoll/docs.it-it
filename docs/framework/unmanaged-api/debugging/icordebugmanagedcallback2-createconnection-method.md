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
ms.openlocfilehash: e98748b523b948dc002f2ebc4e2e79fc7d659918
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781598"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="f799b-102">Metodo ICorDebugManagedCallback2::CreateConnection</span><span class="sxs-lookup"><span data-stu-id="f799b-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="f799b-103">Notifica al debugger che è stata creata una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="f799b-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f799b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f799b-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f799b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f799b-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="f799b-106">in Puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo in cui è stata creata la connessione</span><span class="sxs-lookup"><span data-stu-id="f799b-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="f799b-107">in ID della nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="f799b-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="f799b-108">in Puntatore al nome della nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="f799b-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f799b-109">Note</span><span class="sxs-lookup"><span data-stu-id="f799b-109">Remarks</span></span>  
 <span data-ttu-id="f799b-110">Un callback `CreateConnection` verrà attivato in uno dei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="f799b-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="f799b-111">Quando un debugger si connette a un processo che contiene connessioni.</span><span class="sxs-lookup"><span data-stu-id="f799b-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="f799b-112">In questo caso, il runtime genererà e invierà un evento `CreateConnection` e un evento [ICorDebugManagedCallback2:: ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) per ogni connessione nel processo.</span><span class="sxs-lookup"><span data-stu-id="f799b-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
- <span data-ttu-id="f799b-113">Quando un host chiama [ICLRDebugManager:: BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) nell' [API di hosting](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="f799b-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f799b-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="f799b-114">Requirements</span></span>  
 <span data-ttu-id="f799b-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f799b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f799b-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f799b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f799b-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f799b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f799b-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f799b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f799b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f799b-119">See also</span></span>

- [<span data-ttu-id="f799b-120">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="f799b-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="f799b-121">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="f799b-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
