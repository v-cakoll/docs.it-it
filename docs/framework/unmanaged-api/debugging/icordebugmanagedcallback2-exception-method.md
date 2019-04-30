---
title: Metodo ICorDebugManagedCallback2::Exception
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8952b34781045089945e7e72e179e88300b5fdd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942532"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="5a601-102">Metodo ICorDebugManagedCallback2::Exception</span><span class="sxs-lookup"><span data-stu-id="5a601-102">ICorDebugManagedCallback2::Exception Method</span></span>
<span data-ttu-id="5a601-103">Notifica al debugger che una ricerca di un gestore di eccezioni è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="5a601-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a601-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a601-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a601-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a601-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5a601-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5a601-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5a601-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5a601-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="5a601-108">[in] Un puntatore a un oggetto ICorDebugFrame che rappresenta un frame, come determinato dal `dwEventType` parametro.</span><span class="sxs-lookup"><span data-stu-id="5a601-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="5a601-109">Per altre informazioni, vedere la tabella nella sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="5a601-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="5a601-110">[in] Intero che specifica un offset, come determinato dal `dwEventType` parametro.</span><span class="sxs-lookup"><span data-stu-id="5a601-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="5a601-111">Per altre informazioni, vedere la tabella nella sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="5a601-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="5a601-112">[in] Valore dell'enumerazione CorDebugExceptionCallbackType che specifica il tipo di questo callback di eccezione.</span><span class="sxs-lookup"><span data-stu-id="5a601-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5a601-113">[in] Valore di [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumerazione che specifica informazioni aggiuntive sull'eccezione</span><span class="sxs-lookup"><span data-stu-id="5a601-113">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a601-114">Note</span><span class="sxs-lookup"><span data-stu-id="5a601-114">Remarks</span></span>  
 <span data-ttu-id="5a601-115">Il `Exception` callback viene chiamato in vari momenti durante la fase di ricerca del processo di gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="5a601-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="5a601-116">Vale a dire può essere chiamato più volte durante la rimozione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5a601-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="5a601-117">L'eccezione in fase di elaborazione può essere recuperato dall'oggetto ICorDebugThread fa riferimento il `pThread` parametro.</span><span class="sxs-lookup"><span data-stu-id="5a601-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="5a601-118">Il frame specifico e l'offset sono determinati dal `dwEventType` parametro come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5a601-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="5a601-119">Valore di `dwEventType`</span><span class="sxs-lookup"><span data-stu-id="5a601-119">Value of `dwEventType`</span></span>|<span data-ttu-id="5a601-120">Valore di `pFrame`</span><span class="sxs-lookup"><span data-stu-id="5a601-120">Value of `pFrame`</span></span>|<span data-ttu-id="5a601-121">Valore di `nOffset`</span><span class="sxs-lookup"><span data-stu-id="5a601-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="5a601-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="5a601-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="5a601-123">Frame che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5a601-123">The frame that threw the exception.</span></span>|<span data-ttu-id="5a601-124">Il puntatore dell'istruzione nel frame.</span><span class="sxs-lookup"><span data-stu-id="5a601-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="5a601-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="5a601-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="5a601-126">Il frame di codice utente più vicino al punto dell'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="5a601-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="5a601-127">Il puntatore dell'istruzione nel frame.</span><span class="sxs-lookup"><span data-stu-id="5a601-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="5a601-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="5a601-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="5a601-129">Frame che contiene il gestore catch.</span><span class="sxs-lookup"><span data-stu-id="5a601-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="5a601-130">Offset Microsoft intermediate language (MSIL) dell'inizio del gestore catch.</span><span class="sxs-lookup"><span data-stu-id="5a601-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="5a601-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="5a601-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="5a601-132">NULL</span><span class="sxs-lookup"><span data-stu-id="5a601-132">NULL</span></span>|<span data-ttu-id="5a601-133">Non è definito.</span><span class="sxs-lookup"><span data-stu-id="5a601-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a601-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a601-134">Requirements</span></span>  
 <span data-ttu-id="5a601-135">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a601-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a601-136">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a601-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a601-137">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a601-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a601-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a601-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a601-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a601-139">See also</span></span>

- [<span data-ttu-id="5a601-140">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="5a601-140">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="5a601-141">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5a601-141">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
