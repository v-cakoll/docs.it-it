---
title: Metodo ICorDebugManagedCallback::DebuggerError
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
ms.openlocfilehash: 8f3697f8b193319ebb7b155ad79b8ec25a0a2266
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205281"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="e2572-102">Metodo ICorDebugManagedCallback::DebuggerError</span><span class="sxs-lookup"><span data-stu-id="e2572-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="e2572-103">Notifica al debugger che si è verificato un errore durante il tentativo di gestire un evento dal Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e2572-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2572-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2572-104">Syntax</span></span>  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2572-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2572-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="e2572-106">in Puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="e2572-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="e2572-107">in Valore HRESULT restituito dal gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="e2572-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="e2572-108">in Integer che specifica l'errore CLR.</span><span class="sxs-lookup"><span data-stu-id="e2572-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2572-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e2572-109">Remarks</span></span>  
 <span data-ttu-id="e2572-110">Il processo può essere inserito in modalità pass-through, a seconda della natura dell'errore.</span><span class="sxs-lookup"><span data-stu-id="e2572-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="e2572-111">Il `DebugError` callback indica che i servizi di debug sono stati disabilitati a causa di un errore, pertanto i debugger devono rendere disponibile il messaggio di errore per l'utente.</span><span class="sxs-lookup"><span data-stu-id="e2572-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="e2572-112">[ICorDebugProcess:: GetId](icordebugprocess-getid-method.md) sarà sicuro chiamare, ma tutti gli altri metodi, incluso [ICorDebug:: terminate](icordebug-terminate-method.md), non devono essere chiamati.</span><span class="sxs-lookup"><span data-stu-id="e2572-112">[ICorDebugProcess::GetID](icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="e2572-113">Il debugger deve usare le funzionalità del sistema operativo per terminare i processi.</span><span class="sxs-lookup"><span data-stu-id="e2572-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2572-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2572-114">Requirements</span></span>  
 <span data-ttu-id="e2572-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2572-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2572-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2572-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2572-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2572-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2572-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2572-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2572-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2572-119">See also</span></span>

- [<span data-ttu-id="e2572-120">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="e2572-120">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
