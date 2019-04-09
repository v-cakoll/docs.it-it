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
ms.openlocfilehash: 06e9c7af1c4a769bfb45a8e9f805d97b3bad94aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174187"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="faeae-102">Metodo ICorDebugObjectValue::GetClass</span><span class="sxs-lookup"><span data-stu-id="faeae-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="faeae-103">Ottiene la classe di valore di questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="faeae-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faeae-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="faeae-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faeae-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="faeae-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="faeae-106">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugClass" che rappresenta la classe del valore dell'oggetto rappresentato da questo oggetto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="faeae-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faeae-107">Note</span><span class="sxs-lookup"><span data-stu-id="faeae-107">Remarks</span></span>  
 <span data-ttu-id="faeae-108">Il `GetClass` e [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) ogni i metodi restituiscono le informazioni sul tipo di valore; entrambe sono sostituiti da GetExactType [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="faeae-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faeae-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="faeae-109">Requirements</span></span>  
 <span data-ttu-id="faeae-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faeae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faeae-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="faeae-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faeae-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faeae-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="faeae-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="faeae-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="faeae-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="faeae-114">See also</span></span>
