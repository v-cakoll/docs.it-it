---
title: Metodo ICorDebugCode::GetAddress
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbdf8649e3cb2221e5c74eefd22959dc4b382236
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747690"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="ce2cc-102">Metodo ICorDebugCode::GetAddress</span><span class="sxs-lookup"><span data-stu-id="ce2cc-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="ce2cc-103">Ottiene l'indirizzo virtuale relativo (RVA) del segmento di codice che rappresenta questa interfaccia "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="ce2cc-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce2cc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce2cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce2cc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce2cc-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="ce2cc-106">[out] Puntatore al RVA del segmento di codice.</span><span class="sxs-lookup"><span data-stu-id="ce2cc-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce2cc-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce2cc-107">Requirements</span></span>  
 <span data-ttu-id="ce2cc-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce2cc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce2cc-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce2cc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce2cc-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce2cc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce2cc-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce2cc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce2cc-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce2cc-112">See also</span></span>
