---
title: Metodo ICorDebugVariableSymbol::GetSlotIndex
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: abb84e529768e0be44883511bb89703a4c3199df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="a2ebb-102">Metodo ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="a2ebb-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="a2ebb-103">Ottiene l'indice dello slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="a2ebb-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2ebb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2ebb-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2ebb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a2ebb-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="a2ebb-106">[out] Un puntatore all'indice degli slot della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="a2ebb-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2ebb-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a2ebb-107">Return Value</span></span>  
 <span data-ttu-id="a2ebb-108">`S_OK` se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="a2ebb-108">`S_OK` if successful.</span></span> <span data-ttu-id="a2ebb-109">`E_FAIL` se la variabile è un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="a2ebb-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2ebb-110">Note</span><span class="sxs-lookup"><span data-stu-id="a2ebb-110">Remarks</span></span>  
 <span data-ttu-id="a2ebb-111">L'indice degli slot gestiti di una variabile locale può essere usato per recuperare informazioni sui metadati della variabile.</span><span class="sxs-lookup"><span data-stu-id="a2ebb-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2ebb-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a2ebb-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2ebb-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2ebb-113">Requirements</span></span>  
 <span data-ttu-id="a2ebb-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2ebb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2ebb-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a2ebb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2ebb-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2ebb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2ebb-117">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2ebb-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ebb-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2ebb-118">See Also</span></span>  
 [<span data-ttu-id="a2ebb-119">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="a2ebb-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="a2ebb-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a2ebb-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
