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
ms.openlocfilehash: 8f66369d3ac5ddcfe38fe579cac728eb3a250165
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205631"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="5c44f-102">Metodo ICorDebugManagedCallback2::ExceptionUnwind</span><span class="sxs-lookup"><span data-stu-id="5c44f-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="5c44f-103">Fornisce una notifica di stato durante il processo di rimozione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5c44f-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c44f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c44f-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c44f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c44f-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5c44f-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5c44f-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5c44f-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5c44f-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="5c44f-108">in Valore dell'enumerazione CorDebugExceptionUnwindCallbackType che specifica l'evento che viene segnalato dal callback durante la fase di rimozione.</span><span class="sxs-lookup"><span data-stu-id="5c44f-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5c44f-109">in Valore dell'enumerazione [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) che specifica informazioni aggiuntive sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5c44f-109">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c44f-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5c44f-110">Remarks</span></span>  
 <span data-ttu-id="5c44f-111">`ExceptionUnwind`viene chiamato in diversi punti durante la fase di rimozione del processo di gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="5c44f-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="5c44f-112">`ExceptionUnwind`può essere chiamato più volte durante la rimozione di una singola eccezione.</span><span class="sxs-lookup"><span data-stu-id="5c44f-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="5c44f-113">Se `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, il puntatore all'istruzione si troverà nel frame foglia del thread, in corrispondenza del punto di sequenza precedente, che può essere costituito da diverse istruzioni prima, dall'istruzione che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5c44f-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c44f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c44f-114">Requirements</span></span>  
 <span data-ttu-id="5c44f-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c44f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c44f-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c44f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c44f-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c44f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c44f-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c44f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c44f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c44f-119">See also</span></span>

- [<span data-ttu-id="5c44f-120">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="5c44f-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="5c44f-121">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5c44f-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
