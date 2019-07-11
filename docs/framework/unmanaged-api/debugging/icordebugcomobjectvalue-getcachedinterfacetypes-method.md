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
ms.openlocfilehash: c7325e84d8fe4df9a31543426c6376d0941306fd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748460"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="89f31-102">Metodo ICorDebugComObjectValue::GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="89f31-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="89f31-103">Fornisce un enumeratore per i tipi di interfaccia che l'oggetto corrente è stato eseguito il cast a o utilizzato come.</span><span class="sxs-lookup"><span data-stu-id="89f31-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89f31-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89f31-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89f31-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="89f31-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="89f31-106">[in] Un valore che indica se il metodo restituisce solo le interfacce di Windows Runtime (`IInspectable` interfacce) o tutte le interfacce COM memorizzati nella cache dal runtime callable wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="89f31-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="89f31-107">[out] Un puntatore all'indirizzo di un enumeratore ICorDebugTypeEnum che fornisce accesso agli oggetti ICorDebugType che rappresentano i tipi di interfaccia memorizzati nella cache filtrata in base alla `bIInspectableOnly`.</span><span class="sxs-lookup"><span data-stu-id="89f31-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89f31-108">Note</span><span class="sxs-lookup"><span data-stu-id="89f31-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89f31-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89f31-109">Requirements</span></span>  
 <span data-ttu-id="89f31-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89f31-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89f31-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89f31-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89f31-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89f31-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89f31-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89f31-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f31-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89f31-114">See also</span></span>

- [<span data-ttu-id="89f31-115">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="89f31-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="89f31-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="89f31-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
