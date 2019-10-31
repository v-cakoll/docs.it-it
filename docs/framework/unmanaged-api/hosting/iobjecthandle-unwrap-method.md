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
ms.openlocfilehash: be488ebe663169cabc5b569335dfc784fdf30556
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102685"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="8f54c-102">Metodo IObjectHandle::Unwrap</span><span class="sxs-lookup"><span data-stu-id="8f54c-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="8f54c-103">Rimuove il wrapping di un oggetto marshalling per valore da riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="8f54c-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f54c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f54c-104">Syntax</span></span>  
  
```cpp  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f54c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f54c-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="8f54c-106">out Puntatore all'oggetto di cui eseguire l'unwrapper.</span><span class="sxs-lookup"><span data-stu-id="8f54c-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f54c-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f54c-107">Requirements</span></span>  
 <span data-ttu-id="8f54c-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f54c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f54c-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8f54c-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f54c-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8f54c-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f54c-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f54c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
