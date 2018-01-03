---
title: Funzione _CorImageUnloading
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorImageUnloading
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorImageUnloading
helpviewer_keywords: _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f0c105e84d34e83320d6c7d159a94ba4148b302
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corimageunloading-function"></a><span data-ttu-id="1a34f-102">Funzione _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="1a34f-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="1a34f-103">Notifica al caricatore quando vengono scaricate le immagini dei moduli gestiti.</span><span class="sxs-lookup"><span data-stu-id="1a34f-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="1a34f-104">Questa funzione non è implementata.</span><span class="sxs-lookup"><span data-stu-id="1a34f-104">This function is not implemented.</span></span> <span data-ttu-id="1a34f-105">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="1a34f-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a34f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a34f-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a34f-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="1a34f-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="1a34f-108">[in] Puntatore alla posizione iniziale dell'immagine da scaricare.</span><span class="sxs-lookup"><span data-stu-id="1a34f-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a34f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a34f-109">Requirements</span></span>  
 <span data-ttu-id="1a34f-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a34f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a34f-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1a34f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1a34f-112">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a34f-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1a34f-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a34f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a34f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a34f-114">See Also</span></span>  
 [<span data-ttu-id="1a34f-115">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="1a34f-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
