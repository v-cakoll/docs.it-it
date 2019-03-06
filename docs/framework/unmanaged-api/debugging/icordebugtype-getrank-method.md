---
title: Metodo ICorDebugType::GetRank
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetRank
helpviewer_keywords:
- GetRank method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetRank method [.NET Framework debugging]
ms.assetid: 72d3d927-f590-4f2d-8f60-448f3dfb96af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 134fe55de71e3d6a9a68249febc4c70f11d4f36f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482548"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="7a724-102">Metodo ICorDebugType::GetRank</span><span class="sxs-lookup"><span data-stu-id="7a724-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="7a724-103">Ottiene il numero di dimensioni in un tipo di matrice.</span><span class="sxs-lookup"><span data-stu-id="7a724-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a724-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a724-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a724-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7a724-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="7a724-106">[out] Puntatore al numero di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7a724-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a724-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a724-107">Requirements</span></span>  
 <span data-ttu-id="7a724-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a724-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a724-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a724-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a724-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a724-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a724-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a724-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
