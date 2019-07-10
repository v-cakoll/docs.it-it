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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e9e33e65b1cdeabe203c67ee4d4f259e2f7ac99
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770074"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="831ca-102">Metodo ICorDebugThreadEnum::Next</span><span class="sxs-lookup"><span data-stu-id="831ca-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="831ca-103">Ottiene il numero di istanze ICorDebugThread specificate nell'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="831ca-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="831ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="831ca-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="831ca-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="831ca-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="831ca-106">[in] Il numero di `ICorDebugThread` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="831ca-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="831ca-107">[out] Una matrice di puntatori, ognuno dei quali punta a un `ICorDebugThread` oggetto che rappresenta un thread.</span><span class="sxs-lookup"><span data-stu-id="831ca-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="831ca-108">[out] Puntatore al numero di `ICorDebugThread` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="831ca-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="831ca-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="831ca-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="831ca-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="831ca-110">Requirements</span></span>  
 <span data-ttu-id="831ca-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="831ca-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="831ca-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="831ca-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="831ca-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="831ca-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="831ca-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="831ca-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
