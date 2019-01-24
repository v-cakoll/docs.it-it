---
title: Metodo ICorPublishAppDomainEnum::Next
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1492c9eac9d647c2b71c47cf758265152783d991
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54673883"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="6625f-102">Metodo ICorPublishAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="6625f-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="6625f-103">Ottiene il numero specificato di domini applicazione attualmente esistenti nel processo, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="6625f-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6625f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6625f-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6625f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6625f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6625f-106">[in] Il numero di elementi da recuperare.</span><span class="sxs-lookup"><span data-stu-id="6625f-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="6625f-107">[out] Un puntatore alla matrice di recuperati [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) oggetti, ognuno dei quali rappresenta un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6625f-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6625f-108">[out] Puntatore al numero di domini applicazione effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="6625f-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="6625f-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="6625f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6625f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6625f-110">Requirements</span></span>  
 <span data-ttu-id="6625f-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6625f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6625f-112">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="6625f-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6625f-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6625f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6625f-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6625f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6625f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6625f-115">See also</span></span>
- [<span data-ttu-id="6625f-116">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="6625f-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)
