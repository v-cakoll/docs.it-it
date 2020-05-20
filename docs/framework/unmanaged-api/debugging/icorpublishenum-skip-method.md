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
ms.openlocfilehash: b68a9ec1e8fee4fdecd2114af28c75c4a236cb3a
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421146"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="81478-102">Metodo ICorPublishEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="81478-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="81478-103">Sposta il cursore verso l'interno dell'enumerazione in base al numero di elementi specificato.</span><span class="sxs-lookup"><span data-stu-id="81478-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81478-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81478-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81478-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="81478-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="81478-106">in Numero di elementi in base ai quali spostare il cursore avanti.</span><span class="sxs-lookup"><span data-stu-id="81478-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81478-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="81478-107">Requirements</span></span>  
 <span data-ttu-id="81478-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81478-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81478-109">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="81478-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="81478-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81478-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81478-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81478-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81478-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81478-112">See also</span></span>

- [<span data-ttu-id="81478-113">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="81478-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
