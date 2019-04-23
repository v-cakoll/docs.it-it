---
title: Metodo ICorDebugManagedCallback2::ExceptionUnwind
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faba9631e85ac84ff1517b64e9a3f5567ee7c9dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214794"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="031bb-102">Metodo ICorDebugManagedCallback2::ExceptionUnwind</span><span class="sxs-lookup"><span data-stu-id="031bb-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="031bb-103">Fornisce una notifica sullo stato durante il processo di rimozione di eccezione.</span><span class="sxs-lookup"><span data-stu-id="031bb-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="031bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="031bb-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="031bb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="031bb-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="031bb-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="031bb-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="031bb-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="031bb-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="031bb-108">[in] Valore dell'enumerazione CorDebugExceptionUnwindCallbackType che specifica l'evento segnalato dal callback durante la fase di rimozione.</span><span class="sxs-lookup"><span data-stu-id="031bb-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="031bb-109">[in] Valore di [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumerazione che specifica informazioni aggiuntive sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="031bb-109">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="031bb-110">Note</span><span class="sxs-lookup"><span data-stu-id="031bb-110">Remarks</span></span>  
 <span data-ttu-id="031bb-111">`ExceptionUnwind` viene chiamato in vari momenti durante la fase di rimozione del processo di gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="031bb-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="031bb-112">`ExceptionUnwind` può essere chiamato più volte durante la rimozione di un'unica eccezione.</span><span class="sxs-lookup"><span data-stu-id="031bb-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="031bb-113">Se `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, il puntatore all'istruzione saranno nel frame foglia del thread, in corrispondenza del punto di sequenza prima (ciò può essere più istruzioni) dell'istruzione che ha causato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="031bb-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="031bb-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="031bb-114">Requirements</span></span>  
 <span data-ttu-id="031bb-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="031bb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="031bb-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="031bb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="031bb-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="031bb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="031bb-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="031bb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="031bb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="031bb-119">See also</span></span>

- [<span data-ttu-id="031bb-120">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="031bb-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="031bb-121">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="031bb-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
