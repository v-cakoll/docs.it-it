---
title: Metodo ICorDebugProcess::GetHelperThreadID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad62b267eb0c49ff8fbefeb45b523c21edc705fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766049"
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="a6276-102">Metodo ICorDebugProcess::GetHelperThreadID</span><span class="sxs-lookup"><span data-stu-id="a6276-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="a6276-103">Ottiene l'ID di thread del sistema operativo (OS) del thread di supporto interno del debugger.</span><span class="sxs-lookup"><span data-stu-id="a6276-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6276-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6276-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6276-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a6276-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="a6276-106">[out] ID del thread di supporto interno del debugger di thread di un puntatore al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a6276-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6276-107">Note</span><span class="sxs-lookup"><span data-stu-id="a6276-107">Remarks</span></span>  
 <span data-ttu-id="a6276-108">Durante il debug gestito e non gestito, è responsabilità del debugger per garantire che il thread con l'ID specificato rimanga in esecuzione se raggiunge un punto di interruzione inserito dal debugger.</span><span class="sxs-lookup"><span data-stu-id="a6276-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="a6276-109">Un debugger può anche scegliere di nascondere questo thread da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a6276-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="a6276-110">Se l'helper esiste ancora alcun thread nel processo, il `GetHelperThreadID` metodo viene restituito zero in \*`pThreadID`.</span><span class="sxs-lookup"><span data-stu-id="a6276-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="a6276-111">È possibile memorizzare nella cache dell'ID del thread di helper, perché può cambiare nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="a6276-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="a6276-112">È necessario ripetere la query l'ID del thread in corrispondenza di ogni evento di arresto.</span><span class="sxs-lookup"><span data-stu-id="a6276-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="a6276-113">L'ID del thread del thread di supporto del debugger saranno corretto in ogni non gestito [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) eventi, consentendo in tal modo un debugger determinare l'ID del thread del suo thread helper e lo nasconde da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a6276-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="a6276-114">Un thread in cui viene identificato come un thread di supporto durante una funzione non gestita `ICorDebugManagedCallback::CreateThread` evento non verrà mai eseguito il codice utente gestito.</span><span class="sxs-lookup"><span data-stu-id="a6276-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6276-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6276-115">Requirements</span></span>  
 <span data-ttu-id="a6276-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6276-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6276-117">**Intestazione:** CorDebug.idl.</span><span class="sxs-lookup"><span data-stu-id="a6276-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="a6276-118">Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a6276-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="a6276-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6276-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6276-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6276-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
