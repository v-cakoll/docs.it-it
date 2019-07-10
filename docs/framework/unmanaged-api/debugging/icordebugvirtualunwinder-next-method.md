---
title: 'Metodo icordebugvirtualunwinder:: Next'
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd12861b34d577a002fbf0cc8a7962b7bfc35fe1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775337"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="a4be8-102">Metodo icordebugvirtualunwinder:: Next</span><span class="sxs-lookup"><span data-stu-id="a4be8-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="a4be8-103">Avanza fino al contesto del chiamante.</span><span class="sxs-lookup"><span data-stu-id="a4be8-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4be8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4be8-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4be8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4be8-105">Parameters</span></span>  
 <span data-ttu-id="a4be8-106">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a4be8-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4be8-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a4be8-107">Return Value</span></span>  
 <span data-ttu-id="a4be8-108">`S_OK` se la rimozione è stata eseguita correttamente o `CORDBG_S_AT_END_OF_STACK` se la rimozione non riesce perché non vi sono più frame.</span><span class="sxs-lookup"><span data-stu-id="a4be8-108">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="a4be8-109">Se viene restituito un HRESULT, le API ICorDebug restituiranno `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="a4be8-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4be8-110">Note</span><span class="sxs-lookup"><span data-stu-id="a4be8-110">Remarks</span></span>  
 <span data-ttu-id="a4be8-111">Il percorso di chiamate nello stack deve garantire un progresso in avanti, in modo che un'eventuale chiamata a `Next` restituisca un errore HRESULT o `CORDBG_S_AT_END_OF_STACK`.</span><span class="sxs-lookup"><span data-stu-id="a4be8-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="a4be8-112">Restituzione `S_OK` per un periodo illimitato può provocare un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="a4be8-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4be8-113">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a4be8-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4be8-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4be8-114">Requirements</span></span>  
 <span data-ttu-id="a4be8-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4be8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4be8-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4be8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4be8-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4be8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4be8-118">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4be8-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4be8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4be8-119">See also</span></span>

- [<span data-ttu-id="a4be8-120">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="a4be8-120">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="a4be8-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a4be8-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
