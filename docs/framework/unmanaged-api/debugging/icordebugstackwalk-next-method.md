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
ms.openlocfilehash: b76d17337408653d130ee0cb8594e759bdade37c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791874"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="a8fa4-102">Metodo ICorDebugStackWalk::Next</span><span class="sxs-lookup"><span data-stu-id="a8fa4-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="a8fa4-103">Sposta l'oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) nel frame successivo.</span><span class="sxs-lookup"><span data-stu-id="a8fa4-103">Moves the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8fa4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8fa4-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a8fa4-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a8fa4-105">Return Value</span></span>  
 <span data-ttu-id="a8fa4-106">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="a8fa4-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a8fa4-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a8fa4-107">HRESULT</span></span>|<span data-ttu-id="a8fa4-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8fa4-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a8fa4-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="a8fa4-109">S_OK</span></span>|<span data-ttu-id="a8fa4-110">Il runtime è stato rimosso fino al frame successivo. vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="a8fa4-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="a8fa4-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a8fa4-111">E_FAIL</span></span>|<span data-ttu-id="a8fa4-112">Impossibile avanzare l'oggetto `ICorDebugStackWalk`.</span><span class="sxs-lookup"><span data-stu-id="a8fa4-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="a8fa4-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="a8fa4-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="a8fa4-114">È stata raggiunta la fine dello stack come risultato della rimozione.</span><span class="sxs-lookup"><span data-stu-id="a8fa4-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="a8fa4-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="a8fa4-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="a8fa4-116">Il puntatore al frame è già alla fine dello stack. non è pertanto possibile accedere a nessun frame aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="a8fa4-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="a8fa4-117">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="a8fa4-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8fa4-118">Note</span><span class="sxs-lookup"><span data-stu-id="a8fa4-118">Remarks</span></span>  
 <span data-ttu-id="a8fa4-119">Il metodo `Next` sposta l'oggetto `ICorDebugStackWalk` al frame chiamante solo se il runtime è in grado di rimuovere il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="a8fa4-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="a8fa4-120">In caso contrario, l'oggetto avanza al frame successivo che il runtime è in grado di rimuovere.</span><span class="sxs-lookup"><span data-stu-id="a8fa4-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8fa4-121">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a8fa4-121">Requirements</span></span>  
 <span data-ttu-id="a8fa4-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8fa4-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8fa4-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8fa4-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8fa4-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8fa4-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8fa4-125">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8fa4-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8fa4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8fa4-126">See also</span></span>

- [<span data-ttu-id="a8fa4-127">Interfaccia ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="a8fa4-127">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="a8fa4-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a8fa4-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a8fa4-129">Debug</span><span class="sxs-lookup"><span data-stu-id="a8fa4-129">Debugging</span></span>](index.md)
