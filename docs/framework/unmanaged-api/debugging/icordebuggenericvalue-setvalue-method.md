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
ms.openlocfilehash: ae64fcccb49123f34cca2622a972a89bf700904f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476685"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="f1ef9-102">Metodo ICorDebugGenericValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="f1ef9-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="f1ef9-103">Copia un nuovo valore dal buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="f1ef9-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1ef9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1ef9-104">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1ef9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1ef9-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="f1ef9-106">[in] Un puntatore al buffer da cui copiare il valore.</span><span class="sxs-lookup"><span data-stu-id="f1ef9-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1ef9-107">Note</span><span class="sxs-lookup"><span data-stu-id="f1ef9-107">Remarks</span></span>  
 <span data-ttu-id="f1ef9-108">Per i tipi di riferimento, il valore è il riferimento, non il contenuto.</span><span class="sxs-lookup"><span data-stu-id="f1ef9-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1ef9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1ef9-109">Requirements</span></span>  
 <span data-ttu-id="f1ef9-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1ef9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1ef9-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1ef9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1ef9-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1ef9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1ef9-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1ef9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
