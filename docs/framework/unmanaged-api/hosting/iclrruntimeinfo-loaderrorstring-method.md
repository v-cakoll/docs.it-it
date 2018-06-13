---
title: Metodo ICLRRuntimeInfo::LoadErrorString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43a00d687c6a9ec42cb8573e70d181b4dc2c7d0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433217"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="9b46b-102">Metodo ICLRRuntimeInfo::LoadErrorString</span><span class="sxs-lookup"><span data-stu-id="9b46b-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="9b46b-103">Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="9b46b-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="9b46b-104">Questo metodo sostituisce le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b46b-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="9b46b-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="9b46b-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
-   [<span data-ttu-id="9b46b-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="9b46b-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="9b46b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b46b-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b46b-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="9b46b-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="9b46b-109">[in] HRESULT da convertire.</span><span class="sxs-lookup"><span data-stu-id="9b46b-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="9b46b-110">[out] La stringa di messaggio associata all'HRESULT specificato.</span><span class="sxs-lookup"><span data-stu-id="9b46b-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="9b46b-111">[in, out] Le dimensioni di `pwzbuffer` per evitare sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="9b46b-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="9b46b-112">Se `pwzbuffer` è null, `pcchBuffer` fornisce la dimensione prevista di `pwzbuffer` per consentire la preallocazione.</span><span class="sxs-lookup"><span data-stu-id="9b46b-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="9b46b-113">[in] L'identificatore delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="9b46b-113">[in] The culture identifier.</span></span> <span data-ttu-id="9b46b-114">Per utilizzare le impostazioni cultura predefinite, è necessario specificare -1.</span><span class="sxs-lookup"><span data-stu-id="9b46b-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b46b-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9b46b-115">Return Value</span></span>  
 <span data-ttu-id="9b46b-116">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="9b46b-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9b46b-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b46b-117">HRESULT</span></span>|<span data-ttu-id="9b46b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b46b-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b46b-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b46b-119">S_OK</span></span>|<span data-ttu-id="9b46b-120">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9b46b-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="9b46b-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9b46b-121">E_POINTER</span></span>|<span data-ttu-id="9b46b-122">`pcchBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="9b46b-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="9b46b-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9b46b-123">E_INVALIDARG</span></span>|<span data-ttu-id="9b46b-124">`pwzBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="9b46b-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b46b-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9b46b-125">Requirements</span></span>  
 <span data-ttu-id="9b46b-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b46b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b46b-127">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="9b46b-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9b46b-128">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9b46b-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b46b-129">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b46b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b46b-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b46b-130">See Also</span></span>  
 [<span data-ttu-id="9b46b-131">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="9b46b-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="9b46b-132">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="9b46b-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="9b46b-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="9b46b-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
