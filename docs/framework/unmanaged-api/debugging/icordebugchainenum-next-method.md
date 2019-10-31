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
ms.openlocfilehash: 3c11a0547ad5acc5613324d7e9d7439d44549dbc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125805"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="b5c82-102">Metodo ICorDebugChainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="b5c82-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="b5c82-103">Ottiene il numero specificato di istanze di ICorDebugChain dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="b5c82-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5c82-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5c82-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5c82-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b5c82-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b5c82-106">in Numero di istanze di `ICorDebugChain` da recuperare.</span><span class="sxs-lookup"><span data-stu-id="b5c82-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="b5c82-107">out Matrice di puntatori, ciascuno dei quali punta a un oggetto `ICorDebugChain` che rappresenta una catena.</span><span class="sxs-lookup"><span data-stu-id="b5c82-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b5c82-108">out Puntatore al numero di istanze di `ICorDebugChain` restituite effettivamente.</span><span class="sxs-lookup"><span data-stu-id="b5c82-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="b5c82-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="b5c82-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5c82-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5c82-110">Requirements</span></span>  
 <span data-ttu-id="b5c82-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5c82-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5c82-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5c82-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5c82-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5c82-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5c82-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5c82-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
