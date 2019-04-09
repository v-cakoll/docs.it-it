---
title: Metodo IcorDebugVariableHome::GetLiveRange
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e2c9e981f431bb87df61a71389abf3d42a6a507
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123812"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="e0a42-102">Metodo IcorDebugVariableHome::GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="e0a42-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="e0a42-103">Ottiene l'intervallo nativo su cui questa variabile è in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="e0a42-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0a42-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0a42-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0a42-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e0a42-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="e0a42-106">[out] L'offset logico in cui la variabile è primo in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="e0a42-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="e0a42-107">[out] L'offset logico immediatamente dopo il punto in corrispondenza del quale la variabile è l'ultimo in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="e0a42-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0a42-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0a42-108">Requirements</span></span>  
 <span data-ttu-id="e0a42-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0a42-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0a42-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0a42-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0a42-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0a42-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e0a42-112">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e0a42-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0a42-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0a42-113">See also</span></span>

- [<span data-ttu-id="e0a42-114">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="e0a42-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
