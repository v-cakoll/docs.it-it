---
title: Metodo ICorDebugChainEnum::Next
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e78340d26e4a7ab67fa6c312b1dbd537c5c0a28c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="51859-102">Metodo ICorDebugChainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="51859-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="51859-103">Ottiene il numero specificato di istanze di ICorDebugChain nell'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="51859-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51859-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51859-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51859-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="51859-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="51859-106">[in] Il numero di `ICorDebugChain` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="51859-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="51859-107">[out] Matrice di puntatori, ognuno dei quali punta a un `ICorDebugChain` oggetto che rappresenta una catena.</span><span class="sxs-lookup"><span data-stu-id="51859-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="51859-108">[out] Un puntatore al numero di `ICorDebugChain` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="51859-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="51859-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="51859-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51859-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51859-110">Requirements</span></span>  
 <span data-ttu-id="51859-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51859-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51859-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="51859-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51859-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51859-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51859-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51859-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
