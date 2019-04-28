---
title: Metodo ICLRMetaHost::GetVersionFromFile
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a6c7fd48269a3e8291a548b3e13efe5c8e70652
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61919412"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="ddcfe-102">Metodo ICLRMetaHost::GetVersionFromFile</span><span class="sxs-lookup"><span data-stu-id="ddcfe-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="ddcfe-103">Ottiene .NET Framework versione di compilazione originale un assembly (archiviato nei metadati), dato il percorso di file.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="ddcfe-104">Questo metodo sostituisce le [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="ddcfe-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddcfe-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ddcfe-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddcfe-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ddcfe-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="ddcfe-107">[in] Il percorso del file completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="ddcfe-108">[out] La versione di compilazione di .NET Framework archiviata nei metadati, nel formato "v*un'*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="ddcfe-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="ddcfe-109">*Oggetto*, *B*, e *X* sono numeri decimali che corrispondono alla versione principale, la versione secondaria e il numero di build.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="ddcfe-110">La lunghezza di questa stringa è limitata a MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddcfe-111">Questo output corrisponde al nome di directory per la versione di .NET Framework, così come appare sotto C:\Windows\Microsoft.NET\Framework.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="ddcfe-112">I valori di esempio sono "v1.0.3705", "v1.1.4322", "v2.0.50727" e "v4.0. *X*", dove *X* dipende dal numero di build installato.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="ddcfe-113">Si noti che è necessario il prefisso "v".</span><span class="sxs-lookup"><span data-stu-id="ddcfe-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="ddcfe-114">[in, out] Le dimensioni di `pwzbuffer` per evitare i sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ddcfe-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ddcfe-115">Return Value</span></span>  
 <span data-ttu-id="ddcfe-116">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ddcfe-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ddcfe-117">HRESULT</span></span>|<span data-ttu-id="ddcfe-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddcfe-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ddcfe-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="ddcfe-119">S_OK</span></span>|<span data-ttu-id="ddcfe-120">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="ddcfe-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ddcfe-121">E_POINTER</span></span>|<span data-ttu-id="ddcfe-122">`pwzbuffer` o `pcchBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="ddcfe-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="ddcfe-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="ddcfe-124">Il buffer è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ddcfe-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ddcfe-125">Requirements</span></span>  
 <span data-ttu-id="ddcfe-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddcfe-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddcfe-127">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ddcfe-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ddcfe-128">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ddcfe-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ddcfe-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddcfe-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddcfe-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddcfe-130">See also</span></span>

- [<span data-ttu-id="ddcfe-131">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="ddcfe-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="ddcfe-132">Hosting</span><span class="sxs-lookup"><span data-stu-id="ddcfe-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
