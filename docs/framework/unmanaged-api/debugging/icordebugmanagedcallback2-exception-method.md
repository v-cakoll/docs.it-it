---
title: Metodo ICorDebugManagedCallback2::Exception
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 79a8fa4709aeb04164bd1c2da07607435b76fff5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="08e5f-102">Metodo ICorDebugManagedCallback2::Exception</span><span class="sxs-lookup"><span data-stu-id="08e5f-102">ICorDebugManagedCallback2::Exception Method</span></span>
<span data-ttu-id="08e5f-103">Notifica al debugger che si è iniziata una ricerca di un gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="08e5f-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08e5f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08e5f-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="08e5f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="08e5f-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="08e5f-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il thread su cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="08e5f-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="08e5f-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread su cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="08e5f-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="08e5f-108">[in] Un puntatore a un oggetto ICorDebugFrame che rappresenta un frame, come determinato dal `dwEventType` parametro.</span><span class="sxs-lookup"><span data-stu-id="08e5f-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="08e5f-109">Per ulteriori informazioni, vedere la tabella nella sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="08e5f-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="08e5f-110">[in] Valore intero che specifica un offset, come determinato dal `dwEventType` parametro.</span><span class="sxs-lookup"><span data-stu-id="08e5f-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="08e5f-111">Per ulteriori informazioni, vedere la tabella nella sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="08e5f-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="08e5f-112">[in] Valore dell'enumerazione CorDebugExceptionCallbackType che specifica il tipo di callback dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="08e5f-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="08e5f-113">[in] Il valore di [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumerazione che specifica informazioni aggiuntive sull'eccezione</span><span class="sxs-lookup"><span data-stu-id="08e5f-113">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08e5f-114">Note</span><span class="sxs-lookup"><span data-stu-id="08e5f-114">Remarks</span></span>  
 <span data-ttu-id="08e5f-115">Il `Exception` callback viene chiamato in vari momenti durante la fase di ricerca del processo di gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="08e5f-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="08e5f-116">Ovvero, può essere chiamato più volte durante la rimozione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="08e5f-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="08e5f-117">L'eccezione in fase di elaborazione può essere recuperato dall'oggetto ICorDebugThread a cui fa riferimento il `pThread` parametro.</span><span class="sxs-lookup"><span data-stu-id="08e5f-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="08e5f-118">Il frame e l'offset sono determinati dalle `dwEventType` parametro come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="08e5f-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="08e5f-119">Valore di `dwEventType`</span><span class="sxs-lookup"><span data-stu-id="08e5f-119">Value of `dwEventType`</span></span>|<span data-ttu-id="08e5f-120">Valore di `pFrame`</span><span class="sxs-lookup"><span data-stu-id="08e5f-120">Value of `pFrame`</span></span>|<span data-ttu-id="08e5f-121">Valore di `nOffset`</span><span class="sxs-lookup"><span data-stu-id="08e5f-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="08e5f-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="08e5f-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="08e5f-123">Frame che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="08e5f-123">The frame that threw the exception.</span></span>|<span data-ttu-id="08e5f-124">Puntatore all'istruzione nel frame.</span><span class="sxs-lookup"><span data-stu-id="08e5f-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="08e5f-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="08e5f-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="08e5f-126">Il frame di codice utente più vicino al punto dell'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="08e5f-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="08e5f-127">Puntatore all'istruzione nel frame.</span><span class="sxs-lookup"><span data-stu-id="08e5f-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="08e5f-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="08e5f-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="08e5f-129">Il frame che contiene il gestore catch.</span><span class="sxs-lookup"><span data-stu-id="08e5f-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="08e5f-130">Offset Microsoft intermediate language (MSIL) dell'inizio del gestore catch.</span><span class="sxs-lookup"><span data-stu-id="08e5f-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="08e5f-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="08e5f-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="08e5f-132">NULL</span><span class="sxs-lookup"><span data-stu-id="08e5f-132">NULL</span></span>|<span data-ttu-id="08e5f-133">Non è definito.</span><span class="sxs-lookup"><span data-stu-id="08e5f-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="08e5f-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08e5f-134">Requirements</span></span>  
 <span data-ttu-id="08e5f-135">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08e5f-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08e5f-136">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="08e5f-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08e5f-137">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08e5f-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08e5f-138">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08e5f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08e5f-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08e5f-139">See Also</span></span>  
 [<span data-ttu-id="08e5f-140">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="08e5f-140">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="08e5f-141">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="08e5f-141">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
