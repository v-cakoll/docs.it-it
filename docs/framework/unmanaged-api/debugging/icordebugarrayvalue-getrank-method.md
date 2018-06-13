---
title: Metodo ICorDebugArrayValue::GetRank
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetRank
helpviewer_keywords:
- ICorDebugArrayValue::GetRank method [.NET Framework debugging]
- GetRank method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 5e83c82c-593d-4691-90b0-383d218b415e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdac5bc1d205184771388b13e9b5380ff42bfba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401927"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="c07f1-102">Metodo ICorDebugArrayValue::GetRank</span><span class="sxs-lookup"><span data-stu-id="c07f1-102">ICorDebugArrayValue::GetRank Method</span></span>
<span data-ttu-id="c07f1-103">Ottiene il numero di dimensioni nella matrice.</span><span class="sxs-lookup"><span data-stu-id="c07f1-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c07f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c07f1-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c07f1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c07f1-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="c07f1-106">[out] Un puntatore al numero di dimensioni in questo `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="c07f1-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c07f1-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c07f1-107">Requirements</span></span>  
 <span data-ttu-id="c07f1-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c07f1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c07f1-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c07f1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c07f1-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c07f1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c07f1-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c07f1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
