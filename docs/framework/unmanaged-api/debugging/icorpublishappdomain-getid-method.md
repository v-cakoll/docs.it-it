---
title: Metodo ICorPublishAppDomain::GetID
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44a2038af5d6ef46ad7cc661603e99b2f3dd67a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215924"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="d4417-102">Metodo ICorPublishAppDomain::GetID</span><span class="sxs-lookup"><span data-stu-id="d4417-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="d4417-103">Ottiene l'identificatore univoco per questo [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d4417-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4417-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4417-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4417-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4417-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="d4417-106">[out] Un puntatore all'identificatore del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4417-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4417-107">Note</span><span class="sxs-lookup"><span data-stu-id="d4417-107">Remarks</span></span>  
 <span data-ttu-id="d4417-108">L'identificatore è univoco solo nell'ambito del processo che contiene.</span><span class="sxs-lookup"><span data-stu-id="d4417-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4417-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4417-109">Requirements</span></span>  
 <span data-ttu-id="d4417-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4417-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4417-111">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="d4417-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d4417-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4417-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d4417-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d4417-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d4417-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4417-114">See also</span></span>

- [<span data-ttu-id="d4417-115">Interfaccia ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="d4417-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
