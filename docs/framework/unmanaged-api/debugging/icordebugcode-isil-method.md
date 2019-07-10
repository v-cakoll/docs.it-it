---
title: Metodo ICorDebugCode::IsIL
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1257c870371895cec89996be0e94906597b09ed8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747459"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="d5609-102">Metodo ICorDebugCode::IsIL</span><span class="sxs-lookup"><span data-stu-id="d5609-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="d5609-103">Ottiene un valore che indica se questo "ICorDebugCode" rappresenta il codice compilato in Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="d5609-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5609-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5609-104">Syntax</span></span>  
  
```cpp  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5609-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d5609-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="d5609-106">[out] `true` se l'oggetto `ICorDebugCode` rappresenta il codice che è stata compilata in MSIL; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d5609-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5609-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d5609-107">Requirements</span></span>  
 <span data-ttu-id="d5609-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5609-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5609-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5609-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5609-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5609-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5609-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5609-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5609-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5609-112">See also</span></span>
