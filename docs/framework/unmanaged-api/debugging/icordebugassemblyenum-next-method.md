---
title: Metodo ICorDebugAssemblyEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugAssemblyEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 69f43a24caff7e67f307bbf4521094e8ebfd98cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="b5625-102">Metodo ICorDebugAssemblyEnum::Next</span><span class="sxs-lookup"><span data-stu-id="b5625-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="b5625-103">Ottiene il numero di assembly specificato dalla raccolta, a partire dalla posizione corrente del cursore.</span><span class="sxs-lookup"><span data-stu-id="b5625-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5625-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5625-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5625-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b5625-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b5625-106">[in] Il numero di assembly da recuperare.</span><span class="sxs-lookup"><span data-stu-id="b5625-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="b5625-107">[out] Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugAssembly che rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="b5625-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b5625-108">[out] Puntatore al numero di assembly effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="b5625-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="b5625-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="b5625-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5625-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5625-110">Requirements</span></span>  
 <span data-ttu-id="b5625-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5625-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5625-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b5625-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5625-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5625-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5625-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5625-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
