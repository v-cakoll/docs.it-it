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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83265c4f6dffed76f1710378cf5293aac7020ef2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119353"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="a4b23-102">Metodo ICorDebugValue::GetType</span><span class="sxs-lookup"><span data-stu-id="a4b23-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="a4b23-103">Ottiene il tipo primitivo di questo oggetto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="a4b23-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4b23-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4b23-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4b23-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4b23-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="a4b23-106">[out] Puntatore a un valore di enumerazione che indica il tipo del valore "CorElementType".</span><span class="sxs-lookup"><span data-stu-id="a4b23-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4b23-107">Note</span><span class="sxs-lookup"><span data-stu-id="a4b23-107">Remarks</span></span>  
 <span data-ttu-id="a4b23-108">Se l'oggetto è un tipo complesso in fase di esecuzione, tale tipo può essere esaminato mediante le sottoclassi appropriate del `ICorDebugValue` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a4b23-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="a4b23-109">Ad esempio, "ICorDebugObjectValue," che eredita da `ICorDebugValue`, rappresenta un tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="a4b23-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="a4b23-110">Il `GetType` e [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) ogni i metodi restituiscono le informazioni sul tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="a4b23-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="a4b23-111">Entrambi sono sostituiti da GetExactType [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="a4b23-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4b23-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4b23-112">Requirements</span></span>  
 <span data-ttu-id="a4b23-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4b23-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4b23-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4b23-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4b23-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4b23-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a4b23-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a4b23-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a4b23-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4b23-117">See also</span></span>
