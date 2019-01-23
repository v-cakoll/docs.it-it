---
title: Metodo ICorDebugController::Terminate
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 362ae813846ab31f170ae49288735996eb1e9555
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531759"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="0ba95-102">Metodo ICorDebugController::Terminate</span><span class="sxs-lookup"><span data-stu-id="0ba95-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="0ba95-103">Termina il processo con il codice di uscita specificato.</span><span class="sxs-lookup"><span data-stu-id="0ba95-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ba95-104">Questo metodo è un wrapper per Win32 `TerminateProcess` (funzione).</span><span class="sxs-lookup"><span data-stu-id="0ba95-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="0ba95-105">Pertanto `Terminate` Usa il codice di uscita nello stesso modo in cui Win32 `TerminateProcess` funzione lo usa.</span><span class="sxs-lookup"><span data-stu-id="0ba95-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ba95-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ba95-106">Syntax</span></span>  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ba95-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ba95-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="0ba95-108">[in] Valore numerico che rappresenta il codice di uscita.</span><span class="sxs-lookup"><span data-stu-id="0ba95-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="0ba95-109">I valori numerici validi sono definiti in winbase. h.</span><span class="sxs-lookup"><span data-stu-id="0ba95-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ba95-110">Note</span><span class="sxs-lookup"><span data-stu-id="0ba95-110">Remarks</span></span>  
 <span data-ttu-id="0ba95-111">Se il processo viene arrestato quando `Terminate` viene chiamato, il processo deve essere continuata usando il [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) metodo in modo che il debugger riceve conferma della terminazione tramite il [ ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) oppure [ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="0ba95-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ba95-112">Questo metodo non è implementato da un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0ba95-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="0ba95-113">Vale a dire, non viene implementato nel <xref:System.AppDomain> livello.</span><span class="sxs-lookup"><span data-stu-id="0ba95-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ba95-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ba95-114">Requirements</span></span>  
 <span data-ttu-id="0ba95-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ba95-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ba95-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ba95-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ba95-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ba95-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ba95-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ba95-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ba95-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ba95-119">See also</span></span>

