---
title: Metodo ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1657ed4d8326b573fe081b98c1fc414e231ac465
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420622"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="93cda-102">Metodo ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="93cda-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="93cda-103">Ottiene l'indice dello slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="93cda-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93cda-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93cda-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93cda-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="93cda-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="93cda-106">[out] Un puntatore all'indice degli slot della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="93cda-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93cda-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="93cda-107">Return Value</span></span>  
 <span data-ttu-id="93cda-108">`S_OK` se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="93cda-108">`S_OK` if successful.</span></span> <span data-ttu-id="93cda-109">`E_FAIL` se la variabile è un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="93cda-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93cda-110">Note</span><span class="sxs-lookup"><span data-stu-id="93cda-110">Remarks</span></span>  
 <span data-ttu-id="93cda-111">L'indice degli slot gestiti di una variabile locale può essere usato per recuperare informazioni sui metadati della variabile.</span><span class="sxs-lookup"><span data-stu-id="93cda-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93cda-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="93cda-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93cda-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93cda-113">Requirements</span></span>  
 <span data-ttu-id="93cda-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93cda-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93cda-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="93cda-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93cda-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="93cda-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93cda-117">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93cda-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93cda-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93cda-118">See Also</span></span>  
 [<span data-ttu-id="93cda-119">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="93cda-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="93cda-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="93cda-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
