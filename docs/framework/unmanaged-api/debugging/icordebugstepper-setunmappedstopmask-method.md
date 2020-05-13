---
title: Metodo ICorDebugStepper::SetUnmappedStopMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
ms.openlocfilehash: ef458fda8e8b7e75f92a4b3c06eabec106180d23
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379257"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="be07e-102">Metodo ICorDebugStepper::SetUnmappedStopMask</span><span class="sxs-lookup"><span data-stu-id="be07e-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="be07e-103">Imposta un valore che specifica il tipo di codice non mappato in cui l'esecuzione si arresterà.</span><span class="sxs-lookup"><span data-stu-id="be07e-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be07e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be07e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be07e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="be07e-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="be07e-106">in Valore dell'enumerazione CorDebugUnmappedStop che specifica il tipo di codice di cui non è stato eseguito il mapping in cui l'esecuzione viene interrotta dal debugger.</span><span class="sxs-lookup"><span data-stu-id="be07e-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="be07e-107">Il valore predefinito è STOP_OTHER_UNMAPPED.</span><span class="sxs-lookup"><span data-stu-id="be07e-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="be07e-108">Il valore STOP_UNMANAGED è valido solo con il debug di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="be07e-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be07e-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="be07e-109">Remarks</span></span>  
 <span data-ttu-id="be07e-110">Quando il debugger trova una compilazione JIT (just-in-Time) che non dispone di un mapping corrispondente a MSIL (Microsoft Intermediate Language), l'esecuzione viene interrotta se il flag che specifica il tipo di codice non mappato è stato impostato. in caso contrario, l'esecuzione di un'istruzione continua in modo trasparente.</span><span class="sxs-lookup"><span data-stu-id="be07e-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="be07e-111">Se il debugger non usa un stepper per accedere a un metodo, non verrà necessariamente eseguito il codice non mappato.</span><span class="sxs-lookup"><span data-stu-id="be07e-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be07e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be07e-112">Requirements</span></span>  
 <span data-ttu-id="be07e-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be07e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be07e-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be07e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be07e-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be07e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be07e-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be07e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
