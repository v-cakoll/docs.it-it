---
title: Metodo ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: affe67006c9e37d55b0f9d107c92441da44c9ab8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138792"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="06749-102">Metodo ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="06749-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="06749-103">Ottiene l'indice dello slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="06749-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06749-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06749-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06749-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="06749-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="06749-106">[out] Un puntatore all'indice degli slot della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="06749-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06749-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="06749-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="06749-108">Se ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="06749-108">if successful.</span></span> `E_FAIL` <span data-ttu-id="06749-109">Se la variabile è un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="06749-109">if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06749-110">Note</span><span class="sxs-lookup"><span data-stu-id="06749-110">Remarks</span></span>  
 <span data-ttu-id="06749-111">L'indice degli slot gestiti di una variabile locale può essere usato per recuperare informazioni sui metadati della variabile.</span><span class="sxs-lookup"><span data-stu-id="06749-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06749-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="06749-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06749-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06749-113">Requirements</span></span>  
 <span data-ttu-id="06749-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06749-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06749-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06749-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06749-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06749-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="06749-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="06749-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="06749-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06749-118">See also</span></span>

- [<span data-ttu-id="06749-119">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="06749-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="06749-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="06749-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
