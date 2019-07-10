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
ms.openlocfilehash: 9be126e45d8428d8786e9aadf2195133d1957440
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754830"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="77066-102">Metodo ICorDebugFrameEnum::Next</span><span class="sxs-lookup"><span data-stu-id="77066-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="77066-103">Ottiene il numero specificato di istanze ICorDebugFrame, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="77066-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77066-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77066-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77066-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="77066-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="77066-106">[in] Il numero di `ICorDebugFrame` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="77066-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="77066-107">[out] Una matrice di puntatori, ognuno dei quali punta a un `ICorDebugFrame` oggetto.</span><span class="sxs-lookup"><span data-stu-id="77066-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="77066-108">[out] Un puntatore al numero di `ICorDebugFrame` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="77066-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="77066-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="77066-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77066-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="77066-110">Requirements</span></span>  
 <span data-ttu-id="77066-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77066-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77066-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77066-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77066-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77066-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77066-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77066-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
