---
title: Metodo ICorDebugStepper::SetRangeIL
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetRangeIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9b4ee64022374cb4e1950acceb3f32925b736bb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478687"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="dad63-102">Metodo ICorDebugStepper::SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="dad63-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="dad63-103">Imposta un valore che specifica se le chiamate a [StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) passare i valori relativi al codice nativo o relativo alla Microsoft a livello intermedio codice language (MSIL) del metodo che è in corso rientri argomento tramite.</span><span class="sxs-lookup"><span data-stu-id="dad63-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dad63-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dad63-104">Syntax</span></span>  
  
```  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dad63-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dad63-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="dad63-106">[in] Impostare su `true` per specificare che gli intervalli sono relativi al codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="dad63-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="dad63-107">Impostare su `false` per specificare che gli intervalli sono rispetto al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="dad63-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="dad63-108">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="dad63-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dad63-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dad63-109">Requirements</span></span>  
 <span data-ttu-id="dad63-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dad63-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dad63-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dad63-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dad63-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dad63-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dad63-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dad63-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
