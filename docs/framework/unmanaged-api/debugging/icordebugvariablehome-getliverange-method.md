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
ms.openlocfilehash: c0f9c586a9e95fc2e57c4956601f6dce2b988159
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423065"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="a4b45-102">Metodo IcorDebugVariableHome::GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="a4b45-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="a4b45-103">Ottiene l'intervallo nativo su cui questa variabile è in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="a4b45-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4b45-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4b45-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4b45-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4b45-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="a4b45-106">[out] L'offset logico in cui la variabile è il prima in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="a4b45-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="a4b45-107">[out] L'offset logico immediatamente dopo il punto in cui la variabile è l'ultimo in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="a4b45-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4b45-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4b45-108">Requirements</span></span>  
 <span data-ttu-id="a4b45-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4b45-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4b45-110">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a4b45-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4b45-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a4b45-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4b45-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4b45-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4b45-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4b45-113">See Also</span></span>  
 [<span data-ttu-id="a4b45-114">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="a4b45-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
