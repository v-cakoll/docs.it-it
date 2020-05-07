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
ms.openlocfilehash: 6b02657012870de4d0f888f6c05b115b25073fa2
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892839"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="7d478-102">Metodo ICorDebugComObjectValue::GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="7d478-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="7d478-103">Fornisce un enumeratore per i tipi di interfaccia a cui è stato eseguito il cast o l'utilizzo dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="7d478-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d478-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d478-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d478-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7d478-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="7d478-106">in Valore che indica se il metodo restituisce solo interfacce Windows Runtime (`IInspectable` interfacce) o tutte le interfacce COM memorizzate nella cache dal Runtime Callable Wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="7d478-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="7d478-107">out Puntatore all'indirizzo di un enumeratore ICorDebugTypeEnum che fornisce l'accesso agli oggetti ICorDebugType che rappresentano i tipi di interfaccia memorizzati nella `bIInspectableOnly`cache filtrati in base a.</span><span class="sxs-lookup"><span data-stu-id="7d478-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d478-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7d478-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d478-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d478-109">Requirements</span></span>  
 <span data-ttu-id="7d478-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d478-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d478-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d478-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d478-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d478-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d478-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d478-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d478-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d478-114">See also</span></span>

- [<span data-ttu-id="7d478-115">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="7d478-115">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="7d478-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7d478-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
