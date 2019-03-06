---
title: Metodo ICorDebugFrameEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68098895b2ad7f5c08d30f222777e52d4ee3f063
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476659"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="c037e-102">Metodo ICorDebugFrameEnum::Next</span><span class="sxs-lookup"><span data-stu-id="c037e-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="c037e-103">Ottiene il numero specificato di istanze ICorDebugFrame, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="c037e-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c037e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c037e-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c037e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c037e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c037e-106">[in] Il numero di `ICorDebugFrame` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="c037e-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="c037e-107">[out] Una matrice di puntatori, ognuno dei quali punta a un `ICorDebugFrame` oggetto.</span><span class="sxs-lookup"><span data-stu-id="c037e-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c037e-108">[out] Un puntatore al numero di `ICorDebugFrame` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="c037e-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="c037e-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="c037e-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c037e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c037e-110">Requirements</span></span>  
 <span data-ttu-id="c037e-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c037e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c037e-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c037e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c037e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c037e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c037e-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c037e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
