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
ms.openlocfilehash: b819f1f02870a8a85a531d7d341cbaf488a1ccd6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093753"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="2b4c4-102">Metodo ICorDebugVariableHome::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="2b4c4-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="2b4c4-103">Ottiene l'indice degli slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b4c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b4c4-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b4c4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2b4c4-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="2b4c4-106">[out] Un puntatore all'indice dello slot di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b4c4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2b4c4-107">Return Value</span></span>  
 <span data-ttu-id="2b4c4-108">Il metodo restituisce i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="2b4c4-109">Value</span><span class="sxs-lookup"><span data-stu-id="2b4c4-109">Value</span></span>|<span data-ttu-id="2b4c4-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b4c4-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="2b4c4-111">La chiamata al metodo ha restituito un valore di indice degli slot in `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="2b4c4-112">L'oggetto corrente [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanza rappresenta un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b4c4-113">Note</span><span class="sxs-lookup"><span data-stu-id="2b4c4-113">Remarks</span></span>  
 <span data-ttu-id="2b4c4-114">L'indice degli slot è utilizzabile per recuperare i metadati per questa variabile locale.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b4c4-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2b4c4-115">Requirements</span></span>  
 <span data-ttu-id="2b4c4-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b4c4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b4c4-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b4c4-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b4c4-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b4c4-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2b4c4-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2b4c4-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2b4c4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b4c4-120">See also</span></span>

- [<span data-ttu-id="2b4c4-121">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="2b4c4-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
