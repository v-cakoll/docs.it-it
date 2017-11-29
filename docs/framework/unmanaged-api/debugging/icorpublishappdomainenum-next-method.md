---
title: Metodo ICorPublishAppDomainEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomainEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 79b9ad5711ac1d0166a7ad328cc227f17780476c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="6f60f-102">Metodo ICorPublishAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="6f60f-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="6f60f-103">Ottiene il numero specificato di domini applicazione che esiste nel processo, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="6f60f-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f60f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f60f-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f60f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f60f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6f60f-106">[in] Il numero di elementi da recuperare.</span><span class="sxs-lookup"><span data-stu-id="6f60f-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="6f60f-107">[out] Recuperata un puntatore alla matrice di [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) oggetti, ognuno dei quali rappresenta un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="6f60f-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6f60f-108">[out] Puntatore al numero di domini applicazione effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="6f60f-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="6f60f-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="6f60f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f60f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f60f-110">Requirements</span></span>  
 <span data-ttu-id="6f60f-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f60f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f60f-112">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="6f60f-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6f60f-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f60f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f60f-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f60f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f60f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f60f-115">See Also</span></span>  
 [<span data-ttu-id="6f60f-116">ICorPublishAppDomainEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6f60f-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)
