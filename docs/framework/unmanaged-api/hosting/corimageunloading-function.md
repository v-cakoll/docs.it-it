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
ms.openlocfilehash: b488b6a887b0c66d8c17f8ea78f48f7d2ea31011
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758403"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="82ff1-102">Funzione _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="82ff1-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="82ff1-103">Notifica al caricatore quando vengono scaricate immagini dei moduli gestiti.</span><span class="sxs-lookup"><span data-stu-id="82ff1-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="82ff1-104">Questa funzione non è implementata.</span><span class="sxs-lookup"><span data-stu-id="82ff1-104">This function is not implemented.</span></span> <span data-ttu-id="82ff1-105">Se chiamato, viene restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="82ff1-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82ff1-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82ff1-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82ff1-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="82ff1-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="82ff1-108">[in] Puntatore alla posizione iniziale dell'immagine da scaricare.</span><span class="sxs-lookup"><span data-stu-id="82ff1-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82ff1-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82ff1-109">Requirements</span></span>  
 <span data-ttu-id="82ff1-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82ff1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82ff1-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="82ff1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82ff1-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="82ff1-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82ff1-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82ff1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82ff1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82ff1-114">See also</span></span>

- [<span data-ttu-id="82ff1-115">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="82ff1-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
