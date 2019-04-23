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
ms.openlocfilehash: 71e32211e6ab16fb5e4e2c624dbad3af5fd6b09f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132019"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="ab857-102">Metodo ICorDebugObjectValue::IsValueClass</span><span class="sxs-lookup"><span data-stu-id="ab857-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="ab857-103">Ottiene un valore che indica se questo valore di oggetto è un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="ab857-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab857-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab857-104">Syntax</span></span>  
  
```  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab857-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ab857-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="ab857-106">[out] Un puntatore a un valore booleano che è `true` se il valore dell'oggetto, rappresentato da "ICorDebugObjectValue" è un tipo di valore anziché un tipo di riferimento; in caso contrario, `pbIsValueClass` è `false`.</span><span class="sxs-lookup"><span data-stu-id="ab857-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab857-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab857-107">Requirements</span></span>  
 <span data-ttu-id="ab857-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab857-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab857-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab857-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab857-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab857-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab857-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab857-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab857-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab857-112">See also</span></span>
