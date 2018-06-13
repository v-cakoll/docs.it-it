---
title: Metodo IObjectHandle::Unwrap
ms.date: 03/30/2017
api_name:
- IObjectHandle.Unwrap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d9a8f9aa910054a4541e4ff8c1f7cad63077ba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439950"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="baf8c-102">Metodo IObjectHandle::Unwrap</span><span class="sxs-lookup"><span data-stu-id="baf8c-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="baf8c-103">Annulla il wrapping un oggetto di effettuare il marshalling in base al valore di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="baf8c-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baf8c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="baf8c-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="baf8c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="baf8c-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="baf8c-106">[out] Un puntatore all'oggetto da rimuovere il wrapping.</span><span class="sxs-lookup"><span data-stu-id="baf8c-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baf8c-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="baf8c-107">Requirements</span></span>  
 <span data-ttu-id="baf8c-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baf8c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baf8c-109">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="baf8c-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="baf8c-110">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="baf8c-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="baf8c-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baf8c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf8c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baf8c-112">See Also</span></span>  
 
