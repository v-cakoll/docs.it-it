---
title: Metodo ICorDebugHeapValue::IsValid
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e1edb1d25a62a9a689c397339740e563d986c8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700223"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="a9d07-102">Metodo ICorDebugHeapValue::IsValid</span><span class="sxs-lookup"><span data-stu-id="a9d07-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="a9d07-103">Ottiene un valore che indica se l'oggetto rappresentato da questo ICorDebugHeapValue è valido.</span><span class="sxs-lookup"><span data-stu-id="a9d07-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="a9d07-104">Questo metodo è stato deprecato in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="a9d07-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9d07-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9d07-105">Syntax</span></span>  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9d07-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a9d07-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="a9d07-107">[out] Un puntatore a un valore booleano che indica se questo valore sull'heap è valido.</span><span class="sxs-lookup"><span data-stu-id="a9d07-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9d07-108">Note</span><span class="sxs-lookup"><span data-stu-id="a9d07-108">Remarks</span></span>  
 <span data-ttu-id="a9d07-109">Il valore non è valido se è stato recuperato dal garbage collector.</span><span class="sxs-lookup"><span data-stu-id="a9d07-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="a9d07-110">Questo metodo è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="a9d07-110">This method has been deprecated.</span></span> <span data-ttu-id="a9d07-111">In .NET Framework 2.0, tutti i valori sono validi finché [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) viene chiamato, a quel punto i valori vengono invalidati.</span><span class="sxs-lookup"><span data-stu-id="a9d07-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9d07-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a9d07-112">Requirements</span></span>  
 <span data-ttu-id="a9d07-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9d07-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9d07-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9d07-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9d07-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9d07-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9d07-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9d07-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
