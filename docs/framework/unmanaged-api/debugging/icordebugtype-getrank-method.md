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
ms.openlocfilehash: 9f112e0d064041a877963939b78029da08bbbed1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417654"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="1d09b-102">Metodo ICorDebugType::GetRank</span><span class="sxs-lookup"><span data-stu-id="1d09b-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="1d09b-103">Ottiene il numero di dimensioni in un tipo di matrice.</span><span class="sxs-lookup"><span data-stu-id="1d09b-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d09b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d09b-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d09b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1d09b-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="1d09b-106">[out] Puntatore al numero di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="1d09b-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d09b-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1d09b-107">Requirements</span></span>  
 <span data-ttu-id="1d09b-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d09b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d09b-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="1d09b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d09b-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1d09b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d09b-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d09b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
