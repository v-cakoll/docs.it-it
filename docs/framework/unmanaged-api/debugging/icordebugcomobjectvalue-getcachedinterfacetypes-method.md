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
ms.openlocfilehash: f720b06581ac60c8bd68dc5e85f15843fd9425f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788899"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="e32ed-102">Metodo ICorDebugComObjectValue::GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="e32ed-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="e32ed-103">Fornisce un enumeratore per i tipi di interfaccia a cui è stato eseguito il cast o l'utilizzo dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="e32ed-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e32ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e32ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e32ed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e32ed-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="e32ed-106">in Valore che indica se il metodo restituisce solo Windows Runtime interfacce (`IInspectable` interfacce) o tutte le interfacce COM memorizzate nella cache dal Runtime Callable Wrapper (RCW).</span><span class="sxs-lookup"><span data-stu-id="e32ed-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="e32ed-107">out Puntatore all'indirizzo di un enumeratore ICorDebugTypeEnum che fornisce l'accesso agli oggetti ICorDebugType che rappresentano i tipi di interfaccia memorizzati nella cache filtrati in base al `bIInspectableOnly`.</span><span class="sxs-lookup"><span data-stu-id="e32ed-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e32ed-108">Note</span><span class="sxs-lookup"><span data-stu-id="e32ed-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e32ed-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e32ed-109">Requirements</span></span>  
 <span data-ttu-id="e32ed-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e32ed-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e32ed-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e32ed-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e32ed-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e32ed-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e32ed-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e32ed-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e32ed-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e32ed-114">See also</span></span>

- [<span data-ttu-id="e32ed-115">Interfaccia ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="e32ed-115">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="e32ed-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e32ed-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
