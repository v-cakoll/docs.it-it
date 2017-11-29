---
title: Metodo IObjectHandle::Unwrap
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IObjectHandle.Unwrap
api_location: mscoree.dll
api_type: COM
f1_keywords: Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d4ff12674fefbde6afbbe76cb411dbbe33d2187
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="d461a-102">Metodo IObjectHandle::Unwrap</span><span class="sxs-lookup"><span data-stu-id="d461a-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="d461a-103">Annulla il wrapping un oggetto di effettuare il marshalling in base al valore di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="d461a-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d461a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d461a-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d461a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d461a-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="d461a-106">[out] Un puntatore all'oggetto da rimuovere il wrapping.</span><span class="sxs-lookup"><span data-stu-id="d461a-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d461a-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d461a-107">Requirements</span></span>  
 <span data-ttu-id="d461a-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d461a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d461a-109">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="d461a-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d461a-110">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d461a-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d461a-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d461a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d461a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d461a-112">See Also</span></span>  
 
