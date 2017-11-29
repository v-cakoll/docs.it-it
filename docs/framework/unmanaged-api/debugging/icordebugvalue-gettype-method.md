---
title: Metodo ICorDebugValue::GetType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue.GetType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d214da529aed40d33bdf18530560e9cd7b00f60a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="8e8c4-102">Metodo ICorDebugValue::GetType</span><span class="sxs-lookup"><span data-stu-id="8e8c4-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="8e8c4-103">Ottiene il tipo primitivo di questo oggetto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="8e8c4-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e8c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e8c4-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e8c4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8e8c4-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="8e8c4-106">[out] Un puntatore a un valore di enumerazione che indica il tipo del valore "CorElementType".</span><span class="sxs-lookup"><span data-stu-id="8e8c4-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e8c4-107">Note</span><span class="sxs-lookup"><span data-stu-id="8e8c4-107">Remarks</span></span>  
 <span data-ttu-id="8e8c4-108">Se l'oggetto è un tipo complesso di in fase di esecuzione, tale tipo può esaminato mediante le sottoclassi di appropriate di `ICorDebugValue` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8e8c4-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="8e8c4-109">Ad esempio, "ICorDebugObjectValue," che eredita da `ICorDebugValue`, rappresenta un tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="8e8c4-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="8e8c4-110">Il `GetType` e [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) i metodi restituiscono informazioni sul tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="8e8c4-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="8e8c4-111">Entrambi sono sostituiti da GetExactType [Icordebugvalue2](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="8e8c4-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e8c4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e8c4-112">Requirements</span></span>  
 <span data-ttu-id="8e8c4-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e8c4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e8c4-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8e8c4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e8c4-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e8c4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e8c4-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e8c4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e8c4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e8c4-117">See Also</span></span>  
 
