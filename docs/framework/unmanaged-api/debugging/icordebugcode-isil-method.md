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
ms.openlocfilehash: 2086b12cac75af1c75a13997784e04113630c4f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496166"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="8f4fa-102">Metodo ICorDebugCode::IsIL</span><span class="sxs-lookup"><span data-stu-id="8f4fa-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="8f4fa-103">Ottiene un valore che indica se questo "ICorDebugCode" rappresenta il codice compilato in Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="8f4fa-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f4fa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f4fa-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f4fa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f4fa-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="8f4fa-106">[out] `true` se l'oggetto `ICorDebugCode` rappresenta il codice che è stata compilata in MSIL; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="8f4fa-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f4fa-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f4fa-107">Requirements</span></span>  
 <span data-ttu-id="8f4fa-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f4fa-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f4fa-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f4fa-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f4fa-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f4fa-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f4fa-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f4fa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f4fa-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f4fa-112">See also</span></span>

