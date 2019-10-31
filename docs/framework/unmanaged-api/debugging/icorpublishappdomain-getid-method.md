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
ms.openlocfilehash: 33a72d9aea09f808d42d1a17a7ec5640d20d7c79
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140381"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="3ca6f-102">Metodo ICorPublishAppDomain::GetID</span><span class="sxs-lookup"><span data-stu-id="3ca6f-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="3ca6f-103">Ottiene l'identificatore univoco per questo [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="3ca6f-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca6f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ca6f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ca6f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3ca6f-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="3ca6f-106">out Puntatore all'identificatore del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ca6f-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ca6f-107">Note</span><span class="sxs-lookup"><span data-stu-id="3ca6f-107">Remarks</span></span>  
 <span data-ttu-id="3ca6f-108">L'identificatore è univoco solo nell'ambito del processo contenitore.</span><span class="sxs-lookup"><span data-stu-id="3ca6f-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ca6f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ca6f-109">Requirements</span></span>  
 <span data-ttu-id="3ca6f-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ca6f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ca6f-111">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="3ca6f-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3ca6f-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ca6f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ca6f-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ca6f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca6f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ca6f-114">See also</span></span>

- [<span data-ttu-id="3ca6f-115">Interfaccia ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="3ca6f-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
