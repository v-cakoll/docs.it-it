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
ms.openlocfilehash: a82606d90444c2d543065287780e42da4f8b4943
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180687"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="9909a-102">Metodo ICorDebugCode::IsIL</span><span class="sxs-lookup"><span data-stu-id="9909a-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="9909a-103">Ottiene un valore che indica se questo "ICorDebugCode" rappresenta il codice compilato in Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="9909a-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9909a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9909a-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9909a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9909a-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="9909a-106">[out] `true` se l'oggetto `ICorDebugCode` rappresenta il codice che è stata compilata in MSIL; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9909a-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9909a-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9909a-107">Requirements</span></span>  
 <span data-ttu-id="9909a-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9909a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9909a-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9909a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9909a-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9909a-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9909a-111">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9909a-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9909a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9909a-112">See also</span></span>
