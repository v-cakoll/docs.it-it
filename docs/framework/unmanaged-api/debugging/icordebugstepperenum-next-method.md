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
ms.openlocfilehash: 293d1a9cd93b5ce45105427e7df864ad8bfbe77a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379186"
---
# <a name="icordebugstepperenumnext-method"></a><span data-ttu-id="2792f-102">Metodo ICorDebugStepperEnum::Next</span><span class="sxs-lookup"><span data-stu-id="2792f-102">ICorDebugStepperEnum::Next Method</span></span>
<span data-ttu-id="2792f-103">Ottiene il numero specificato di istanze di ICorDebugStepper dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="2792f-103">Gets the specified number of ICorDebugStepper instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2792f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2792f-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2792f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2792f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2792f-106">in Numero di `ICorDebugStepper` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="2792f-106">[in] The number of `ICorDebugStepper` instances to be retrieved.</span></span>  
  
 `steppers`  
 <span data-ttu-id="2792f-107">out Matrice di puntatori, ciascuno dei quali punta a un `ICorDebugStepper` oggetto.</span><span class="sxs-lookup"><span data-stu-id="2792f-107">[out] An array of pointers, each of which points to an `ICorDebugStepper` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2792f-108">out Puntatore al numero di `ICorDebugStepper` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="2792f-108">[out] Pointer to the number of `ICorDebugStepper` instances actually returned.</span></span> <span data-ttu-id="2792f-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="2792f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2792f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2792f-110">Requirements</span></span>  
 <span data-ttu-id="2792f-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2792f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2792f-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2792f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2792f-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2792f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2792f-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2792f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
