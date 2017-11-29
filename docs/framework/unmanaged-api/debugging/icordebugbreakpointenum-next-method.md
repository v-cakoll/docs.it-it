---
title: Metodo ICorDebugBreakpointEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpointEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0be36669678d33a73809c6be95563321f754697c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="9a529-102">Metodo ICorDebugBreakpointEnum::Next</span><span class="sxs-lookup"><span data-stu-id="9a529-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="9a529-103">Ottiene il numero specificato di istanze di ICorDebugBreakpoint nell'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="9a529-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a529-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a529-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a529-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a529-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9a529-106">[in] Il numero di `ICorDebugBreakpoint` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="9a529-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="9a529-107">[out] Matrice di puntatori, ognuno dei quali punta a un `ICorDebugBreakpoint` oggetto che rappresenta un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="9a529-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9a529-108">[out] Un puntatore al numero di `ICorDebugBreakpoint` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="9a529-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="9a529-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="9a529-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a529-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a529-110">Requirements</span></span>  
 <span data-ttu-id="9a529-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a529-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a529-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9a529-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a529-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a529-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a529-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a529-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
