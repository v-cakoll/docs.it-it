---
title: Metodo ICorDebugManagedCallback2::FunctionRemapOpportunity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8a8360913597dfb5156399a45f86d2cc1a9f453d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="0179c-102">Metodo ICorDebugManagedCallback2::FunctionRemapOpportunity</span><span class="sxs-lookup"><span data-stu-id="0179c-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="0179c-103">Notifica al debugger che l'esecuzione del codice ha raggiunto un punto di sequenza in una versione precedente di una funzione modificata.</span><span class="sxs-lookup"><span data-stu-id="0179c-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0179c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0179c-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0179c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0179c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0179c-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio dell'applicazione contenente la funzione modificata.</span><span class="sxs-lookup"><span data-stu-id="0179c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="0179c-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread su cui è stato rilevato il punto di interruzione di modifica del mapping.</span><span class="sxs-lookup"><span data-stu-id="0179c-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="0179c-108">[in] Un puntatore a un oggetto ICorDebugFunction che rappresenta la versione della funzione attualmente in esecuzione sul thread.</span><span class="sxs-lookup"><span data-stu-id="0179c-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="0179c-109">[in] Un puntatore a un oggetto ICorDebugFunction che rappresenta la versione più recente della funzione.</span><span class="sxs-lookup"><span data-stu-id="0179c-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="0179c-110">[in] Offset Microsoft intermediate language (MSIL) del puntatore all'istruzione nella versione precedente della funzione.</span><span class="sxs-lookup"><span data-stu-id="0179c-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0179c-111">Note</span><span class="sxs-lookup"><span data-stu-id="0179c-111">Remarks</span></span>  
 <span data-ttu-id="0179c-112">Questo callback consente al debugger la possibilità di modificare il mapping al puntatore all'istruzione al suo posto nella nuova versione della funzione specificata mediante la chiamata di [ICorDebugILFrame2:: RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="0179c-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="0179c-113">Se il debugger non chiama `RemapFunction` prima di chiamare il [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) (metodo), il runtime continuerà a eseguire il codice obsoleto e verrà generato un altro `FunctionRemapOpportunity` callback al successivo punto di sequenza.</span><span class="sxs-lookup"><span data-stu-id="0179c-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="0179c-114">Verrà richiamato il callback di ogni frame è in esecuzione una versione precedente della funzione specificata fino a quando il debugger restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="0179c-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0179c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0179c-115">Requirements</span></span>  
 <span data-ttu-id="0179c-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0179c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0179c-117">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0179c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0179c-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0179c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0179c-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0179c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0179c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0179c-120">See Also</span></span>  
 [<span data-ttu-id="0179c-121">ICorDebugManagedCallback2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="0179c-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="0179c-122">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="0179c-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
