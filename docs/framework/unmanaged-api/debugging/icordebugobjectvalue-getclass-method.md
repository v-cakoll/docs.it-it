---
title: Metodo ICorDebugObjectValue::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dff7a42cac7002e170e8da3c3505fe37bd5eb85f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418763"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="11c2a-102">Metodo ICorDebugObjectValue::GetClass</span><span class="sxs-lookup"><span data-stu-id="11c2a-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="11c2a-103">Ottiene la classe di valore di questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="11c2a-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11c2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11c2a-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11c2a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="11c2a-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="11c2a-106">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugClass" che rappresenta la classe del valore dell'oggetto rappresentato dall'oggetto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="11c2a-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11c2a-107">Note</span><span class="sxs-lookup"><span data-stu-id="11c2a-107">Remarks</span></span>  
 <span data-ttu-id="11c2a-108">Il `GetClass` e [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) i metodi restituiscono informazioni sul tipo di valore; entrambi vengono sostituiti da GetExactType [Icordebugvalue2](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="11c2a-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11c2a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11c2a-109">Requirements</span></span>  
 <span data-ttu-id="11c2a-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11c2a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11c2a-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="11c2a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11c2a-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="11c2a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11c2a-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11c2a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11c2a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11c2a-114">See Also</span></span>  
    
 
