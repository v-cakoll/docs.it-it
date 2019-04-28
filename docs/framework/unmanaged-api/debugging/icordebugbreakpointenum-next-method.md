---
title: Metodo ICorDebugBreakpointEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18b65eb3e733fa7970e4c0e7de09755598eaf149
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645344"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="307d5-102">Metodo ICorDebugBreakpointEnum::Next</span><span class="sxs-lookup"><span data-stu-id="307d5-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="307d5-103">Ottiene il numero di istanze ICorDebugBreakpoint specificato dall'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="307d5-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="307d5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="307d5-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="307d5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="307d5-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="307d5-106">[in] Il numero di `ICorDebugBreakpoint` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="307d5-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="307d5-107">[out] Una matrice di puntatori, ognuno dei quali punta a un `ICorDebugBreakpoint` oggetto che rappresenta un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="307d5-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="307d5-108">[out] Un puntatore al numero di `ICorDebugBreakpoint` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="307d5-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="307d5-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="307d5-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="307d5-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="307d5-110">Requirements</span></span>  
 <span data-ttu-id="307d5-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="307d5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="307d5-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="307d5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="307d5-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="307d5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="307d5-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="307d5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
