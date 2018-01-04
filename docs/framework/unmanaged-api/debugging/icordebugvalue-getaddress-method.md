---
title: Metodo ICorDebugValue::GetAddress
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue.GetAddress
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8aa5a0c3740b6cf97d2a5d855343a36b90fd538
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="81cd1-102">Metodo ICorDebugValue::GetAddress</span><span class="sxs-lookup"><span data-stu-id="81cd1-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="81cd1-103">Ottiene l'indirizzo dell'oggetto "ICorDebugValue", che è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="81cd1-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81cd1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81cd1-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81cd1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="81cd1-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="81cd1-106">[out] Puntatore a un `CORDB_ADDRESS` oggetto che specifica l'indirizzo di questo oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="81cd1-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81cd1-107">Note</span><span class="sxs-lookup"><span data-stu-id="81cd1-107">Remarks</span></span>  
 <span data-ttu-id="81cd1-108">Se il valore è disponibile, viene restituito 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="81cd1-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="81cd1-109">Questo problema può verificarsi se il valore è almeno parzialmente nei registri o archiviati in un handle del garbage collector (`GCHandle`).</span><span class="sxs-lookup"><span data-stu-id="81cd1-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81cd1-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="81cd1-110">Requirements</span></span>  
 <span data-ttu-id="81cd1-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81cd1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81cd1-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="81cd1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81cd1-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81cd1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81cd1-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81cd1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81cd1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81cd1-115">See Also</span></span>  
 
