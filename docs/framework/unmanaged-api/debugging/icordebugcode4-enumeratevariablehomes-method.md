---
title: 'Metodo interfacce icordebugcode4:: EnumerateVariableHomes'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: 850cbd2367dddd9f46375817e271cb8e7183cf64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121093"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="7e0f5-102">Metodo interfacce icordebugcode4:: EnumerateVariableHomes</span><span class="sxs-lookup"><span data-stu-id="7e0f5-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="7e0f5-103">Ottiene un enumeratore per le variabili e gli argomenti locali in una funzione.</span><span class="sxs-lookup"><span data-stu-id="7e0f5-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e0f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e0f5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e0f5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7e0f5-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="7e0f5-106">Puntatore all'indirizzo di un oggetto interfaccia [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) che è un enumeratore per le variabili e gli argomenti locali in una funzione.</span><span class="sxs-lookup"><span data-stu-id="7e0f5-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e0f5-107">Note</span><span class="sxs-lookup"><span data-stu-id="7e0f5-107">Remarks</span></span>  
 <span data-ttu-id="7e0f5-108">L'oggetto interfaccia [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) è un enumeratore standard derivato dall'interfaccia "ICorDebugEnum" che consente di enumerare gli oggetti [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7e0f5-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="7e0f5-109">La raccolta può includere più oggetti [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) per lo stesso indice di slot o di argomento se hanno case diverse in punti diversi della funzione.</span><span class="sxs-lookup"><span data-stu-id="7e0f5-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e0f5-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e0f5-110">Requirements</span></span>  
 <span data-ttu-id="7e0f5-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e0f5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e0f5-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e0f5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e0f5-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e0f5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e0f5-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e0f5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e0f5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e0f5-115">See also</span></span>

- [<span data-ttu-id="7e0f5-116">Interfaccia ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="7e0f5-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [<span data-ttu-id="7e0f5-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7e0f5-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
