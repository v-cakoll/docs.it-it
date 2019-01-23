---
title: Funzione _CorImageUnloading
ms.date: 03/30/2017
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be2edd5b217466a58aa9c478dadc10004ebda721
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556142"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="e5660-102">Funzione _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="e5660-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="e5660-103">Notifica al caricatore quando vengono scaricate immagini dei moduli gestiti.</span><span class="sxs-lookup"><span data-stu-id="e5660-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="e5660-104">Questa funzione non è implementata.</span><span class="sxs-lookup"><span data-stu-id="e5660-104">This function is not implemented.</span></span> <span data-ttu-id="e5660-105">Se chiamato, viene restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="e5660-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5660-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5660-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5660-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5660-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="e5660-108">[in] Puntatore alla posizione iniziale dell'immagine da scaricare.</span><span class="sxs-lookup"><span data-stu-id="e5660-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5660-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5660-109">Requirements</span></span>  
 <span data-ttu-id="e5660-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5660-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5660-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e5660-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5660-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e5660-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e5660-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5660-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5660-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5660-114">See also</span></span>
- [<span data-ttu-id="e5660-115">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="e5660-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
