---
title: Metodo ICorDebugProcessEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cd5dbc27376f8cd391f9ecc006c04d9a3a1eea8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419744"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="74fc5-102">Metodo ICorDebugProcessEnum::Next</span><span class="sxs-lookup"><span data-stu-id="74fc5-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="74fc5-103">Ottiene il numero specificato di istanze di ICorDebugProcess nell'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="74fc5-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74fc5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74fc5-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74fc5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74fc5-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="74fc5-106">[in] Il numero di `ICorDebugProcess` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="74fc5-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processess`  
 <span data-ttu-id="74fc5-107">[out] Matrice di puntatori, ognuno dei quali punta a un `ICorDebugProcess` oggetto che rappresenta un processo.</span><span class="sxs-lookup"><span data-stu-id="74fc5-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="74fc5-108">[out] Puntatore al numero di `ICorDebugProcess` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="74fc5-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="74fc5-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="74fc5-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74fc5-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74fc5-110">Requirements</span></span>  
 <span data-ttu-id="74fc5-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74fc5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74fc5-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="74fc5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74fc5-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="74fc5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74fc5-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74fc5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
