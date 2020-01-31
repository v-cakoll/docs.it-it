---
title: Metodo ICorDebugUnmanagedCallback::DebugEvent
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
ms.openlocfilehash: cb52150a17c9ec8f4bbc25c13b85bce56b221eeb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791197"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a><span data-ttu-id="5fbcb-102">Metodo ICorDebugUnmanagedCallback::DebugEvent</span><span class="sxs-lookup"><span data-stu-id="5fbcb-102">ICorDebugUnmanagedCallback::DebugEvent Method</span></span>
<span data-ttu-id="5fbcb-103">Notifica al debugger che è stato generato un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-103">Notifies the debugger that a native event has been fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fbcb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5fbcb-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fbcb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5fbcb-105">Parameters</span></span>  
 `pDebugEvent`  
 <span data-ttu-id="5fbcb-106">in Puntatore all'evento nativo.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-106">[in] A pointer to the native event.</span></span>  
  
 `fOutOfBand`  
 <span data-ttu-id="5fbcb-107">[in] `true`, se l'interazione con lo stato del processo gestito è Impossibile quando si verifica un evento non gestito, finché il debugger non chiama [ICorDebugController:: continue](icordebugcontroller-continue-method.md); in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-107">[in] `true`, if interaction with the managed process state is impossible after an unmanaged event occurs, until the debugger calls [ICorDebugController::Continue](icordebugcontroller-continue-method.md); otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fbcb-108">Note</span><span class="sxs-lookup"><span data-stu-id="5fbcb-108">Remarks</span></span>  
 <span data-ttu-id="5fbcb-109">Se il thread di cui è in corso il debug è un thread Win32, non usare alcun membro dell'interfaccia di debug Win32.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-109">If the thread being debugged is a Win32 thread, do not use any members of the Win32 debugging interface.</span></span> <span data-ttu-id="5fbcb-110">È possibile chiamare `ICorDebugController::Continue` solo in un thread Win32 e solo quando si continua oltre un evento fuori banda.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-110">You can call `ICorDebugController::Continue` only on a Win32 thread and only when continuing past an out-of-band event.</span></span>  
  
 <span data-ttu-id="5fbcb-111">Il callback `DebugEvent` non segue le regole standard per i callback.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-111">The `DebugEvent` callback does not follow the standard rules for callbacks.</span></span> <span data-ttu-id="5fbcb-112">Quando si chiama `DebugEvent`, il processo si trova nello stato RAW di debug del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-112">When you call `DebugEvent`, the process will be in the raw, OS-debug stopped state.</span></span> <span data-ttu-id="5fbcb-113">Il processo non verrà sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-113">The process will not be synchronized.</span></span> <span data-ttu-id="5fbcb-114">Lo stato verrà automaticamente inserito quando necessario per soddisfare le richieste di informazioni sul codice gestito, operazione che può comportare altri callback di `DebugEvent` annidati.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-114">It will automatically enter the synchronized state when necessary to satisfy requests for information about managed code, which may result in other nested `DebugEvent` callbacks.</span></span>  
  
 <span data-ttu-id="5fbcb-115">Chiamare [ICorDebugProcess:: ClearCurrentException](icordebugprocess-clearcurrentexception-method.md) nel processo per ignorare un evento di eccezione prima di continuare il processo.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-115">Call [ICorDebugProcess::ClearCurrentException](icordebugprocess-clearcurrentexception-method.md) on the process to ignore an exception event before continuing the process.</span></span> <span data-ttu-id="5fbcb-116">La chiamata a questo metodo invia DBG_CONTINUE anziché DBG_EXCEPTION_NOT_HANDLED nella richiesta continue e cancella automaticamente i punti di interruzione fuori banda e le eccezioni a singolo passaggio.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-116">Calling this method sends DBG_CONTINUE instead of DBG_EXCEPTION_NOT_HANDLED on the continue request, and automatically clears out-of-band breakpoints and single-step exceptions.</span></span> <span data-ttu-id="5fbcb-117">Gli eventi fuori banda possono arrivare in qualsiasi momento, anche quando l'applicazione di cui è in corso il debug viene arrestata e quando esiste già un evento in banda in sospeso.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-117">Out-of-band events can come at any time, even when the application being debugged appears stopped and when an outstanding in-band event already exists.</span></span>  
  
 <span data-ttu-id="5fbcb-118">Nel .NET Framework versione 2,0, il debugger deve continuare immediatamente dopo un evento del punto di interruzione fuori banda.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-118">In the .NET Framework version 2.0, the debugger should immediately continue past an out-of-band breakpoint event.</span></span> <span data-ttu-id="5fbcb-119">Il debugger deve usare i metodi [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) e [ICorDebugProcess2:: ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md) per aggiungere e rimuovere punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-119">The debugger should be using the [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) and [ICorDebugProcess2::ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md) methods to add and remove breakpoints.</span></span> <span data-ttu-id="5fbcb-120">Questi metodi ignoreranno automaticamente eventuali punti di interruzione fuori banda.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-120">These methods will skip over any out-of-band breakpoints automatically.</span></span> <span data-ttu-id="5fbcb-121">Pertanto, gli unici punti di interruzione fuori banda che vengono inviati devono essere punti di interruzione non elaborati già presenti nel flusso di istruzioni, ad esempio una chiamata alla funzione Win32 `DebugBreak`.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-121">Thus, the only out-of-band breakpoints that get dispatched should be raw breakpoints that are already in the instruction stream, such as a call to the Win32 `DebugBreak` function.</span></span> <span data-ttu-id="5fbcb-122">Non tentare di usare `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess:: GetThreadContext](icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](icordebugprocess-setthreadcontext-method.md)o qualsiasi altro membro dell' [API di debug](index.md).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-122">Do not try to use `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](icordebugprocess-setthreadcontext-method.md), or any other member of the [debugging API](index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fbcb-123">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="5fbcb-123">Requirements</span></span>  
 <span data-ttu-id="5fbcb-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fbcb-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fbcb-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fbcb-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fbcb-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fbcb-127">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fbcb-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fbcb-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fbcb-128">See also</span></span>

- [<span data-ttu-id="5fbcb-129">Interfaccia ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="5fbcb-129">ICorDebugUnmanagedCallback Interface</span></span>](icordebugunmanagedcallback-interface.md)
