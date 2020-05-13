---
title: Metodo ICorDebugStackWalk::Next
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
ms.openlocfilehash: b89e968e9b12943c8192af3b280f8bd321a02110
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378783"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="039f3-102">Metodo ICorDebugStackWalk::Next</span><span class="sxs-lookup"><span data-stu-id="039f3-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="039f3-103">Sposta l'oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) nel frame successivo.</span><span class="sxs-lookup"><span data-stu-id="039f3-103">Moves the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="039f3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="039f3-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="039f3-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="039f3-105">Return Value</span></span>  
 <span data-ttu-id="039f3-106">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="039f3-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="039f3-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="039f3-107">HRESULT</span></span>|<span data-ttu-id="039f3-108">Description</span><span class="sxs-lookup"><span data-stu-id="039f3-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="039f3-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="039f3-109">S_OK</span></span>|<span data-ttu-id="039f3-110">Il runtime è stato rimosso fino al frame successivo. vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="039f3-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="039f3-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="039f3-111">E_FAIL</span></span>|<span data-ttu-id="039f3-112">`ICorDebugStackWalk`Impossibile avanzare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="039f3-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="039f3-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="039f3-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="039f3-114">È stata raggiunta la fine dello stack come risultato della rimozione.</span><span class="sxs-lookup"><span data-stu-id="039f3-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="039f3-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="039f3-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="039f3-116">Il puntatore al frame è già alla fine dello stack. non è pertanto possibile accedere a nessun frame aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="039f3-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="039f3-117">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="039f3-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="039f3-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="039f3-118">Remarks</span></span>  
 <span data-ttu-id="039f3-119">Il `Next` metodo sposta l' `ICorDebugStackWalk` oggetto al frame chiamante solo se il runtime è in grado di rimuovere il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="039f3-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="039f3-120">In caso contrario, l'oggetto avanza al frame successivo che il runtime è in grado di rimuovere.</span><span class="sxs-lookup"><span data-stu-id="039f3-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="039f3-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="039f3-121">Requirements</span></span>  
 <span data-ttu-id="039f3-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="039f3-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="039f3-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="039f3-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="039f3-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="039f3-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="039f3-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="039f3-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="039f3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="039f3-126">See also</span></span>

- [<span data-ttu-id="039f3-127">Interfaccia ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="039f3-127">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="039f3-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="039f3-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="039f3-129">Debug</span><span class="sxs-lookup"><span data-stu-id="039f3-129">Debugging</span></span>](index.md)
