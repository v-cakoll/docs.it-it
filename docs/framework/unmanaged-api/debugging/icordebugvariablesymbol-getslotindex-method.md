---
title: Metodo ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c7b70638b963968fb3ed7e294f1767718f9bc34
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501292"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="a8906-102">Metodo ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="a8906-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="a8906-103">Ottiene l'indice dello slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="a8906-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8906-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8906-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8906-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a8906-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="a8906-106">[out] Un puntatore all'indice degli slot della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="a8906-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8906-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a8906-107">Return Value</span></span>  
 <span data-ttu-id="a8906-108">`S_OK` se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="a8906-108">`S_OK` if successful.</span></span> <span data-ttu-id="a8906-109">`E_FAIL` se la variabile è un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="a8906-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8906-110">Note</span><span class="sxs-lookup"><span data-stu-id="a8906-110">Remarks</span></span>  
 <span data-ttu-id="a8906-111">L'indice degli slot gestiti di una variabile locale può essere usato per recuperare informazioni sui metadati della variabile.</span><span class="sxs-lookup"><span data-stu-id="a8906-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8906-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a8906-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8906-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a8906-113">Requirements</span></span>  
 <span data-ttu-id="a8906-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8906-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8906-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8906-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8906-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8906-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8906-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8906-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8906-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8906-118">See also</span></span>
- [<span data-ttu-id="a8906-119">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="a8906-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="a8906-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a8906-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
