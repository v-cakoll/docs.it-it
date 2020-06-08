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
ms.openlocfilehash: a3093f33f2220b22b7b4b373f6d79a341abf8c9c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501937"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="1d68e-102">Metodo ICorDebugManagedCallback2::DestroyConnection</span><span class="sxs-lookup"><span data-stu-id="1d68e-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="1d68e-103">Notifica al debugger che la connessione specificata è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="1d68e-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d68e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d68e-104">Syntax</span></span>  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d68e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1d68e-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="1d68e-106">in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo contenente la connessione distrutta.</span><span class="sxs-lookup"><span data-stu-id="1d68e-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="1d68e-107">in ID della connessione distrutta.</span><span class="sxs-lookup"><span data-stu-id="1d68e-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d68e-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1d68e-108">Remarks</span></span>  
 <span data-ttu-id="1d68e-109">Un `DestroyConnection` callback verrà generato quando un host chiama [ICLRDebugManager:: ENDCONNECTION](../hosting/iclrdebugmanager-endconnection-method.md) nell'API di [hosting](../hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="1d68e-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d68e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1d68e-110">Requirements</span></span>  
 <span data-ttu-id="1d68e-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d68e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d68e-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d68e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d68e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d68e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d68e-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d68e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d68e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d68e-115">See also</span></span>

- [<span data-ttu-id="1d68e-116">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="1d68e-116">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="1d68e-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="1d68e-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
