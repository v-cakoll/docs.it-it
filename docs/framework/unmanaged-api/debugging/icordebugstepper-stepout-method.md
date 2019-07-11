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
ms.openlocfilehash: 36a33b74a692761d772a888ce918aa28a2d92678
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760563"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="91f53-102">Metodo ICorDebugStepper::StepOut</span><span class="sxs-lookup"><span data-stu-id="91f53-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="91f53-103">Fa sì che questo ICorDebugStepper passo a passo del thread e che venga completato quando il frame corrente restituisce il controllo al chiama frame.</span><span class="sxs-lookup"><span data-stu-id="91f53-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91f53-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91f53-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="91f53-105">Note</span><span class="sxs-lookup"><span data-stu-id="91f53-105">Remarks</span></span>  
 <span data-ttu-id="91f53-106">Oggetto `StepOut` operazione verrà completata dopo essere tornati in genere dal frame corrente per il frame di chiamata.</span><span class="sxs-lookup"><span data-stu-id="91f53-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="91f53-107">Se `StepOut` viene chiamato quando nel codice non gestito, il passaggio verrà completata quando il frame corrente viene restituito al codice gestito che lo ha chiamato.</span><span class="sxs-lookup"><span data-stu-id="91f53-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="91f53-108">In .NET Framework versione 2.0, non usare `StepOut` con il flag STOP_UNMANAGED set poiché avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="91f53-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="91f53-109">(Usare [SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) impostare i flag per l'esecuzione di istruzioni.) Debugger di interoperabilità devono Esci da istruzione al codice nativo se stessi.</span><span class="sxs-lookup"><span data-stu-id="91f53-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91f53-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="91f53-110">Requirements</span></span>  
 <span data-ttu-id="91f53-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91f53-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91f53-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91f53-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91f53-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91f53-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91f53-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91f53-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
