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
ms.openlocfilehash: ccebe01c853677f7c78731e757ef7a5f090d6919
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415191"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="984cb-102">Metodo ICorDebugCode::IsIL</span><span class="sxs-lookup"><span data-stu-id="984cb-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="984cb-103">Ottiene un valore che indica se questo "ICorDebugCode" rappresenta il codice compilato in Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="984cb-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="984cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="984cb-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="984cb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="984cb-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="984cb-106">[out] `true` se `ICorDebugCode` rappresenta il codice è stato compilato in MSIL; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="984cb-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="984cb-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="984cb-107">Requirements</span></span>  
 <span data-ttu-id="984cb-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="984cb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="984cb-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="984cb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="984cb-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="984cb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="984cb-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="984cb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="984cb-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="984cb-112">See Also</span></span>  
 
