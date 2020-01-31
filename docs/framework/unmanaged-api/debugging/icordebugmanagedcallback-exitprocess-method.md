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
ms.openlocfilehash: 4380b8a3803e164aab7318821a9dbde32ecc3a0b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781749"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="a2299-102">Metodo ICorDebugManagedCallback::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="a2299-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="a2299-103">Notifica al debugger che un processo è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="a2299-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2299-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2299-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2299-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a2299-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="a2299-106">in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="a2299-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2299-107">Note</span><span class="sxs-lookup"><span data-stu-id="a2299-107">Remarks</span></span>  
 <span data-ttu-id="a2299-108">Non è possibile continuare da un evento `ExitProcess`.</span><span class="sxs-lookup"><span data-stu-id="a2299-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="a2299-109">Questo evento può essere generato in modo asincrono ad altri eventi mentre il processo sembra arrestarsi.</span><span class="sxs-lookup"><span data-stu-id="a2299-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="a2299-110">Questo problema può verificarsi se il processo termina durante l'arresto, in genere a causa di una forza esterna.</span><span class="sxs-lookup"><span data-stu-id="a2299-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="a2299-111">Se il Common Language Runtime (CLR) sta già inviando un callback gestito, questo evento verrà posticipato fino a quando non viene restituito tale callback.</span><span class="sxs-lookup"><span data-stu-id="a2299-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="a2299-112">L'evento `ExitProcess` è l'unico evento di uscita/scaricamento garantito per essere chiamato all'arresto.</span><span class="sxs-lookup"><span data-stu-id="a2299-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2299-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a2299-113">Requirements</span></span>  
 <span data-ttu-id="a2299-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2299-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2299-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2299-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2299-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2299-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2299-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2299-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2299-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2299-118">See also</span></span>

- [<span data-ttu-id="a2299-119">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="a2299-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
