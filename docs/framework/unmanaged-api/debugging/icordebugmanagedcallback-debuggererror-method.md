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
ms.openlocfilehash: 9b96c0a2eca543b9e01ccf92b271b1aa7003c5c9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781940"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="09b66-102">Metodo ICorDebugManagedCallback::DebuggerError</span><span class="sxs-lookup"><span data-stu-id="09b66-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="09b66-103">Notifica al debugger che si è verificato un errore durante il tentativo di gestire un evento dal Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="09b66-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09b66-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09b66-104">Syntax</span></span>  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09b66-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="09b66-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="09b66-106">in Puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="09b66-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="09b66-107">in Valore HRESULT restituito dal gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="09b66-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="09b66-108">in Integer che specifica l'errore CLR.</span><span class="sxs-lookup"><span data-stu-id="09b66-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09b66-109">Note</span><span class="sxs-lookup"><span data-stu-id="09b66-109">Remarks</span></span>  
 <span data-ttu-id="09b66-110">Il processo può essere inserito in modalità pass-through, a seconda della natura dell'errore.</span><span class="sxs-lookup"><span data-stu-id="09b66-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="09b66-111">Il callback `DebugError` indica che i servizi di debug sono stati disabilitati a causa di un errore, pertanto i debugger devono rendere disponibile il messaggio di errore per l'utente.</span><span class="sxs-lookup"><span data-stu-id="09b66-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="09b66-112">[ICorDebugProcess:: GetId](icordebugprocess-getid-method.md) sarà sicuro chiamare, ma tutti gli altri metodi, incluso [ICorDebug:: terminate](icordebug-terminate-method.md), non devono essere chiamati.</span><span class="sxs-lookup"><span data-stu-id="09b66-112">[ICorDebugProcess::GetID](icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="09b66-113">Il debugger deve usare le funzionalità del sistema operativo per terminare i processi.</span><span class="sxs-lookup"><span data-stu-id="09b66-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09b66-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="09b66-114">Requirements</span></span>  
 <span data-ttu-id="09b66-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09b66-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09b66-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09b66-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09b66-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09b66-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09b66-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09b66-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09b66-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09b66-119">See also</span></span>

- [<span data-ttu-id="09b66-120">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="09b66-120">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
