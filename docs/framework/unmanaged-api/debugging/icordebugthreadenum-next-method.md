---
title: Metodo ICorDebugThreadEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
ms.openlocfilehash: c025afac1b53b23636a6160a475704011999d434
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379050"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="bdb5a-102">Metodo ICorDebugThreadEnum::Next</span><span class="sxs-lookup"><span data-stu-id="bdb5a-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="bdb5a-103">Ottiene il numero di istanze di ICorDebugThread specificate dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="bdb5a-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdb5a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bdb5a-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdb5a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bdb5a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="bdb5a-106">in Numero di `ICorDebugThread` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="bdb5a-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="bdb5a-107">out Matrice di puntatori, ciascuno dei quali punta a un `ICorDebugThread` oggetto che rappresenta un thread.</span><span class="sxs-lookup"><span data-stu-id="bdb5a-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="bdb5a-108">out Puntatore al numero di `ICorDebugThread` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="bdb5a-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="bdb5a-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="bdb5a-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdb5a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bdb5a-110">Requirements</span></span>  
 <span data-ttu-id="bdb5a-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdb5a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdb5a-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdb5a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdb5a-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdb5a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdb5a-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdb5a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
