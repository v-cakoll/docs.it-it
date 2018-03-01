---
title: Metodo ICorDebugComObjectValue::GetCachedInterfaceTypes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e99054b32deb6b2e4b621ea4c193e416220f8f6f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="d5957-102">Metodo ICorDebugComObjectValue::GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="d5957-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="d5957-103">Fornisce un enumeratore per i tipi di interfaccia che l'oggetto corrente è stato eseguito il cast a o utilizzato come.</span><span class="sxs-lookup"><span data-stu-id="d5957-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5957-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5957-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5957-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d5957-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="d5957-106">[in] Un valore che indica se il metodo restituisce solo [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfacce (`IInspectable` interfacce) o tutte le interfacce COM memorizzati nella cache dal runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="d5957-106">[in] A value that indicates whether the method returns only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="d5957-107">[out] Un puntatore all'indirizzo di un enumeratore ICorDebugTypeEnum che fornisce accesso agli oggetti ICorDebugType che rappresentano i tipi di interfaccia memorizzati nella cache filtrata in base a `bIInspectableOnly`.</span><span class="sxs-lookup"><span data-stu-id="d5957-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5957-108">Note</span><span class="sxs-lookup"><span data-stu-id="d5957-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5957-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d5957-109">Requirements</span></span>  
 <span data-ttu-id="d5957-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5957-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5957-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="d5957-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5957-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5957-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5957-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5957-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5957-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5957-114">See Also</span></span>  
 [<span data-ttu-id="d5957-115">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="d5957-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 [<span data-ttu-id="d5957-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d5957-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
