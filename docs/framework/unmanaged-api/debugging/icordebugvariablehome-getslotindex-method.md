---
title: 'Metodo ICorDebugVariableHome:: GetSlotIndex'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
ms.openlocfilehash: dfc2e91599e7f05d90d56af07b71313e9eecaa51
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121058"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="67007-102">Metodo ICorDebugVariableHome:: GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="67007-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="67007-103">Ottiene l'indice di slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="67007-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67007-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67007-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67007-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="67007-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="67007-106">out Puntatore all'indice di slot di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="67007-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67007-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="67007-107">Return Value</span></span>  
 <span data-ttu-id="67007-108">Il metodo restituisce i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="67007-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="67007-109">Value</span><span class="sxs-lookup"><span data-stu-id="67007-109">Value</span></span>|<span data-ttu-id="67007-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67007-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="67007-111">La chiamata al metodo ha restituito un valore di indice di slot in `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="67007-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="67007-112">L'istanza corrente di [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) rappresenta un argomento della funzione.</span><span class="sxs-lookup"><span data-stu-id="67007-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67007-113">Note</span><span class="sxs-lookup"><span data-stu-id="67007-113">Remarks</span></span>  
 <span data-ttu-id="67007-114">Lo slot-index può essere usato per recuperare i metadati per la variabile locale.</span><span class="sxs-lookup"><span data-stu-id="67007-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67007-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67007-115">Requirements</span></span>  
 <span data-ttu-id="67007-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67007-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67007-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67007-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67007-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67007-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67007-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67007-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67007-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67007-120">See also</span></span>

- [<span data-ttu-id="67007-121">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="67007-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
