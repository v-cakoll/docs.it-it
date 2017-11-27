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
ms.openlocfilehash: 90df58e2765cdecf4a1ec22cf5540e5cfa9530a9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corimageunloading-function"></a><span data-ttu-id="cbced-102">Funzione _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="cbced-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="cbced-103">Notifica al caricatore quando vengono scaricate le immagini dei moduli gestiti.</span><span class="sxs-lookup"><span data-stu-id="cbced-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="cbced-104">Questa funzione non è implementata.</span><span class="sxs-lookup"><span data-stu-id="cbced-104">This function is not implemented.</span></span> <span data-ttu-id="cbced-105">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="cbced-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbced-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbced-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbced-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="cbced-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="cbced-108">[in] Puntatore alla posizione iniziale dell'immagine da scaricare.</span><span class="sxs-lookup"><span data-stu-id="cbced-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbced-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cbced-109">Requirements</span></span>  
 <span data-ttu-id="cbced-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbced-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbced-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cbced-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbced-112">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cbced-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cbced-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbced-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbced-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbced-114">See Also</span></span>  
 [<span data-ttu-id="cbced-115">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="cbced-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
