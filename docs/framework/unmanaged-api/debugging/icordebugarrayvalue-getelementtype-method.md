---
title: Metodo ICorDebugArrayValue::GetElementType
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementType
helpviewer_keywords:
- ICorDebugArrayValue::GetElementType method [.NET Framework debugging]
- GetElementType method [.NET Framework debugging]
ms.assetid: ed71961e-ae9b-4dfc-9554-06637696d697
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e0159ce6ad1087838681214533d386f4d44cee2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737468"
---
# <a name="icordebugarrayvaluegetelementtype-method"></a><span data-ttu-id="89431-102">Metodo ICorDebugArrayValue::GetElementType</span><span class="sxs-lookup"><span data-stu-id="89431-102">ICorDebugArrayValue::GetElementType Method</span></span>
<span data-ttu-id="89431-103">Ottiene un valore che indica il tipo semplice di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="89431-103">Gets a value that indicates the simple type of the elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89431-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89431-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementType (  
    [out] CorElementType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89431-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="89431-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="89431-106">[out] Puntatore a un valore dell'enumerazione CorElementType che indica il tipo.</span><span class="sxs-lookup"><span data-stu-id="89431-106">[out] A pointer to a value of the CorElementType enumeration that indicates the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89431-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89431-107">Requirements</span></span>  
 <span data-ttu-id="89431-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89431-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89431-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89431-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89431-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89431-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89431-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89431-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
