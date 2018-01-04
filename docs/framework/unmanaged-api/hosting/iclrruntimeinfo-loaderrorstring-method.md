---
title: Metodo ICLRRuntimeInfo::LoadErrorString
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.LoadErrorString
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6253844e931b7b9126b2df28c7977eaa1d92d70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="246a9-102">Metodo ICLRRuntimeInfo::LoadErrorString</span><span class="sxs-lookup"><span data-stu-id="246a9-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="246a9-103">Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="246a9-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="246a9-104">Questo metodo sostituisce le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="246a9-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="246a9-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="246a9-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
-   [<span data-ttu-id="246a9-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="246a9-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="246a9-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="246a9-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="246a9-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="246a9-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="246a9-109">[in] HRESULT da convertire.</span><span class="sxs-lookup"><span data-stu-id="246a9-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="246a9-110">[out] La stringa di messaggio associata all'HRESULT specificato.</span><span class="sxs-lookup"><span data-stu-id="246a9-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="246a9-111">[in, out] Le dimensioni di `pwzbuffer` per evitare sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="246a9-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="246a9-112">Se `pwzbuffer` è null, `pcchBuffer` fornisce la dimensione prevista di `pwzbuffer` per consentire la preallocazione.</span><span class="sxs-lookup"><span data-stu-id="246a9-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="246a9-113">[in] L'identificatore delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="246a9-113">[in] The culture identifier.</span></span> <span data-ttu-id="246a9-114">Per utilizzare le impostazioni cultura predefinite, è necessario specificare -1.</span><span class="sxs-lookup"><span data-stu-id="246a9-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="246a9-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="246a9-115">Return Value</span></span>  
 <span data-ttu-id="246a9-116">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="246a9-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="246a9-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="246a9-117">HRESULT</span></span>|<span data-ttu-id="246a9-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="246a9-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="246a9-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="246a9-119">S_OK</span></span>|<span data-ttu-id="246a9-120">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="246a9-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="246a9-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="246a9-121">E_POINTER</span></span>|<span data-ttu-id="246a9-122">`pcchBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="246a9-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="246a9-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="246a9-123">E_INVALIDARG</span></span>|<span data-ttu-id="246a9-124">`pwzBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="246a9-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="246a9-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="246a9-125">Requirements</span></span>  
 <span data-ttu-id="246a9-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="246a9-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="246a9-127">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="246a9-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="246a9-128">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="246a9-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="246a9-129">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="246a9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="246a9-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="246a9-130">See Also</span></span>  
 [<span data-ttu-id="246a9-131">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="246a9-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="246a9-132">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="246a9-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="246a9-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="246a9-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
