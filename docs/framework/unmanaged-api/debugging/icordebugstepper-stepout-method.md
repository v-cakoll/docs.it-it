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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f663f5134cf34bf9beb66da20bbb5886baff5415
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987428"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="e37f1-102">Metodo ICorDebugStepper::StepOut</span><span class="sxs-lookup"><span data-stu-id="e37f1-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="e37f1-103">Fa sì che questo ICorDebugStepper passo a passo del thread e che venga completato quando il frame corrente restituisce il controllo al chiama frame.</span><span class="sxs-lookup"><span data-stu-id="e37f1-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e37f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e37f1-104">Syntax</span></span>  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e37f1-105">Note</span><span class="sxs-lookup"><span data-stu-id="e37f1-105">Remarks</span></span>  
 <span data-ttu-id="e37f1-106">Oggetto `StepOut` operazione verrà completata dopo essere tornati in genere dal frame corrente per il frame di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e37f1-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="e37f1-107">Se `StepOut` viene chiamato quando nel codice non gestito, il passaggio verrà completata quando il frame corrente viene restituito al codice gestito che lo ha chiamato.</span><span class="sxs-lookup"><span data-stu-id="e37f1-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="e37f1-108">In .NET Framework versione 2.0, non usare `StepOut` con il flag STOP_UNMANAGED set poiché avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e37f1-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="e37f1-109">(Usare [SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) impostare i flag per l'esecuzione di istruzioni.) Debugger di interoperabilità devono Esci da istruzione al codice nativo se stessi.</span><span class="sxs-lookup"><span data-stu-id="e37f1-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e37f1-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e37f1-110">Requirements</span></span>  
 <span data-ttu-id="e37f1-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e37f1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e37f1-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e37f1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e37f1-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e37f1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e37f1-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e37f1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
