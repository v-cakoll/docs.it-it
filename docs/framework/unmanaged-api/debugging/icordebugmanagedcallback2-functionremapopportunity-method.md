---
title: Metodo ICorDebugManagedCallback2::FunctionRemapOpportunity
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24f058ff11a1155aa53a1d1f222ff1230c1c23e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760992"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="346d1-102">Metodo ICorDebugManagedCallback2::FunctionRemapOpportunity</span><span class="sxs-lookup"><span data-stu-id="346d1-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="346d1-103">Notifica al debugger che l'esecuzione di codice ha raggiunto un punto di sequenza in una versione precedente di una funzione modificata.</span><span class="sxs-lookup"><span data-stu-id="346d1-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="346d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="346d1-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="346d1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="346d1-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="346d1-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente la funzione modificata.</span><span class="sxs-lookup"><span data-stu-id="346d1-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="346d1-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stato rilevato il punto di interruzione di modifica del mapping.</span><span class="sxs-lookup"><span data-stu-id="346d1-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="346d1-108">[in] Un puntatore a un oggetto ICorDebugFunction che rappresenta la versione della funzione attualmente in esecuzione sul thread.</span><span class="sxs-lookup"><span data-stu-id="346d1-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="346d1-109">[in] Un puntatore a un oggetto ICorDebugFunction che rappresenta la versione più recente della funzione.</span><span class="sxs-lookup"><span data-stu-id="346d1-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="346d1-110">[in] Offset Microsoft intermediate language (MSIL) del puntatore dell'istruzione nella versione precedente della funzione.</span><span class="sxs-lookup"><span data-stu-id="346d1-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="346d1-111">Note</span><span class="sxs-lookup"><span data-stu-id="346d1-111">Remarks</span></span>  
 <span data-ttu-id="346d1-112">Questo callback consente al debugger di un'opportunità per rimappare il puntatore all'istruzione al suo posto nella nuova versione della funzione specificata mediante la chiamata di [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="346d1-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="346d1-113">Se non ne richiama il debugger `RemapFunction` prima di chiamare il [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) metodo, il runtime continua a eseguire il codice precedente e verrà generato un altro `FunctionRemapOpportunity` callback al successivo punto di sequenza.</span><span class="sxs-lookup"><span data-stu-id="346d1-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="346d1-114">Questo callback verrà richiamato per ogni fotogramma che è in esecuzione una versione precedente della funzione specificata fino a quando il debugger restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="346d1-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="346d1-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="346d1-115">Requirements</span></span>  
 <span data-ttu-id="346d1-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="346d1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="346d1-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="346d1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="346d1-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="346d1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="346d1-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="346d1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="346d1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="346d1-120">See also</span></span>

- [<span data-ttu-id="346d1-121">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="346d1-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="346d1-122">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="346d1-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
