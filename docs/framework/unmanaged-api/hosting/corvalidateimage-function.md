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
ms.openlocfilehash: 426b39aa3d1ada5ae44565a742b70681a7bcf6d3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493457"
---
# <a name="_corvalidateimage-function"></a><span data-ttu-id="e1cba-102">Funzione _CorValidateImage</span><span class="sxs-lookup"><span data-stu-id="e1cba-102">_CorValidateImage Function</span></span>
<span data-ttu-id="e1cba-103">Convalida le immagini del modulo gestito e invia una notifica al caricatore del sistema operativo dopo che sono state caricate.</span><span class="sxs-lookup"><span data-stu-id="e1cba-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1cba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1cba-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1cba-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e1cba-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="e1cba-106">in Puntatore alla posizione iniziale dell'immagine da convalidare come codice gestito.</span><span class="sxs-lookup"><span data-stu-id="e1cba-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="e1cba-107">L'immagine deve essere già caricata in memoria.</span><span class="sxs-lookup"><span data-stu-id="e1cba-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="e1cba-108">in Nome file dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="e1cba-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1cba-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e1cba-109">Return Value</span></span>  
 <span data-ttu-id="e1cba-110">Questa funzione restituisce i valori standard `E_INVALIDARG` , `E_OUTOFMEMORY` , `E_UNEXPECTED` e `E_FAIL` , nonché i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="e1cba-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="e1cba-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e1cba-111">Return value</span></span>|<span data-ttu-id="e1cba-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1cba-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="e1cba-113">L'immagine non è valida.</span><span class="sxs-lookup"><span data-stu-id="e1cba-113">The image is invalid.</span></span> <span data-ttu-id="e1cba-114">Questo valore dispone del valore HRESULT 0xC000007BL.</span><span class="sxs-lookup"><span data-stu-id="e1cba-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="e1cba-115">L'immagine è valida.</span><span class="sxs-lookup"><span data-stu-id="e1cba-115">The image is valid.</span></span> <span data-ttu-id="e1cba-116">Questo valore dispone del valore HRESULT 0x00000000L.</span><span class="sxs-lookup"><span data-stu-id="e1cba-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1cba-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e1cba-117">Remarks</span></span>  
 <span data-ttu-id="e1cba-118">In Windows XP e versioni successive, il caricatore del sistema operativo controlla la presenza di moduli gestiti esaminando il bit di directory del descrittore COM nell'intestazione Common Object File Format (COFF).</span><span class="sxs-lookup"><span data-stu-id="e1cba-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="e1cba-119">Un bit set indica un modulo gestito.</span><span class="sxs-lookup"><span data-stu-id="e1cba-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="e1cba-120">Se il caricatore rileva un modulo gestito, carica MsCorEE. dll e chiama `_CorValidateImage` , che esegue le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1cba-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="e1cba-121">Conferma che l'immagine è un modulo gestito valido.</span><span class="sxs-lookup"><span data-stu-id="e1cba-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="e1cba-122">Modifica il punto di ingresso nell'immagine in un punto di ingresso nel Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e1cba-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="e1cba-123">Per le versioni a 64 bit di Windows, modifica l'immagine in memoria mediante la trasformazione da PE32 a PE32 + format.</span><span class="sxs-lookup"><span data-stu-id="e1cba-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="e1cba-124">Torna al caricatore quando vengono caricate le immagini del modulo gestito.</span><span class="sxs-lookup"><span data-stu-id="e1cba-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="e1cba-125">Per le immagini eseguibili, il caricatore del sistema operativo chiama la funzione [_CorExeMain](corexemain-function.md) , indipendentemente dal punto di ingresso specificato nell'eseguibile.</span><span class="sxs-lookup"><span data-stu-id="e1cba-125">For executable images, the operating system loader then calls the [_CorExeMain](corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="e1cba-126">Per le immagini di assembly DLL, il caricatore chiama la funzione [_CorDllMain](cordllmain-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e1cba-126">For DLL assembly images, the loader calls the [_CorDllMain](cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="e1cba-127">`_CorExeMain`oppure `_CorDllMain` esegue le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1cba-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="e1cba-128">Inizializza CLR.</span><span class="sxs-lookup"><span data-stu-id="e1cba-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="e1cba-129">Individua il punto di ingresso gestito dall'intestazione CLR dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e1cba-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="e1cba-130">Inizia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e1cba-130">Begins execution.</span></span>  
  
 <span data-ttu-id="e1cba-131">Il caricatore chiama la funzione [_CorImageUnloading](corimageunloading-function.md) quando vengono scaricate le immagini del modulo gestito.</span><span class="sxs-lookup"><span data-stu-id="e1cba-131">The loader calls the [_CorImageUnloading](corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="e1cba-132">Questa funzione, tuttavia, non esegue alcuna azione. restituisce semplicemente.</span><span class="sxs-lookup"><span data-stu-id="e1cba-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1cba-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1cba-133">Requirements</span></span>  
 <span data-ttu-id="e1cba-134">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1cba-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1cba-135">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e1cba-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e1cba-136">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e1cba-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e1cba-137">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1cba-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1cba-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1cba-138">See also</span></span>

- [<span data-ttu-id="e1cba-139">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="e1cba-139">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
