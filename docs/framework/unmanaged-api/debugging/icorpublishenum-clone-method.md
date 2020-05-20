---
title: Metodo ICorPublishEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
ms.openlocfilehash: 38f49e8fe632e9b38ede8815de6d8865278351f9
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421202"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="2d4c2-102">Metodo ICorPublishEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="2d4c2-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="2d4c2-103">Crea una copia di questo oggetto [ICorPublishEnum](icorpublishenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2d4c2-103">Creates a copy of this [ICorPublishEnum](icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d4c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d4c2-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d4c2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2d4c2-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="2d4c2-106">out Puntatore all'indirizzo di un `ICorPublishEnum` oggetto che è una copia di questo `ICorPublishEnum` oggetto.</span><span class="sxs-lookup"><span data-stu-id="2d4c2-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d4c2-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d4c2-107">Requirements</span></span>  
 <span data-ttu-id="2d4c2-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d4c2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d4c2-109">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="2d4c2-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2d4c2-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d4c2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d4c2-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d4c2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d4c2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d4c2-112">See also</span></span>

- [<span data-ttu-id="2d4c2-113">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="2d4c2-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
