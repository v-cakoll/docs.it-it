---
title: Metodo ICorDebugVariableHome::GetSlotIndex
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61014e067b2afb8b7e4be0488ed6a3c7f1bd6fc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420700"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="bfa9c-102">Metodo ICorDebugVariableHome::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="bfa9c-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="bfa9c-103">Ottiene l'indice dello slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="bfa9c-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa9c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bfa9c-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bfa9c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bfa9c-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="bfa9c-106">[out] Un puntatore per l'indice dello slot di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="bfa9c-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfa9c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bfa9c-107">Return Value</span></span>  
 <span data-ttu-id="bfa9c-108">Il metodo restituisce i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="bfa9c-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="bfa9c-109">Valore</span><span class="sxs-lookup"><span data-stu-id="bfa9c-109">Value</span></span>|<span data-ttu-id="bfa9c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfa9c-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="bfa9c-111">La chiamata al metodo ha restituito un valore di indice dello slot in `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="bfa9c-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="bfa9c-112">Corrente [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanza rappresenta un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="bfa9c-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfa9c-113">Note</span><span class="sxs-lookup"><span data-stu-id="bfa9c-113">Remarks</span></span>  
 <span data-ttu-id="bfa9c-114">L'indice dello slot può essere utilizzato per recuperare i metadati per questa variabile locale.</span><span class="sxs-lookup"><span data-stu-id="bfa9c-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfa9c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bfa9c-115">Requirements</span></span>  
 <span data-ttu-id="bfa9c-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfa9c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfa9c-117">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="bfa9c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfa9c-118">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="bfa9c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfa9c-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfa9c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa9c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfa9c-120">See Also</span></span>  
 [<span data-ttu-id="bfa9c-121">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="bfa9c-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
