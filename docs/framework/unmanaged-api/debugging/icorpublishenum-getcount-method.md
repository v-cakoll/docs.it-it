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
ms.openlocfilehash: 0b3754fbcca50b52039dc358aed7070b8a152ead
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790629"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="063f0-102">Metodo ICorPublishEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="063f0-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="063f0-103">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="063f0-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="063f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="063f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="063f0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="063f0-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="063f0-106">out Puntatore al numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="063f0-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="063f0-107">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="063f0-107">Requirements</span></span>  
 <span data-ttu-id="063f0-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="063f0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="063f0-109">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="063f0-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="063f0-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="063f0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="063f0-111">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="063f0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="063f0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="063f0-112">See also</span></span>

- [<span data-ttu-id="063f0-113">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="063f0-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
