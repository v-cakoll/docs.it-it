---
title: Metodo ICorDebugManagedCallback::ExitProcess
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04b8ac6751024e64cc866fce1cfe72fb42e41200
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760446"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="6bc4e-102">Metodo ICorDebugManagedCallback::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="6bc4e-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="6bc4e-103">Notifica al debugger che un processo è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="6bc4e-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bc4e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bc4e-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bc4e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6bc4e-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="6bc4e-106">[in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="6bc4e-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bc4e-107">Note</span><span class="sxs-lookup"><span data-stu-id="6bc4e-107">Remarks</span></span>  
 <span data-ttu-id="6bc4e-108">Non è possibile continuare da un `ExitProcess` evento.</span><span class="sxs-lookup"><span data-stu-id="6bc4e-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="6bc4e-109">Questo evento possono essere attivati in modo asincrono e gli altri eventi mentre il processo sembra essere stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="6bc4e-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="6bc4e-110">Ciò può verificarsi se il processo viene terminato mentre arrestato, in genere a causa di circostanza esterna.</span><span class="sxs-lookup"><span data-stu-id="6bc4e-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="6bc4e-111">Se common language runtime (CLR) sta già inviando un callback gestito, questo evento verrà posticipato fino al dopo tale callback ha restituito.</span><span class="sxs-lookup"><span data-stu-id="6bc4e-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="6bc4e-112">Il `ExitProcess` eventi sono l'unico evento/Scaricamento di uscita che viene chiamato in fase di arresto.</span><span class="sxs-lookup"><span data-stu-id="6bc4e-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bc4e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6bc4e-113">Requirements</span></span>  
 <span data-ttu-id="6bc4e-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bc4e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bc4e-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6bc4e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6bc4e-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bc4e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bc4e-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bc4e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc4e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bc4e-118">See also</span></span>

- [<span data-ttu-id="6bc4e-119">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="6bc4e-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
