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
ms.openlocfilehash: 4c18607d5373b415228846350a3dd0637ade1b45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917592"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="06c9d-102">Metodo IObjectHandle::Unwrap</span><span class="sxs-lookup"><span data-stu-id="06c9d-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="06c9d-103">Annulla il wrapping di un oggetto di effettuare il marshalling per valore da un riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="06c9d-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06c9d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06c9d-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06c9d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="06c9d-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="06c9d-106">[out] Un puntatore all'oggetto per essere annullato il wrapping.</span><span class="sxs-lookup"><span data-stu-id="06c9d-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06c9d-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06c9d-107">Requirements</span></span>  
 <span data-ttu-id="06c9d-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06c9d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06c9d-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="06c9d-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06c9d-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="06c9d-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06c9d-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06c9d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
