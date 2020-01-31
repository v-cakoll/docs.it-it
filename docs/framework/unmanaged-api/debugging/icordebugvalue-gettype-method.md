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
ms.openlocfilehash: 7def2bd2c0f3ab501fdb918a0e9a7ee154159b78
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791148"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="20d73-102">Metodo ICorDebugValue::GetType</span><span class="sxs-lookup"><span data-stu-id="20d73-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="20d73-103">Ottiene il tipo primitivo di questo oggetto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="20d73-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20d73-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20d73-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20d73-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="20d73-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="20d73-106">out Puntatore a un valore dell'enumerazione "CorElementType" che indica il tipo del valore.</span><span class="sxs-lookup"><span data-stu-id="20d73-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20d73-107">Note</span><span class="sxs-lookup"><span data-stu-id="20d73-107">Remarks</span></span>  
 <span data-ttu-id="20d73-108">Se l'oggetto è un tipo di runtime complesso, il tipo può essere esaminato tramite le sottoclassi appropriate dell'interfaccia `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="20d73-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="20d73-109">Ad esempio, "ICorDebugObjectValue", che eredita da `ICorDebugValue`, rappresenta un tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="20d73-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="20d73-110">I metodi `GetType` e [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) restituiscono informazioni sul tipo di un valore.</span><span class="sxs-lookup"><span data-stu-id="20d73-110">The `GetType` and [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="20d73-111">Entrambi sono sostituiti dal metodo [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md) in grado di riconoscere i generics.</span><span class="sxs-lookup"><span data-stu-id="20d73-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20d73-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="20d73-112">Requirements</span></span>  
 <span data-ttu-id="20d73-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20d73-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20d73-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20d73-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20d73-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20d73-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20d73-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20d73-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20d73-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20d73-117">See also</span></span>
