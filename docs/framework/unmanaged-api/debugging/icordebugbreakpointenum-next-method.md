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
ms.openlocfilehash: d29576c6f073f1d0e8e0aea417fc38c09a8327c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122738"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="9aed8-102">Metodo ICorDebugBreakpointEnum::Next</span><span class="sxs-lookup"><span data-stu-id="9aed8-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="9aed8-103">Ottiene il numero specificato di istanze di ICorDebugBreakpoint dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="9aed8-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aed8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9aed8-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9aed8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9aed8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9aed8-106">in Numero di istanze di `ICorDebugBreakpoint` da recuperare.</span><span class="sxs-lookup"><span data-stu-id="9aed8-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="9aed8-107">out Matrice di puntatori, ciascuno dei quali punta a un oggetto `ICorDebugBreakpoint` che rappresenta un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="9aed8-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9aed8-108">out Puntatore al numero di istanze di `ICorDebugBreakpoint` restituite effettivamente.</span><span class="sxs-lookup"><span data-stu-id="9aed8-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="9aed8-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="9aed8-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aed8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9aed8-110">Requirements</span></span>  
 <span data-ttu-id="9aed8-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9aed8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9aed8-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9aed8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9aed8-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9aed8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9aed8-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9aed8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
