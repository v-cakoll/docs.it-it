---
title: Metodo ICorDebugStepper::StepRange
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
ms.openlocfilehash: b040d9454a5a3a0d550bb645953c783357419f73
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379486"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="34514-102">Metodo ICorDebugStepper::StepRange</span><span class="sxs-lookup"><span data-stu-id="34514-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="34514-103">Fa in modo che questo ICorDebugStepper a un singolo passaggio tramite il thread contenitore e restituisca quando raggiunge il codice oltre l'ultimo intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="34514-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34514-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34514-104">Syntax</span></span>  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34514-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="34514-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="34514-106">in Impostare su `true` per eseguire un'istruzione in una funzione chiamata all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="34514-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="34514-107">Impostare su `false` per eseguire l'istruzione/routine della funzione.</span><span class="sxs-lookup"><span data-stu-id="34514-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="34514-108">in Matrice di strutture di COR_DEBUG_STEP_RANGE, ognuna delle quali specifica un intervallo.</span><span class="sxs-lookup"><span data-stu-id="34514-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="34514-109">[in] Dimensione della matrice `ranges`.</span><span class="sxs-lookup"><span data-stu-id="34514-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34514-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="34514-110">Remarks</span></span>  
 <span data-ttu-id="34514-111">Il `StepRange` metodo funziona come il metodo [ICorDebugStepper:: Step](icordebugstepper-step-method.md) , ad eccezione del fatto che non viene completato fino a quando non viene raggiunto il codice non compreso nell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="34514-111">The `StepRange` method works like the [ICorDebugStepper::Step](icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="34514-112">Questa operazione può essere più efficiente rispetto all'esecuzione di un'istruzione alla volta.</span><span class="sxs-lookup"><span data-stu-id="34514-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="34514-113">Gli intervalli vengono specificati come un elenco di coppie di offset dall'inizio del frame del stepper.</span><span class="sxs-lookup"><span data-stu-id="34514-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="34514-114">Gli intervalli sono relativi al codice MSIL (Microsoft Intermediate Language) di un metodo.</span><span class="sxs-lookup"><span data-stu-id="34514-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="34514-115">Chiamare [ICorDebugStepper:: SetRangeIL](icordebugstepper-setrangeil-method.md) con `false` per rendere gli intervalli relativi al codice nativo di un metodo.</span><span class="sxs-lookup"><span data-stu-id="34514-115">Call [ICorDebugStepper::SetRangeIL](icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34514-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34514-116">Requirements</span></span>  
 <span data-ttu-id="34514-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34514-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34514-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34514-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34514-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34514-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34514-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34514-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
