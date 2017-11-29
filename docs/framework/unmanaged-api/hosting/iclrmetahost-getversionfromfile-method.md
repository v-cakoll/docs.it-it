---
title: Metodo ICLRMetaHost::GetVersionFromFile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.GetVersionFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90fcf5ca8306c4e91ff6b96bac36ad2639d81d5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="1a976-102">Metodo ICLRMetaHost::GetVersionFromFile</span><span class="sxs-lookup"><span data-stu-id="1a976-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="1a976-103">Ottiene .NET Framework versione di compilazione originale un assembly (archiviato nei metadati), dato il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="1a976-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="1a976-104">Questo metodo sostituisce il [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="1a976-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a976-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a976-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a976-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1a976-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="1a976-107">[in] Il percorso completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1a976-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="1a976-108">[out] La versione di compilazione di .NET Framework archiviata nei metadati, nel formato "v*A*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="1a976-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="1a976-109">*Oggetto*, *B*, e *X* sono numeri decimali che corrispondono alla versione principale, la versione secondaria e il numero di build.</span><span class="sxs-lookup"><span data-stu-id="1a976-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="1a976-110">La lunghezza di questa stringa è limitata a MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="1a976-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a976-111">Questo output corrisponde al nome di directory per la versione di .NET Framework, così come viene visualizzato in C:\Windows\Microsoft.NET\Framework.</span><span class="sxs-lookup"><span data-stu-id="1a976-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="1a976-112">I valori di esempio sono "v 1.0.3705", "ASP.NET v 1.1.4322", "v 2.0.50727" e "v 4.0. *X*", dove *X* dipende dal numero di build installato.</span><span class="sxs-lookup"><span data-stu-id="1a976-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="1a976-113">Si noti che il prefisso "v" è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1a976-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="1a976-114">[in, out] Le dimensioni di `pwzbuffer` per evitare sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="1a976-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a976-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1a976-115">Return Value</span></span>  
 <span data-ttu-id="1a976-116">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="1a976-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1a976-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1a976-117">HRESULT</span></span>|<span data-ttu-id="1a976-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a976-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a976-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="1a976-119">S_OK</span></span>|<span data-ttu-id="1a976-120">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="1a976-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="1a976-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1a976-121">E_POINTER</span></span>|<span data-ttu-id="1a976-122">`pwzbuffer` o `pcchBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="1a976-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="1a976-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="1a976-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="1a976-124">Il buffer è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="1a976-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a976-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a976-125">Requirements</span></span>  
 <span data-ttu-id="1a976-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a976-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a976-127">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="1a976-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1a976-128">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a976-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a976-129">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a976-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a976-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a976-130">See Also</span></span>  
 [<span data-ttu-id="1a976-131">ICLRMetaHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1a976-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="1a976-132">Hosting</span><span class="sxs-lookup"><span data-stu-id="1a976-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
