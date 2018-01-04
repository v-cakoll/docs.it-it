---
title: Funzione CLRCreateInstance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type: COM
f1_keywords: CLRCreateInstance
helpviewer_keywords: CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d95815dd0b2a1cdbddcb28a2e176bc12d3270ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="09029-102">Funzione CLRCreateInstance</span><span class="sxs-lookup"><span data-stu-id="09029-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="09029-103">Fornisce una delle tre interfacce: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), o [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="09029-103">Provides one of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09029-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09029-104">Syntax</span></span>  
  
```  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09029-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="09029-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="09029-106">[in] Uno dei tre identificatori di classe: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy o CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="09029-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="09029-107">[in] Uno dei tre identificatori di interfaccia (IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy o IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="09029-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="09029-108">[out] Una delle tre interfacce: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), o [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="09029-108">[out] One of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09029-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="09029-109">Return Value</span></span>  
 <span data-ttu-id="09029-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="09029-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="09029-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09029-111">HRESULT</span></span>|<span data-ttu-id="09029-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="09029-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09029-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="09029-113">S_OK</span></span>|<span data-ttu-id="09029-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="09029-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="09029-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="09029-115">E_POINTER</span></span>|<span data-ttu-id="09029-116">`ppInterface` è null.</span><span class="sxs-lookup"><span data-stu-id="09029-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09029-117">Note</span><span class="sxs-lookup"><span data-stu-id="09029-117">Remarks</span></span>  
 <span data-ttu-id="09029-118">La tabella seguente mostra le combinazioni supportate per `clsid` e `riid`.</span><span class="sxs-lookup"><span data-stu-id="09029-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="09029-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="09029-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="09029-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="09029-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="09029-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="09029-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="09029-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="09029-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="09029-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="09029-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="09029-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="09029-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="09029-125">Il codice seguente viene illustrato come utilizzare `CLRCreateInstance` per ottenere le tre interfacce:</span><span class="sxs-lookup"><span data-stu-id="09029-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
```  
#include <metahost.h>  
#pragma comment(lib, "mscoree.lib")  
  
ICLRMetaHost       *pMetaHost       = NULL;  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
ICLRDebugging      *pCLRDebugging   = NULL;  
HRESULT hr;  
hr = CLRCreateInstance(CLSID_CLRMetaHost, IID_ICLRMetaHost,  
                    (LPVOID*)&pMetaHost);  
hr = CLRCreateInstance (CLSID_CLRMetaHostPolicy, IID_ICLRMetaHostPolicy,  
                    (LPVOID*)&pMetaHostPolicy);  
hr = CLRCreateInstance (CLSID_CLRDebugging, IID_ICLRDebugging,  
                    (LPVOID*)&pCLRDebugging);  
```  
  
## <a name="requirements"></a><span data-ttu-id="09029-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09029-126">Requirements</span></span>  
 <span data-ttu-id="09029-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09029-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09029-128">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="09029-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="09029-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09029-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09029-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09029-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09029-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09029-131">See Also</span></span>  
 [<span data-ttu-id="09029-132">Hosting</span><span class="sxs-lookup"><span data-stu-id="09029-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
