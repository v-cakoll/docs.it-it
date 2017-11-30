---
title: Metodo ICorDebugVariableHome::GetArgumentIndex
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetArgumentIndex
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 175e45758d26d8168279c825d41ee58d049edf0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="836e0-102">Metodo ICorDebugVariableHome::GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="836e0-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="836e0-103">Ottiene l'indice di un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="836e0-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="836e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="836e0-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="836e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="836e0-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="836e0-106">[out] Un puntatore all'indice di argomento.</span><span class="sxs-lookup"><span data-stu-id="836e0-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="836e0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="836e0-107">Return Value</span></span>  
 <span data-ttu-id="836e0-108">Il metodo restituisce i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="836e0-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="836e0-109">Valore</span><span class="sxs-lookup"><span data-stu-id="836e0-109">Value</span></span>|<span data-ttu-id="836e0-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="836e0-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="836e0-111">La chiamata al metodo ha restituito un indice di argomento valido.</span><span class="sxs-lookup"><span data-stu-id="836e0-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="836e0-112">Corrente [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanza rappresenta una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="836e0-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="836e0-113">Note</span><span class="sxs-lookup"><span data-stu-id="836e0-113">Remarks</span></span>  
 <span data-ttu-id="836e0-114">L'indice dell'argomento è utilizzabile per recuperare i metadati per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="836e0-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="836e0-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="836e0-115">Requirements</span></span>  
 <span data-ttu-id="836e0-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="836e0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="836e0-117">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="836e0-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="836e0-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="836e0-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="836e0-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="836e0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="836e0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="836e0-120">See Also</span></span>  
 [<span data-ttu-id="836e0-121">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="836e0-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
