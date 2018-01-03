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
ms.workload: dotnet
ms.openlocfilehash: 739d4d787858f64871269ea9bd467bc49424fbae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="debba-102">Metodo ICorDebugVariableHome::GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="debba-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="debba-103">Ottiene l'indice di un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="debba-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="debba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="debba-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="debba-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="debba-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="debba-106">[out] Un puntatore all'indice di argomento.</span><span class="sxs-lookup"><span data-stu-id="debba-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="debba-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="debba-107">Return Value</span></span>  
 <span data-ttu-id="debba-108">Il metodo restituisce i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="debba-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="debba-109">Valore</span><span class="sxs-lookup"><span data-stu-id="debba-109">Value</span></span>|<span data-ttu-id="debba-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="debba-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="debba-111">La chiamata al metodo ha restituito un indice di argomento valido.</span><span class="sxs-lookup"><span data-stu-id="debba-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="debba-112">Corrente [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanza rappresenta una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="debba-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="debba-113">Note</span><span class="sxs-lookup"><span data-stu-id="debba-113">Remarks</span></span>  
 <span data-ttu-id="debba-114">L'indice dell'argomento è utilizzabile per recuperare i metadati per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="debba-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="debba-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="debba-115">Requirements</span></span>  
 <span data-ttu-id="debba-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="debba-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="debba-117">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="debba-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="debba-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="debba-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="debba-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="debba-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="debba-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="debba-120">See Also</span></span>  
 [<span data-ttu-id="debba-121">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="debba-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
