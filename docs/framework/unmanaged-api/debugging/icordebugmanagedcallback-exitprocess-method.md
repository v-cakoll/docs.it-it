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
ms.openlocfilehash: 4518637eb47acf416a02c045f8ca6f8a90167277
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130784"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="d9e99-102">Metodo ICorDebugManagedCallback::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="d9e99-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="d9e99-103">Notifica al debugger che un processo è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="d9e99-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9e99-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9e99-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9e99-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9e99-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="d9e99-106">in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="d9e99-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9e99-107">Note</span><span class="sxs-lookup"><span data-stu-id="d9e99-107">Remarks</span></span>  
 <span data-ttu-id="d9e99-108">Non è possibile continuare da un evento `ExitProcess`.</span><span class="sxs-lookup"><span data-stu-id="d9e99-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="d9e99-109">Questo evento può essere generato in modo asincrono ad altri eventi mentre il processo sembra arrestarsi.</span><span class="sxs-lookup"><span data-stu-id="d9e99-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="d9e99-110">Questo problema può verificarsi se il processo termina durante l'arresto, in genere a causa di una forza esterna.</span><span class="sxs-lookup"><span data-stu-id="d9e99-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="d9e99-111">Se il Common Language Runtime (CLR) sta già inviando un callback gestito, questo evento verrà posticipato fino a quando non viene restituito tale callback.</span><span class="sxs-lookup"><span data-stu-id="d9e99-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="d9e99-112">L'evento `ExitProcess` è l'unico evento di uscita/scaricamento garantito per essere chiamato all'arresto.</span><span class="sxs-lookup"><span data-stu-id="d9e99-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9e99-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9e99-113">Requirements</span></span>  
 <span data-ttu-id="d9e99-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9e99-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9e99-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9e99-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9e99-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9e99-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9e99-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9e99-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e99-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9e99-118">See also</span></span>

- [<span data-ttu-id="d9e99-119">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="d9e99-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
