---
title: Metodo ICorPublishEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f191c31ec5333fbea52c298f477c8c624beb92b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424508"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="fa642-102">Metodo ICorPublishEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="fa642-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="fa642-103">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="fa642-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa642-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa642-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa642-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa642-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="fa642-106">[out] Puntatore al numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="fa642-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa642-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa642-107">Requirements</span></span>  
 <span data-ttu-id="fa642-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa642-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa642-109">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="fa642-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="fa642-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="fa642-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa642-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa642-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa642-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa642-112">See Also</span></span>  
 [<span data-ttu-id="fa642-113">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="fa642-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
