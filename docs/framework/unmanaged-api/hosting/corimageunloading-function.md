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
ms.openlocfilehash: 585287f63f57f55e877c94684820833b6d1add60
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616538"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="ae78d-102">Funzione _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="ae78d-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="ae78d-103">Notifica al caricatore quando le immagini del modulo gestito vengono scaricate.</span><span class="sxs-lookup"><span data-stu-id="ae78d-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="ae78d-104">Questa funzione non è implementata.</span><span class="sxs-lookup"><span data-stu-id="ae78d-104">This function is not implemented.</span></span> <span data-ttu-id="ae78d-105">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ae78d-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae78d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae78d-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae78d-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae78d-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="ae78d-108">in Puntatore alla posizione iniziale dell'immagine da scaricare.</span><span class="sxs-lookup"><span data-stu-id="ae78d-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae78d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae78d-109">Requirements</span></span>  
 <span data-ttu-id="ae78d-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae78d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae78d-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ae78d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae78d-112">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ae78d-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ae78d-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae78d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae78d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae78d-114">See also</span></span>

- [<span data-ttu-id="ae78d-115">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="ae78d-115">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
