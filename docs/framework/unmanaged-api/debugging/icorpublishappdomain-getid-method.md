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
ms.openlocfilehash: 36c5c674f3cdf867107b9ee85a5befadc9246d78
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396311"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="1e634-102">Metodo ICorPublishAppDomain::GetID</span><span class="sxs-lookup"><span data-stu-id="1e634-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="1e634-103">Ottiene l'identificatore univoco per questo [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1e634-103">Gets the unique identifier for this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e634-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e634-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e634-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1e634-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="1e634-106">out Puntatore all'identificatore del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1e634-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e634-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="1e634-107">Remarks</span></span>  
 <span data-ttu-id="1e634-108">L'identificatore è univoco solo nell'ambito del processo contenitore.</span><span class="sxs-lookup"><span data-stu-id="1e634-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e634-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e634-109">Requirements</span></span>  
 <span data-ttu-id="1e634-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e634-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e634-111">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="1e634-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1e634-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e634-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e634-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e634-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e634-114">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1e634-114">See also</span></span>

- [<span data-ttu-id="1e634-115">Interfaccia ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="1e634-115">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
