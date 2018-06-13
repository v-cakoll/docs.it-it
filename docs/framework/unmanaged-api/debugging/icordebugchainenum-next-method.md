---
title: Metodo ICorDebugChainEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd4f27b958aa4b25c2662d8a5e9da6bcdc73d5d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404456"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="3f7ff-102">Metodo ICorDebugChainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="3f7ff-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="3f7ff-103">Ottiene il numero specificato di istanze di ICorDebugChain nell'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="3f7ff-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f7ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f7ff-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f7ff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f7ff-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3f7ff-106">[in] Il numero di `ICorDebugChain` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="3f7ff-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="3f7ff-107">[out] Matrice di puntatori, ognuno dei quali punta a un `ICorDebugChain` oggetto che rappresenta una catena.</span><span class="sxs-lookup"><span data-stu-id="3f7ff-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="3f7ff-108">[out] Un puntatore al numero di `ICorDebugChain` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="3f7ff-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="3f7ff-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="3f7ff-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f7ff-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f7ff-110">Requirements</span></span>  
 <span data-ttu-id="3f7ff-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f7ff-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f7ff-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3f7ff-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f7ff-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="3f7ff-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f7ff-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f7ff-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
