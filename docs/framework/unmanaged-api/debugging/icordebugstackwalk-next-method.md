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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 367c43dc08722288dc3b32b5133f7770ffc3a27c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423104"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="665cf-102">Metodo ICorDebugStackWalk::Next</span><span class="sxs-lookup"><span data-stu-id="665cf-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="665cf-103">Sposta il [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) oggetto al frame successivo.</span><span class="sxs-lookup"><span data-stu-id="665cf-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="665cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="665cf-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="665cf-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="665cf-105">Return Value</span></span>  
 <span data-ttu-id="665cf-106">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="665cf-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="665cf-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="665cf-107">HRESULT</span></span>|<span data-ttu-id="665cf-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="665cf-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="665cf-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="665cf-109">S_OK</span></span>|<span data-ttu-id="665cf-110">Il runtime rimosso correttamente fino al frame successivo (vedere la sezione Osservazioni).</span><span class="sxs-lookup"><span data-stu-id="665cf-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="665cf-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="665cf-111">E_FAIL</span></span>|<span data-ttu-id="665cf-112">Il `ICorDebugStackWalk` non è stato possibile avanzare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="665cf-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="665cf-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="665cf-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="665cf-114">In seguito a questa rimozione è stata raggiunta la fine dello stack.</span><span class="sxs-lookup"><span data-stu-id="665cf-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="665cf-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="665cf-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="665cf-116">Puntatore ai frame è già alla fine dello stack. Pertanto, non è possibile accedere ulteriori frame.</span><span class="sxs-lookup"><span data-stu-id="665cf-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="665cf-117">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="665cf-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="665cf-118">Note</span><span class="sxs-lookup"><span data-stu-id="665cf-118">Remarks</span></span>  
 <span data-ttu-id="665cf-119">Il `Next` metodo anticipi il `ICorDebugStackWalk` dell'oggetto al frame chiamante solo se il runtime può rimuovere il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="665cf-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="665cf-120">In caso contrario, l'oggetto passa al frame successivo che il runtime è in grado di rimozione.</span><span class="sxs-lookup"><span data-stu-id="665cf-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="665cf-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="665cf-121">Requirements</span></span>  
 <span data-ttu-id="665cf-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="665cf-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="665cf-123">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="665cf-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="665cf-124">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="665cf-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="665cf-125">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="665cf-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="665cf-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="665cf-126">See Also</span></span>  
 [<span data-ttu-id="665cf-127">Interfaccia ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="665cf-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 [<span data-ttu-id="665cf-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="665cf-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="665cf-129">Debug</span><span class="sxs-lookup"><span data-stu-id="665cf-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
