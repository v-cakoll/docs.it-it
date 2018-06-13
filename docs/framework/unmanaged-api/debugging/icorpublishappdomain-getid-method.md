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
ms.openlocfilehash: 41b39597a5a438592d2ae07a16510f5406a91a43
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422832"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="618ea-102">Metodo ICorPublishAppDomain::GetID</span><span class="sxs-lookup"><span data-stu-id="618ea-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="618ea-103">Ottiene l'identificatore univoco per questo [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="618ea-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="618ea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="618ea-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="618ea-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="618ea-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="618ea-106">[out] Un puntatore all'identificatore del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="618ea-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="618ea-107">Note</span><span class="sxs-lookup"><span data-stu-id="618ea-107">Remarks</span></span>  
 <span data-ttu-id="618ea-108">L'identificatore è univoco solo nell'ambito del processo che contiene.</span><span class="sxs-lookup"><span data-stu-id="618ea-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="618ea-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="618ea-109">Requirements</span></span>  
 <span data-ttu-id="618ea-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="618ea-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="618ea-111">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="618ea-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="618ea-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="618ea-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="618ea-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="618ea-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="618ea-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="618ea-114">See Also</span></span>  
 [<span data-ttu-id="618ea-115">Interfaccia ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="618ea-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
