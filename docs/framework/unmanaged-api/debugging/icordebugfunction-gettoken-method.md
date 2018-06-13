---
title: Metodo ICorDebugFunction::GetToken
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetToken
helpviewer_keywords:
- ICorDebugFunction::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: c6bbf479-062e-48e9-9c70-0f92e293e36a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acfb8910df6e20bf55ed33fdbb9b1c30d22f4684
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412052"
---
# <a name="icordebugfunctiongettoken-method"></a><span data-ttu-id="25f3a-102">Metodo ICorDebugFunction::GetToken</span><span class="sxs-lookup"><span data-stu-id="25f3a-102">ICorDebugFunction::GetToken Method</span></span>
<span data-ttu-id="25f3a-103">Ottiene i metadati del token per questa funzione.</span><span class="sxs-lookup"><span data-stu-id="25f3a-103">Gets the metadata token for this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25f3a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25f3a-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdMethodDef *pMethodDef  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25f3a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="25f3a-105">Parameters</span></span>  
 `pMethodDef`  
 <span data-ttu-id="25f3a-106">[out] Un puntatore a un `mdMethodDef` token che fa riferimento ai metadati per questa funzione.</span><span class="sxs-lookup"><span data-stu-id="25f3a-106">[out] A pointer to an `mdMethodDef` token that references the metadata for this function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25f3a-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25f3a-107">Requirements</span></span>  
 <span data-ttu-id="25f3a-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25f3a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25f3a-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="25f3a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25f3a-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="25f3a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25f3a-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25f3a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
