---
title: Funzione CLRCreateInstance
ms.date: 03/30/2017
api_name:
- CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- CLRCreateInstance
helpviewer_keywords:
- CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9dc3f87ce727076d561923fe35495bbfe4419e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768121"
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="ed6b6-102">Funzione CLRCreateInstance</span><span class="sxs-lookup"><span data-stu-id="ed6b6-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="ed6b6-103">Fornisce una delle tre interfacce: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), o [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ed6b6-103">Provides one of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed6b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed6b6-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed6b6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed6b6-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="ed6b6-106">[in] Uno dei tre identificatori di classe: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy o CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="ed6b6-107">[in] Uno dei tre identificatori di interfaccia (IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy o IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="ed6b6-108">[out] Una delle tre interfacce: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), o [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ed6b6-108">[out] One of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed6b6-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ed6b6-109">Return Value</span></span>  
 <span data-ttu-id="ed6b6-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ed6b6-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed6b6-111">HRESULT</span></span>|<span data-ttu-id="ed6b6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed6b6-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed6b6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed6b6-113">S_OK</span></span>|<span data-ttu-id="ed6b6-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="ed6b6-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ed6b6-115">E_POINTER</span></span>|<span data-ttu-id="ed6b6-116">`ppInterface` è null.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed6b6-117">Note</span><span class="sxs-lookup"><span data-stu-id="ed6b6-117">Remarks</span></span>  
 <span data-ttu-id="ed6b6-118">La tabella seguente mostra le combinazioni supportate per `clsid` e `riid`.</span><span class="sxs-lookup"><span data-stu-id="ed6b6-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`clsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="ed6b6-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="ed6b6-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="ed6b6-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="ed6b6-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="ed6b6-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="ed6b6-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="ed6b6-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="ed6b6-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="ed6b6-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="ed6b6-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="ed6b6-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="ed6b6-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="ed6b6-125">Il codice seguente viene illustrato come utilizzare `CLRCreateInstance` per ottenere tutte le tre interfacce:</span><span class="sxs-lookup"><span data-stu-id="ed6b6-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
```cpp  
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
  
## <a name="requirements"></a><span data-ttu-id="ed6b6-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed6b6-126">Requirements</span></span>  
 <span data-ttu-id="ed6b6-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed6b6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed6b6-128">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ed6b6-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ed6b6-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ed6b6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed6b6-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed6b6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed6b6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed6b6-131">See also</span></span>

- [<span data-ttu-id="ed6b6-132">Hosting</span><span class="sxs-lookup"><span data-stu-id="ed6b6-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
