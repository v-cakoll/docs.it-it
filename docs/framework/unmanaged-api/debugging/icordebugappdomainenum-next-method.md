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
ms.openlocfilehash: 84ca240f937e210846e6eb9a17abfe70a280b87d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403556"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="fc552-102">Metodo ICorDebugAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="fc552-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="fc552-103">Ottiene il numero di domini applicazione specificato dalla raccolta, a partire dalla posizione corrente del cursore.</span><span class="sxs-lookup"><span data-stu-id="fc552-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc552-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc552-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc552-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc552-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="fc552-106">[in] Il numero di domini di applicazione da recuperare.</span><span class="sxs-lookup"><span data-stu-id="fc552-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="fc552-107">[out] Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugAppDomain che rappresenta un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="fc552-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="fc552-108">[out] Puntatore al numero di domini applicazione effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="fc552-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="fc552-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="fc552-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc552-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc552-110">Requirements</span></span>  
 <span data-ttu-id="fc552-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc552-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc552-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="fc552-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc552-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="fc552-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc552-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc552-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
