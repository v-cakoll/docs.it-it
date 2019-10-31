---
title: Metodo ICorPublishEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
ms.openlocfilehash: eb9e5bdf85c6d487fd82422522854076c03e2288
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140458"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="2a6fb-102">Metodo ICorPublishEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="2a6fb-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="2a6fb-103">Sposta il cursore verso l'interno dell'enumerazione in base al numero di elementi specificato.</span><span class="sxs-lookup"><span data-stu-id="2a6fb-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a6fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a6fb-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a6fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2a6fb-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2a6fb-106">in Numero di elementi in base ai quali spostare il cursore avanti.</span><span class="sxs-lookup"><span data-stu-id="2a6fb-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a6fb-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2a6fb-107">Requirements</span></span>  
 <span data-ttu-id="2a6fb-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a6fb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a6fb-109">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="2a6fb-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2a6fb-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a6fb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a6fb-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a6fb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a6fb-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a6fb-112">See also</span></span>

- [<span data-ttu-id="2a6fb-113">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="2a6fb-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
