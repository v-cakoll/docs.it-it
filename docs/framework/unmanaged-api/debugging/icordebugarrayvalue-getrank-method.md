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
ms.openlocfilehash: 699c65aae205efd5b08f1d163b4ff9a223bbc217
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645656"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="3168b-102">Metodo ICorDebugArrayValue::GetRank</span><span class="sxs-lookup"><span data-stu-id="3168b-102">ICorDebugArrayValue::GetRank Method</span></span>
<span data-ttu-id="3168b-103">Ottiene il numero di dimensioni nella matrice.</span><span class="sxs-lookup"><span data-stu-id="3168b-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3168b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3168b-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3168b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3168b-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="3168b-106">[out] Un puntatore al numero di dimensioni in questo `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="3168b-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3168b-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3168b-107">Requirements</span></span>  
 <span data-ttu-id="3168b-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3168b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3168b-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3168b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3168b-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3168b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3168b-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3168b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
