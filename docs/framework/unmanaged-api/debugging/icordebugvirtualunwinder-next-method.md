---
title: Metodo ICorDebugVirtualUnwinder::Next
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
ms.openlocfilehash: 55f10a6148f0b11cf74492afe947d5921a1d1458
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396422"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="8fc13-102">Metodo ICorDebugVirtualUnwinder::Next</span><span class="sxs-lookup"><span data-stu-id="8fc13-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="8fc13-103">Avanza fino al contesto del chiamante.</span><span class="sxs-lookup"><span data-stu-id="8fc13-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fc13-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8fc13-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fc13-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8fc13-105">Parameters</span></span>  
 <span data-ttu-id="8fc13-106">No.</span><span class="sxs-lookup"><span data-stu-id="8fc13-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fc13-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8fc13-107">Return Value</span></span>  
 <span data-ttu-id="8fc13-108">`S_OK` se la rimozione è stata eseguita correttamente o `CORDBG_S_AT_END_OF_STACK` se la rimozione non riesce perché non vi sono più frame.</span><span class="sxs-lookup"><span data-stu-id="8fc13-108">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="8fc13-109">Se viene restituito un HRESULT, le API ICorDebug restituiranno `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="8fc13-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fc13-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="8fc13-110">Remarks</span></span>  
 <span data-ttu-id="8fc13-111">Il percorso di chiamate nello stack deve garantire un progresso in avanti, in modo che un'eventuale chiamata a `Next` restituisca un errore HRESULT o `CORDBG_S_AT_END_OF_STACK`.</span><span class="sxs-lookup"><span data-stu-id="8fc13-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="8fc13-112">La restituzione illimitata `S_OK` può causare un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="8fc13-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8fc13-113">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8fc13-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fc13-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8fc13-114">Requirements</span></span>  
 <span data-ttu-id="8fc13-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fc13-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fc13-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8fc13-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fc13-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fc13-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fc13-118">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fc13-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc13-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="8fc13-119">See also</span></span>

- [<span data-ttu-id="8fc13-120">Interfaccia ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="8fc13-120">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="8fc13-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8fc13-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
