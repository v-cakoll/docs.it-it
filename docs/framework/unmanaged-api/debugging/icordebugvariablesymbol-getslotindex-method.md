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
ms.openlocfilehash: d632bc792152afcfc94b51235dc0699fb3efc245
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="3ba5a-102">Metodo ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="3ba5a-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="3ba5a-103">Ottiene l'indice dello slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="3ba5a-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ba5a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ba5a-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ba5a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3ba5a-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="3ba5a-106">[out] Un puntatore all'indice degli slot della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="3ba5a-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ba5a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3ba5a-107">Return Value</span></span>  
 <span data-ttu-id="3ba5a-108">`S_OK` se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="3ba5a-108">`S_OK` if successful.</span></span> <span data-ttu-id="3ba5a-109">`E_FAIL` se la variabile è un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="3ba5a-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ba5a-110">Note</span><span class="sxs-lookup"><span data-stu-id="3ba5a-110">Remarks</span></span>  
 <span data-ttu-id="3ba5a-111">L'indice degli slot gestiti di una variabile locale può essere usato per recuperare informazioni sui metadati della variabile.</span><span class="sxs-lookup"><span data-stu-id="3ba5a-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ba5a-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3ba5a-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ba5a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ba5a-113">Requirements</span></span>  
 <span data-ttu-id="3ba5a-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ba5a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ba5a-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3ba5a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ba5a-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ba5a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ba5a-117">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ba5a-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ba5a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ba5a-118">See Also</span></span>  
 [<span data-ttu-id="3ba5a-119">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="3ba5a-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="3ba5a-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3ba5a-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
