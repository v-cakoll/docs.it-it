---
title: Metodo ICorDebugStepper::StepOut
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
ms.openlocfilehash: 08cf2d0bb09080296fc1fcc69b5817f4d6118765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791720"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="39a8a-102">Metodo ICorDebugStepper::StepOut</span><span class="sxs-lookup"><span data-stu-id="39a8a-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="39a8a-103">Fa in modo che questo ICorDebugStepper a un singolo passaggio tramite il thread contenitore e venga completato quando il frame corrente restituisce il controllo al frame chiamante.</span><span class="sxs-lookup"><span data-stu-id="39a8a-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39a8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39a8a-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="39a8a-105">Note</span><span class="sxs-lookup"><span data-stu-id="39a8a-105">Remarks</span></span>  
 <span data-ttu-id="39a8a-106">Un'operazione di `StepOut` verrà completata dopo la restituzione normale dal frame corrente al frame chiamante.</span><span class="sxs-lookup"><span data-stu-id="39a8a-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="39a8a-107">Se `StepOut` viene chiamato quando si trova nel codice non gestito, il passaggio viene completato quando il frame corrente torna al codice gestito che lo ha chiamato.</span><span class="sxs-lookup"><span data-stu-id="39a8a-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="39a8a-108">In .NET Framework versione 2,0, non usare `StepOut` con il flag di STOP_UNMANAGED impostato in quanto avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="39a8a-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="39a8a-109">(Usare [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) per impostare i flag per l'esecuzione di un'istruzione). I debugger di interoperabilità devono uscire dal codice nativo.</span><span class="sxs-lookup"><span data-stu-id="39a8a-109">(Use [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39a8a-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="39a8a-110">Requirements</span></span>  
 <span data-ttu-id="39a8a-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39a8a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39a8a-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39a8a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39a8a-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39a8a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39a8a-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39a8a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
