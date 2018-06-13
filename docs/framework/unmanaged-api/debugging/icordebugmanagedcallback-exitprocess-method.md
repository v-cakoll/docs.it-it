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
ms.openlocfilehash: 42330296defe90980dd431ce39765a549057b82a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416881"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="9205a-102">Metodo ICorDebugManagedCallback::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="9205a-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="9205a-103">Notifica al debugger che un processo è terminato.</span><span class="sxs-lookup"><span data-stu-id="9205a-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9205a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9205a-104">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9205a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9205a-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="9205a-106">[in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="9205a-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9205a-107">Note</span><span class="sxs-lookup"><span data-stu-id="9205a-107">Remarks</span></span>  
 <span data-ttu-id="9205a-108">È possibile proseguire da un `ExitProcess` evento.</span><span class="sxs-lookup"><span data-stu-id="9205a-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="9205a-109">Questo evento potrebbe essere generato in modo asincrono e gli altri eventi mentre il processo da arrestare.</span><span class="sxs-lookup"><span data-stu-id="9205a-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="9205a-110">Ciò può verificarsi se il processo viene interrotto mentre arrestato, in genere a causa di alcune forza esterna.</span><span class="sxs-lookup"><span data-stu-id="9205a-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="9205a-111">Se common language runtime (CLR) sta già inviando un callback gestito, questo evento verrà ritardato fino a dopo che ha restituito il callback.</span><span class="sxs-lookup"><span data-stu-id="9205a-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="9205a-112">Il `ExitProcess` evento è l'unico evento di uscita o scaricamento che viene chiamato in fase di arresto.</span><span class="sxs-lookup"><span data-stu-id="9205a-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9205a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9205a-113">Requirements</span></span>  
 <span data-ttu-id="9205a-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9205a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9205a-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9205a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9205a-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9205a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9205a-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9205a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9205a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9205a-118">See Also</span></span>  
 [<span data-ttu-id="9205a-119">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9205a-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
