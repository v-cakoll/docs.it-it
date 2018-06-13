---
title: Metodo ICorDebugValue::GetAddress
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c0fa19841580c7cfe8902577c3f756712a35893
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420658"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="5e5c6-102">Metodo ICorDebugValue::GetAddress</span><span class="sxs-lookup"><span data-stu-id="5e5c6-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="5e5c6-103">Ottiene l'indirizzo dell'oggetto "ICorDebugValue", che è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="5e5c6-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e5c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e5c6-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e5c6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5e5c6-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="5e5c6-106">[out] Puntatore a un `CORDB_ADDRESS` oggetto che specifica l'indirizzo di questo oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="5e5c6-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e5c6-107">Note</span><span class="sxs-lookup"><span data-stu-id="5e5c6-107">Remarks</span></span>  
 <span data-ttu-id="5e5c6-108">Se il valore è disponibile, viene restituito 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="5e5c6-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="5e5c6-109">Questo problema può verificarsi se il valore è almeno parzialmente nei registri o archiviati in un handle del garbage collector (`GCHandle`).</span><span class="sxs-lookup"><span data-stu-id="5e5c6-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e5c6-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5e5c6-110">Requirements</span></span>  
 <span data-ttu-id="5e5c6-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e5c6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e5c6-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="5e5c6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e5c6-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5e5c6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e5c6-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e5c6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e5c6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e5c6-115">See Also</span></span>  
 
