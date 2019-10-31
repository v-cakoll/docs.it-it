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
ms.openlocfilehash: 199f58456e64ccf7ef771d42d5c7d64b189cb670
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125503"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="6078c-102">Metodo ICorDebugComObjectValue::GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="6078c-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="6078c-103">Fornisce un enumeratore per i tipi di interfaccia a cui è stato eseguito il cast o l'utilizzo dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="6078c-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6078c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6078c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6078c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6078c-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="6078c-106">in Valore che indica se il metodo restituisce solo Windows Runtime interfacce (`IInspectable` interfacce) o tutte le interfacce COM memorizzate nella cache dal Runtime Callable Wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="6078c-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="6078c-107">out Puntatore all'indirizzo di un enumeratore ICorDebugTypeEnum che fornisce l'accesso agli oggetti ICorDebugType che rappresentano i tipi di interfaccia memorizzati nella cache filtrati in base al `bIInspectableOnly`.</span><span class="sxs-lookup"><span data-stu-id="6078c-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6078c-108">Note</span><span class="sxs-lookup"><span data-stu-id="6078c-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6078c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6078c-109">Requirements</span></span>  
 <span data-ttu-id="6078c-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6078c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6078c-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6078c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6078c-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6078c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6078c-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6078c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6078c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6078c-114">See also</span></span>

- [<span data-ttu-id="6078c-115">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="6078c-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="6078c-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6078c-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
