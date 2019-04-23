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
ms.openlocfilehash: c14d364320c82f061ef606a402563dacfce28139
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186238"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="e81de-102">Metodo ICorPublishAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="e81de-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="e81de-103">Ottiene il numero specificato di domini applicazione attualmente esistenti nel processo, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="e81de-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e81de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e81de-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e81de-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e81de-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e81de-106">[in] Il numero di elementi da recuperare.</span><span class="sxs-lookup"><span data-stu-id="e81de-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="e81de-107">[out] Un puntatore alla matrice di recuperati [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) oggetti, ognuno dei quali rappresenta un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e81de-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e81de-108">[out] Puntatore al numero di domini applicazione effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="e81de-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="e81de-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="e81de-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e81de-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e81de-110">Requirements</span></span>  
 <span data-ttu-id="e81de-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e81de-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e81de-112">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="e81de-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e81de-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e81de-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e81de-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e81de-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e81de-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e81de-115">See also</span></span>

- [<span data-ttu-id="e81de-116">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="e81de-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)
