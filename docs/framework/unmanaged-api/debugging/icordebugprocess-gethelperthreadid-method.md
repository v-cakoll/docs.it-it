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
ms.openlocfilehash: d0dc301c67d09ebb15bf47cef15e642fb7c78fb9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792614"
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="0512e-102">Metodo ICorDebugProcess::GetHelperThreadID</span><span class="sxs-lookup"><span data-stu-id="0512e-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="0512e-103">Ottiene l'ID del thread del sistema operativo del thread helper interno del debugger.</span><span class="sxs-lookup"><span data-stu-id="0512e-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0512e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0512e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0512e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0512e-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="0512e-106">out Puntatore all'ID del thread del sistema operativo del thread helper interno del debugger.</span><span class="sxs-lookup"><span data-stu-id="0512e-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0512e-107">Note</span><span class="sxs-lookup"><span data-stu-id="0512e-107">Remarks</span></span>  
 <span data-ttu-id="0512e-108">Durante il debug gestito e non gestito, è responsabilità del debugger garantire che il thread con l'ID specificato rimanga in esecuzione se raggiunge un punto di interruzione inserito dal debugger.</span><span class="sxs-lookup"><span data-stu-id="0512e-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="0512e-109">Un debugger può anche voler nascondere questo thread dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0512e-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="0512e-110">Se nel processo non è ancora presente alcun thread helper, il metodo `GetHelperThreadID` restituisce zero in \*`pThreadID`.</span><span class="sxs-lookup"><span data-stu-id="0512e-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="0512e-111">Non è possibile memorizzare nella cache l'ID del thread di supporto perché potrebbe cambiare nel tempo.</span><span class="sxs-lookup"><span data-stu-id="0512e-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="0512e-112">È necessario eseguire di nuovo la query sull'ID del thread a ogni evento di interruzione.</span><span class="sxs-lookup"><span data-stu-id="0512e-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="0512e-113">L'ID thread del thread helper del debugger sarà corretto in ogni evento [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) non gestito, consentendo così a un debugger di determinare l'ID del thread del relativo thread helper e di nasconderlo dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0512e-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="0512e-114">Un thread identificato come thread Helper durante un evento `ICorDebugManagedCallback::CreateThread` non gestito non eseguirà mai codice utente gestito.</span><span class="sxs-lookup"><span data-stu-id="0512e-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0512e-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="0512e-115">Requirements</span></span>  
 <span data-ttu-id="0512e-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0512e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0512e-117">**Intestazione:** CorDebug. idl.</span><span class="sxs-lookup"><span data-stu-id="0512e-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="0512e-118">CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="0512e-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="0512e-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0512e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0512e-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0512e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
