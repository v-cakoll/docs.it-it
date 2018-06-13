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
ms.openlocfilehash: 95532d6721467b482b1d79d611f8055b606bb4a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413508"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="74883-102">Metodo ICorDebugHeapValue::IsValid</span><span class="sxs-lookup"><span data-stu-id="74883-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="74883-103">Ottiene un valore che indica se l'oggetto rappresentato da ICorDebugHeapValue è valido.</span><span class="sxs-lookup"><span data-stu-id="74883-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="74883-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="74883-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74883-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74883-105">Syntax</span></span>  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74883-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="74883-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="74883-107">[out] Un puntatore a un valore booleano che indica se questo valore sull'heap è valido.</span><span class="sxs-lookup"><span data-stu-id="74883-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74883-108">Note</span><span class="sxs-lookup"><span data-stu-id="74883-108">Remarks</span></span>  
 <span data-ttu-id="74883-109">Il valore è valido se è stato recuperato dal garbage collector.</span><span class="sxs-lookup"><span data-stu-id="74883-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="74883-110">Questo metodo è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="74883-110">This method has been deprecated.</span></span> <span data-ttu-id="74883-111">In .NET Framework 2.0, tutti i valori sono validi fino a quando [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) viene chiamato, in cui i valori vengono invalidati.</span><span class="sxs-lookup"><span data-stu-id="74883-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74883-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74883-112">Requirements</span></span>  
 <span data-ttu-id="74883-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74883-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74883-114">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="74883-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74883-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="74883-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74883-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74883-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
