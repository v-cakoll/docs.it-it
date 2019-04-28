---
title: Metodo ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: affe67006c9e37d55b0f9d107c92441da44c9ab8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768823"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="1b1bb-102">Metodo ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="1b1bb-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="1b1bb-103">Ottiene l'indice dello slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="1b1bb-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b1bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b1bb-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b1bb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b1bb-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="1b1bb-106">[out] Un puntatore all'indice degli slot della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="1b1bb-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b1bb-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1b1bb-107">Return Value</span></span>  
 <span data-ttu-id="1b1bb-108">`S_OK` se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="1b1bb-108">`S_OK` if successful.</span></span> <span data-ttu-id="1b1bb-109">`E_FAIL` se la variabile è un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="1b1bb-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b1bb-110">Note</span><span class="sxs-lookup"><span data-stu-id="1b1bb-110">Remarks</span></span>  
 <span data-ttu-id="1b1bb-111">L'indice degli slot gestiti di una variabile locale può essere usato per recuperare informazioni sui metadati della variabile.</span><span class="sxs-lookup"><span data-stu-id="1b1bb-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b1bb-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1b1bb-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b1bb-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b1bb-113">Requirements</span></span>  
 <span data-ttu-id="1b1bb-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b1bb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b1bb-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b1bb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b1bb-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b1bb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b1bb-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b1bb-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b1bb-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b1bb-118">See also</span></span>

- [<span data-ttu-id="1b1bb-119">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="1b1bb-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="1b1bb-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1b1bb-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
