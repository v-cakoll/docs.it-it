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
ms.openlocfilehash: 815dc63a2dedecc613506b0f98702f58d6e7bd04
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783795"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="bb75f-102">Metodo ICorDebugController::EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="bb75f-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="bb75f-103">Ottiene un enumeratore per i thread gestiti attivi nel processo.</span><span class="sxs-lookup"><span data-stu-id="bb75f-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb75f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb75f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb75f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bb75f-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="bb75f-106">out Puntatore all'indirizzo di un oggetto "ICorDebugThreadEnum" che rappresenta un enumeratore per tutti i thread gestiti attivi nel processo.</span><span class="sxs-lookup"><span data-stu-id="bb75f-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb75f-107">Note</span><span class="sxs-lookup"><span data-stu-id="bb75f-107">Remarks</span></span>  
 <span data-ttu-id="bb75f-108">Un thread viene considerato attivo dopo l'invio del callback [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) e prima dell'invio del callback [ICorDebugManagedCallback:: ExitThread](icordebugmanagedcallback-exitthread-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bb75f-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="bb75f-109">Un thread gestito potrebbe non avere necessariamente frame gestiti nello stack.</span><span class="sxs-lookup"><span data-stu-id="bb75f-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="bb75f-110">I thread possono essere enumerati anche prima del callback [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bb75f-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="bb75f-111">L'enumerazione sarà naturalmente vuota.</span><span class="sxs-lookup"><span data-stu-id="bb75f-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb75f-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="bb75f-112">Requirements</span></span>  
 <span data-ttu-id="bb75f-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb75f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb75f-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb75f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb75f-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb75f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb75f-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb75f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb75f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb75f-117">See also</span></span>
