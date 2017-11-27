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
ms.openlocfilehash: f10fe48bc2b61a9de5d0703720629f31531c1ea1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="0107c-102">Funzione CLRCreateInstance</span><span class="sxs-lookup"><span data-stu-id="0107c-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="0107c-103">Fornisce una delle tre interfacce: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), o [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0107c-103">Provides one of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0107c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0107c-104">Syntax</span></span>  
  
```  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0107c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0107c-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="0107c-106">[in] Uno dei tre identificatori di classe: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy o CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="0107c-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="0107c-107">[in] Uno dei tre identificatori di interfaccia (IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy o IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="0107c-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="0107c-108">[out] Una delle tre interfacce: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), o [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0107c-108">[out] One of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0107c-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0107c-109">Return Value</span></span>  
 <span data-ttu-id="0107c-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="0107c-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0107c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0107c-111">HRESULT</span></span>|<span data-ttu-id="0107c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0107c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0107c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0107c-113">S_OK</span></span>|<span data-ttu-id="0107c-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="0107c-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="0107c-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="0107c-115">E_POINTER</span></span>|<span data-ttu-id="0107c-116">`ppInterface` è null.</span><span class="sxs-lookup"><span data-stu-id="0107c-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0107c-117">Note</span><span class="sxs-lookup"><span data-stu-id="0107c-117">Remarks</span></span>  
 <span data-ttu-id="0107c-118">La tabella seguente mostra le combinazioni supportate per `clsid` e `riid`.</span><span class="sxs-lookup"><span data-stu-id="0107c-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="0107c-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="0107c-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="0107c-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="0107c-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="0107c-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="0107c-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="0107c-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="0107c-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="0107c-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="0107c-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="0107c-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="0107c-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="0107c-125">Il codice seguente viene illustrato come utilizzare `CLRCreateInstance` per ottenere le tre interfacce:</span><span class="sxs-lookup"><span data-stu-id="0107c-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="0107c-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0107c-126">Requirements</span></span>  
 <span data-ttu-id="0107c-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0107c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0107c-128">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="0107c-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0107c-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0107c-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0107c-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0107c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0107c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0107c-131">See Also</span></span>  
 [<span data-ttu-id="0107c-132">Hosting</span><span class="sxs-lookup"><span data-stu-id="0107c-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
