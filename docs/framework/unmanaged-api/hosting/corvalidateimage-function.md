---
title: Funzione _CorValidateImage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03deb62a84a1e9c6cee898fe0023c34b8c538ece
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="ba158-102">Funzione _CorValidateImage</span><span class="sxs-lookup"><span data-stu-id="ba158-102">_CorValidateImage Function</span></span>
<span data-ttu-id="ba158-103">Convalida delle immagini dei moduli gestiti e notifica al caricatore del sistema operativo dopo che sono stati caricati.</span><span class="sxs-lookup"><span data-stu-id="ba158-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba158-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba158-104">Syntax</span></span>  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ba158-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba158-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="ba158-106">[in] Puntatore alla posizione iniziale dell'immagine per convalidare come codice gestito.</span><span class="sxs-lookup"><span data-stu-id="ba158-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="ba158-107">L'immagine deve essere già caricata in memoria.</span><span class="sxs-lookup"><span data-stu-id="ba158-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="ba158-108">[in] Il nome file dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="ba158-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba158-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ba158-109">Return Value</span></span>  
 <span data-ttu-id="ba158-110">Questa funzione restituisce i valori standard `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, e `E_FAIL`, nonché i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="ba158-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="ba158-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ba158-111">Return value</span></span>|<span data-ttu-id="ba158-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba158-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="ba158-113">L'immagine non è valido.</span><span class="sxs-lookup"><span data-stu-id="ba158-113">The image is invalid.</span></span> <span data-ttu-id="ba158-114">Questo valore HRESULT 0xC000007BL.</span><span class="sxs-lookup"><span data-stu-id="ba158-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="ba158-115">L'immagine è valido.</span><span class="sxs-lookup"><span data-stu-id="ba158-115">The image is valid.</span></span> <span data-ttu-id="ba158-116">Questo valore HRESULT 0x00000000L.</span><span class="sxs-lookup"><span data-stu-id="ba158-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba158-117">Note</span><span class="sxs-lookup"><span data-stu-id="ba158-117">Remarks</span></span>  
 <span data-ttu-id="ba158-118">In Windows XP e versioni successive, il caricatore del sistema operativo controlla la presenza di moduli gestiti esaminando il bit di Directory descrittore COM nell'intestazione common object file formato COFF ().</span><span class="sxs-lookup"><span data-stu-id="ba158-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="ba158-119">Un bit impostato indica un modulo gestito.</span><span class="sxs-lookup"><span data-stu-id="ba158-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="ba158-120">Se il caricatore rileva un modulo gestito, carica MsCorEE.dll e chiama `_CorValidateImage`, che esegue le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba158-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
-   <span data-ttu-id="ba158-121">Conferma che l'immagine è un modulo gestito valido.</span><span class="sxs-lookup"><span data-stu-id="ba158-121">Confirms that the image is a valid managed module.</span></span>  
  
-   <span data-ttu-id="ba158-122">Modifica il punto di ingresso nell'immagine per un punto di ingresso in common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ba158-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
-   <span data-ttu-id="ba158-123">Per le versioni a 64 bit di Windows, modifica l'immagine presente in memoria trasformandola dal formato PE32 al formato PE32 +.</span><span class="sxs-lookup"><span data-stu-id="ba158-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
-   <span data-ttu-id="ba158-124">Restituisce un valore per il caricatore quando le immagini dei moduli gestiti caricati.</span><span class="sxs-lookup"><span data-stu-id="ba158-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="ba158-125">Per le immagini eseguibili, il caricatore del sistema operativo chiama quindi il [CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funzione, indipendentemente dal punto di ingresso specificato nel file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="ba158-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="ba158-126">Per le immagini di assembly DLL, il caricatore chiama la [CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="ba158-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="ba158-127">`_CorExeMain`o `_CorDllMain` esegue le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba158-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
-   <span data-ttu-id="ba158-128">Inizializza il CLR.</span><span class="sxs-lookup"><span data-stu-id="ba158-128">Initializes the CLR.</span></span>  
  
-   <span data-ttu-id="ba158-129">Individua il punto di ingresso gestito dall'intestazione CLR dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ba158-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
-   <span data-ttu-id="ba158-130">Inizia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ba158-130">Begins execution.</span></span>  
  
 <span data-ttu-id="ba158-131">Le chiamate del caricatore di [CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) funzione quando gestito immagini vengono scaricate.</span><span class="sxs-lookup"><span data-stu-id="ba158-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="ba158-132">Tuttavia, questa funzione non esegue alcuna operazione. Restituisce solo.</span><span class="sxs-lookup"><span data-stu-id="ba158-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba158-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba158-133">Requirements</span></span>  
 <span data-ttu-id="ba158-134">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba158-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba158-135">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ba158-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba158-136">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba158-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba158-137">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba158-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba158-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba158-138">See Also</span></span>  
 [<span data-ttu-id="ba158-139">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="ba158-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
