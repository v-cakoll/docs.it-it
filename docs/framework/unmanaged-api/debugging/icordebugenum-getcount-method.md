---
title: Metodo ICorDebugEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::GetCount
helpviewer_keywords:
- ICorDebugEnum::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: d8a74304-1cb2-4977-a21d-e1af48c563ff
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4af328c537fbc3b64eb1a2ac3df3a4e4224789e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466622"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="277e5-102">Metodo ICorDebugEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="277e5-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="277e5-103">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="277e5-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="277e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="277e5-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="277e5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="277e5-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="277e5-106">[out] Puntatore al numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="277e5-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="277e5-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="277e5-107">Requirements</span></span>  
 <span data-ttu-id="277e5-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="277e5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="277e5-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="277e5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="277e5-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="277e5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="277e5-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="277e5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
