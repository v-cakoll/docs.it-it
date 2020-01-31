---
title: Metodo ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 3510daffb55bdb22aa5f835bf27157e7c8428509
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790899"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="c7ad8-102">Metodo ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="c7ad8-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="c7ad8-103">Ottiene l'indice dello slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="c7ad8-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7ad8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7ad8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7ad8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c7ad8-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="c7ad8-106">[out] Un puntatore all'indice degli slot della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="c7ad8-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7ad8-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c7ad8-107">Return Value</span></span>  
 <span data-ttu-id="c7ad8-108">`S_OK` se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="c7ad8-108">`S_OK` if successful.</span></span> <span data-ttu-id="c7ad8-109">`E_FAIL` se la variabile è un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="c7ad8-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7ad8-110">Note</span><span class="sxs-lookup"><span data-stu-id="c7ad8-110">Remarks</span></span>  
 <span data-ttu-id="c7ad8-111">L'indice degli slot gestiti di una variabile locale può essere usato per recuperare informazioni sui metadati della variabile.</span><span class="sxs-lookup"><span data-stu-id="c7ad8-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7ad8-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c7ad8-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7ad8-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="c7ad8-113">Requirements</span></span>  
 <span data-ttu-id="c7ad8-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7ad8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7ad8-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7ad8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7ad8-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7ad8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7ad8-117">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7ad8-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ad8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7ad8-118">See also</span></span>

- [<span data-ttu-id="c7ad8-119">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="c7ad8-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="c7ad8-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c7ad8-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
