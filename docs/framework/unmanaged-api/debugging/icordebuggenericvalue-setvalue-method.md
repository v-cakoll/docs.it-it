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
ms.openlocfilehash: 83aebad108a743d25b8ea93c99060d10bf5c3980
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413208"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="7ad32-102">Metodo ICorDebugGenericValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="7ad32-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="7ad32-103">Copia un nuovo valore dal buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="7ad32-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ad32-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ad32-104">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ad32-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7ad32-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="7ad32-106">[in] Un puntatore al buffer da cui copiare il valore.</span><span class="sxs-lookup"><span data-stu-id="7ad32-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ad32-107">Note</span><span class="sxs-lookup"><span data-stu-id="7ad32-107">Remarks</span></span>  
 <span data-ttu-id="7ad32-108">Per i tipi di riferimento, il valore è il riferimento, non il contenuto.</span><span class="sxs-lookup"><span data-stu-id="7ad32-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ad32-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ad32-109">Requirements</span></span>  
 <span data-ttu-id="7ad32-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ad32-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ad32-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="7ad32-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ad32-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="7ad32-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ad32-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ad32-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
