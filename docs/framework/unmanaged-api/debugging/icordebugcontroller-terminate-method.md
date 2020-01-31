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
ms.openlocfilehash: 851a127c117b826c271dd021c41cfdb36045a1ff
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783750"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="3f1b2-102">Metodo ICorDebugController::Terminate</span><span class="sxs-lookup"><span data-stu-id="3f1b2-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="3f1b2-103">Termina il processo con il codice di uscita specificato.</span><span class="sxs-lookup"><span data-stu-id="3f1b2-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f1b2-104">Questo metodo è un wrapper per la funzione Win32 `TerminateProcess`.</span><span class="sxs-lookup"><span data-stu-id="3f1b2-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="3f1b2-105">Pertanto, `Terminate` utilizza il codice di uscita nello stesso modo in cui la funzione `TerminateProcess` Win32 la utilizza.</span><span class="sxs-lookup"><span data-stu-id="3f1b2-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f1b2-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f1b2-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f1b2-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f1b2-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="3f1b2-108">in Valore numerico che rappresenta il codice di uscita.</span><span class="sxs-lookup"><span data-stu-id="3f1b2-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="3f1b2-109">I valori numerici validi sono definiti in winbase. h.</span><span class="sxs-lookup"><span data-stu-id="3f1b2-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f1b2-110">Note</span><span class="sxs-lookup"><span data-stu-id="3f1b2-110">Remarks</span></span>  
 <span data-ttu-id="3f1b2-111">Se il processo viene interrotto quando viene chiamato `Terminate`, il processo deve essere continuato usando il metodo [ICorDebugController:: continue](icordebugcontroller-continue-method.md) , in modo che il debugger riceva la conferma della terminazione tramite il callback [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) o [ICorDebugManagedCallback:: ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3f1b2-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f1b2-112">Questo metodo non è implementato da un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="3f1b2-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="3f1b2-113">Ovvero non viene implementato a livello di <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="3f1b2-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f1b2-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3f1b2-114">Requirements</span></span>  
 <span data-ttu-id="3f1b2-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f1b2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f1b2-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f1b2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f1b2-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f1b2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f1b2-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f1b2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f1b2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f1b2-119">See also</span></span>
