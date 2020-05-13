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
ms.openlocfilehash: 7fadffaab6eee5beed513f339ea300acef5a1c6b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378998"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="9b137-102">Metodo ICorDebugStepper::SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="9b137-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="9b137-103">Imposta un valore che specifica se le chiamate a [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) passano valori di argomento relativi al codice nativo o rispetto al codice MSIL (Microsoft Intermediate Language) del metodo di cui è in corso il passaggio.</span><span class="sxs-lookup"><span data-stu-id="9b137-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b137-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b137-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b137-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9b137-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="9b137-106">in Impostare su `true` per specificare che gli intervalli sono relativi al codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="9b137-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="9b137-107">Impostare su `false` per specificare che gli intervalli sono relativi al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="9b137-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="9b137-108">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="9b137-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b137-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9b137-109">Requirements</span></span>  
 <span data-ttu-id="9b137-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b137-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b137-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b137-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b137-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b137-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b137-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b137-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
