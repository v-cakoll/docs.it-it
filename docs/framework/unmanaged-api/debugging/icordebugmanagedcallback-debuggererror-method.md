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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd7909b94343b1fb83836f5c369ddc1993f049d2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191174"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="a193d-102">Metodo ICorDebugManagedCallback::DebuggerError</span><span class="sxs-lookup"><span data-stu-id="a193d-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="a193d-103">Notifica al debugger che si è verificato un errore durante il tentativo di gestire un evento da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a193d-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a193d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a193d-104">Syntax</span></span>  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a193d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a193d-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="a193d-106">[in] Un puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="a193d-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="a193d-107">[in] Il valore HRESULT restituito dal gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a193d-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="a193d-108">[in] Valore intero che specifica l'errore CLR.</span><span class="sxs-lookup"><span data-stu-id="a193d-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a193d-109">Note</span><span class="sxs-lookup"><span data-stu-id="a193d-109">Remarks</span></span>  
 <span data-ttu-id="a193d-110">Il processo può essere inserito in modalità pass-through, a seconda della natura dell'errore.</span><span class="sxs-lookup"><span data-stu-id="a193d-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="a193d-111">Il `DebugError` callback indica che i servizi di debug sono stati disabilitati a causa di un errore, in modo debugger devono rendere disponibile il messaggio di errore all'utente.</span><span class="sxs-lookup"><span data-stu-id="a193d-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="a193d-112">[ICorDebugProcess:: GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) saranno sicure per chiamata, ma tutti gli altri metodi, tra cui [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), non deve essere chiamato.</span><span class="sxs-lookup"><span data-stu-id="a193d-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="a193d-113">Il debugger deve utilizzare le funzionalità del sistema operativo per la terminazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="a193d-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a193d-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a193d-114">Requirements</span></span>  
 <span data-ttu-id="a193d-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a193d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a193d-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a193d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a193d-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a193d-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a193d-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a193d-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a193d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a193d-119">See also</span></span>

- [<span data-ttu-id="a193d-120">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="a193d-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
