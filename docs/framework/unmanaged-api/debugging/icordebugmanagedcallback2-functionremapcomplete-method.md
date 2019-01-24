---
title: Metodo ICorDebugManagedCallback2::FunctionRemapComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1909b7123bde23058e42394db86af83d08e2354
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685386"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="d4f7b-102">Metodo ICorDebugManagedCallback2::FunctionRemapComplete</span><span class="sxs-lookup"><span data-stu-id="d4f7b-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="d4f7b-103">Notifica al debugger che l'esecuzione di codice è passata a una nuova versione di una funzione modificata.</span><span class="sxs-lookup"><span data-stu-id="d4f7b-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f7b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4f7b-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4f7b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4f7b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d4f7b-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente la funzione modificata.</span><span class="sxs-lookup"><span data-stu-id="d4f7b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="d4f7b-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stato rilevato il punto di interruzione di modifica del mapping.</span><span class="sxs-lookup"><span data-stu-id="d4f7b-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="d4f7b-108">[in] Un puntatore a un oggetto ICorDebugFunction che rappresenta la versione della funzione attualmente in esecuzione sul thread.</span><span class="sxs-lookup"><span data-stu-id="d4f7b-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4f7b-109">Note</span><span class="sxs-lookup"><span data-stu-id="d4f7b-109">Remarks</span></span>  
 <span data-ttu-id="d4f7b-110">Questo callback consente al debugger di ricreare tutti i gestori di istruzioni che esisteva in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d4f7b-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4f7b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4f7b-111">Requirements</span></span>  
 <span data-ttu-id="d4f7b-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4f7b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4f7b-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4f7b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4f7b-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4f7b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4f7b-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4f7b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f7b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4f7b-116">See also</span></span>
- [<span data-ttu-id="d4f7b-117">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="d4f7b-117">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="d4f7b-118">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="d4f7b-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
