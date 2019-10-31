---
title: Metodo ICorDebugController::EnumerateThreads
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
ms.openlocfilehash: 291f6c05171b5e507afaa70537aafdc9002a506e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125403"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="ac80c-102">Metodo ICorDebugController::EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="ac80c-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="ac80c-103">Ottiene un enumeratore per i thread gestiti attivi nel processo.</span><span class="sxs-lookup"><span data-stu-id="ac80c-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac80c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac80c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac80c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac80c-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="ac80c-106">out Puntatore all'indirizzo di un oggetto "ICorDebugThreadEnum" che rappresenta un enumeratore per tutti i thread gestiti attivi nel processo.</span><span class="sxs-lookup"><span data-stu-id="ac80c-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac80c-107">Note</span><span class="sxs-lookup"><span data-stu-id="ac80c-107">Remarks</span></span>  
 <span data-ttu-id="ac80c-108">Un thread viene considerato attivo dopo l'invio del callback [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) e prima dell'invio del callback [ICorDebugManagedCallback:: ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ac80c-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="ac80c-109">Un thread gestito potrebbe non avere necessariamente frame gestiti nello stack.</span><span class="sxs-lookup"><span data-stu-id="ac80c-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="ac80c-110">I thread possono essere enumerati anche prima del callback [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ac80c-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="ac80c-111">L'enumerazione sarà naturalmente vuota.</span><span class="sxs-lookup"><span data-stu-id="ac80c-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac80c-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac80c-112">Requirements</span></span>  
 <span data-ttu-id="ac80c-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac80c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac80c-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac80c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac80c-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac80c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac80c-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac80c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac80c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac80c-117">See also</span></span>
