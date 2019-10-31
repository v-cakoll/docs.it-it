---
title: Metodo ICorDebugValue::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 284a74823b01305f8c6e025f70bb9209c8607b7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137069"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="1bdb3-102">Metodo ICorDebugValue::GetType</span><span class="sxs-lookup"><span data-stu-id="1bdb3-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="1bdb3-103">Ottiene il tipo primitivo di questo oggetto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="1bdb3-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bdb3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1bdb3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bdb3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1bdb3-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="1bdb3-106">out Puntatore a un valore dell'enumerazione "CorElementType" che indica il tipo del valore.</span><span class="sxs-lookup"><span data-stu-id="1bdb3-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bdb3-107">Note</span><span class="sxs-lookup"><span data-stu-id="1bdb3-107">Remarks</span></span>  
 <span data-ttu-id="1bdb3-108">Se l'oggetto è un tipo di runtime complesso, il tipo può essere esaminato tramite le sottoclassi appropriate dell'interfaccia `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="1bdb3-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="1bdb3-109">Ad esempio, "ICorDebugObjectValue", che eredita da `ICorDebugValue`, rappresenta un tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="1bdb3-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="1bdb3-110">I metodi `GetType` e [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) restituiscono informazioni sul tipo di un valore.</span><span class="sxs-lookup"><span data-stu-id="1bdb3-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="1bdb3-111">Entrambi sono sostituiti dal metodo [ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) in grado di riconoscere i generics.</span><span class="sxs-lookup"><span data-stu-id="1bdb3-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bdb3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1bdb3-112">Requirements</span></span>  
 <span data-ttu-id="1bdb3-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bdb3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bdb3-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1bdb3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1bdb3-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bdb3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bdb3-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bdb3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bdb3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bdb3-117">See also</span></span>
