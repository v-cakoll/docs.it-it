---
title: Metodo ICorDebugVariableHome::GetSlotIndex
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetSlotIndex
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3eb8ed980fd523d0b0d29fbef770652a1d96146f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="f9328-102">Metodo ICorDebugVariableHome::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="f9328-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="f9328-103">Ottiene l'indice dello slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="f9328-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9328-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9328-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9328-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f9328-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="f9328-106">[out] Un puntatore per l'indice dello slot di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="f9328-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9328-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f9328-107">Return Value</span></span>  
 <span data-ttu-id="f9328-108">Il metodo restituisce i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="f9328-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="f9328-109">Valore</span><span class="sxs-lookup"><span data-stu-id="f9328-109">Value</span></span>|<span data-ttu-id="f9328-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9328-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="f9328-111">La chiamata al metodo ha restituito un valore di indice dello slot in `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="f9328-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="f9328-112">Corrente [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanza rappresenta un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="f9328-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9328-113">Note</span><span class="sxs-lookup"><span data-stu-id="f9328-113">Remarks</span></span>  
 <span data-ttu-id="f9328-114">L'indice dello slot può essere utilizzato per recuperare i metadati per questa variabile locale.</span><span class="sxs-lookup"><span data-stu-id="f9328-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9328-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9328-115">Requirements</span></span>  
 <span data-ttu-id="f9328-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9328-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9328-117">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f9328-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9328-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9328-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9328-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9328-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9328-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9328-120">See Also</span></span>  
 [<span data-ttu-id="f9328-121">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="f9328-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
