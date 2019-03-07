---
title: Metodo ICorDebugAppDomainEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fefc933cc84fede1f3dea16d4b13e09801a96e0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497353"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="579d9-102">Metodo ICorDebugAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="579d9-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="579d9-103">Ottiene il numero di domini dell'applicazione specificato dalla raccolta, a partire dalla posizione corrente del cursore.</span><span class="sxs-lookup"><span data-stu-id="579d9-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="579d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="579d9-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="579d9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="579d9-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="579d9-106">[in] Il numero di domini di applicazione da recuperare.</span><span class="sxs-lookup"><span data-stu-id="579d9-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="579d9-107">[out] Una matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugAppDomain che rappresenta un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="579d9-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="579d9-108">[out] Puntatore al numero di domini applicazione effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="579d9-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="579d9-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="579d9-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="579d9-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="579d9-110">Requirements</span></span>  
 <span data-ttu-id="579d9-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="579d9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="579d9-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="579d9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="579d9-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="579d9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="579d9-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="579d9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
