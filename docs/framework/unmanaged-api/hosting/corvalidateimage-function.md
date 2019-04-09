---
title: Funzione _CorValidateImage
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df9cc0cc86237b1ec439a4ec4fa6a75429c416d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111176"
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="f968b-102">Funzione _CorValidateImage</span><span class="sxs-lookup"><span data-stu-id="f968b-102">_CorValidateImage Function</span></span>
<span data-ttu-id="f968b-103">Convalida delle immagini dei moduli gestiti e notifica al caricatore del sistema operativo dopo che sono stati caricati.</span><span class="sxs-lookup"><span data-stu-id="f968b-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f968b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f968b-104">Syntax</span></span>  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f968b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f968b-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="f968b-106">[in] Un puntatore alla posizione iniziale dell'immagine per convalidare come codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f968b-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="f968b-107">L'immagine deve essere già caricata in memoria.</span><span class="sxs-lookup"><span data-stu-id="f968b-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="f968b-108">[in] Nome file dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="f968b-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f968b-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f968b-109">Return Value</span></span>  
 <span data-ttu-id="f968b-110">Questa funzione restituisce i valori standard `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, e `E_FAIL`, nonché i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="f968b-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="f968b-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f968b-111">Return value</span></span>|<span data-ttu-id="f968b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f968b-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="f968b-113">L'immagine non è valido.</span><span class="sxs-lookup"><span data-stu-id="f968b-113">The image is invalid.</span></span> <span data-ttu-id="f968b-114">Questo valore HRESULT 0xC000007BL.</span><span class="sxs-lookup"><span data-stu-id="f968b-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="f968b-115">L'immagine è valida.</span><span class="sxs-lookup"><span data-stu-id="f968b-115">The image is valid.</span></span> <span data-ttu-id="f968b-116">Questo valore HRESULT 0x00000000L.</span><span class="sxs-lookup"><span data-stu-id="f968b-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f968b-117">Note</span><span class="sxs-lookup"><span data-stu-id="f968b-117">Remarks</span></span>  
 <span data-ttu-id="f968b-118">In Windows XP e versioni successive, il caricatore del sistema operativo cerca moduli gestiti esaminando il bit COM descrittore Directory nell'intestazione common object file formato COFF ().</span><span class="sxs-lookup"><span data-stu-id="f968b-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="f968b-119">Un bit impostato indica un modulo gestito.</span><span class="sxs-lookup"><span data-stu-id="f968b-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="f968b-120">Se il caricatore rileva un modulo gestito, carica Mscoree. dll e chiamate `_CorValidateImage`, che consente di eseguire le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f968b-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
-   <span data-ttu-id="f968b-121">Conferma che l'immagine è un modulo gestito valido.</span><span class="sxs-lookup"><span data-stu-id="f968b-121">Confirms that the image is a valid managed module.</span></span>  
  
-   <span data-ttu-id="f968b-122">Modifica il punto di ingresso nell'immagine a un punto di ingresso in common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f968b-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
-   <span data-ttu-id="f968b-123">Per le versioni a 64 bit di Windows, consente di modificare l'immagine che si trova in memoria e trasformato dal formato PE32 al formato PE32 +.</span><span class="sxs-lookup"><span data-stu-id="f968b-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
-   <span data-ttu-id="f968b-124">Notifica al caricatore quando vengono caricate le immagini dei moduli gestiti.</span><span class="sxs-lookup"><span data-stu-id="f968b-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="f968b-125">Per le immagini eseguibili, il caricatore del sistema operativo chiama quindi il [CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funzione, indipendentemente dal punto di ingresso specificato nel file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="f968b-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="f968b-126">Per le immagini di assembly DLL, il caricatore chiama il [CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="f968b-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 `_CorExeMain` <span data-ttu-id="f968b-127">o `_CorDllMain` esegue le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f968b-127">or `_CorDllMain` performs the following actions:</span></span>  
  
-   <span data-ttu-id="f968b-128">Inizializza CLR.</span><span class="sxs-lookup"><span data-stu-id="f968b-128">Initializes the CLR.</span></span>  
  
-   <span data-ttu-id="f968b-129">Individua il punto di ingresso gestito da un'intestazione CLR dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f968b-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
-   <span data-ttu-id="f968b-130">Inizia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f968b-130">Begins execution.</span></span>  
  
 <span data-ttu-id="f968b-131">Le chiamate del caricatore il [CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) funzionino quando vengono gestiti vengono scaricate immagini dei moduli.</span><span class="sxs-lookup"><span data-stu-id="f968b-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="f968b-132">Tuttavia, questa funzione non esegue alcuna operazione. Restituisce solo.</span><span class="sxs-lookup"><span data-stu-id="f968b-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f968b-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f968b-133">Requirements</span></span>  
 <span data-ttu-id="f968b-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f968b-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f968b-135">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f968b-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f968b-136">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f968b-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f968b-137">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f968b-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f968b-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f968b-138">See also</span></span>

- [<span data-ttu-id="f968b-139">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="f968b-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
