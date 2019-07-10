---
title: Metodo ICorDebugFrame::GetFunctionToken
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunctionToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f50e5fcee3705e05aeed820cf736613c12b00e50
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754866"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="c6634-102">Metodo ICorDebugFrame::GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="c6634-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="c6634-103">Ottiene il token di metadati per la funzione che contiene il codice associato a questo frame dello stack.</span><span class="sxs-lookup"><span data-stu-id="c6634-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6634-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6634-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6634-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c6634-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="c6634-106">[out] Un puntatore a un `mdMethodDef` token che fa riferimento ai metadati per la funzione.</span><span class="sxs-lookup"><span data-stu-id="c6634-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6634-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6634-107">Requirements</span></span>  
 <span data-ttu-id="c6634-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6634-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6634-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6634-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6634-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6634-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6634-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6634-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
