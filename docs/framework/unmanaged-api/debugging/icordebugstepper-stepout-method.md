---
title: Metodo ICorDebugStepper::StepOut
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepOut
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b3ceca69b6b4710a3f1b8e1e9bdb4baf574119c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="eb963-102">Metodo ICorDebugStepper::StepOut</span><span class="sxs-lookup"><span data-stu-id="eb963-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="eb963-103">Fa sì che ICorDebugStepper passo a passo del thread e che venga completato quando il frame corrente restituisce il controllo al frame chiamante.</span><span class="sxs-lookup"><span data-stu-id="eb963-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb963-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb963-104">Syntax</span></span>  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="eb963-105">Note</span><span class="sxs-lookup"><span data-stu-id="eb963-105">Remarks</span></span>  
 <span data-ttu-id="eb963-106">Oggetto `StepOut` operazione verrà completata dopo la restituzione in genere dal frame corrente per il frame del chiamante.</span><span class="sxs-lookup"><span data-stu-id="eb963-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="eb963-107">Se `StepOut` viene chiamato quando nel codice non gestito, il passaggio verrà completato quando il frame corrente viene restituito al codice gestito che lo hanno chiamato.</span><span class="sxs-lookup"><span data-stu-id="eb963-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="eb963-108">In .NET Framework versione 2.0, non usare `StepOut` con il flag STOP_UNMANAGED set perché avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="eb963-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="eb963-109">(Utilizzare [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) per impostare i flag per l'esecuzione di istruzioni.) Debugger di interoperabilità devono Esci da istruzione al codice nativo se stessi.</span><span class="sxs-lookup"><span data-stu-id="eb963-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb963-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eb963-110">Requirements</span></span>  
 <span data-ttu-id="eb963-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb963-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb963-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="eb963-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb963-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb963-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb963-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb963-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
