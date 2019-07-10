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
ms.openlocfilehash: 5dc29663153f837b660262eae51b6f032617d027
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765063"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="7c23e-102">Metodo ICorDebugValue::GetAddress</span><span class="sxs-lookup"><span data-stu-id="7c23e-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="7c23e-103">Ottiene l'indirizzo dell'oggetto "ICorDebugValue", che è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="7c23e-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c23e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c23e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c23e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c23e-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="7c23e-106">[out] Puntatore a un `CORDB_ADDRESS` oggetto che specifica l'indirizzo di questo oggetto di valore.</span><span class="sxs-lookup"><span data-stu-id="7c23e-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c23e-107">Note</span><span class="sxs-lookup"><span data-stu-id="7c23e-107">Remarks</span></span>  
 <span data-ttu-id="7c23e-108">Se il valore non è disponibile, viene restituito 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="7c23e-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="7c23e-109">Questo problema può verificarsi se il valore è almeno in parte nei registri o archiviato in un handle del garbage collector (`GCHandle`).</span><span class="sxs-lookup"><span data-stu-id="7c23e-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c23e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c23e-110">Requirements</span></span>  
 <span data-ttu-id="7c23e-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c23e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c23e-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c23e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c23e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c23e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c23e-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c23e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c23e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c23e-115">See also</span></span>
