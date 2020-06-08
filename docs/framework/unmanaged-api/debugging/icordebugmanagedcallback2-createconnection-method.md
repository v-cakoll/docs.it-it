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
ms.openlocfilehash: 8e31f0a649fd1ca80d6557a0a7176549c67bf203
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501924"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="a2280-102">Metodo ICorDebugManagedCallback2::CreateConnection</span><span class="sxs-lookup"><span data-stu-id="a2280-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="a2280-103">Notifica al debugger che è stata creata una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="a2280-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2280-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2280-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2280-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a2280-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="a2280-106">in Puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo in cui è stata creata la connessione</span><span class="sxs-lookup"><span data-stu-id="a2280-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="a2280-107">in ID della nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="a2280-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="a2280-108">in Puntatore al nome della nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="a2280-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2280-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a2280-109">Remarks</span></span>  
 <span data-ttu-id="a2280-110">Un `CreateConnection` callback verrà attivato in uno dei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="a2280-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="a2280-111">Quando un debugger si connette a un processo che contiene connessioni.</span><span class="sxs-lookup"><span data-stu-id="a2280-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="a2280-112">In questo caso, il runtime genererà e invierà un `CreateConnection` evento e un evento [ICorDebugManagedCallback2:: ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) per ogni connessione nel processo.</span><span class="sxs-lookup"><span data-stu-id="a2280-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
- <span data-ttu-id="a2280-113">Quando un host chiama [ICLRDebugManager:: BeginConnection](../hosting/iclrdebugmanager-beginconnection-method.md) nell' [API di hosting](../hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="a2280-113">When a host calls [ICLRDebugManager::BeginConnection](../hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2280-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2280-114">Requirements</span></span>  
 <span data-ttu-id="a2280-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2280-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2280-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2280-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2280-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2280-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2280-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2280-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2280-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2280-119">See also</span></span>

- [<span data-ttu-id="a2280-120">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="a2280-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="a2280-121">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="a2280-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
