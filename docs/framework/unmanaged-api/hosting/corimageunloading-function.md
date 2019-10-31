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
ms.openlocfilehash: 30e3a88140c8a438001e8428df4c5ee879c83376
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136914"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="f5a07-102">Funzione _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="f5a07-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="f5a07-103">Notifica al caricatore quando le immagini del modulo gestito vengono scaricate.</span><span class="sxs-lookup"><span data-stu-id="f5a07-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="f5a07-104">Questa funzione non è implementata.</span><span class="sxs-lookup"><span data-stu-id="f5a07-104">This function is not implemented.</span></span> <span data-ttu-id="f5a07-105">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="f5a07-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a07-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5a07-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a07-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="f5a07-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="f5a07-108">in Puntatore alla posizione iniziale dell'immagine da scaricare.</span><span class="sxs-lookup"><span data-stu-id="f5a07-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5a07-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f5a07-109">Requirements</span></span>  
 <span data-ttu-id="f5a07-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5a07-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a07-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f5a07-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5a07-112">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f5a07-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f5a07-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a07-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a07-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5a07-114">See also</span></span>

- [<span data-ttu-id="f5a07-115">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="f5a07-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
