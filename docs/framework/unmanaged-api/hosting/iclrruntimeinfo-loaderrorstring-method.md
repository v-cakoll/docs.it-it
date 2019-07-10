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
ms.openlocfilehash: 9e6638f731b335ba7552379cdc77fa912a1def4d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748383"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="1c3da-102">Metodo ICLRRuntimeInfo::LoadErrorString</span><span class="sxs-lookup"><span data-stu-id="1c3da-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="1c3da-103">Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="1c3da-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="1c3da-104">Questo metodo sostituisce le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c3da-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="1c3da-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="1c3da-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
- [<span data-ttu-id="1c3da-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="1c3da-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="1c3da-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c3da-107">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c3da-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="1c3da-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="1c3da-109">[in] Il valore HRESULT da convertire.</span><span class="sxs-lookup"><span data-stu-id="1c3da-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="1c3da-110">[out] La stringa di messaggio associata all'HRESULT specificato.</span><span class="sxs-lookup"><span data-stu-id="1c3da-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="1c3da-111">[in, out] Le dimensioni di `pwzbuffer` per evitare i sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="1c3da-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="1c3da-112">Se `pwzbuffer` è null, `pcchBuffer` fornisce le dimensioni previste del `pwzbuffer` per consentire la preallocazione.</span><span class="sxs-lookup"><span data-stu-id="1c3da-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="1c3da-113">[in] Identificatore delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="1c3da-113">[in] The culture identifier.</span></span> <span data-ttu-id="1c3da-114">Per usare le impostazioni cultura predefinite, è necessario specificare -1.</span><span class="sxs-lookup"><span data-stu-id="1c3da-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c3da-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1c3da-115">Return Value</span></span>  
 <span data-ttu-id="1c3da-116">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="1c3da-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1c3da-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1c3da-117">HRESULT</span></span>|<span data-ttu-id="1c3da-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c3da-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1c3da-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c3da-119">S_OK</span></span>|<span data-ttu-id="1c3da-120">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="1c3da-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="1c3da-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1c3da-121">E_POINTER</span></span>|<span data-ttu-id="1c3da-122">`pcchBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="1c3da-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="1c3da-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1c3da-123">E_INVALIDARG</span></span>|<span data-ttu-id="1c3da-124">`pwzBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="1c3da-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c3da-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c3da-125">Requirements</span></span>  
 <span data-ttu-id="1c3da-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c3da-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c3da-127">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1c3da-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1c3da-128">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1c3da-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c3da-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c3da-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c3da-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c3da-130">See also</span></span>

- [<span data-ttu-id="1c3da-131">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="1c3da-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="1c3da-132">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="1c3da-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="1c3da-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="1c3da-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
