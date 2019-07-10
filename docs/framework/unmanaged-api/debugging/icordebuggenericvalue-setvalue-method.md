---
title: Metodo ICorDebugGenericValue::SetValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b6907cdf78fc70c75ddd711cd8593427857b172
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756886"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="60917-102">Metodo ICorDebugGenericValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="60917-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="60917-103">Copia un nuovo valore dal buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="60917-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60917-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60917-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60917-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="60917-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="60917-106">[in] Un puntatore al buffer da cui copiare il valore.</span><span class="sxs-lookup"><span data-stu-id="60917-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60917-107">Note</span><span class="sxs-lookup"><span data-stu-id="60917-107">Remarks</span></span>  
 <span data-ttu-id="60917-108">Per i tipi di riferimento, il valore è il riferimento, non il contenuto.</span><span class="sxs-lookup"><span data-stu-id="60917-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60917-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60917-109">Requirements</span></span>  
 <span data-ttu-id="60917-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60917-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60917-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60917-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60917-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60917-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60917-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60917-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
