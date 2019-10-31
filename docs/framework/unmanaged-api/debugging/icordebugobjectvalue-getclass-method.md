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
ms.openlocfilehash: 4719f155957f04471d4ad2b8d71bec9c0f0d30c0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096094"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="99f21-102">Metodo ICorDebugObjectValue::GetClass</span><span class="sxs-lookup"><span data-stu-id="99f21-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="99f21-103">Ottiene la classe del valore di questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="99f21-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99f21-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99f21-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99f21-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="99f21-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="99f21-106">out Puntatore all'indirizzo di un oggetto "ICorDebugClass" che rappresenta la classe del valore dell'oggetto rappresentato da questo oggetto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="99f21-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99f21-107">Note</span><span class="sxs-lookup"><span data-stu-id="99f21-107">Remarks</span></span>  
 <span data-ttu-id="99f21-108">I metodi `GetClass` e [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) restituiscono informazioni sul tipo di un valore. entrambi sono sostituiti dai generics-Aware [ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="99f21-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99f21-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="99f21-109">Requirements</span></span>  
 <span data-ttu-id="99f21-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99f21-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99f21-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99f21-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99f21-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99f21-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99f21-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99f21-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f21-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99f21-114">See also</span></span>
