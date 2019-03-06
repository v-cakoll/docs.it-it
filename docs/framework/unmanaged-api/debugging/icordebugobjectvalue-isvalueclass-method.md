---
title: Metodo ICorDebugObjectValue::IsValueClass
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12ba95eca2a103cffa07247a6ce474263e42e5ad
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487525"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="ee508-102">Metodo ICorDebugObjectValue::IsValueClass</span><span class="sxs-lookup"><span data-stu-id="ee508-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="ee508-103">Ottiene un valore che indica se questo valore di oggetto è un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="ee508-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee508-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee508-104">Syntax</span></span>  
  
```  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee508-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee508-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="ee508-106">[out] Un puntatore a un valore booleano che è `true` se il valore dell'oggetto, rappresentato da "ICorDebugObjectValue" è un tipo di valore anziché un tipo di riferimento; in caso contrario, `pbIsValueClass` è `false`.</span><span class="sxs-lookup"><span data-stu-id="ee508-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee508-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee508-107">Requirements</span></span>  
 <span data-ttu-id="ee508-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee508-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee508-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee508-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee508-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee508-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee508-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee508-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee508-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee508-112">See also</span></span>


