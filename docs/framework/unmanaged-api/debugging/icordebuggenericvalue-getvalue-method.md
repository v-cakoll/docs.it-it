---
title: Metodo ICorDebugGenericValue::GetValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53db4dcb13303c9e7bdd77a46b3c9526364bac06
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471225"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="e8ba3-102">Metodo ICorDebugGenericValue::GetValue</span><span class="sxs-lookup"><span data-stu-id="e8ba3-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="e8ba3-103">Copia il valore di questo oggetto generico nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="e8ba3-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8ba3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8ba3-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8ba3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8ba3-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="e8ba3-106">[out] Puntatore al valore rappresentato da questo oggetto ICorDebugGenericValue.</span><span class="sxs-lookup"><span data-stu-id="e8ba3-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="e8ba3-107">Il valore può essere un tipo semplice o un tipo riferimento (vale a dire, un puntatore).</span><span class="sxs-lookup"><span data-stu-id="e8ba3-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8ba3-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8ba3-108">Requirements</span></span>  
 <span data-ttu-id="e8ba3-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8ba3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8ba3-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8ba3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8ba3-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8ba3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8ba3-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8ba3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
