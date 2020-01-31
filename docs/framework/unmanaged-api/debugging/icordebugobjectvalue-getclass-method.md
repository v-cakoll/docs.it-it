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
ms.openlocfilehash: d15938e94d647fd5fded23c72bdc200d198d21a7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792696"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="fa311-102">Metodo ICorDebugObjectValue::GetClass</span><span class="sxs-lookup"><span data-stu-id="fa311-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="fa311-103">Ottiene la classe del valore di questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa311-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa311-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa311-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa311-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa311-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="fa311-106">out Puntatore all'indirizzo di un oggetto "ICorDebugClass" che rappresenta la classe del valore dell'oggetto rappresentato da questo oggetto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="fa311-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa311-107">Note</span><span class="sxs-lookup"><span data-stu-id="fa311-107">Remarks</span></span>  
 <span data-ttu-id="fa311-108">I metodi `GetClass` e [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) restituiscono informazioni sul tipo di un valore. entrambi sono sostituiti dai generics-Aware [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="fa311-108">The `GetClass` and [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa311-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="fa311-109">Requirements</span></span>  
 <span data-ttu-id="fa311-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa311-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa311-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa311-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa311-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa311-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa311-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa311-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa311-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa311-114">See also</span></span>
