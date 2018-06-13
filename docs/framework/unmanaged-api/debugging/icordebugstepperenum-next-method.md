---
title: Metodo ICorDebugStepperEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum::Next
helpviewer_keywords:
- Next method, ICorDebugStepperEnum interface [.NET Framework debugging]
- ICorDebugStepperEnum::Next method [.NET Framework debugging]
ms.assetid: d0ea0f30-e8d2-48b0-8477-e1a029ceb4dd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bd62e4c5476aacf736f2ddfea008790861d931c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419617"
---
# <a name="icordebugstepperenumnext-method"></a><span data-ttu-id="db39b-102">Metodo ICorDebugStepperEnum::Next</span><span class="sxs-lookup"><span data-stu-id="db39b-102">ICorDebugStepperEnum::Next Method</span></span>
<span data-ttu-id="db39b-103">Ottiene il numero specificato di istanze di ICorDebugStepper nell'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="db39b-103">Gets the specified number of ICorDebugStepper instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db39b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db39b-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db39b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="db39b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="db39b-106">[in] Il numero di `ICorDebugStepper` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="db39b-106">[in] The number of `ICorDebugStepper` instances to be retrieved.</span></span>  
  
 `steppers`  
 <span data-ttu-id="db39b-107">[out] Matrice di puntatori, ognuno dei quali punta a un `ICorDebugStepper` oggetto.</span><span class="sxs-lookup"><span data-stu-id="db39b-107">[out] An array of pointers, each of which points to an `ICorDebugStepper` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="db39b-108">[out] Puntatore al numero di `ICorDebugStepper` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="db39b-108">[out] Pointer to the number of `ICorDebugStepper` instances actually returned.</span></span> <span data-ttu-id="db39b-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="db39b-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db39b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db39b-110">Requirements</span></span>  
 <span data-ttu-id="db39b-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db39b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db39b-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="db39b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db39b-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="db39b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db39b-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db39b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
