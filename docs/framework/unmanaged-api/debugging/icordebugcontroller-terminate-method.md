---
title: Metodo ICorDebugController::Terminate
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
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e7647df7a67d8357e72f8f41b0b3f586675aaac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="055e8-102">Metodo ICorDebugController::Terminate</span><span class="sxs-lookup"><span data-stu-id="055e8-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="055e8-103">Termina il processo con il codice di uscita specificato.</span><span class="sxs-lookup"><span data-stu-id="055e8-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="055e8-104">Questo metodo è un wrapper per Win32 `TerminateProcess` (funzione).</span><span class="sxs-lookup"><span data-stu-id="055e8-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="055e8-105">Di conseguenza, `Terminate` utilizza il codice di uscita nello stesso modo in cui Win32 `TerminateProcess` funzione.</span><span class="sxs-lookup"><span data-stu-id="055e8-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="055e8-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="055e8-106">Syntax</span></span>  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="055e8-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="055e8-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="055e8-108">[in] Un valore numerico che rappresenta il codice di uscita.</span><span class="sxs-lookup"><span data-stu-id="055e8-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="055e8-109">I valori numerici validi sono definiti in winbase.</span><span class="sxs-lookup"><span data-stu-id="055e8-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="055e8-110">Note</span><span class="sxs-lookup"><span data-stu-id="055e8-110">Remarks</span></span>  
 <span data-ttu-id="055e8-111">Se il processo viene arrestato quando `Terminate` viene chiamato, il processo di proseguire con la [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) metodo in modo che il debugger riceve una conferma di chiusura tramite il [ ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) o [ICorDebugManagedCallback:: ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="055e8-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="055e8-112">Questo metodo non è implementato da un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="055e8-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="055e8-113">Ovvero, non è implementato nel <xref:System.AppDomain> livello.</span><span class="sxs-lookup"><span data-stu-id="055e8-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="055e8-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="055e8-114">Requirements</span></span>  
 <span data-ttu-id="055e8-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="055e8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="055e8-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="055e8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="055e8-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="055e8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="055e8-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="055e8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="055e8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="055e8-119">See Also</span></span>  
 
