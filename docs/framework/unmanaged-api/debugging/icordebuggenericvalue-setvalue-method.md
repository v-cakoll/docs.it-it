---
title: Metodo ICorDebugGenericValue::SetValue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGenericValue.SetValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f76bb1b017453d7ca890f9d6b1b603f9b0d790bc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="c4c5a-102">Metodo ICorDebugGenericValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="c4c5a-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="c4c5a-103">Copia un nuovo valore dal buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="c4c5a-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4c5a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4c5a-104">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4c5a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c4c5a-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="c4c5a-106">[in] Un puntatore al buffer da cui copiare il valore.</span><span class="sxs-lookup"><span data-stu-id="c4c5a-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4c5a-107">Note</span><span class="sxs-lookup"><span data-stu-id="c4c5a-107">Remarks</span></span>  
 <span data-ttu-id="c4c5a-108">Per i tipi di riferimento, il valore è il riferimento, non il contenuto.</span><span class="sxs-lookup"><span data-stu-id="c4c5a-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4c5a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4c5a-109">Requirements</span></span>  
 <span data-ttu-id="c4c5a-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4c5a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4c5a-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c4c5a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4c5a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4c5a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4c5a-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4c5a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
