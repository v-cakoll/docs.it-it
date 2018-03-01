---
title: Metodo ICorDebugFrame::GetFunctionToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9d36606dfffb6ff5872ee88f00d3d94f3ececce5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="da56d-102">Metodo ICorDebugFrame::GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="da56d-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="da56d-103">Ottiene il token di metadati per la funzione che contiene il codice associato a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="da56d-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da56d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da56d-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da56d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da56d-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="da56d-106">[out] Un puntatore a un `mdMethodDef` token che fa riferimento ai metadati per la funzione.</span><span class="sxs-lookup"><span data-stu-id="da56d-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da56d-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da56d-107">Requirements</span></span>  
 <span data-ttu-id="da56d-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da56d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da56d-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="da56d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da56d-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da56d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da56d-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da56d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
