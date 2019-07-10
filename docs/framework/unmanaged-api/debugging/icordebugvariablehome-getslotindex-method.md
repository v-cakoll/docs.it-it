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
ms.openlocfilehash: 199c3ba5d5b9588db4c665070b4dec6266cefc2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760350"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="ce95a-102">Metodo ICorDebugVariableHome::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="ce95a-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="ce95a-103">Ottiene l'indice degli slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="ce95a-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce95a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce95a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce95a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce95a-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="ce95a-106">[out] Un puntatore all'indice dello slot di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="ce95a-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce95a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ce95a-107">Return Value</span></span>  
 <span data-ttu-id="ce95a-108">Il metodo restituisce i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="ce95a-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="ce95a-109">Value</span><span class="sxs-lookup"><span data-stu-id="ce95a-109">Value</span></span>|<span data-ttu-id="ce95a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce95a-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="ce95a-111">La chiamata al metodo ha restituito un valore di indice degli slot in `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="ce95a-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="ce95a-112">L'oggetto corrente [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanza rappresenta un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="ce95a-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce95a-113">Note</span><span class="sxs-lookup"><span data-stu-id="ce95a-113">Remarks</span></span>  
 <span data-ttu-id="ce95a-114">L'indice degli slot è utilizzabile per recuperare i metadati per questa variabile locale.</span><span class="sxs-lookup"><span data-stu-id="ce95a-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce95a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce95a-115">Requirements</span></span>  
 <span data-ttu-id="ce95a-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce95a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce95a-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce95a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce95a-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce95a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce95a-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce95a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce95a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce95a-120">See also</span></span>

- [<span data-ttu-id="ce95a-121">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="ce95a-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
