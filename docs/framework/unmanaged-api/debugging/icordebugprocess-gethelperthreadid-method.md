---
title: Metodo ICorDebugProcess::GetHelperThreadID
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetHelperThreadID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 092e99cb1d5534cee56db08b5a2eedaaa2fc4724
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="8b801-102">Metodo ICorDebugProcess::GetHelperThreadID</span><span class="sxs-lookup"><span data-stu-id="8b801-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="8b801-103">Ottiene l'ID di thread del sistema operativo () del thread di supporto interno del debugger.</span><span class="sxs-lookup"><span data-stu-id="8b801-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b801-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b801-104">Syntax</span></span>  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b801-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8b801-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="8b801-106">[out] ID del thread di supporto interno del debugger di thread di un puntatore al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8b801-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b801-107">Note</span><span class="sxs-lookup"><span data-stu-id="8b801-107">Remarks</span></span>  
 <span data-ttu-id="8b801-108">Durante il debug gestito e non gestito, è responsabilità del debugger per assicurarsi che il thread con l'ID specificato rimane in esecuzione se rilevato un punto di interruzione inserito dal debugger.</span><span class="sxs-lookup"><span data-stu-id="8b801-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="8b801-109">Un debugger può anche scegliere di nascondere questo thread da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8b801-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="8b801-110">Se nessun thread di supporto nel processo non esiste ancora, la `GetHelperThreadID` metodo restituirà zero in *`pThreadID`.</span><span class="sxs-lookup"><span data-stu-id="8b801-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in *`pThreadID`.</span></span>  
  
 <span data-ttu-id="8b801-111">È possibile memorizzare nella cache l'ID del thread di supporto, perché può cambiare nel tempo.</span><span class="sxs-lookup"><span data-stu-id="8b801-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="8b801-112">È necessario eseguire una query nuovamente l'ID di thread a ogni evento di arresto.</span><span class="sxs-lookup"><span data-stu-id="8b801-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="8b801-113">L'ID di thread del thread di supporto del debugger sarà corretto in ogni non gestito [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) evento, consentendo in tal modo un debugger determinare l'ID del thread di supporto e di nasconderlo da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8b801-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="8b801-114">Un thread che durante una funzione non gestita viene identificato come un thread di supporto `ICorDebugManagedCallback::CreateThread` evento non verrà mai eseguito codice utente gestito.</span><span class="sxs-lookup"><span data-stu-id="8b801-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b801-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8b801-115">Requirements</span></span>  
 <span data-ttu-id="8b801-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b801-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b801-117">**Intestazione:** CorDebug.idl.</span><span class="sxs-lookup"><span data-stu-id="8b801-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="8b801-118">Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8b801-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="8b801-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b801-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b801-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b801-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
