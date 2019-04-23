---
title: Metodo ICorDebugComObjectValue::GetCachedInterfaceTypes
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36e6313ae7b4c67a20bee6d2a76a4ed1da84acbe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115219"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="99d60-102">Metodo ICorDebugComObjectValue::GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="99d60-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="99d60-103">Fornisce un enumeratore per i tipi di interfaccia che l'oggetto corrente è stato eseguito il cast a o utilizzato come.</span><span class="sxs-lookup"><span data-stu-id="99d60-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99d60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99d60-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99d60-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="99d60-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="99d60-106">[in] Un valore che indica se il metodo restituisce solo [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfacce (`IInspectable` interfacce) o tutte le interfacce COM memorizzati nella cache dal runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="99d60-106">[in] A value that indicates whether the method returns only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="99d60-107">[out] Un puntatore all'indirizzo di un enumeratore ICorDebugTypeEnum che fornisce accesso agli oggetti ICorDebugType che rappresentano i tipi di interfaccia memorizzati nella cache filtrata in base alla `bIInspectableOnly`.</span><span class="sxs-lookup"><span data-stu-id="99d60-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99d60-108">Note</span><span class="sxs-lookup"><span data-stu-id="99d60-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99d60-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="99d60-109">Requirements</span></span>  
 <span data-ttu-id="99d60-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99d60-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99d60-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99d60-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99d60-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99d60-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99d60-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99d60-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d60-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99d60-114">See also</span></span>

- [<span data-ttu-id="99d60-115">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="99d60-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="99d60-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="99d60-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
