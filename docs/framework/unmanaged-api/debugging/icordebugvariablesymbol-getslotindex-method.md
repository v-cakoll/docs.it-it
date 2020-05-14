---
title: Metodo ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 251a978e96ff396d0d9d9282ded7f8a25ae0ba0b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397090"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="14d3d-102">Metodo ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="14d3d-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="14d3d-103">Ottiene l'indice dello slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="14d3d-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14d3d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14d3d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14d3d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="14d3d-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="14d3d-106">[out] Un puntatore all'indice degli slot della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="14d3d-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14d3d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="14d3d-107">Return Value</span></span>  
 <span data-ttu-id="14d3d-108">`S_OK` se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="14d3d-108">`S_OK` if successful.</span></span> <span data-ttu-id="14d3d-109">`E_FAIL` se la variabile è un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="14d3d-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14d3d-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="14d3d-110">Remarks</span></span>  
 <span data-ttu-id="14d3d-111">L'indice degli slot gestiti di una variabile locale può essere usato per recuperare informazioni sui metadati della variabile.</span><span class="sxs-lookup"><span data-stu-id="14d3d-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14d3d-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="14d3d-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14d3d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="14d3d-113">Requirements</span></span>  
 <span data-ttu-id="14d3d-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14d3d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14d3d-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14d3d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14d3d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14d3d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14d3d-117">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14d3d-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14d3d-118">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="14d3d-118">See also</span></span>

- [<span data-ttu-id="14d3d-119">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="14d3d-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="14d3d-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="14d3d-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
